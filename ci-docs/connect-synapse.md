---
title: Yhteyden muodostaminen Azure Synapse -tietolähteeseen (esiversio)
description: Käytä Azure Synapsen tietokantaa tietolähteenä Dynamics 365 Customer Insightsissa.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 675fd03c44a7a7a492b111895d79c2e77f93a5b5
ms.sourcegitcommit: 4ba74816ebfa46412c64c40a61e1f31c4ccc40f2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2022
ms.locfileid: "9738152"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Yhteyden muodostaminen Azure Synapse Analytics -tietolähteeseen (esiversio)

Azure Synapse Analytics on yritysanalyysipalvelu, joka nopeuttaa tietovarastojen ja suurien tietojärjestelmien tuottamia oivalluksia. Azure Synapse Analytics tuo yhteen parhaat SQL-tekniikat, joita käytetään yrityksen tietojen tallennustilassa, Spark-tekniikat Big Datalle, Data Explorer loki- ja aikasarjojen analysoinnissa, tietojen integrointiputkia ja ETL/ELT-teknologioita sekä syvällistä integrointia muiden Azure-palveluiden, kuten Power BI, Cosmos DB ja AzureML, kanssa.

Lisätietoja on kohdassa [Azure Synapsen yleiskatsaus](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>edellytykset

> [!NOTE]
> [Palomuurilla käyttöön otettuja](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) Synapse-työtiloja ei tällä hetkellä tueta.
> [!IMPORTANT]
> Varmista, että määrität kaikki **roolimääritykset** kuvatulla tavalla.  

**Customer Insightsissa**:

* Sinulla on **Järjestelmänvalvoja**-rooli Customer Insightsissa. Lisätietoja [käyttöoikeuksista ja Customer Insightsista](permissions.md#add-users).

**Azuressa**:

- Aktiivinen Azure-tilaus.

- Jos käytät uutta Azure Data Lake Storage Gen2 -tiliä, *Customer Insightsin palvelun päänimellä*, joka on Dynamics 365 AI for Customer Insights, on oltava **tallennustilan blob-tietojen käsittelijän** oikeudet. Lisätietoja [yhteyden muodostamisesta Azure Data Lake Storageen palvelun pääobjektin avulla Customer Insightsiin](connect-service-principal.md). Data Lake Storage Gen2:ssa **on oltava käytössä** [hierarkkinen](/azure/storage/blobs/data-lake-storage-namespace) nimiavaruus.

- Resurssiryhmässä, jossa Azure Synapse workspace sijaitsee, on määritettävä *palvelun päänimelle*, joka on Dynamics 365 AI for Customer Insights ja *Customer Insightsin käyttäjälle* on määritettävä vähintään **luku**-oikeudet. Lisätietoja on kohdassa [Azure-roolien määrittäminen Azure-portaalin avulla](/azure/role-based-access-control/role-assignments-portal).

- *Käyttäjä* tarvitsee **Storage Blob Data Contributor** -oikeudet Azure Data Lake Storage Gen2 -tilillä, jossa tiedot ovat ja josta ne on linkitetty Azure Synapse -työtilaan. Lisätietoja [Azure-portaalin käyttämisestä Azure-roolin määrittämiseen blob- ja jonotiedoille](/azure/storage/common/storage-auth-aad-rbac-portal) sekä [Storage Blob Data Contributor -oikeuksista](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse -työtilassa hallittu identiteetti](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* tarvitsee **Storage Blob Data Contributor** -oikeudet Azure Data Lake Storage Gen2 tilille, jossa tiedot ovat ja josta ne on linkitetty Azure Synapse -työtilaan. Lisätietoja [Azure-portaalin käyttämisestä Azure-roolin määrittämiseen blob- ja jonotiedoille](/azure/storage/common/storage-auth-aad-rbac-portal) sekä [Storage Blob Data Contributor -oikeuksista](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse workspacessa *Customer Insightsin palvelun päänimelle*, joka on Dynamics 365 AI for Customer Insights, on määritettävä **Synapse-järjestelmänvalvojan** rooli. **Käyttäjä** tarvitsee vähintään työtilalle määritetyn **Synapse-osallistuja** -roolin. Lisätietoja on kohdassa [Käytönvalvonnan määrittäminen Synapse-työtilaa varten](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Jos Customer Insights -ympäristö tallentaa tiedot [omaan Azure Data Lake Storageen](own-data-lake-storage.md), Azure Synapse Analytics -yhteyden muodostava käyttäjä tarvitsee vähintään Data Lake -tallennustilatilin sisäänrakennetun **Lukija**-roolin. Lisätietoja on kohdassa [Azure-roolien määrittäminen Azure-portaalin avulla](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Yhdistäminen Data Lake -tietokantaan Azure Synapse Analyticsissa

1. Valitse **Tiedot** > **Tietolähteet**.

1. Valitse **Lisää tietolähde**.

1. Valitse **Azure Synapse Analytics (esiversio)** -menetelmä.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Synapse Analytics -tietojen yhteydenmuodostusikkuna":::
  
1. Anna tietolähteelle **nimi** ja valinnainen **kuvaus**

1. Valitse [käytettävissä oleva yhteys](connections.md) Azure Synapse Analyticsiin tai [luo uusi yhteys](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. Valitse valittuun Azure Synapse Analytics -yhteyteen yhdistetystä työtilasta **Tietokanta** ja valitse sitten **Seuraava**. Tällä hetkellä ainoa tuettu tietokantatyyppi on *Data Lake -tietokanta*.

1. Valitse yhdistetystä tietokannasta käsiteltävät entiteetit ja valitse **Seuraava**.

1. Voit myös valita tietoentiteetit, joille tietojen profilointi sallitaan.

1. Valitse **Tallenna**, jos haluat ottaa valintasi käyttöön ja aloittaa tietojen käsittelyn juuri luomastasi tietolähteestä, joka on linkitetty Lake-tietokantatauluihin Azure Synapse Analyticsissa. Avautuvalla **Tietolähteet**-sivulla on näkyy uusi tietolähde, jonka tilana on **Päivitetään**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Tietojen lataaminen voi viedä aikaa. Kun päivitys on onnistunut, käsiteltyjä tietoja voi tarkastella [**Entiteetit**](entities.md)-sivulla.

[!INCLUDE [footer-include](includes/footer-banner.md)]
