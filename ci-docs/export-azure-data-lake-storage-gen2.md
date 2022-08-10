---
title: Tietojen vienti Azure Data Lake Storage Gen2:een (esiversio)
description: Tietoja yhteyden määrittämisestä Azure Data Lake Storage Gen2:een.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196436"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Tietojen vienti Azure Data Lake Storage Gen2:een (esiversio)

Tallenna Customer Insights -tietosi Data Lake Storage Gen2 -tilille tai käytä sitä tietojesi siirtämiseen muihin sovelluksiin.

## <a name="prerequisites"></a>edellytykset

- [Tallennustili käytettäväksi Azure Data Lake Gen 2:n kanssa](/azure/storage/blobs/create-data-lake-storage-account). Lisätietoja tallennustilin nimen ja tiliavaimen löytämisestä on ohjeaiheessa [Azure-portaalin tallennustilatilin asetusten hallinta](/azure/storage/common/storage-account-manage).
- [Azure Blob -tallennussäilö](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Azure Data Lake Storage Gen2 -vaihtoehtoja ovat [Standard-suorituskyky ja Premium-suorituskykytaso](/azure/storage/blobs/create-data-lake-storage-account). Jos valitset Premium-suorituskykytason, valitse [tilityypiksi premium block blobs](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Määritä yhteys Azure Data Lake Storage Gen2:een

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **Azure Data Lake Gen 2**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna Azure Data Lake Storage Gen2:lle **tilin nimi**, **tilin avain** ja **säilö**.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Azure Data Lake -osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Kirjoita Gen2-tallennustilan Azure Data Lake Storage -kansion nimi.

1. Valitse tähän kohteeseen vietävien entiteettien vieressä oleva valintaruutu.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Viedyt tiedot tallennetaan määritettyyn Azure Data Lake Gen 2 -tallennussäilöön.

> [!TIP]
> Suuren määrän tietoja sisältävien entiteettien vienti voi aiheuttaa sen, että samassa kansiossa on useita CSV-tiedostoja kunkin viennin osalta. Viennit jaetaan suorituskykysyistä, sillä näin kunkin viennin suorittamiseen kuluva aika voidaan pitää mahdollisimman lyhyenä.

[!INCLUDE [footer-include](includes/footer-banner.md)]
