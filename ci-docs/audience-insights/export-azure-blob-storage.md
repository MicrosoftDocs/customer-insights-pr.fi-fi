---
title: Customer Insights -tietojen vieminen Azure Blob -säilöön
description: Tutustu Azure Blob -säilöyhteyden määritykseen.
ms.date: 09/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0986ee5caf5fa079994ca584fb2c4d9294ddb80b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596173"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Azure Blob -säilön yhdistin (esikatselu)

Tallenna Customer Insights -tietosi Azure Blob -säilöön tai käytä sitä tietojesi siirtämiseen muihin sovelluksiin.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Azure Blob -säilön yhdistimen määritys

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.

1. Valitse kohdassa **Azure Blob -säilö** **Määritä**.

1. Anna Azure Blob -säilön **Tilin nimi**, **Tilin avain** ja **Säilö**.
    - Lisätietoja Azure Blob -säilön tilinimen ja käyttöoikeusavaimen etsimisestä on kohdassa [Tallennustilatilin asetusten hallinta Azure-portaalissa](/azure/storage/common/storage-account-manage).
    - Lisätietoja säilön luomisesta on kohdassa [Säilön luominen](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Anna kohteelle tunnistettava nimi **Näyttönimi**-kentässä.

1. Valitse **Seuraava**.

1. Valitse tähän kohteeseen vietävien entiteettien vieressä oleva valintaruutu.

1. Valitse **Tallenna**.

Viedyt tiedot tallennetaan määritettyyn Azure Blob -säilöön. Säilöön luodaan automaattisesti seuraavat kansiopolut:

- Lähde-entiteetit ja järjestelmän luomat entiteetit: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Esimerkki: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Vietyjen entiteettien model.json-arvo pysyy tasolla %ExportDestinationName%
  - Esimerkki: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Tietojen vieminen

Voit [viedä tietoja tarvittaessa](export-destinations.md#export-data-on-demand). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.


[!INCLUDE[footer-include](../includes/footer-banner.md)]