---
title: Customer Insightsin tietojen vieminen Autopilotiin
description: Tietoja yhteyden määrittämisestä Autopilotiin.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269234"
---
# <a name="connector-for-autopilot-preview"></a>Autopilot-yhdistin (esiversio)

Vie yhdistettyjen asiakasprofiilien segmentit Autopilotiin ja käytä niitä Autopilotin sähköpostimarkkinoinnissa. 

## <a name="prerequisites"></a>Edellytykset

-   [Autopilot-tili](https://www.autopilothq.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
-   Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="connect-to-autopilot"></a>Muodosta yhteys Autopilotiin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.

1. Valitse **Autopilot**-kohdassa **Määritä**.

1. Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Autopilot-yhteyden määritysruutu.":::

1. Anna **Autopilotin ohjelmointirajapinnan avain** [Autopilotin ohjelmointirajapinnan avain](https://autopilot.docs.apiary.io/#).

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Käynnistä Autopilot-yhteys valitsemalla **Yhdistä**.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Määritä vienti valitsemalla **Next**.

## <a name="configure-the-connector"></a>Yhdistimen määrittäminen

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa. Toimi samalla tavalla muiden valinnaisten kenttien osalta. Näitä kenttiä ovat esimerkiksi **Etunimi**, **Sukunimi**.

1. Valitse segmentit, jotka haluat viedä. On erittäin **suositeltavaa, että asiakastietueita viedään enintään 100 000** Autopilotiin. 

1. Valitse **Tallenna**.

## <a name="export-the-data"></a>Tietojen vieminen

Voit [viedä tietoja tarvittaessa](export-destinations.md). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Voit viedä yhteensä enintään 100 000 asiakasprofiilia Autopilotiin.
- Autopilot-vienti on rajoitettu segmentteihin.
- 100 000 profiilin vieminen Autopilotiin voi kestää muutaman tunnin. 
- Autopilotiin vietävien profiilien määrä määräytyy Autopilot-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Autopilotiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Autopilot noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]