---
title: Customer Insightsin suojausasetukset
description: Tietoja tietoturva-asetuksista Dynamics 365 Customer Insightsissa.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947411"
---
# <a name="security-settings-in-customer-insights"></a>Customer Insightsin suojausasetukset

**Tietoturva**-sivulla on vaihtoehtoja, joiden avulla voit määrittää käyttöoikeuksia ja ominaisuuksia, jotka auttavat tekemään Dynamics 365 Customer Insightsista entistä turvallisemman. Vain järjestelmänvalvojat voivat käyttää tätä sivua.

Määritä asetukset kohdassa **Järjestelmänvalvoja** > **Tietoturva**.

**Tietoturva**-sivu sisältää seuraavat välilehdet:

- [Käyttäjät](#users-tab)
- [Ohjelmointirajapinnat](#apis-tab)
- [Yksityisviestit](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Asiakastietojen käyttäminen turvallisesti asiakkaan Lockboxin avulla (esiversio)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Käyttäjät-välilehti

Customer Insights -tietojen käyttöoikeus rajoittuu organisaatiosi käyttäjiin, jotka järjestelmänvalvoja on lisännyt sovellukseen. **Käyttäjät**-välilehdessä voit hallita käyttäjien pääsy- ja käyttöoikeuksia. Lisätietoja on kohdassa [käyttäjän oikeudet](permissions.md).

## <a name="apis-tab"></a>Ohjelmointirajapinnat-välilehti

Tarkastele ja hallitse avaimia, joilla voit käyttää [Customer Insights -ohjelmointirajapintoja](apis.md) ympäristön tietojen kanssa.

Voit luoda uusia perus- ja toissijaisia avaimia valitsemalla **Luo uudelleen ensisijainen** tai **Luo uudelleen toissijainen**. 

Jos haluat estää ympäristön ohjelmointirajapinnan käytön, valitse **Poista käytöstä**. Jos ohjelmointirajapinnat on poistettu käytöstä, voit valita **Ota käyttöön**, jos haluat myöntää käyttöoikeudet uudelleen.

## <a name="private-links-tab"></a>Yksityiset linkit -välilehti

[Azuren yksityisen linkin](/azure/private-link/private-link-overview) ansiosta Customer Insights voi muodostaa näennäisversiossa yhteyden Azure Data Lake Storage -tiliin yksityisen päätepisteen kautta. Jos tallennustilatili ei ole julkisessa verkossa, tämän rajoitetun verkon tietoihin voi muodostaa yhteyden yksityisen linkin kautta.

> [!IMPORTANT]
> Yksityistä linkkiä käyttävän yhteyden määrittämisen tarvitaan vähimmäisroolivaatimus:
>
> - Customer Insights: järjestelmänvalvoja
> - Azuren sisäinen rooli: [tallennustilatilin osallistuja](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Mukautetun Azure-roolin oikeudet: [Microsoft.Storage/storageAccounts/read ja Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Yksityinen linkki määritetään Customer Insightsissa kahdessa vaiheessa. Ensin käynnistetään yksityisen linkin luonti valitsemalla Customer Insightsissa **Hallinta** > **Suojaus** > **Yksityiset linkit**. **Lisää yksityinen linkki** -ruudussa on luettelo niistä vuokraajan tallennustilatileistä, joihin katseluoikeudet käyttäjällä on. Valitse tallennustilatili ja hyväksy yksityisen linkin luonti.

Seuraavaksi yksityinen linkki on hyväksyttävä Data Lake Storage -tilillä. Hyväksy uusi yksityinen linkki avaamalla näytössä oleva linkki.

## <a name="key-vault-tab"></a>Key Vault -välilehti

**Key Vault** -välilehdessä voi linkittää oman [Azure Key Vaultin](/azure/key-vault/general/basic-concepts) ympäristöön ja hallita sitä.
Erillistä key vaultia voidaan käyttää salaisten koodien valmisteluun ja käyttämiseen organisaation vaatimustenmukaisuusrajalla. Customer Insights voi käyttää Azure Key Vaultin salaisia koodeja [yhteyksien määrittämiseen](connections.md) kolmannen osapuolen järjestelmiin.

Lisätietoja on kohdassa [Oman Azure Key Vaultin tuominen](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Asiakastietojen käyttäminen turvallisesti asiakkaan Lockboxin avulla (esiversio)

Customer Insights käyttää Power Platformin Asiakkaan Lockbox -ominaisuutta. Asiakkaan Lockbox on liittymä, jossa voi tarkastella ja hyväksyä (tai hylätä) tietojen käyttöoikeuspyyntöjä. Näitä pyyntöjä syntyy, kun tukipalvelupyynnön ratkaiseminen edellyttää asiakastietojen käyttöoikeutta. Tämän ominaisuuden käyttö edellyttää, että Customer Insightsiin on jo luotu vuokraajassa yhteys Microsoft Dataverse -ympäristöön.

Lisätietoja asiakkaan Lockboxista on Power Platformin asiakkaan Lockboxin [yhteenvedossa](/power-platform/admin/about-lockbox#summary). Artikkelissa käsitellään myös [työnkulkua](/power-platform/admin/about-lockbox#workflow) ja [määritystä](/power-platform/admin/about-lockbox#enable-the-lockbox-policy), joita asiakkaan Lockboxin käyttöönotto edellyttää.

> [!IMPORTANT]
> Power Platformin yleiset järjestelmänvalvojat tai Power Platform järjestelmänvalvojat voivat hyväksyä Customer Insightsin asiakkaan Lockbox-pyyntöjä.

[!INCLUDE [footer-include](includes/footer-banner.md)]
