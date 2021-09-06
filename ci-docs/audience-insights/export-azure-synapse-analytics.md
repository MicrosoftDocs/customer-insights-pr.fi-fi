---
title: Customer Insights -tietojen vieminen Azure Synapse -analytiikkaan
description: Tietoja yhteyden määrittämisestä ja viennistä Azure Synapse -analytiikkaan.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f206043298bdbf8a84b0ef37b47a43290653beba7d3d0e8b807ec74513614aa8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031929"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Vie tietoja Azure Synapse -analytiikkaan (esiversio)

Azure Synapse on analytiikkapalvelu, joka nopeuttaa merkityksellisten tietojen saamista tietovarastoista ja massadatajärjestelmistä. Voit käsitellä ja käyttää Customer Insights -tietojasi -sivustolla [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Edellytykset

Seuraavien edellytysten on täytyttävä, jotta yhteys Customer Insightsista Azure Synapseen voidaan määrittää.

> [!NOTE]
> Varmista, että määrität kaikki **roolimääritykset** kuvatulla tavalla.  

## <a name="prerequisites-in-customer-insights"></a>Edellytykset Customer Insightsissa

* Sinulla on  **Järjestelmänvalvoja**-rooli käyttäjäryhmän merkityksellisissä tiedoissa. Lisätietoja [käyttöoikeuksien määrittämisestä käyttäjäryhmän merkityksellisissä tiedoissa](permissions.md#assign-roles-and-permissions)

Azuressa: 

- Aktiivinen Azure-tilaus.

- Käytettäessä uutta Azure Data Lake Storage Gen2 tiliä, *käyttäjäryhmän merkityksellisten tietojen palvelun pää* tarvitsee **Storage Blob Data Contributor** -oikeudet. Lue lisää [yhteyden muodostamisesta Azure Data Lake Storage Gen2- tiliin Azuren palvelun pään avulla käyttäjäryhmän merkityksellisillä tiedoilla](connect-service-principal.md). Data Lake Storage Gen2:ssa **on oltava käytössä** [hierarkkinen](/azure/storage/blobs/data-lake-storage-namespace) nimiavaruus.

- Resurssiryhmässä, jossa Azure Synapse -työtila sijaitsee, *palvelun pää* ja *käyttäjäryhmän merkitykselliset tiedot* tarvitsevat vähintään **Lukija**-oikeudet. Lisätietoja on kohdassa [Azure-roolien määrittäminen Azure-portaalin avulla](/azure/role-based-access-control/role-assignments-portal).

- *Käyttäjä* tarvitsee **Storage Blob Data Contributor** -oikeudet Azure Data Lake Storage Gen2 -tilillä, jossa tiedot ovat ja josta ne on linkitetty Azure Synapse -työtilaan. Lisätietoja [Azure-portaalin käyttämisestä Azure-roolin määrittämiseen blob- ja jonotiedoille](/azure/storage/common/storage-auth-aad-rbac-portal) sekä [Storage Blob Data Contributor -oikeuksista](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse -työtilassa hallittu identiteetti](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* tarvitsee **Storage Blob Data Contributor** -oikeudet Azure Data Lake Storage Gen2 tilille, jossa tiedot ovat ja josta ne on linkitetty Azure Synapse -työtilaan. Lisätietoja [Azure-portaalin käyttämisestä Azure-roolin määrittämiseen blob- ja jonotiedoille](/azure/storage/common/storage-auth-aad-rbac-portal) sekä [Storage Blob Data Contributor -oikeuksista](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse-työtilassa *käyttäjäryhmän merkityksellisten tietojen pää* tarvitsee **Synapsen järjestelmänvalvoja** -roolin. Lisätietoja on kohdassa [Käytönvalvonnan määrittäminen Synapse-työtilaa varten](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Määritä yhteys ja vie Azure Synapseen

### <a name="configure-a-connection"></a>Yhteyden määrittäminen

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse **Azure Synapse -analytiikka** tai valitse **Määritä** **Azure Synapse -analytiikka** -ruudussa yhteyden määrittämistä varten.

1. Anna yhteydelle tunnistettava nimi Näyttönimi-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valitse tai etsi tilaus, jossa haluat käyttää Customer Insights -tietoja. Kun tilaus on valittuna, voit myös valita **työtilan**, **tallennustilan tilin** ja **säilön**.

1. Tallenna yhteys valisemalla **Tallenna**.

### <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on aiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys **Azure Synapse -analytiikka** -osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä [yhteyksiä](connections.md) ei ole käytettävissäsi.

1. Anna viennille tunnistettava **Näyttönimi** ja **Tietokannan nimi**.

1. Valitse Azure Synapse -analytiikkaan vietävät entiteetit.
   > [!NOTE]
   > [Common Data Model -kansioon](connect-common-data-model.md) perustuvia tietolähteitä ei tueta.

2. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).

### <a name="update-an-export"></a>Viennin päivittäminen

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Muokkaa** viennille, jota haluat päivittää.

   - **Lisää** tai **Poista** entiteettejä valinnasta. Jos entiteetit poistetaan valinnasta, niitä ei poisteta Synapse Analytics -tietokannasta. Tulevat tietojen päivitykset eivät kuitenkaan päivitä tietokannan poistettuja entiteettejä.

   - **Tietokannan nimen muuttaminen** luo uuden Synapse Analytics -tietokannan. Tietokanta, jonka nimi on määritetty aiemmin, ei saa päivityksiä tulevissa päivityksissä.
