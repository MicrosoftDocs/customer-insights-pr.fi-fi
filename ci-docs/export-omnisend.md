---
title: Segmenttien vieminen Omnisendiin (esiversio)
description: Tietoja yhteyden määrittämisestä ja viennistä Omnisendiin.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 15918b2e2550869115d30ea4d84b4549c3c7d1ca
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052277"
---
# <a name="export-segments-to-omnisend-preview"></a>Segmenttien vieminen Omnisendiin (esiversio)

Vie yhtenäisten asiakasprofiilien segmentit Omnisendiin ja käytä niitä markkinointiaktiviteetteihin.

## <a name="prerequisites"></a>Edellytykset

-   Sinulla on [Omnisend-tili](https://www.omnisend.com/) ja sitä vastaavat järjestelmänvalvojan tunnistetiedot.
-   Olet [määrittänyt segmenttejä](segments.md) Customer Insightsissa.
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Vientiä kohden voit viedä enintään miljoona asiakasprofiilia Omnisendiin, ja se voi kestää neljä tuntia.
- Vieminen Omnisendiin rajoittuu segmentteihin.
- Omnisendiin vietävien asiakasprofiilien määrä riippuu sopimuksestasi Omnisendin kanssa.

## <a name="set-up-connection-to-omnisend"></a>Määritä yhteys Omnisendiin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Omnisend**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna [Omnisendin API-avain](https://support.omnisend.com/en/articles/1061890-generating-api-key).

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Alusta yhteys Omnisendiin valitsemalla **Yhdistä**.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Omnisend-osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta. Omnisendiin pitää viedä segmenttejä. Voit myös viedä etunimen, sukunimen, osoitteen, maan/alueen, osavaltion, kaupungin ja postinumeron yksilöllisempien sähköpostiviestien luomiseksi. Yhdistä nämä kenttä valitsemalla **Lisää määrite**.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun otat tietojen siirron käyttöön Dynamics 365 Customer Insightsista Ommisendiin, sallit tietojen siirtämisen Dynamics 365 Customer Insightsin vaatimustenmukaisuuden rajojen ulkopuolelle, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilötiedot. Microsoft siirtää nämä tiedot ohjeesi mukaisesti, mutta olet vastuussa siitä, että Ommisend täyttää mahdolliset tietosuoja- tai tietoturvavelvollisuudet. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.
