---
title: Customer Insights -tietojen vieminen Facebook Ads Manageriin (sisältää videon)
description: Tietoja yhteyden määrittämisestä ja viennistä Facebook Ads Manageriin.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 781cf10e1bb5ddaf82d4a17c7a77e0c43c41a1c2
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226491"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Segmenttiluettelon vieminen Facebook Ads Manageriin (esiversio)

Voit luoda kampanjoita Facebookissa ja Instagramissaa viemällä yhdistettyjen asiakasprofiilien segmenttejä Facebook Ads Manageriin.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>Yhteyden edellytykset

- Tarvitset [**Facebook Ads -tilin**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), joka sisältää [**Facebookin yritystilin**](https://business.facebook.com/).
- Sinun on oltava [**Facebook Ads -tilin**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) järjestelmänvalvoja.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Jopa 10 miljoonaa asiakasprofiilia vientiä kohden Facebook Ads -ratkaisun hallinnassa.
- Vienti Facebook Ads Manageriin on rajoitettu segmentteihin.
- Voit luoda tai päivittää Facebookissa mukautettuja kohderyhmiä vain *asiakasluettelo*-tyypeille.
- Kymmenen miljoonaa asiakasprofiilia sisältävien segmenttien vieminen voi kestää 90 minuuttia.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Määritä yhteys Facebook Ads Manageriin

Ennen kuin käyttäjät voivat luoda viennin, järjestelmänvalvojan on määritettävä yhteys palveluun ja sallittava osallistujien käyttää yhteyttä.

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Facebook Ads Manager**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Todenna Facebook Adsin avulla: 

   1. Valitse **Jatka Facebookilla**, jos haluat kirjautua sisään Facebook Ads -tilillä.

   1. Salli **ads_management**-oikeus Facebook-todennuksen jälkeen.

   1. Valitse **Facebook Ad -tili**, jota haluat käyttää.

   1. Valitse **aiemmin luotu mukautettu käyttäjäryhmä** avattavasta luettelosta tai luo **uusi mukautettu käyttäjäryhmä**. Lisätietoja on kohdassa [**Kohdeyleisöt Facebook Ads Managerissa**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Voit luoda tai päivittää Facebookissa mukautettuja kohderyhmiä vain *asiakasluettelo*-tyypille tämän viennin yhteydessä. Joissakin tapauksissa avattavassa luettelossa ovat eri tyyppiset mukautetut käyttäjäryhmät. Jos valitset jonkin toisen tyypin kuin *asiakasluettelo*, vienti epäonnistuu. 

1. Tarkista tietojen **Tietosuoja ja vaatimustenmukaisuus** ja valitse **Hyväksyn**.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**. 

1. Valitse **Yhteys vientiä varten** -kentässä yhteys **Facebook Ads Manager** -osasta. Jos et näe tämän osan nimeä, nämä yhteystyypit eivät ole käytettävissä.

1. Valitse **Choose your key identifier** -kentässä **Email**, **Name and address** tai **Phone**, jonka avulla lähetetään Facebook Ads Manageriin. 

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.

1. Yhdistä yhdistetyn asiakasentiteetin vastaavat määritteet valittua avaintunnistetta varten.
   > [!TIP]
   > Parhaat vastaavuudet saat, jos valitset avaintunnisteeksi **sähköpostin**. Lisätunnusten lisääminen voi parantaa vastaavuutta.

1. Valitse **Lisää määrite**, jos haluat yhdistää lisää määritteitä lähetettäväksi Facebook Ads Manageriin. Facebook Ads -ratkaisun hallinnan määritteiden vastaavuus määritetään seuraaviin käyttäjän määrittämiin kutsumanimiin: **FN** = **etunimi**, **LN** = **sukunimi**, **FI** = **ensimmäinen alkukirjain**, **PHONE** = **puhelin**, **GEN** = **sukupuoli**, **DOB** = **syntymäaika**, **ST** = **osavaltio**, **CT** = **kaupunki**, **ZIP** = **postinumero**, **COUNTRY** = **maa tai alue**

1. Valitse segmentit, jotka haluat viedä.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. 

Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Facebookin mainosten hallintaan otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Facebook Ads noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
