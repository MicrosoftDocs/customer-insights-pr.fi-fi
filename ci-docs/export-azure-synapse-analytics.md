---
title: Tietojen vienti Azure Synapse Analyticsiin (esiversio)
description: Tietoja Azure Synapse Analytics -yhteyden määrittämisestä.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 60bacb313e0426564310f3c1339bf3b732e17489
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081145"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Tietojen vienti Azure Synapse Analyticsiin (esiversio)

Azure Synapse on analytiikkapalvelu, joka nopeuttaa merkityksellisten tietojen saamista tietovarastoista ja massadatajärjestelmistä. Voit käsitellä ja käyttää Customer Insights -tietojasi -sivustolla [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Edellytykset

Seuraavien edellytysten on täytyttävä, jotta yhteys Customer Insightsista Azure Synapseen voidaan määrittää.

> [!NOTE]
> Varmista, että määrität kaikki **roolimääritykset** kuvatulla tavalla.  

## <a name="prerequisites-in-customer-insights"></a>Edellytykset Customer Insightsissa

* Azure Active Directory (AD) -käyttäjätilillä on **järjestelmänvalvojan** rooli Customer Insightsissa. Lue lisää [käyttäjäoikeuksien määrittämisestä](permissions.md#assign-roles-and-permissions).

Azuressa: 

- Aktiivinen Azure-tilaus.

- Jos käytät uutta Azure Data Lake Storage Gen2 -tiliä, *Customer Insightsin palvelun päänimellä* on oltava **tallennustilan blob-tietojen käsittelijän** oikeudet. Lisätietoja [yhteyden muodostamisesta Azure Data Lake Storage Gen2 -tiliin Azure-palvelun pääobjektin avulla Customer Insightsille](connect-service-principal.md). Data Lake Storage Gen2:ssa **on oltava käytössä** [hierarkkinen](/azure/storage/blobs/data-lake-storage-namespace) nimiavaruus.

- Resurssiryhmässä, jossa Azure Synapse workspace sijaitsee, on määritettävä *palvelun päänimelle* ja *järjestelmänvalvojan käyttöoikeudet Customer Insightsissa omaavalle Azure AD -käyttäjälle* vähintään **lukuoikeudet**. Lisätietoja on kohdassa [Azure-roolien määrittäminen Azure-portaalin avulla](/azure/role-based-access-control/role-assignments-portal).

- *Järjestelmänvalvojan käyttöoikeudet Customer Insightsissa omaava Azure AD -käyttäjä* tarvitsee **tallennustilan blob-tietojen käsittelijän** oikeudet Azure Data Lake Storage Gen2 -tilillä, kun tiedot sijaitsevat Azure Synapse workspacessa ja kun ne linkitetään sinne. Lisätietoja [Azure-portaalin käyttämisestä Azure-roolin määrittämiseen blob- ja jonotiedoille](/azure/storage/common/storage-auth-aad-rbac-portal) sekä [Storage Blob Data Contributor -oikeuksista](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse -työtilassa hallittu identiteetti](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* tarvitsee **Storage Blob Data Contributor** -oikeudet Azure Data Lake Storage Gen2 tilille, jossa tiedot ovat ja josta ne on linkitetty Azure Synapse -työtilaan. Lisätietoja [Azure-portaalin käyttämisestä Azure-roolin määrittämiseen blob- ja jonotiedoille](/azure/storage/common/storage-auth-aad-rbac-portal) sekä [Storage Blob Data Contributor -oikeuksista](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse workspacessa *Customer Insightsin palvelun päänimelle* on määritettävä **Synapse-järjestelmänvalvojan** rooli. Lisätietoja on kohdassa [Käytönvalvonnan määrittäminen Synapse-työtilaa varten](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Määritä yhteys ja vie Azure Synapseen

### <a name="configure-a-connection"></a>Yhteyden määrittäminen

Yhteyden luonti edellyttää, että Customer Insightsin palvelun päänimi ja käyttäjätili tarvitsevat sen *resurssiryhmän* **Lukija**-oikeuden, jossa Synapse Analytics -työtila sijaitsee. Lisäksi palvelun päänimi ja käyttäjä tarvitsevat Synapse Analytics -työtilassa **Synapse-järjestelmänvalvojan** oikeudet. 

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse **Azure Synapse Analytics** tai valitse **Azure Synapse Analytics** -ruudussa **Määritä** määrittääksesi yhteyden.

1. Anna yhteydelle tunnistettava nimi Näyttönimi-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valitse tai etsi tilaus, jossa haluat käyttää Customer Insights -tietoja. Kun tilaus on valittuna, voit myös valita **työtilan**, **tallennustilan tilin** ja **säilön**.

1. Tallenna yhteys valisemalla **Tallenna**.

### <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Jaetun yhteyden viennin määrittämiseen tarvitaan vähintään **osallistujan** oikeudet Customer Insightsissa. Lisätietoja on aiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys **Azure Synapse Analytics**-osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä [yhteyksiä](connections.md) ei ole käytettävissäsi.

1. Anna viennille tunnistettava **Näyttönimi** ja **Tietokannan nimi**. Vienti luo uuden [Azure Synapsen Data Lake -tietokannan](/azure/synapse-analytics/database-designer/concepts-lake-database) yhteydessä määritettyyn työtilaan.

1. Valitse entiteetit, jotka haluat viedä Azure Synapse Analyticsiin.
   > [!NOTE]
   > [Common Data Model -kansioon](connect-common-data-model.md) perustuvia tietolähteitä ei tueta.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).

Synapse Analyticsiin vietyjen tietojen kyselyyn tarvitaan **tallennustilan Blob-tietojen lukijan** käyttöoikeus vientien työtilan kohdetallennustilassa. 

### <a name="update-an-export"></a>Viennin päivittäminen

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Muokkaa** viennille, jota haluat päivittää.

   - **Lisää** tai **Poista** entiteettejä valinnasta. Jos entiteetit poistetaan valinnasta, niitä ei poisteta Synapse Analytics -tietokannasta. Tulevat tietojen päivitykset eivät kuitenkaan päivitä tietokannan poistettuja entiteettejä.

   - **Tietokannan nimen muuttaminen** luo uuden Synapse Analytics -tietokannan. Tietokanta, jonka nimi on määritetty aiemmin, ei saa päivityksiä tulevissa päivityksissä.
