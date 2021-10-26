---
title: Customer Insights -tietojen vieminen Constant Contactiin
description: Tietoja yhteyden määrittämisestä ja viennistä Constant Contactiin.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b25e4f11e21d059c2d867e925c0ae5635a87addc
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/08/2021
ms.locfileid: "7619115"
---
# <a name="export-segments-to-constant-contact-preview"></a>Segmenttien vieminen Constant Contactiin (esiversio)

Vie yhtenäisten asiakasprofiilien segmentit Constant Contactiin ja käytä niitä markkinointiaktiviteetteihin. 

## <a name="prerequisites-for-a-connection"></a>Yhteyden edellytykset

-   Sinulla on [Constant Contact -tili](https://www.constantcontact.com/account-home) ja sitä vastaavat järjestelmänvalvojan tunnistetiedot.
-   Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Voit viedä vientiä kohden enintään miljoona asiakasprofiilia Constant Contactiin.
- Vieminen Constant Contactiin rajoittuu segmentteihin.
- Enintään yhden miljoonan asiakasprofiilin vieminen Constant Contactiin voi kestää tunnin. 
- Constant Contactiin vietävien asiakasprofiilien määrä riippuu Constant Contact -sopimuksestasi ja sen sisältämistä rajoituksista.

## <a name="set-up-connection-to-constant-contact"></a>Constant Contact -yhteyden määrittäminen

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Constant Contact**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Alusta yhteys Constant Contactiin valitsemalla **Yhdistä**.

1. Valitse **Todenna vakioyhteyshenkilöllä** ja anna vakioyhteyshenkilön järjestelmänvalvojan tunnistetiedot. 

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Constant Contact -osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Anna [**Constant Contact -luettelon tunnus**](https://app.constantcontact.com/pages/contacts/ui#lists). Avaa luettelo Constant Contactissa, jotta löydät luettelon tunnuksen URL-osoitteesta.

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta. Constant Contactiin pitää viedä segmenttejä.

1. Vaihtoehtoisesti voit viedä Etunimi- ja Sukunimi-kentät lisäkenttinä, joiden avulla sähköposteja voidaan mukauttaa. Yhdistä nämä kenttä valitsemalla **Lisää määrite**.

1. Valitse segmentit, jotka haluat viedä.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun otat tietojen siirron käyttöön Dynamics 365 Customer Insightsista Constant Contactiin, sallit tietojen siirtämisen Dynamics 365 Customer Insightsin vaatimustenmukaisuuden rajojen ulkopuolelle, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilötiedot. Microsoft siirtää nämä tiedot ohjeesi mukaisesti, mutta olet vastuussa siitä, että Constant Contact täyttää mahdolliset tietosuoja- tai tietoturvavelvollisuudet. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.
