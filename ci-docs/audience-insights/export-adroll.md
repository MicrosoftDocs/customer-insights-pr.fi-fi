---
title: Customer Insightsin tietojen vieminen AdRolliin
description: Tietoja yhteyden määrittämisestä AdRolliin.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697070"
---
# <a name="connector-for-adroll-preview"></a>AdRoll-yhdistin (esiversio)

Vie yhtenäisten asiakasprofiilien segmentit AdRolliin ja käytä niitä mainostarkoituksiin. 

## <a name="prerequisites"></a>Edellytykset

-   [AdRoll-tili](https://www.adroll.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
-   Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="connect-to-adroll"></a>Muodosta yhteys AdRolliin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.

1. Valitse **AdRoll**-kohdassa **Määritä**.

1. Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="AdRoll-yhteyden määritysruutu.":::

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Käynnistä AdRoll-yhteys valitsemalla **Yhdistä**.

1. Valitse **Todenna AdRollin avulla** ja anna AdRoll-tunnistetiedot. 

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Anna **AdRoll-mainostajatunnuksesi** [AdRoll-mainostettava](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Määritä vienti valitsemalla **Next**.

## <a name="configure-the-connector"></a>Yhdistimen määrittäminen

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa. Segmenttejä on vietävä AdRolliin.

1. Valitse segmentit, jotka haluat viedä. Valitse segmentti, jossa on vähintään 100 jäsentä. Pienempiä segmenttejä ei voi viedä. Lisäksi vietävän segmentin enimmäiskoko on 250 000 jäsentä per vienti. 

1. Valitse **Tallenna**.

## <a name="export-the-data"></a>Tietojen vieminen

Voit [viedä tietoja tarvittaessa](export-destinations.md). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Voit viedä yhteensä enintään 250 000 asiakasprofiilia per vienti AdRolliin.
- Alle 100 profiilin segmenttejä ei voi viedä AdRolliin. 
- AdRoll-vienti on rajoitettu segmentteihin.
- Jopa 250 000 profiilin vieminen AdRolliin voi kestää 10 minuuttia. 
- AdRolliin vietävien profiilien määrä määräytyy AdRoll-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys AdRolliin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että AdRoll noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.
