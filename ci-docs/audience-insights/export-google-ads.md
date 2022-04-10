---
title: Customer Insightsin tietojen vieminen Google Adsiin
description: Tietoja yhteyden määrittämisestä ja viennistä Google Adsiin.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7a85237f7aff564d6b540b2c11553a52f875fac4
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523790"
---
# <a name="export-segments-to-google-ads-preview"></a>Segmenttien vieminen Google Adsiin (esiversio)

Vie yhdistettyjen asiakasprofiilien segmentit Google Ads -käyttäjäryhmäluetteloon ja käytä niitä mainostamisessa Google Searchissa, Gmailissa, YouTubessa ja Google Display Networkissa. 


## <a name="prerequisites-for-connection"></a>Yhteyden edellytykset

-   [Google Ads -tili](https://ads.google.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
-   [Asiakkaan vastaavuuskäytännön](https://support.google.com/adspolicy/answer/6299717) vaatimukset täyttyvät.
-   [Uudelleenmarkkinointiluetteloiden kokojen](https://support.google.com/google-ads/answer/7558048) edellytys on täytettävä.
-   [Segmentit on määritetty](segments.md).
-   Viedyissä segmenteissä olevat Unified customer profile -profiilit sisältävät kentät, jotka edustavat sähköpostiosoitetta, puhelinnumeroa, mobiilimainostajan tunnusta, kolmannen osapuolen käyttäjätunnusta tai osoitetta.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Google Ads -vienti on rajoitettu segmentteihin.
- Miljoona asiakasprofiilia sisältävä segmenttien vienti voi kestää 30 minuuttia palveluntarjoajan päässä olevien rajoitusten vuoksi. 
- Google Ads -vastaavuuden saavuttaminen voi kestää 48 tuntia.

## <a name="set-up-connection-to-google-ads"></a>Määritä yhteys Google Adsiin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Google Ads**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna **[Google Ads -asiakastunnus](https://support.google.com/google-ads/answer/1704344)**.

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Valitse **Todenna Google Adsin avulla** ja anna Google Ads -tunnistetiedot.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**. 

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Google Ads -osasta. Jos et näe tämän osan nimeä, nämä yhteystyypit eivät ole käytettävissä.

1. Jos haluat luoda uuden käyttäjäryhmän, jätä Googlen käyttäjäryhmän tunnus -kenttä tyhjäksi. Luomme automaattisesti uuden käyttäjäryhmän Google Ads -tiliisi ja käytämme viedyn segmentin nimeä. Jos haluat päivittää aiemmin luodun Google Ads -käyttäjäryhmän, anna [Google Adsin käyttäjäryhmätunnus](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. Valitse **Tietojen vastaavuus** -osassa vähintään yksi vietävä tietokenttä ja valitse kenttä, joka vastaa Customer Insightsin vastaavia tietokenttiä.

1. Valitse segmentit, jotka haluat viedä. 

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. 

Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Google Adsiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Google Ads noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
