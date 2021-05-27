---
title: Customer Insightsin tietojen vieminen Facebookin mainosten hallintaan
description: Tietoja yhteyden määrittämisestä ja viennistä Facebook Ads Manageriin.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976038"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Segmenttiluettelon vieminen Facebook Ads Manageriin (esiversio)

Voit luoda kampanjoita Facebookissa ja Instagramissaa viemällä yhdistettyjen asiakasprofiilien segmenttejä Facebook Ads Manageriin.

## <a name="prerequisites-for-connection"></a>Yhteyden edellytykset

- Sinulla on oltava [**Facebook-mainostili**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), joka sisältää [**Facebook-yritystilin**](https://business.facebook.com/).
- Sinun on oltava [**Facebook Ad -tilin**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) järjestelmänvalvoja.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään 10 miljoonaa asiakasprofiilia yhdessä viennissä Facebook Ads Manageriin.
- Vienti Facebook Ads Manageriin on rajoitettu segmentteihin.
- Voit luoda tai päivittää Facebookissa mukautettuja kohderyhmiä vain *asiakasluettelo*-tyypeille.
- Yhteensä 10 miljoonan profiilin segmenttien vienti voi kestää 90 minuuttia.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Määritä yhteys Facebook Ads Manageriin

Ennen kuin käyttäjät voivat luoda viennin, järjestelmänvalvojan on määritettävä yhteys palveluun ja sallittava osallistujien käyttää yhteyttä.

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Facebook Ads Manager**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on **Järjestelmänvalvojat**. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Todenna Facebook Adsin avulla: 

   1. Valitse **Continue with Facebook** kirjautuaksesi Facebook Ad -tiliisi.

   1. Salli **ads_management**-oikeus Facebook-todennuksen jälkeen.

   1. Valitse **Facebook Ad -tili**, jota haluat käyttää.

   1. Valitse yleisö avattavasta **Existing custom audience** -valikosta tai luo uusi **New custom audience** -kohdassa. Lisätietoja on kohdassa [**Kohdeyleisöt Facebook Ads Managerissa**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Voit luoda tai päivittää Facebookissa mukautettuja kohderyhmiä vain *asiakasluettelo*-tyypille tämän viennin yhteydessä. Joissakin tapauksissa avattavasta luettelosta näet erityyppisiä mukautettuja kohdeyleisöjä. Jos valitset jonkin toisen tyypin kuin *asiakasluettelo*, vienti epäonnistuu. 

1. Tarkista tietojen **Tietosuoja ja vaatimustenmukaisuus** ja valitse **Hyväksyn**.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**. 

1. Valitse **Yhteys vientiä varten** -kentässä yhteys **Facebook Ads Manager** -osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Valitse **Choose your key identifier** -kentässä **Email**, **Name and address** tai **Phone**, jonka avulla lähetetään Facebook Ads Manageriin. 

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.

1. Yhdistä yhdistetyn asiakasentiteetin vastaavat määritteet valittua avaintunnistetta varten.
   > [VIHJE] Paras vaihtoehtosi on se, että valitaan **Email** tunnukseksi. Lisätunnusten lisääminen voi parantaa vastaavuutta.

1. Valitse **Lisää määrite**, jos haluat yhdistää lisää määritteitä lähetettäväksi Facebook Ads Manageriin. Facebook Ads Managerin määritteet yhdistetään seuraaviin kenttien lyhyisiin nimiin: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**

1. Valitse segmentit, jotka haluat viedä.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Facebookin mainosten hallintaan otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Facebook Ads noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
