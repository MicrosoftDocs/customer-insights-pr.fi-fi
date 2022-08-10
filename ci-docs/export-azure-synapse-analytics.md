---
title: Tietojen vienti Azure Synapse Analyticsiin (esiversio)
description: Tietoja Azure Synapse Analytics -yhteyden määrittämisestä.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196390"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Tietojen vienti Azure Synapse Analyticsiin (esiversio)

Azure Synapse on analytiikkapalvelu, joka nopeuttaa merkityksellisten tietojen saamista tietovarastoista ja massadatajärjestelmistä. Voit käsitellä ja käyttää Customer Insights -tietojasi -sivustolla [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>edellytykset

> [!NOTE]
> Varmista, että määrität kaikki **roolimääritykset** kuvatulla tavalla.

- Azure Active Directory (AD) -käyttäjätililläsi on oltava [järjestelmänvalvojan](permissions.md#assign-roles-and-permissions) rooli Customer Insightsissa.

Azuressa:

- Aktiivinen Azure-tilaus.

- Jos käytät uutta Azure Data Lake Storage Gen2 -tiliä, [Customer Insightsin palvelun päänimellä](connect-service-principal.md) on **tallennustilan blob-tietojen käsittelijän** oikeudet. Data Lake Storage Gen2:ssa **on oltava käytössä** [hierarkkinen](/azure/storage/blobs/data-lake-storage-namespace) nimiavaruus.

- Resurssiryhmässä, jossa Azure Synapse workspace sijaitsee, on määritettävä *palvelun päänimelle* ja järjestelmänvalvojan käyttöoikeudet Customer Insightsissa omaavalle *Azure AD -käyttäjälle* vähintään **luku**[oikeudet](/azure/role-based-access-control/role-assignments-portal).

- *Järjestelmänvalvojan käyttöoikeudet Customer Insightsissa omaavalla Azure AD -käyttäjällä* on **tallennustilan blob-tietojen käsittelijän** oikeudet Azure Data Lake Storage Gen2 -tilillä, kun tiedot sijaitsevat Azure Synapse workspacessa ja kun ne linkitetään sinne. Lisätietoja [Azure-portaalin käyttämisestä Azure-roolin määrittämiseen blob- ja jonotiedoille](/azure/storage/common/storage-auth-aad-rbac-portal) sekä [Storage Blob Data Contributor -oikeuksista](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse workspacessa hallitulla identiteetillä](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* on **Storage Blob Data Contributor** -oikeudet Azure Data Lake Storage Gen2 tilille, jossa tiedot ovat ja josta ne on linkitetty Azure Synapse workspaceen. Lisätietoja [Azure-portaalin käyttämisestä Azure-roolin määrittämiseen blob- ja jonotiedoille](/azure/storage/common/storage-auth-aad-rbac-portal) sekä [Storage Blob Data Contributor -oikeuksista](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse workspacessa *Customer Insightsin palvelun päänimellä* on **Synapse-järjestelmänvalvojan** [rooli](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-connection-to-azure-synapse"></a>Määritä Azure Synapse -yhteydet

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **Azure Synapse Analytics**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valitse tai etsi tilaus, jossa haluat käyttää Customer Insights -tietoja. Kun tilaus on valittuna, voit myös valita **työtilan**, **tallennustilan tilin** ja **säilön**.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)] Jaetun yhteyden viennin määrittämiseen tarvitaan vähintään **osallistujan** oikeudet Customer Insightsissa.

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Azure Synapse Analytics -osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennille tunnistettava **Näyttönimi** ja **Tietokannan nimi**. Vienti luo uuden [Azure Synapsen Data Lake -tietokannan](/azure/synapse-analytics/database-designer/concepts-lake-database) yhteydessä määritettyyn työtilaan.

1. Valitse entiteetit, jotka haluat viedä Azure Synapse Analyticsiin.
   > [!NOTE]
   > [Common Data Model -kansioon](connect-common-data-model.md) perustuvia tietolähteitä ei tueta.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Synapse Analyticsiin vietyjen tietojen kyselyyn tarvitaan **tallennustilan Blob-tietojen lukijan** käyttöoikeus vientien työtilan kohdetallennustilassa.

## <a name="update-an-export"></a>Viennin päivittäminen

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Muokkaa** viennille, jota haluat päivittää.

   - **Lisää** tai **Poista** entiteettejä valinnasta. Jos entiteetit poistetaan valinnasta, niitä ei poisteta Synapse Analytics -tietokannasta. Tulevat tietojen päivitykset eivät kuitenkaan päivitä tietokannan poistettuja entiteettejä.

   - **Tietokannan nimen muuttaminen** luo uuden Synapse Analytics -tietokannan. Tietokanta, jonka nimi on määritetty aiemmin, ei saa päivityksiä tulevissa päivityksissä.

[!INCLUDE [footer-include](includes/footer-banner.md)]
