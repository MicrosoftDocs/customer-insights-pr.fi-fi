---
title: Segmenttien vieminen Iterableen (esiversio)
description: Tietoja Iterable-yhteyden määrittämisestä ja viennistä siihen.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 69e2bd207c98fc2530620018bf95dd869d1798f6
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724478"
---
# <a name="export-segments-to-iterable-preview"></a>Segmenttien vieminen Iterableen (esiversio)

Vie yhdistettyjen asiakasprofiilien segmentit Iterableen ja käytä niitä markkinointiaktiviteetteihin.

## <a name="prerequisites"></a>edellytykset

- [Iterable-tili](https://iterable.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
- [Iterable-ohjelmointirajapinnan avain](https://support.iterable.com/hc/en-us/articles/360043464871)
- [Määritetyt segmentit](segments.md) Customer Insightsissa.
- Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Yksityistä linkkiä, joka on yhdessä Oman tallennustilan (BYOS) kanssa, ei tueta.
- Enintään yhden miljoonan asiakasprofiilin vieminen Iterableen, mikä voi kestää 30 minuuttia. Iterableen vietävien asiakasprofiilien määrä riippuu Iterable-sopimuksestasi.
- Vain segmentit.

## <a name="set-up-connection-to-iterable"></a>Määritä yhteys Iterableen

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **Iterable**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Jatka kirjautumista antamalla Iterable-ohjelmointirajapinnan avain.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Käynnistä yhteys valitsemalla **Yhdistä**.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Iterable-osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta. Iterablessa luotuun luetteloon tulee täsmälleen sama nimi kuin segmentin nimessä kohteessa Dynamics 365 Customer Insights.

1. Valitse segmentit, jotka haluat viedä.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
