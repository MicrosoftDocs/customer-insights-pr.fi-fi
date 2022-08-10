---
title: Customer Insights -tietojen vieminen InMobiin
description: Tietoja InMobi-yhteyden määrittämisestä ja viennistä siihen.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195884"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Customer Insights -tietojen vieminen InMobiin (esiversio)

Customer Insights -esiintymän segmenttiluetteloiden tai muiden tietojen vieminen [InMobiin](https://www.inmobi.com/).

## <a name="prerequisites"></a>edellytykset

- [InMobi-tili](https://www.inmobi.com/) ja järjestelmänvalvojan tunnistetiedot.
- [Azure Blob -tallennustilatilin](/azure/storage/blobs/create-data-lake-storage-account) nimi ja tiliavain. Lisätietoja nimen ja tiliavaimen löytämisestä on ohjeaiheessa [Azure-portaalin tallennustilatilin asetusten hallinta](/azure/storage/common/storage-account-manage).
- [Azure Blob Tallennus -säilö](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) InMobi-tietojen vientiä varten. 
- InMobi luo suoran yhteyden Blob-tallennustilaan ja määrittää tietojen automaattisen tuonnin InMobiin. Prosessi käynnistetään ottamalla yhteys InMobi-edustajaan.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Azure Blob -tallennustilavaihtoehtoja ovat [Standard-suorituskyky ja Premium-suorituskykytaso](/azure/storage/blobs/storage-blob-performance-tiers). Jos valitset Premium-suorituskykytason, valitse [tilityypiksi premium block blobs](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Määritä yhteys Azure Blob Tallennus -säilöön

[Määritä yhteys Azure Blob Tallennus -säilöösi](export-azure-blob-storage.md)

## <a name="configure-an-export"></a>Viennin määrittäminen

[Viennin määrittäminen](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
