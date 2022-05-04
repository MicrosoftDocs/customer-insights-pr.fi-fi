---
title: Customer Insights -tietojen vieminen Campaign Monitoriin
description: Tietoja yhteyden määrittämisestä ja viennistä Campaign Monitoriin.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b351e491ee830b6360d4efe33d32a726c2e553ba
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646063"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Segmenttien vieminen Campaign Monitoriin (esiversio)

Vie yhtenäisten asiakasprofiilien segmentit Campaign Monitoriin ja käytä niitä markkinointiaktiviteetteihin.

## <a name="prerequisites"></a>Edellytykset

-   Sinulla on [Campaign Monitor -tili](https://www.campaignmonitor.com/) ja sitä vastaavat järjestelmänvalvojan tunnistetiedot.
-   Olet [määrittänyt segmenttejä](segments.md) Customer Insightsissa.
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Voit viedä vientiä kohden enintään miljoona asiakasprofiilia Campaign Monitoriin.
- Vieminen Campaign Monitoriin rajoittuu segmentteihin.
- Enintään yhden miljoonan asiakasprofiilin vieminen Campaign Monitoriin voi kestää 20 minuuttia. 
- Campaign Monitoriin vietävien asiakasprofiilien määrä riippuu Campaign Monitor -sopimuksestasi ja sen sisältämistä rajoituksista.

## <a name="set-up-connection-to-campaign-monitor"></a>Määritä yhteys Campaign Monitoriin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Campaign Monitor**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Alusta yhteys Campaign Monitoriin valitsemalla **Yhdistä**.

1. Valitse **Todenna Campaign Monitorin avulla** ja anna Campaign Monitorin järjestelmänvalvojan tunnistetiedot.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Campaign Monitor -osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Anna [**Campaign Monitor -luettelon tunnus**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   [Luo API-avain](https://www.campaignmonitor.com/api/getting-started/) Campaign Monitorin **tiliasetuksista**, jotta näet ohjelmointirajapinnan luettelotunnuksen.  

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta. Campaign Monitoriin pitää viedä segmenttejä.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun otat tietojen siirron käyttöön Dynamics 365 Customer Insightsista Campaign Monitoriin, sallit tietojen siirtämisen Dynamics 365 Customer Insightsin vaatimustenmukaisuuden rajojen ulkopuolelle, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilötiedot. Microsoft siirtää nämä tiedot ohjeesi mukaisesti, mutta olet vastuussa siitä, että Campaign Monitor täyttää mahdolliset tietosuoja- tai tietoturvavelvollisuudet. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.
