---
title: Segmenttien vieminen Omnisendiin (esiversio)
description: Tietoja yhteyden määrittämisestä ja viennistä Omnisendiin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fb57e2bd70592f4ce4e1a13e21901dc69734f6bf
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725166"
---
# <a name="export-segments-to-omnisend-preview"></a>Segmenttien vieminen Omnisendiin (esiversio)

Vie yhtenäisten asiakasprofiilien segmentit Omnisendiin ja käytä niitä markkinointiaktiviteetteihin.

## <a name="prerequisites"></a>edellytykset

- [Omnisend-tili](https://www.omnisend.com/) ja sitä vastaavat järjestelmänvalvojan tunnistetiedot.
- [Omnisend-ohjelmointirajapinnan avain](https://support.omnisend.com/en/articles/1061890-generating-api-key).
- [Määritetyt segmentit](segments.md) Customer Insightsissa.
- Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Yksityistä linkkiä, joka on yhdessä Oman tallennustilan (BYOS) kanssa, ei tueta.
- Vientiä kohden voi viedä enintään miljoona asiakasprofiilia Omnisendiin, mikä voi kestää neljä tuntia. Omnisendiin vietävien asiakasprofiilien määrä määräytyy Omnisend-sopimuksesi mukaan.
- Vain segmentit.

## <a name="set-up-connection-to-omnisend"></a>Määritä yhteys Omnisendiin

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **Omnisend**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna Omnisendin API-avain.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Käynnistä yhteys valitsemalla **Yhdistä**.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Omnisend-osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta.

1. Voit myös viedä **etunimen**, **sukunimen**, **osoitteen**, **maan/alueen**, **osavaltion**, **kaupungin** ja **postinumeron** mukautettujen sähköpostiviestien luomiseksi. Yhdistä nämä kenttä valitsemalla **Lisää määrite**.

1. Valitse segmentit, jotka haluat viedä.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
