---
title: Evästeiden ja käyttäjän käyttäjätietojen tallentamista koskevan suostumuksen hallinta
description: Tutustu siihen, miten evästeitä ja käyttäjän suostumusta käytetään verkkosivustojen vierailijoiden tunnistamiseen.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036734"
---
# <a name="manage-cookies-and-user-consent"></a>Evästeiden ja käyttäjän suostumuksen hallinta

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insightsin vuorovaikutuksen merkitykselliset tiedot -ominaisuus tunnistaa verkkosivuston vierailijat evästeiden ja paikallisen tallennustilan (`localStorage`) avulla.

Evästeet ovat pieniä tiedostoja, jotka tallentavat tietoja käyttäjän vuorovaikutuksesta verkkosivuston kanssa. Ne tallennetaan verkkoselaimiin. Kun käyttäjät vierailevat verkkosivustolla, jolle käyttäjät ovat tallentaneet evästeitä, selain lähettää nämä tiedot palvelimeen, joka palauttaa käyttäjälle yksilöllisiä tietoja. Tämä tekniikka mahdollistaa esimerkiksi sen, että verkko-ostoskoriin valitut esineet säilyvät, vaikka käyttäjä siirtyisi pois verkkosivustolta.

## <a name="user-consent"></a>Käyttäjän suostumus

[Yleinen tietosuoja-asetus (GDPR)](/dynamics365/get-started/gdpr/) on Euroopan unionin (EU) asetus, jossa määrätään, miten organisaatioiden pitää käsitellä käyttäjiensä yksityisyyttä ja suojausta. Evästeet tallentavat tai keräävät usein "henkilötietoja", kuten verkkotunnisteita, jotka kuuluvat GDPR:n piiriin. Jos yrityksessäsi on töissä EU:n rekisteröityjä ja/tai sillä on myyntiä rekisteröidyille, GDPR vaikuttaa sinuun. [Lisätietoja siitä, miten Microsoft voi auttaa GDPR:n noudattamisessa](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Jotta vuorovaikutuksen merkityksellisten tietojen SDK voi tallentaa evästeitä tai muita arkaluonteisia tietoja, sinun täytyy määrittää, ovatko käyttäjät antaneet suostumuksensa. Tämä tapahtuu SDK:n valmistelun yhteydessä.

Jos ilmoitat, että käyttäjän suostumusta ei ole, SDK ei tallenna tietoja eikä lähetä tapahtumia, joita voidaan käyttää käyttäjän käyttäytymisen seuraamiseen. Aiemmin tallennetut tiedot poistetaan selaimesta.

Jos käyttäjän suostumuksen arvoa ei määritetä, SDK olettaa, että käyttäjä on antanut siihen luvan. Tämä tarkoittaa sitä, että jos sinä (asiakkaanamme) et määritä arvoa käyttäjän suostumukselle SDK:ssa, tiedot kerätään. Jos kuitenkin määrität, että käyttäjän hyväksynnän suostumuksen on oltava "tosi", tietoja ei kerätä, jos käyttäjä kieltää suostumuksensa tai ei anna nimenomaista suostumusta.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Vierailijatietojen tallennus vuorovaikutuksen merkityksellisten tietojen ominaisuudessa

### <a name="cookies"></a>Pikkuleivät

- _msei
    - Tallentaa anonyymin käyttäjätunnuksen. Eväste määritetään asiakkaan toimialueella, ja se vanhenee 365 päivän kuluttua.

### <a name="local-storage"></a>Paikallinen tallennustila

Vuorovaikutuksen merkityksellisten tietojen ominaisuus käyttää myös paikallista tallennustilaa ( `localStorage`), jotta muita kuin arkaluontoisia tietoja voidaan seurata. Nämä tiedot tallennetaan kokonaan itse selaimeen, eikä liikennettä lähetetä palvelimiin tai palvelimista.

- *EISession.Id* 
    - Tallentaa tietoja käynnissä olevasta käyttäjäistunnosta, kuten istuntotunnuksen, istunnon alkamisajan ja sen päättymisajan.
- *EISession.Previous*
    - Tallentaa kulloisenkin istunnon edellisen sivun URL-osoitteen, jolla on vierailtu.
    
Paikallisen tallennustilan avaimet eivät vanhene automaattisesti. SDK nollaa ne seuraavan istunnon aikana.

## <a name="deleting-cookies"></a>Evästeiden poistaminen

Asiakkaasi voivat poistaa evästeitä ja paikallisia tallennustilan avaimia manuaalisesti milloin tahansa selainten asetusten kautta.


[!INCLUDE[footer-include](../includes/footer-banner.md)]