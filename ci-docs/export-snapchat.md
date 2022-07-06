---
title: Segmenttien vieminen Snapchatiin (esiversio)
description: Tietoja yhteyden määrittämisestä ja viennistä Snapchatiin.
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: abe04cd1464c3f7df969da3c769329382d603d7e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051909"
---
# <a name="export-segments-to-snapchat-preview"></a>Segmenttien vieminen Snapchatiin (esiversio)

Vie yhtenäisten asiakasprofiilien segmentit Snapchatiin ja käytä niitä mainontaan. 

## <a name="prerequisites-for-a-connection"></a>Yhteyden edellytykset

-   Sinulla on [Snapchat-yritystili](https://business.snapchat.com/), [Snapchat-mainostili](https://ads.snapchat.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot. Ainakin organisaatiotilin jäsenyys ja tietyn mainostilin tietojen hallinta. 
-   Vähintään yksi käyttäjäryhmä Snapchatin käyttäjäryhmän hallinnassa, ja sen tyypin on oltava SAM (Snap Audience Match). 
-   Olet [määrittänyt segmenttejä](segments.md) Customer Insightsissa.
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Vieminen Snapchatiin rajoittuu segmentteihin.
- Enintään yhden miljoonan asiakasprofiilin vieminen Snapchatiin voi kestää 15 minuuttia. 

## <a name="set-up-connection-to-snapchat"></a>Määritä yhteys Snapchatiin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Snapchat**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Alusta yhteys Snapchatiin valitsemalla **Yhdistä**.

1. Valitse **Todenna Snapchatin avulla** ja anna Snapchatin järjestelmänvalvojan tunnistetiedot. 

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Snapchat-osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Anna [**Snapchat-segmentin tai käyttäjäryhmän tunnus**](https://businesshelp.snapchat.com/s/article/custom-audiences). Käyttäjäryhmän tunnus löytyy URL-osoitteesta sen jälkeen, kun käyttäjäryhmä on valittu Snapchatin käyttäjäryhmän hallinnassa. 

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta. Snapchatiin pitää viedä segmenttejä.

1. Valitse segmentit, jotka haluat viedä. 

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun otat tietojen siirron käyttöön Dynamics 365 Customer Insightsista Snapchatiin, sallit tietojen siirtämisen Dynamics 365 Customer Insightsin vaatimustenmukaisuuden rajojen ulkopuolelle, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilötiedot. Microsoft siirtää nämä tiedot ohjeesi mukaisesti, mutta olet vastuussa siitä, että Snapchat täyttää mahdolliset tietosuoja- tai tietoturvavelvollisuudet. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.
