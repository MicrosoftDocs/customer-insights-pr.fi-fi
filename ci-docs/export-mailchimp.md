---
title: Segmenttien vieminen Mailchimpiin (esiversio)
description: Tietoja yhteyden määrittämisestä ja viennistä Mailchimpiin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d74672768afec94e899ff0aec8c118c2afcde368
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725028"
---
# <a name="export-segments-to-mailchimp-preview"></a>Segmenttien vieminen Mailchimpiin (esiversio)

Uutiskirjeiden ja sähköpostikampanjoiden luonti viemällä yhtenäistettyjä asiakasprofiilisegmenttejä Mailchimpiin.

## <a name="prerequisites"></a>edellytykset

- [Mailchimp-tili](https://mailchimp.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
- [Aiemmin luotuja käyttäjäryhmiä Mailchimpissa](https://mailchimp.com/help/create-audience/) ja vastaavia [käyttäjäryhmätunnuksia](https://mailchimp.com/help/find-audience-id/).
- [Määritetyt segmentit](segments.md).
- Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Yksityistä linkkiä, joka on yhdessä Oman tallennustilan (BYOS) kanssa, ei tueta.
- Vientiä kohden voi viedä enintään miljoona asiakasprofiilia Mailchimpiin, mikä voi kestää 3 tuntia. Mailchimpiin vietävien asiakasprofiilien määrä riippuu Mailchimpin kanssa tekemästäsi sopimuksesta.
- Vain segmentit.

## <a name="set-up-connection-to-mailchimp"></a>Määritä yhteys Mailchimpiin

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **Mailchimp**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Käynnistä yhteys valitsemalla **Yhdistä**.

1. Valitse **Todenna Mailchimpin avulla** ja anna Mailchimp-tunnistetiedot.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Mailchimp-osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Anna **Mailchimp-käyttäjäryhmän tunnus**.

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta.

1. Voit myös viedä **etunimen** ja **sukunimen** yksilöllisempien sähköpostiviestien luomiseksi. Yhdistä nämä kenttä valitsemalla **Lisää määrite**.

1. Valitse segmentit, jotka haluat viedä.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
