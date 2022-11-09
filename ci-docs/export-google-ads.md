---
title: Segmenttien vieminen Google Adsiin (esiversio)
description: Tietoja yhteyden määrittämisestä ja viennistä Google Adsiin.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725074"
---
# <a name="export-segments-to-google-ads-preview"></a>Segmenttien vieminen Google Adsiin (esiversio)

Vie yhdistettyjen asiakasprofiilien segmentit Google Ads -käyttäjäryhmäluetteloon ja käytä niitä mainostamisessa Google Searchissa, Gmailissa, YouTubessa ja Google Display Networkissa.

## <a name="prerequisites"></a>edellytykset

- [Google Ads -tili](https://ads.google.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
- [Google Ads -asiakastunnus](https://support.google.com/google-ads/answer/1704344).
- [Asiakkaan vastaavuuskäytännön](https://support.google.com/adspolicy/answer/6299717) vaatimukset täyttyvät.
- [Uudelleenmarkkinointiluetteloiden kokojen](https://support.google.com/google-ads/answer/7558048) edellytys on täytettävä.
- [Määritetyt segmentit](segments.md).
- Viedyissä segmenteissä olevat Unified customer profile -profiilit sisältävät kentät, jotka edustavat sähköpostiosoitetta, puhelinnumeroa, mobiilimainostajan tunnusta, kolmannen osapuolen käyttäjätunnusta tai osoitetta.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Yksityistä linkkiä, joka on yhdessä Oman tallennustilan (BYOS) kanssa, ei tueta.
- Jopa miljoonan asiakasprofiilin vienti Google Adsiin, mikä voi kestää 30 minuuttia, koska palvelun puolella on rajoituksia.
- Vain segmentit.
- Google Ads -vastaavuuden saavuttaminen voi kestää 48 tuntia.

## <a name="set-up-connection-to-google-ads"></a>Määritä yhteys Google Adsiin

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **Google Ads**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna Google Ads -asiakastunnus.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Valitse **Todenna Google Adsin avulla** ja anna Google Ads -tunnistetiedot.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Google Ads -osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Valitse käytetäänkö jo luotua käyttäjäryhmää vai luodaanko uusi:
   - Jos haluat päivittää aiemmin luodun Google Ads -käyttäjäryhmän, anna [Google Adsin käyttäjäryhmätunnus](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns)
   - Jos haluat luoda uuden käyttäjäryhmän, jätä Googlen käyttäjäryhmän tunnus -kenttä tyhjäksi. Customer Insights luo automaattisesti uuden käyttäjäryhmän Google Ads -tiliisi ja käyttää viedyn segmentin nimeä.

1. Valitse **Tietojen vastaavuus** -osassa vähintään yksi vietävä tietokenttä ja valitse kenttä, joka vastaa Customer Insightsin vastaavia tietokenttiä.

1. Valitse segmentit, jotka haluat viedä.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
