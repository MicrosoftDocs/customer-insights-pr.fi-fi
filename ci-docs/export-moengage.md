---
title: Segmenttien vieminen MoEngage-sovellukseen
description: Tietoja MoEngage-yhteyden määrittämisestä ja viennistä siihen sovellukseen.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199113"
---
# <a name="export-segments-to-moengage-preview"></a>Segmenttien vieminen MoEngage-sovellukseen (esiversio)

Vie yhdistettyjen asiakasprofiilien segmentit MoEngageen ja käytä niitä MoEngagen sähköpostimarkkinoinnissa.

## <a name="prerequisites-for-a-connection"></a>Yhteyden edellytykset

- [MoEngage-tili](https://www.moengage.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
- MoEngage API -avain MoEngagen kohdasta Asetukset -> ohjelmointirajapinta.
- [Määritetyt segmentit](segments.md) Customer Insightsissa.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään 100 000 asiakasprofiilin vieminen kerrallaan MoEngageen, mikä voi kestää 15 minuuttia. MoEngageen vietävien asiakasprofiilien määrä riippuu MoEngage-sopimuksestasi.
- Vain segmentit.

## <a name="set-up-connection-to-moengage"></a>Määritä MoEngage-yhteys

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **MoEngage**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna MoEngage [MoEngage Data -ohjelmointirajapintatunnus ja ohjelmointirajapinta-avain](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Alusta yhteys MoEngageen valitsemalla **Yhdistä**.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys MoEngage-osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta. Toista samat vaiheet muille valinnaisille kentille.

1. Valitse segmentit, jotka haluat viedä. Luodaan vähintään yksi segmentti, jolla on sama nimi kuin valitut MoEngage-segmentit kohdassa **Segmentit** > **Mukautetut segmentit**.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
