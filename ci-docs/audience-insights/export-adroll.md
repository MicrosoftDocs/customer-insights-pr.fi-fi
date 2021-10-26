---
title: Customer Insightsin tietojen vieminen AdRolliin
description: Tietoja yhteyden määrittämisestä ja viennistä AdRolliin.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f9373ea18e77723c988392a5a2959baa66d8eae9
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617332"
---
# <a name="export-segments-to-adroll-preview"></a>Segmenttien vieminen AdRolliin (esiversio)

Vie yhtenäisten asiakasprofiilien segmentit AdRolliin ja käytä niitä mainostarkoituksiin. 

## <a name="prerequisites-for-a-connection"></a>Yhteyden edellytykset

-   [AdRoll-tili](https://www.adroll.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
-   Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Voit viedä kerralla enintään 250 000 asiakasprofiilia AdRolliin.
- AdRolliin ei voi viedä segmenttejä, jotka sisältävät vähemmän kuin 100 asiakasprofiilia. 
- AdRoll-vienti on rajoitettu segmentteihin.
- Enintään 250 000 asiakasprofiilin vieminen AdRolliin voi kestää 10 minuuttia. 
- AdRolliin vietävien asiakasprofiilien määrä riippuu sopimuksestasi AdRollin kanssa.

## <a name="set-up-connection-to-adroll"></a>Määritä yhteys AdRolliin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **AdRoll**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Käynnistä AdRoll-yhteys valitsemalla **Yhdistä**.

1. Valitse **Todenna AdRollin avulla** ja anna AdRoll-tunnistetiedot. 

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys AdRoll-osasta. Jos et näe tämän osan nimeä, nämä yhteystyypit eivät ole käytettävissä.

1. Syötä **AdRoll-mainostajan tunnus**. Lisätietoja on kohdassa [AdRoll-mainostajien profiilit](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta. Segmenttejä on vietävä AdRolliin.

1. Valitse segmentit, jotka haluat viedä. Valitse segmentti, jossa on vähintään 100 jäsentä. Pienempiä segmenttejä ei voi viedä. Lisäksi vietävän segmentin enimmäiskoko on 250 000 jäsentä per vienti. 

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. 

Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys AdRolliin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että AdRoll noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.
