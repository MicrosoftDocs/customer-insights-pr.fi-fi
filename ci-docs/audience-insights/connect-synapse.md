---
title: Tietojen käsittely Azure Synapse Analyticsista
description: Käytä Azure Synapsen tietokantaa tietolähteenä Dynamics 365 Customer Insightsissa.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356019"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Yhteyden muodostaminen Azure Synapse -tietolähteeseen (esiversio)

Azure Synapse Analytics on yritysanalyysipalvelu, joka nopeuttaa tietovarastojen ja suurien tietojärjestelmien tuottamia oivalluksia. Azure Synapse Analytics tuo yhteen parhaat SQL-tekniikat, joita käytetään yrityksen tietojen tallennustilassa, Spark-tekniikat Big Datalle, Data Explorer loki- ja aikasarjojen analysoinnissa, tietojen integrointiputkia ja ETL/ELT-teknologioita sekä syvällistä integrointia muiden Azure-palveluiden, kuten Power BI, Cosmos DB ja AzureML, kanssa.

Lisätietoja on kohdassa [Azure Synapsen yleiskatsaus](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>edellytykset

Seuraavien edellytysten on täytyttävä, jotta yhteys Customer Insightsista Azure Synapseen voidaan määrittää.

> [!IMPORTANT]
> Varmista, että määrität kaikki **roolimääritykset** kuvatulla tavalla.  

## <a name="prerequisites-in-customer-insights"></a>Edellytykset Customer Insightsissa

* Sinulla on **Järjestelmänvalvoja**-rooli Customer Insightsissa. Lisätietoja [käyttöoikeuksista ja käyttäjäryhmän merkityksellisistä tiedoista](permissions.md#assign-roles-and-permissions).

Azuressa: 

- Aktiivinen Azure-tilaus.

- Käytettäessä uutta Azure Data Lake Storage Gen2 tiliä, *käyttäjäryhmän merkityksellisten tietojen palvelun pää* tarvitsee **Storage Blob Data Contributor** -oikeudet. Lisätietoja [yhteyden muodostamisesta Azure Data Lake Storageen palvelun pääobjektin avulla kohdeyleisön tietojen saamiseksi](connect-service-principal.md). Data Lake Storage Gen2:ssa **on oltava käytössä** [hierarkkinen](/azure/storage/blobs/data-lake-storage-namespace) nimiavaruus.

- Resurssiryhmässä, jossa Azure Synapse -työtila sijaitsee, *palvelun pää* ja *käyttäjäryhmän merkitykselliset tiedot* tarvitsevat vähintään **Lukija**-oikeudet. Lisätietoja on kohdassa [Azure-roolien määrittäminen Azure-portaalin avulla](/azure/role-based-access-control/role-assignments-portal).

- *Käyttäjä* tarvitsee **Storage Blob Data Contributor** -oikeudet Azure Data Lake Storage Gen2 -tilillä, jossa tiedot ovat ja josta ne on linkitetty Azure Synapse -työtilaan. Lisätietoja [Azure-portaalin käyttämisestä Azure-roolin määrittämiseen blob- ja jonotiedoille](/azure/storage/common/storage-auth-aad-rbac-portal) sekä [Storage Blob Data Contributor -oikeuksista](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse -työtilassa hallittu identiteetti](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* tarvitsee **Storage Blob Data Contributor** -oikeudet Azure Data Lake Storage Gen2 tilille, jossa tiedot ovat ja josta ne on linkitetty Azure Synapse -työtilaan. Lisätietoja [Azure-portaalin käyttämisestä Azure-roolin määrittämiseen blob- ja jonotiedoille](/azure/storage/common/storage-auth-aad-rbac-portal) sekä [Storage Blob Data Contributor -oikeuksista](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse-työtilassa *käyttäjäryhmän merkityksellisten tietojen pää* tarvitsee **Synapsen järjestelmänvalvoja** -roolin. Lisätietoja on kohdassa [Käytönvalvonnan määrittäminen Synapse-työtilaa varten](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Yhdistäminen Data Lake -tietokantoihin Azure Synapse Analyticsissa

1. Valitse **Tiedot** > **Tietolähteet**.

1. Valitse **Lisää tietolähde**.

1. Valitse **Azure Synapse Analytics (esiversio)** -menetelmä.

1. Anna tietolähteelle **nimi** ja luo tietolähde valitsemalla **Seuraava**. 

1. Valitse [käytettävissä oleva yhteys](connections.md) Azure Synapse Analyticsiin tai luo uusi yhteys.

1. Valitse valittuun Azure Synapse Analytics -yhteyteen yhdistetystä työtilasta **Lake-tietokanta** ja valitse sitten **Seuraava**.

1. Valitse yhdistetystä tietokannasta entiteetit, jotka käsitellään. 

1. Voit myös valita tietoentiteetit, joille tietojen profilointi sallitaan. 

1. Valitse **Tallenna**, jos haluat ottaa valintasi käyttöön ja aloittaa tietojen käsittelyn juuri luomastasi tietolähteestä, joka on linkitetty Lake-tietokantatauluihin Azure Synapse Analyticsissa.
