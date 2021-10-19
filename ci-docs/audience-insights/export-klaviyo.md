---
title: Customer Insights -tietojen vieminen Klaviyo-ratkaisuun
description: Lisätietoja yhteyden ja viennin määrittämisestä Klaviyo-ratkaisuun.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7c1297fd5381c00c07d6501186c51fe4798773d1
ms.sourcegitcommit: 205f931ec671a0ab1850f2c1c94df3307ffb62c9
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/13/2021
ms.locfileid: "7385784"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Segmenttiluetteloiden vieminen Klaviyoon (esikatselu)

Vie yhdistettyjen asiakasprofiilien segmentit Klaviyo-ratkaisuun ja käytä niitä markkinointiaktiviteeteissa.

## <a name="prerequisites"></a>Edellytykset

-   Sinulla on [Klaviyo-tili](https://www.klaviyo.com/) ja vastaavat järjestelmänvalvojan valtuustiedot.
-   Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Voit viedä 100 000 profiilia viennissä Klaviyoon.
- Vieminen Klaviyo-ratkaisuun on rajoitettu segmentteihin.
- 1 miljoonan profiilin vieminen Klaviyoon voi kestää 20 minuuttia. 
- Klaviyo-ratkaisuun vietävien profiilien enimmäismäärä riippuu Klaviyo-ratkaisuun liittyvästä sopimuksesta.

## <a name="set-up-connection-to-klaviyo"></a>Määritä yhteys Klaviyoon

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Määritä yhteys valitsemalla **Lisää yhteys**. Valitse lopuksi **Klaviyo**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Jatka sisäänkirjautumista antamalla [Klaviyon API-avain](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys). 

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Valitse **Muodosta yhteys** ja muodosta yhteys Klaviyo-ratkaisuun.

1. Valitse **Todenna Klaviyolla** ja anna Klaviyon järjestelmänvalvojan tunnistetiedot.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Klaviyo-osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Syötä [**Klaviyo-luettelon tunnus**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa. Segmenttien vieminen Klaviyo-ratkaisuun on pakollista.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun otat käyttöön Dynamics 365 Customer Insightsin tietojen siirtämiseksi Klaviyo-ratkaisuun, sallit tietojen siirtämisen säännöstenmukaisuuden rajan ulkopuolelle Dynamics 365 Customer Insightsissa, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilökohtaiset tiedot. Microsoft siirtää nämä tiedot pyyntösi mukaisesti, mutta olet vastuussa siitä, että Klaviyo täyttää kaikki liiketoimintaasi koskevat tietosuoja- tai tietoturvavelvoitteet. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.