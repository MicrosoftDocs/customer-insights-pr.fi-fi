---
title: Customer Insights -tietojen vieminen Azure Blob Storage -säilöön
description: Tietoja yhteyden määrittämisestä ja viennistä Blob-säilöön.
ms.date: 06/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b159f87276581f68e07bb73ffd257080eb3cb56422997b09a613bd7afa4e3980
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034724"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Segmenttiluettelon ja muiden tietojen vieminen Azure Blob Storage -säilöön (esiversio)

Tallenna Customer Insights -tietosi Blob-säilöön, tai käytä sitä tietojesi siirtämiseen muihin sovelluksiin.

## <a name="set-up-the-connection-to-blob-storage"></a>Määritä yhteys Blob-säilöön

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Azure Blob Storage**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna **Tilin nimi**, **Tilin avain** ja **Säilö** Blob-tallennustilille.
    - Lisätietoja Blob Storage -tilin nimen ja tiliavaimen löytämisestä on ohjeaiheessa [Azure-portaalin tallennustilatilin asetusten hallinta](/azure/storage/common/storage-account-manage).
    - Lisätietoja säilön luomisesta on kohdassa [Säilön luominen](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Viimeistele yhteys valitsemalla **Tallenna**. 

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Jos olet ottanut Azure Blob Storage -tilin pehmeän poistoasetuksen käyttöön, vienti epäonnistuu. Poista pehmeä poisto käytöstä, jos haluat viedä tietoja blob-tiedostoihin. Lisätietoja on kohdassa [Blob-objektin pehmeän poiston ottaminen käyttöön](/azure/storage/blobs/soft-delete-blob-enable.md)

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Azure Blob Storage -osasta. Jos et näe tämän osan nimeä, nämä yhteystyypit eivät ole käytettävissä.

1. Valitse tähän kohteeseen vietävien entiteettien vieressä oleva valintaruutu.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.     

Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 

Viedyt tiedot tallennetaan määritettyyn Blob-tallennussäilöön. Säilöön luodaan automaattisesti seuraavat kansiopolut:

- Lähde-entiteetit ja järjestelmän luomat entiteetit:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Esimerkki: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- Vietyjen entiteettien model.json-arvo on tasolla %ExportDestinationName%.  
  - Esimerkki: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
