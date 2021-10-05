---
title: Evästeiden hallinta ja käyttäjän suostumus käyttäjätietojen tallentamiseksi Dynamics 365 Customer Insightsiin
description: Tutustu siihen, miten evästeitä ja käyttäjän suostumusta käytetään verkkosivustojen vierailijoiden tunnistamiseen.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c824e50b723fe7f3b421048bb6ab96b7a9efc31f
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558867"
---
# <a name="manage-cookies-and-user-consent"></a>Evästeiden ja käyttäjän suostumuksen hallinta

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insightsin sitouttamisen merkitykselliset tiedot -ominaisuus tunnistaa verkkosivuston vierailijat evästeiden ja (`localStorage`) avainten avulla.

Evästeet ovat pieniä tiedostoja, jotka tallentavat tietoja käyttäjän vuorovaikutuksesta verkkosivuston kanssa. Ne tallennetaan verkkoselaimiin. Kun käyttäjät vierailevat verkkosivustolla, jolle käyttäjät ovat tallentaneet evästeitä, selain lähettää nämä tiedot palvelimeen, joka palauttaa käyttäjälle yksilöllisiä tietoja. Tämä tekniikka mahdollistaa esimerkiksi sen, että verkko-ostoskoriin valitut esineet säilyvät, vaikka käyttäjä siirtyisi pois verkkosivustolta.

## <a name="user-consent"></a>Käyttäjän suostumus

[Yleinen tietosuoja-asetus (GDPR)](/dynamics365/get-started/gdpr/) on Euroopan unionin (EU) asetus, jossa määrätään, miten organisaatioiden pitää käsitellä käyttäjiensä yksityisyyttä ja suojausta. Evästeet tallentavat tai keräävät usein "henkilötietoja", kuten verkkotunnisteita, jotka kuuluvat GDPR:n piiriin. Jos yrityksessäsi on töissä EU:n rekisteröityjä ja/tai sillä on myyntiä rekisteröidyille, GDPR vaikuttaa sinuun. [Lisätietoja siitä, miten Microsoft voi auttaa GDPR:n noudattamisessa](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Jotta vuorovaikutuksen merkityksellisten tietojen SDK voi tallentaa evästeitä tai muita arkaluonteisia tietoja, sinun täytyy määrittää, ovatko käyttäjät antaneet suostumuksensa. Tämä tapahtuu SDK:n valmistelun yhteydessä määrittämällä määrityksen `userConsent`-kenttä.

Jos ilmoitat, että käyttäjän suostumusta ei ole, SDK ei tallenna tietoja eikä lähetä tapahtumia, joita voidaan käyttää käyttäjän käyttäytymisen seuraamiseen. Aiemmin tallennetut tiedot poistetaan selaimesta.

Jos käyttäjän suostumuksen arvoa ei määritetä, SDK olettaa, että käyttäjä on antanut siihen luvan. Tämä tarkoittaa sitä, että jos sinä (asiakkaanamme) et määritä arvoa käyttäjän suostumukselle SDK:ssa, tiedot kerätään. Jos kuitenkin määrität, että käyttäjän hyväksynnän suostumuksen on oltava "tosi", tietoja ei kerätä, jos käyttäjä kieltää suostumuksensa tai ei anna nimenomaista suostumusta.

Seuraavassa on koodikatkelma www-SDK:n alustamisesta käyttäjän suostumuksella:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Vierailijatietojen tallennus vuorovaikutuksen merkityksellisten tietojen ominaisuudessa

### <a name="cookies"></a>Pikkuleivät

- _msei
    - Tallentaa anonyymin käyttäjätunnuksen. Eväste määritetään asiakkaan toimialueella, ja se vanhenee 365 päivän kuluttua.

### <a name="local-storage"></a>Paikallinen tallennustila

Sitouttamisen merkitykselliset tiedot -ominaisuus käyttää myös (`localStorage`) avaimia ei-luottamuksellisten tietojen seuraamiseen. Nämä tiedot tallennetaan kokonaan itse selaimeen, eikä liikennettä lähetetä palvelimiin tai palvelimista.

- *EISession.Id*
    - Tallentaa tietoja käynnissä olevasta käyttäjäistunnosta, kuten istuntotunnuksen, istunnon alkamisajan ja sen päättymisajan.
- *EISession.Previous*
    - Tallentaa kulloisenkin istunnon edellisen sivun URL-osoitteen, jolla on vierailtu.

Paikallisen tallennustilan avaimet eivät vanhene automaattisesti, ja ne nollataan seuraavan SDK-istunnon aikana.

## <a name="deleting-cookies"></a>Evästeiden poistaminen

Asiakkaasi voivat poistaa evästeitä ja paikallisia tallennustilan avaimia manuaalisesti milloin tahansa selainten asetusten kautta.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
