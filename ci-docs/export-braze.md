---
title: Segmenttien vieminen Brazeen (esiversio)
description: Tietoja Braze-yhteyden määrittämisestä ja viennistä siihen.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081108"
---
# <a name="export-segments-to-braze-preview"></a>Segmenttien vieminen Brazeen (esiversio)

Vie unified customer profile -profiilien segmentit Brazeen ja käytä niitä markkinointiaktiviteetteihin.

## <a name="prerequisites"></a>edellytykset

- Käytössä on [Braze-tili](https://www.braze.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
- [Brazessa on aiemmin luotuja segmenttejä](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Määritetyt segmentit](segments.md) Customer Insightsissa.
- Viedyissä segmenteissä Unified Customer Profile -profiilit sisältävät kentän, joka vastaa sähköpostiosoitetta ja Braze-asiakastunnusta.

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

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Braze-osasta. Jos tämä osa ei ole näkyvissä, tämän tyyppisiä yhteyksiä ei ole käytettävissä.  

1. Lisää raportin **näyttönimi**.

1. Lisää vietävän Braze-segmentin ohjelmointirajapinnan tunnus **Braze-segmentin ohjelmointirajapinnan tunnus** -kenttään. Tämä tunnus on segmentin tiedoissa Braze-ympäristössä.

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta. Valitse **Asiakastunnus**-kentässä kenttä, joka ilmaisee asiakkaan Braze-tunnuksen. Segmenttejä on vietävä Brazeen. Myös muita kenttiä voidaan valita.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Brazeen otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää tällaiset tiedot annettujen ohjeiden mukaisesti, mutta olet vastuussa siitä, että Braze täyttää tietosuoja- ja tietoturvavaatimukset. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.
