---
title: Customer Insightsin tietojen vieminen Azure Data Lake Storage Gen2:een
description: Tietoja yhteyden määrittämisestä Azure Data Lake Storage Gen2:een.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 8b14992f8312d333d8a12501e8a28496c8434779
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646123"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Segmenttiluettelon ja muiden tietojen vieminen Azure Data Lake Storage Gen2:een (esiversio)

Tallenna Customer Insights -tietosi Data Lake Storage Gen2 -tilille tai käytä sitä tietojesi siirtämiseen muihin sovelluksiin.

## <a name="known-limitations"></a>Tunnetut rajoitukset

1. Azure Data Lake Storage Gen2:ta varten voit valita joko [Standard-suorituskyvyn tai Premium-suorituskykytason](/azure/storage/blobs/create-data-lake-storage-account), kun luot tallennustiliä data lake -tallennustilaan. Jos valitset Premium-suorituskykytason, valitse tilityypiksi premium block blobs. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Määritä yhteys Azure Data Lake Storage Gen2:een 


1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Azure Data Lake Gen 2**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna Azure Data Lake Storage Gen2:lle **tilin nimi**, **tilin avain** ja **säilö**.
    - Lisätietoja tallennustilin luomisesta Azure Data Lake Storage Gen2:ssa on kohdassa [Tallennustilin luominen](/azure/storage/blobs/create-data-lake-storage-account). 
    - Lisätietoja Azure Data Lake Gen 2 -tallennustilatilin nimestä ja tiliavaimesta on ohjeaiheessa [Azure-portaalin tallennustilatilin asetusten hallinta](/azure/storage/common/storage-account-manage).

1. Viimeistele yhteys valitsemalla **Tallenna**. 

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys **Azure Data Lake** -osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Valitse tähän kohteeseen vietävien entiteettien vieressä oleva valintaruutu.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 

Viedyt tiedot tallennetaan määritettyyn Azure Data Lake Gen 2 -tallennussäilöön. 

[!INCLUDE [footer-include](includes/footer-banner.md)]