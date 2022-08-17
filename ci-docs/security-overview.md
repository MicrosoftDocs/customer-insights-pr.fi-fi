---
title: Määritä tietoturva-asetukset
description: Tietoja tietoturva-asetuksista Dynamics 365 Customer Insightsissa.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea21163d7dd05370de28ca8340ae9583846adb26
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246058"
---
# <a name="configure-security-settings"></a>Määritä tietoturva-asetukset

Hallitse ohjelmointirajapinnan avaimia, käytä asiakastietoja ja määritä Azuren yksityinen linkki.

## <a name="manage-api-keys"></a>Ohjelmointirajapinta-avainten hallinta

Tarkastele ja hallitse avaimia, joilla voit käyttää [Customer Insights -ohjelmointirajapintoja](apis.md) ympäristön tietojen kanssa.

1. Siirry kohtaan **Järjestelmä** > **Tietoturva** ja valitse **Ohjelmointirajapinnat**-välilehti.

1. Jos ympäristön ohjelmointirajapintaa ei ole määritetty, valitse **Ota käyttöön**. Tai, jos haluat estää ympäristön ohjelmointirajapinnan käytön, valitse **Poista käytöstä** ja vahvista.

1. Hallitse ensisijaisia ja toissijaisia ohjelmointirajapinta-avaimia:

   1. Jos haluat näyttää ensisijaisen tai toissijaisen ohjelmointirajapinta-avaimen, valitse **Näytä** symboli.

   1. Jos haluat kopioida ensisijaisen tai toissijaisen ohjelmointirajapinta-avaimen, valitse **Kopioi** symboli.

   1. Luodaksesi uusia perus- tai toissijaisia ohjelmointirajapinta-avaimia, valitse **Luo uudelleen ensisijainen** tai **Luo uudelleen toissijainen**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Asiakastietojen käyttäminen turvallisesti asiakkaan Lockboxin avulla (esiversio)

Customer Insights käyttää Power Platformin Asiakkaan Lockbox -ominaisuutta. Asiakkaan Lockbox on liittymä, jossa voi tarkastella ja hyväksyä (tai hylätä) tietojen käyttöoikeuspyyntöjä. Näitä pyyntöjä syntyy, kun tukipalvelupyynnön ratkaiseminen edellyttää asiakastietojen käyttöoikeutta. Tämän ominaisuuden käyttö edellyttää, että Customer Insightsiin on jo luotu vuokraajassa yhteys Microsoft Dataverse -ympäristöön.

Lisätietoja asiakkaan Lockboxista on Power Platformin asiakkaan Lockboxin [yhteenvedossa](/power-platform/admin/about-lockbox#summary). Artikkelissa käsitellään myös [työnkulkua](/power-platform/admin/about-lockbox#workflow) ja [määritystä](/power-platform/admin/about-lockbox#enable-the-lockbox-policy), joita asiakkaan Lockboxin käyttöönotto edellyttää.

> [!IMPORTANT]
> Power Platformin yleiset järjestelmänvalvojat tai Power Platform järjestelmänvalvojat voivat hyväksyä Customer Insightsin asiakkaan Lockbox-pyyntöjä.

## <a name="set-up-an-azure-private-link"></a>Azure-yksityislinkin määrittäminen

[Azuren yksityisen linkin](/azure/private-link/private-link-overview) ansiosta Customer Insights voi muodostaa näennäisversiossa yhteyden Azure Data Lake Storage -tiliin yksityisen päätepisteen kautta. Jos tallennustilatili ei ole julkisessa verkossa, tämän rajoitetun verkon tietoihin voi muodostaa yhteyden yksityisen linkin kautta.

> [!IMPORTANT]
> Yksityistä linkkiä käyttävän yhteyden määrittämisen tarvitaan vähimmäisroolivaatimus:
>
> - Customer Insights: järjestelmänvalvoja
> - Azuren sisäinen rooli: [tallennustilatilin osallistuja](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Mukautetun Azure-roolin oikeudet: [Microsoft.Storage/storageAccounts/read ja Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. Siirry Customer Insightsissa kohtaan **Järjestelmänvalvoja** > **Tietoturva** ja valitse **Yksityiset linkit** -välilehti.

1. Valitse **Yksityinen linkki**.

   **Lisää yksityinen linkki** -ruudussa on luettelo niistä vuokraajan tallennustilatileistä, joihin katseluoikeudet käyttäjällä on.

1. Valitse tilaus, resurssiryhmä ja tallennustili.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Valitse **Tallenna**.

1. Siirry Data Lake -tallennustilille ja avaa näytössä esitetty linkki.

1. Hyväksy yksityinen linkki.


[!INCLUDE [footer-include](includes/footer-banner.md)]
