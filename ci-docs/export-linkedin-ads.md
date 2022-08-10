---
title: Segmenttien vieminen LinkedIniin (esiversio)
description: Tietoja yhteyden määrittämisestä ja viennistä LinkedIniin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d1a9ae985043398f4bc38163be26ecf0c3c8e2ba
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196804"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Segmenttien vieminen LinkedIniin (esiversio)

Vie yhdistettyjen asiakasprofiilien segmentit LinkedIn Adsiin ja luo vastaavat kohdeyleisöt. Käytä kohdistettuja kohdeyleisöjä yrityksen ja yhteyshenkilöiden kohdistamiseen.

## <a name="prerequisites"></a>edellytykset

- [LinkedIn Campaign Manager -tili](https://business.linkedin.com/marketing-solutions/ads) ja vastaavat järjestelmänvalvojan tunnistetiedot.
- [LinkedIn Campaign Manager -tilitunnus](https://www.linkedin.com/help/lms/answer/a424270).
- [Määritetyt segmentit](segments.md) Customer Insightsissa.
- Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään 100 000 asiakasprofiilin vieminen kerrallaan LinkedIn Adsiin, mikä voi kestää 10 minuuttia.
- Vain segmentit. Segmentissä on oltava vähintään 300 yksilöllistä profiilia.

## <a name="set-up-connection-to-linkedin-ads"></a>Määritä yhteys LinkedIn Adsiin

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **LinkedIn Ads**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna LinkedIn Campaign Manager -tilitunnus.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Käynnistä yhteys valitsemalla **Yhdistä**.

1. Valitse **Todenna LinkedIn Adsin avulla** ja anna LinkedIn Campaign Manager -järjestelmänvalvojan tunnistetiedot.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys LinkedIn Ads -osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Valitse, haluatko viedä tiedot LinkedInissä [yhteyshenkilöiden kohdistamista](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) varten vai [yrityksen kohdistamista](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) varten.

1. Valitse **Tietojen vastaavuus** -osassa yhteyshenkilöiden kohdistamista varten vähintään yksi kenttä, joka edustaa asiakkaan sähköpostiosoitetta, Apple Ad -tunnusta, Google Ads -tunnusta, Google-käyttäjätunnusta tai etu- ja sukunimeä. Jos valitset yrityksen kohdistamisen, valitse vähintään yksi kenttä, joka edustaa yrityksen nimeä, sähköpostin toimialuetta, LinkedIn-sivun URL-osoitetta, Stock-symbolia tai verkkosivustoa.

1. Viennin lisämäärityksiä varten voidaan valita lisää kenttiä. Yhdistä nämä kenttä valitsemalla **Lisää määrite**.

1. Valitse segmentit, jotka haluat viedä. Kohdeyleisöt LinkedIn Campaign Managerissa luodaan automaattisesti valittujen vietävien segmenttien nimellä. Kustakin segmentistä tulee erillinen kohdeyleisö.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
