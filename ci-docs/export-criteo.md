---
title: Segmenttien vieminen Criteoon (esiversio)
description: Tietoja Criteo-yhteyden määrittämisestä ja viennistä siihen.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 811752da943cd5e40608d48644a1744c7971d3c8
ms.sourcegitcommit: 40ae3322ac95913e485607494754dd03814e42bb
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/11/2022
ms.locfileid: "9760022"
---
# <a name="export-segments-to-criteo-preview"></a>Segmenttien vieminen Criteoon (esiversio)

Vie segmenttejä yhdistetyistä asiakasprofiileista luodaksesi kampanjoita, tarjotaksesi sähköpostimarkkinointia ja käyttääksesi tiettyjä asiakasryhmiä Criteon avulla.

## <a name="prerequisites"></a>edellytykset

- [Criteo Dynamics Retargeting -tili](https://www.criteo.com/login/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
- [Määritetyt segmentit](segments.md).
- Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Vientiä kohden voi viedä enintään miljoona asiakasprofiilia Criteoon, mikä voi kestää 30 minuuttia. Criteoon vietävien asiakasprofiilien määrä määräytyy Criteo-sopimuksesi mukaan.
- Vain segmentit.

## <a name="set-up-connection-to-criteo"></a>Määritä yhteys Criteoon

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **Criteo**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Käynnistä yhteys valitsemalla **Yhdistä**.

1. Valitse **Todenna Criteo** ja anna järjestelmänvalvojakäyttäjänimesi ja tunnistetietosi Criteoon.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Criteo-osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta.

1. Valitse segmentit, jotka haluat viedä.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
