---
title: Tietojen vienti Azure Blob -säilöön (esiversio)
description: Tietoja yhteyden määrittämisestä ja viennistä Blob-säilöön.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195700"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Tietojen vienti Azure Blob -säilöön (esiversio)

Tallenna Customer Insights -tietosi Blob-säilöön, tai käytä sitä tietojesi siirtämiseen muihin sovelluksiin.

## <a name="prerequisites"></a>edellytykset

- [Azure Blob -tallennustilatilin](/azure/storage/blobs/create-data-lake-storage-account) nimi ja tiliavain. Lisätietoja nimen ja tiliavaimen löytämisestä on ohjeaiheessa [Azure-portaalin tallennustilatilin asetusten hallinta](/azure/storage/common/storage-account-manage).
- [Azure Blob -tallennussäilö](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Azure Blob -tallennustilavaihtoehtoja ovat [Standard-suorituskyky ja Premium-suorituskykytaso](/azure/storage/blobs/storage-blob-performance-tiers). Jos valitset Premium-suorituskykytason, valitse [tilityypiksi premium block blobs](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Määritä yhteys Blob-säilöön

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **Azure Blob -tallennus**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna **Tilin nimi**, **Tilin avain** ja **Säilö** Blob-tallennustilille.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Jotta voit määrittää viennin, tarvitset tämän yhteystyypin [käyttöoikeudet](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Jos olet ottanut Azure Blob Storage -tilin [pehmeän poistoasetuksen](/azure/storage/blobs/soft-delete-blob-enable) käyttöön, vienti epäonnistuu. Poista pehmeä poisto käytöstä, jos haluat viedä tietoja blob-tiedostoihin.

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Azure Blob Storage -osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Kirjoita Blob-tallennustilan kansion nimi.

1. Valitse tähän kohteeseen vietävien entiteettien vieressä oleva valintaruutu.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Viedyt tiedot tallennetaan määritettyyn Blob-tallennussäilöön. Säilöön luodaan automaattisesti seuraavat kansiopolut:

- Lähde-entiteetit ja järjestelmän luomat entiteetit:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Esimerkki: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Suuren määrän tietoja sisältävien entiteettien vienti voi aiheuttaa sen, että samassa kansiossa on useita CSV-tiedostoja kunkin viennin osalta. Viennit jaetaan suorituskykysyistä, sillä näin kunkin viennin suorittamiseen kuluva aika voidaan pitää mahdollisimman lyhyenä.

- Vietyjen entiteettien model.json-arvo on tasolla *%ExportDestinationName%*.  
  
  Esimerkki: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
