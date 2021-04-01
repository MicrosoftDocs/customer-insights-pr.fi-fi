---
title: Customer Insightsin tietojen vieminen Google Adsiin
description: Tietoja yhteyden määrittämisestä Google Adsiin.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598243"
---
# <a name="connector-for-google-ads-preview"></a>Google Ads -yhdistin (esiversio)

Vie yhtenäistettyjen asiakasprofiilien segmentit Google Adsin käyttäjäryhmäluetteloon ja käytä profiileja mainontaan Google Haussa, YouTubessa, Gmailissa ja Google Display-verkostossa. 

## <a name="prerequisites"></a>Edellytykset

-   [Google Ads -tili](https://ads.google.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
-   Google Adsissa on aiemmin luotuja käyttäjäryhmiä ja vastaavia tunnuksia. Lisätietoja on kohdassa [Google Ads -käyttäjäryhmät](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   [Segmentit on määritetty](segments.md)
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta, etunimeä ja sukunimeä vastaavat kentät.

## <a name="connect-to-google-ads"></a>Yhdistä Google Adsiin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.

1. Valitse **Google Ads** -kohdassa **Määritä**.

1. Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.

1. Anna **[Google Ads -asiakastunnus](https://support.google.com/google-ads/answer/1704344)**.

1. Anna **[Google Adsin hyväksymä kehittäjätunnus](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Käynnistä yhteys Google Adsiin antamalla **[Google Ads -käyttäjäryhmän tunnus](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** ja valitsemalla **Yhdistä**.

1. Valitse **Todenna Google Adsin avulla** ja anna Google Ads -tunnistetiedot.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Näyttökuva viennin Google Ads -yhteydestä":::

1. Määritä vienti valitsemalla **Next**.

## <a name="configure-the-connector"></a>Yhdistimen määrittäminen

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa. Toimi samalla tavalla **Etunimi**- ja **Sukunimi**-kenttien osalta.

1. Valitse segmentit, jotka haluat viedä. Voit viedä yhteensä enintään 1 000 000 asiakasprofiilia Google Adsiin.

1. Valitse **Tallenna**.

## <a name="export-the-data"></a>Tietojen vieminen

Voit [viedä tietoja tarvittaessa](export-destinations.md). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä. Google Adsin segmentit ovat nyt [Google Ads -käyttäjäryhmissä](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään 1 miljoona profiilia kussakin Google Ads -viennissä.
- Google Ads -vienti on rajoitettu segmentteihin.
- Yhteensä 1 miljoonan profiilin segmenttien vienti voi kestää 5 minuuttia palveluntoimittajan rajoitusten vuoksi. 
- Google Ads -vastaavuuden saavuttaminen voi kestää 48 tuntia.

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Google Adsiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Google Ads noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]