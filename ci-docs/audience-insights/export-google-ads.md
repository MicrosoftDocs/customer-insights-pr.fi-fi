---
title: Customer Insightsin tietojen vieminen Google Adsiin
description: Tietoja yhteyden määrittämisestä ja viennistä Google Adsiin.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ce9579f3d31207e666665237fd8935bb86889f8d
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617914"
---
# <a name="export-segments-to-google-ads-preview"></a>Segmenttien vieminen Google Adsiin (esiversio)

Vie yhdistettyjen asiakasprofiilien segmentit Google Ads -käyttäjäryhmäluetteloon ja käytä niitä mainostamisessa Google Searchissa, Gmailissa, YouTubessa ja Google Display Networkissa. 

> [!IMPORTANT]
> Tällä hetkellä voit luoda uuden yhteyden ja viedä tietoja Google Adsiin vain, jos sinulla on jo hyväksytty Google Adsin kehittäjätunnus. Käytännön muutosten vuoksi päivitämme Google Adsin viennin pian ja tarjoamme vientivaihtoehdon, joka ei edellytä sovelluskehittäjätietuetta käyttökokemuksen jatkuvuuden varmistamiseksi ja viennin helpottamiseksi Google Adsiin. Suosittelemme, että lisää yhteyksiä Google Adsiin ei luoda, jotta uuteen vientivaihtoehtoon siirtyminen helpottuu.

## <a name="prerequisites-for-connection"></a>Yhteyden edellytykset

-   [Google Ads -tili](https://ads.google.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
-   Sinulla on [hyväksytty Google Ads -kehittäjätunnus](https://developers.google.com/google-ads/api/docs/first-call/dev-token). 
-   [Asiakkaan vastaavuuskäytännön](https://support.google.com/adspolicy/answer/6299717) vaatimukset täyttyvät.
-   [Uudelleenmarkkinointiluetteloiden kokojen](https://support.google.com/google-ads/answer/7558048) edellytys on täytettävä.
-   Google Adsissa on aiemmin luotuja käyttäjäryhmiä ja vastaavia tunnuksia. Lisätietoja on kohdassa [Google Ads -käyttäjäryhmät](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   [Segmentit on määritetty](segments.md).
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta, etunimeä ja sukunimeä vastaavat kentät.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään miljoona asiakasprofiilia Google Ads -vientiä kohden.
- Google Ads -vienti on rajoitettu segmentteihin.
- Miljoona asiakasprofiilia sisältävä segmenttien vienti voi kestää viisi minuuttia palveluntarjoajan päässä olevien rajoitusten vuoksi. 
- Google Ads -vastaavuuden saavuttaminen voi kestää 48 tuntia.

## <a name="set-up-connection-to-google-ads"></a>Määritä yhteys Google Adsiin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Google Ads**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna **[Google Ads -asiakastunnus](https://support.google.com/google-ads/answer/1704344)**.

1. Anna **[Google Adsin hyväksymä kehittäjätunnus](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Valitse **Todenna Google Adsin avulla** ja anna Google Ads -tunnistetiedot.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**. 

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Google Ads -osasta. Jos et näe tämän osan nimeä, nämä yhteystyypit eivät ole käytettävissä.

1. Käynnistä yhteys Google Adsiin antamalla **[Google Ads -käyttäjäryhmän tunnus](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** ja valitsemalla **Yhdistä**.

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta.

1. Valitse segmentit, jotka haluat viedä. Voit viedä yhteensä enintään 1 000 000 asiakasprofiilia Google Adsiin.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. 

Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Google Adsiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Google Ads noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
