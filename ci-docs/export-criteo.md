---
title: Segmenttien vieminen Criteoon (esiversio)
description: Tietoja Criteo-yhteyden määrittämisestä ja viennistä siihen.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081129"
---
# <a name="export-segments-to-criteo-preview"></a>Segmenttien vieminen Criteoon (esiversio)

Vie segmenttejä yhdistetyistä asiakasprofiileista luodaksesi kampanjoita, tarjotaksesi sähköpostimarkkinointia ja käyttääksesi tiettyjä asiakasryhmiä Criteon avulla.

## <a name="prerequisites-for-connection"></a>Yhteyden edellytykset

-   Sinulla on [Criteo Dynamics Retargeting -tili](https://www.criteo.com/login/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
-   [Segmentit on määritetty](segments.md).
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään miljoona asiakasprofiilia Criteo-vientiä kohden.
- Vieminen Criteoon rajoittuu segmentteihin.
- Miljoona asiakasprofiilia sisältävien segmenttien vieminen voi kestää 30 minuuttia. 
- Criteoon vietävien asiakasprofiilien määrä riippuu Criteo-sopimuksestasi ja sen sisältämistä rajoituksista.

## <a name="set-up-connection-to-criteo"></a>Määritä yhteys Criteoon

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Criteo**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valitse **Hyväksyn** vahvistaaksesi **tietosuojan ja yhteensopivuuden** ja valitse **Yhdistä**, kun haluat alustaa yhteyden Criteoon.

1. Valitse **Todenna Criteo** ja anna järjestelmänvalvojakäyttäjänimesi ja tunnistetietosi Criteoon. 

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Criteo-osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi. 

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta. 

1. Vaihtoehtoisesti voit viedä **mainostajan tunnuksen** ja **nimen**

1. Valitse segmentit, jotka haluat viedä. 

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Criteoon otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää tällaiset tiedot ohjeittesi mukaisesti, mutta olet vastuussa siitä, että Criteo täyttää tietosuoja- ja tietoturvavaatimukset. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.


[!INCLUDE[footer-include](includes/footer-banner.md)]
