---
title: Segmenttien vieminen Microsoft Advertisingiin (esiversio)
description: Tietoja yhteyden määrittämisestä ja viennistä Microsoft Advertisingiin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196528"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Segmenttien vieminen Microsoft Advertisingiin (esiversio)

Vie Customer Insights -segmentit Microsoft Advertisingiin, jotta voit luoda asiakkaiden vastineen kohdeyleisöille. Käytä näitä kohderyhmiä mainoskampanjoissasi.

## <a name="prerequisites"></a>edellytykset

- [Microsoft Advertising -tili](https://ads.microsoft.com/) ja sitä vastaavat järjestelmänvalvojan tunnistetiedot.
- Microsoft Advertisingin asiakastunnus ja tilitunnus. URL-osoitteen parametreista löydät asiakastunnuksen (`cid`) ja tilitunnuksen (`aid`), kun kirjaudut Microsoft Advertisingiin.
- Customer Match -käyttöehdot on hyväksytty.
- [Määritetyt segmentit](segments.md) Customer Insightsissa.
- Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään 500 000 asiakasprofiilin vieminen kerrallaan Microsoft Advertisingiin, mikä voi kestää 10 minuuttia.
- Vain segmentit.

## <a name="set-up-connection-to-microsoft-advertising"></a>Määritä yhteys Microsoft Advertisingiin

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **Microsoft Advertising**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvo on järjestelmänvalvoja. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna **Microsoft Advertising -asiakastunnus**.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Käynnistä yhteys valitsemalla **Yhdistä**.

1. Valitse **Todenna Microsoft Advertisingin avulla** ja anna Microsoft Advertisingin järjestelmänvalvojan tunnistetiedot.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Microsoft Advertising -osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Valitse vietävät segmentit. Microsoft Advertisingin asiakkaan vastaavuuden kohdeyleisöt luodaan automaattisesti viennissä valittujen segmenttien nimellä. Kustakin segmentistä tulee erillinen Customer Match -yleisö.

1. Anna **Microsoft Advertisingin asiakastunnuksesi ja tilitunnuksesi**.

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, jossa on asiakkaan sähköpostiosoite.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
