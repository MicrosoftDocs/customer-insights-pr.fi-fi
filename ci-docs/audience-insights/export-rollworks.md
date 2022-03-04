---
title: Customer Insights -tietojen vieminen RollWorksiin
description: Tietoja yhteyden määrittämisestä ja viennistä RollWorksiin.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 392084105628ba4e6008a1386a5ac80c809a004e
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225561"
---
# <a name="export-segments-to-rollworks-preview"></a>Segmenttien vieminen RollWorksiin (esiversio)

Vie yhtenäisten asiakasprofiilien segmentit RollWorksiin ja käytä niitä mainontaan. 

## <a name="prerequisites-for-a-connection"></a>Yhteyden edellytykset

-   Sinulla on [RollWorks-tili](https://www.rollworks.com/) ja sitä vastaavat järjestelmänvalvojan tunnistetiedot.
-   Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Voit viedä vientiä kohden enintään 250 000 asiakasprofiilia RollWorksiin.
- RollWorksiin ei voi viedä segmenttejä, jotka sisältävät vähemmän kuin 100 asiakasprofiilia. 
- Vieminen RollWorksiin rajoittuu segmentteihin.
- Enintään 250 000 asiakasprofiilin vieminen RollWorksiin voi kestää 10 minuuttia. 
- RollWorksiin vietävien asiakasprofiilien määrä riippuu RollWorks-sopimuksestasi ja sen sisältämistä rajoituksista.

## <a name="set-up-connection-to-rollworks"></a>Määritä yhteys RollWorksiin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **RollWorks**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Alusta yhteys RollWorksiin valitsemalla **Yhdistä**.

1. Valitse **Todenna RollWorksin avulla** ja anna RollWorksin järjestelmänvalvojan tunnistetiedot.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys RollWorks-osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Anna **RollWorks-mainostajatunnus** [RollWorks-mainostettava](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta. RollWorksiin pitää viedä segmenttejä.

1. Valitse segmentit, jotka haluat viedä. Valitse segmentti, jossa on vähintään 100 jäsentä. Pienempiä segmenttejä ei voi viedä. Lisäksi vietävän segmentin enimmäiskoko on 250 000 jäsentä per vienti. 

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun otat tietojen siirron käyttöön Dynamics 365 Customer Insightsista RollWorksiin, sallit tietojen siirtämisen Dynamics 365 Customer Insightsin vaatimustenmukaisuuden rajojen ulkopuolelle, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilötiedot. Microsoft siirtää nämä tiedot ohjeesi mukaisesti, mutta olet vastuussa siitä, että RollWorks täyttää mahdolliset tietosuoja- tai tietoturvavelvollisuudet. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.
