---
title: Customer Insights -tietojen vieminen InMobiin
description: Tietoja InMobi-yhteyden määrittämisestä ja viennistä siihen.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056539"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Segmenttiluettelon ja muiden tietojen vieminen InMobiin (esiversio)

Customer Insights -esiintymän segmenttiluetteloiden tai muiden tietojen vieminen [InMobiin](https://www.inmobi.com/).

## <a name="prerequisites"></a>edellytykset

1. Käytössä on [InMobi-tili](https://www.inmobi.com/) ja järjestelmänvalvojan tunnistetiedot.
1. Käytössä on Azure Blob -säilötilin nimi ja kyseisen tilin avain. Lisätietoja on kohdassa [Tallennustilin asetusten hallinta Azure-portaalissa](/azure/storage/common/storage-account-manage). Tallennustilillä on säilö, johon InMobi-tiedot voidaan viedä. Lisätietoja on kohdassa [Säilön luonti](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi luo suoran yhteyden Blob-tallennustilaan ja määrittää tietojen automaattisen tuonnin InMobiin. Prosessi käynnistetään ottamalla yhteys InMobi-edustajaan.

## <a name="known-limitations"></a>Tunnetut rajoitukset

1. Azure Blob -tallennustilavaihtoehtoja ovat [Standard-suorituskyky ja Premium-suorituskykytaso](/azure/storage/blobs/storage-blob-performance-tiers). Jos valitset Premium-suorituskykytason, valitse [tilityypiksi premium block blobs](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Azure Blob -tallennustilayhteyden määrittäminen ja viennin määrittäminen

1. [Määritä yhteys Azure Blob -tallennustilaan](export-azure-blob-storage.md) ohjeiden mukaan.
2. [Määritä vienti](export-azure-blob-storage.md#configure-an-export) ohjeiden mukaan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
