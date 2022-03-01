---
title: Customer Insights -tietojen vieminen Azure Blob -säilöön
description: Tutustu Azure Blob -säilöyhteyden määritykseen.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667135"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Azure Blob -säilön yhdistin (esikatselu)

Tallenna Customer Insights -tietosi Azure Blob -säilöön tai käytä sitä tietojesi siirtämiseen muihin sovelluksiin.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Azure Blob -säilön yhdistimen määritys

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.

1. Valitse kohdassa **Azure Blob -säilö** **Määritä**.

1. Anna Azure Blob -säilön **Tilin nimi**, **Tilin avain** ja **Säilö**.
    - Lisätietoja Azure Blob -säilön tilinimen ja käyttöoikeusavaimen etsimisestä on kohdassa [Tallennustilatilin asetusten hallinta Azure-portaalissa](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Lisätietoja säilön luomisesta on kohdassa [Säilön luominen](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Anna kohteelle tunnistettava nimi **Näyttönimi**-kentässä.

1. Valitse **Seuraava**.

1. Valitse tähän kohteeseen vietävien entiteettien vieressä oleva valintaruutu.

1. Valitse **Tallenna**.

Viedyt tiedot tallennetaan määritettyyn Azure Blob -säilöön. Säilöön luodaan automaattisesti seuraavat kansiopolut:

- Lähde-entiteetit ja järjestelmän luomat entiteetit: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Esimerkki: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Tuotujen entiteettien model.json sijaitsee tasolla %ExportDestinationName%
  - Esimerkki: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Tietojen vieminen

Voit [viedä tietoja tarvittaessa](/export-destinations.md#export-data-on-demand). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.
