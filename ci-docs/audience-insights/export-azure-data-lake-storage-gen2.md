---
title: Customer Insightsin tietojen vieminen Azure Data Lake Storage Gen2:een
description: Tietoja yhteyden määrittämisestä Azure Data Lake Storage Gen2:een.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596633"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Azure Data Lake Storage Gen2 -yhdistin (esiversio)

Tallenna Customer Insightsin tiedot Azure Data Lake Storage Gen2:een tai käytä sitä tietojesi siirtämiseen muihin sovelluksiin.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Azure Data Lake Storage Gen2 -yhdistimen määrittäminen

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.

1. Valitse **Azure Data Lake Storage Gen2** -kohdassa **Määritä**.

1. Anna kohteelle tunnistettava nimi **Näyttönimi**-kentässä.

1. Anna Azure Data Lake Storage Gen2:lle **tilin nimi**, **tilin avain** ja **säilö**.
    - Lisätietoja tallennustilin luomisesta Azure Data Lake Storage Gen2:ssa on kohdassa [Tallennustilin luominen](/azure/storage/blobs/create-data-lake-storage-account). 
    - Lisätietoja Azure Data Lake Gen2:n tallennustilin nimestä ja tilin avaimesta on kohdassa [Azure-portaalin tallennustilin asetusten hallinta](/azure/storage/common/storage-account-manage).

1. Valitse **Seuraava**.

1. Valitse tähän kohteeseen vietävien entiteettien vieressä oleva valintaruutu.

1. Valitse **Tallenna**.

## <a name="export-the-data"></a>Tietojen vieminen

Voit [viedä tietoja tarvittaessa](export-destinations.md#export-data-on-demand). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.