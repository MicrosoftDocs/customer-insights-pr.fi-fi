---
title: Customer Insights -tietojen vieminen Microsoft Advertisingiin
description: Tietoja yhteyden määrittämisestä ja viennistä Microsoft Advertisingiin.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124480"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Segmenttien vieminen Microsoft Advertisingiin (esiversio)

Vie Customer Insights -segmentit Microsoft Advertisingiin, jotta voit luoda asiakkaiden vastineen kohdeyleisöille. Käytä näitä kohderyhmiä mainoskampanjoissasi.

## <a name="prerequisites"></a>Edellytykset

-   [Microsoft Advertising -tili](https://ads.microsoft.com/) ja sitä vastaavat järjestelmänvalvojan tunnistetiedot.
-   Olet hyväksynyt asiakkaan vastineen käyttöehdot. 
-   [Määritetyt segmentit](segments.md) käyttäjäryhmän merkityksellisissä tiedoissa.
-   Viedyissä segmenteissä yhdenmukaistetut asiakasprofiilit sisältävät kentän, jolla on sähköpostiosoite.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Voit viedä Microsoft Advertisingiin enintään 500 000 profiilia yhdessä viennissä.
- Vieminen Microsoft Advertisingiin rajoittuu segmentteihin.
- 500 000:n profiilin vienti Microsoft Advertisingiin saattaa kestää noin 10 minuuttia. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Määritä yhteys Microsoft Advertisingiin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Microsoft Advertising**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvo on järjestelmänvalvoja. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Alusta yhteys Microsoft Advertisingiin valitsemalla **Yhdistä**.

1. Valitse **Todenna Microsoft Advertisingin avulla** ja anna Microsoft Advertisingin järjestelmänvalvojan tunnistetiedot.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Microsoft Advertising -osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Valitse vietävät segmentit. Microsoft Advertisingin customer match -kohdeyleisöt luodaan automaattisesti viennissä valittujen segmenttien nimellä. Kustakin segmentistä tulee erillinen Customer Match -yleisö. 

1. Anna **Microsoft Advertisingin asiakastunnuksesi ja tilitunnuksesi**. URL-osoitteen parametreista löydät asiakastunnuksen (`cid`) ja tilitunnuksen (`aid`), kun kirjaudut Microsoft Advertisingiin.

1. Valitse **Tietojen täsmäytys** -osassa **Sähköposti**-kentässä yhdistetyn asiakasprofiilisi kenttä, jossa on asiakkaan sähköpostiosoite. Microsoft Advertisingiin pitää viedä segmenttejä.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun otat tietojen siirron käyttöön Dynamics 365 Customer Insightsista Microsoft Advertisingiin, sallit tietojen siirtämisen Dynamics 365 Customer Insightsin vaatimustenmukaisuuden rajojen ulkopuolelle, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilötiedot. Microsoft siirtää nämä tiedot ohjeesi mukaisesti, mutta olet vastuussa siitä, että Microsoft Advertising täyttää mahdolliset tietosuoja- tai tietoturvavelvollisuudet. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights -järjestelmänvalvojasi voi poistaa tämän vientikohteen milloin tahansa, jos haluat lopettaa tämän toiminnon käytön.