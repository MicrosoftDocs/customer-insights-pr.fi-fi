---
title: Customer Insights -tietojen vieminen LinkedIn Adsiin
description: Tietoja yhteyden määrittämisestä ja viennistä LinkedIniin.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 2cfaa37fd0ac697f29665792bab27a925d8ea1eede0519d424524a7e5accbfeb
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034219"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Segmenttien vieminen LinkedIniin (esiversio)

Vie yhdistettyjen asiakasprofiilien segmentit LinkedIn Adsiin ja luo vastaavat kohdeyleisöt. Käytä kohdistettuja kohdeyleisöjä yrityksen ja yhteyshenkilöiden kohdistamiseen.

## <a name="prerequisites"></a>Edellytykset

-   Sinulla on [LinkedIn Campaign Manager -tili](https://business.linkedin.com/marketing-solutions/ads) ja sitä vastaavat järjestelmänvalvojan tunnistetiedot.
-   Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).
-   Viedyissä segmenteissä asiakasprofiilit sisältävät kentän, jolla on sähköpostiosoite.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Voit viedä LinkedIn Adsiin enintään 100 000 profiilia yhdessä viennissä.
- Vieminen LinkedIn Adsiin rajoittuu segmentteihin.
- 100 000 profiilin vienti LinkedIn Adsiin saattaa kestää noin 10 minuuttia. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Määritä yhteys LinkedIn Adsiin

1. Siirry kohdeyleisön merkityksellisissä tiedoissa kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **LinkedIn Ads**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna [LinkedIn Campaign Manager -tilitunnus](https://www.linkedin.com/help/lms/answer/a424270).

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Alusta yhteys Campaign Monitoriin valitsemalla **Yhdistä**.

1. Valitse **Todenna LinkedIn Adsin avulla** ja anna LinkedIn Campaign Manager -järjestelmänvalvojan tunnistetiedot.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys LinkedIn Ads -osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Valitse, haluatko viedä tiedot LinkedInissä [yhteyshenkilöiden kohdistamista](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) varten vai [yrityksen kohdistamista](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) varten. 

1. Valitse **Tietojen täsmäytys** -osassa yhdistetyn asiakasprofiilisi kenttä, joka edustaa asiakkaan sähköpostiosoitetta. LinkedIn Adsiin pitää viedä segmenttejä.

1. Valitse segmentit, jotka haluat viedä. Kohdeyleisöt LinkedIn Campaign Managerissa luodaan automaattisesti valittujen vietävien segmenttien nimellä. Kustakin segmentistä tulee erillinen kohdeyleisö. 

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun otat tietojen siirron käyttöön Dynamics 365 Customer Insightsista LinkedIn Adsiin, sallit tietojen siirtämisen Dynamics 365 Customer Insightsin vaatimustenmukaisuuden rajojen ulkopuolelle, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilötiedot. Microsoft siirtää nämä tiedot ohjeesi mukaisesti, mutta olet vastuussa siitä, että LinkedIn Ads täyttää mahdolliset tietosuoja- tai tietoturvavelvollisuudet. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights -järjestelmänvalvojasi voi poistaa tämän vientikohteen milloin tahansa, jos haluat lopettaa tämän toiminnon käytön.
