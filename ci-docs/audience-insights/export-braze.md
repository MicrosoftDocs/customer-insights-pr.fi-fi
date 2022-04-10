---
title: Customer Insights -tietojen vieminen Brazeen
description: Tietoja Braze-yhteyden määrittämisestä ja viennistä siihen.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8d7cf95c1f157c771b2d655346464e5af03d73b9
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/31/2022
ms.locfileid: "8524160"
---
# <a name="export-segment-lists-to-braze-preview"></a>Segmenttiluetteloiden vieminen Brazeen (esiversio)

Vie unified customer profile -profiilien segmentit Brazeen ja käytä niitä markkinointiaktiviteetteihin.

## <a name="prerequisites"></a>edellytykset

-   Sinulla on [Braze-tili](https://www.braze.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
-   Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).
-   Viedyissä segmenteissä Unified Customer Profile -profiilit sisältävät kentän, joka vastaa sähköpostiosoitetta ja Braze-asiakastunnusta. 

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Vieminen Brazeen rajoittuu segmentteihin.
- Enintään yhden miljoonan asiakasprofiilin vieminen Brazeen voi kestää 40 minuuttia. 
- Brazeen vietävien asiakasprofiilien määrä riippuu Braze-sopimuksestasi ja sen sisältämistä rajoituksista.

## <a name="set-up-connection-to-braze"></a>Määritä yhteys Brazeen

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Braze**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Jatka kirjautumista antamalla [Braze-ohjelmointirajapinnan avain](https://www.braze.com/docs/api/basics/). 

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Valitse **Yhdistä**, jos haluat alustaa yhteyden Brazeen.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Braze-osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.  

3. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta, valitse Asiakastunnus-kentässä kenttä, joka vastaa asiakkaan Braze-tunnusta. Segmenttejä on vietävä Brazeen. Brazen segmentit luodaan samalla nimellä kuin kohteen Dynamics 365 Customer Insights segmenttikin. Voit valita muita valinnaisia kenttiä vastaavia tietoja varten. 

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Brazeen otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää tällaiset tiedot ohjeittesi mukaisesti, mutta olet vastuussa siitä, että Braze täyttää tietosuoja- ja tietoturvavaatimukset. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.
