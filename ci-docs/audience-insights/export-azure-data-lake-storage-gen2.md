---
title: Customer Insightsin tietojen vieminen Azure Data Lake Storage Gen2:een
description: Tietoja yhteyden määrittämisestä Azure Data Lake Storage Gen2:een.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477175"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Azure Data Lake Storage Gen2 -yhdistin (esiversio)

Tallenna Customer Insightsin tiedot Azure Data Lake Storage Gen2:een tai käytä sitä tietojesi siirtämiseen muihin sovelluksiin.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Azure Data Lake Storage Gen2 -yhdistimen määrittäminen

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.

1. Valitse **Azure Data Lake Storage Gen2** -kohdassa **Määritä**.

1. Anna kohteelle tunnistettava nimi **Näyttönimi**-kentässä.

1. Anna Azure Data Lake Storage Gen2:lle **tilin nimi**, **tilin avain** ja **säilö**.
    - Lisätietoja tallennustilin luomisesta Azure Data Lake Storage Gen2:ssa on kohdassa [Tallennustilin luominen](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Lisätietoja Azure Data Lake Gen2:n tallennustilin nimestä ja tilin avaimesta on kohdassa [Azure-portaalin tallennustilin asetusten hallinta](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Valitse **Seuraava**.

1. Valitse tähän kohteeseen vietävien entiteettien vieressä oleva valintaruutu.

1. Valitse **Tallenna**.

## <a name="export-the-data"></a>Tietojen vieminen

Voit [viedä tietoja tarvittaessa](export-destinations.md#export-data-on-demand). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.
