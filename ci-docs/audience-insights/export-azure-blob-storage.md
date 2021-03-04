---
title: Customer Insights -tietojen vieminen Azure Blob -säilöön
description: Tutustu Azure Blob -säilöyhteyden määritykseen.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ecacf20365e78ced8859dfa54b1b16cb923c00eb
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269188"
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

Voit [viedä tietoja tarvittaessa](export-destinations.md#export-data-on-demand). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.


[!INCLUDE[footer-include](../includes/footer-banner.md)]