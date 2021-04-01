---
title: Customer Insightsin tietojen vieminen DotDigitaliin
description: Tietoja yhteyden määrittämisestä DotDigitaliin.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598013"
---
# <a name="connector-for-dotdigital-preview"></a>DotDigital-yhdistin (esiversio)

Vie yhtenäistettyjen asiakasprofiilien segmentit DotDigital-osoitekirjoihin ja käytä niitä kampanjoissa, sähköpostimarkkinoinnissa ja asiakassegmenttien muodostamisessa DotDigitalin kanssa. 

## <a name="prerequisites"></a>Edellytykset

-   [DotDigital-tili](https://dotdigital.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
-   DotDigitalissa on aiemmin luotuja osoitekirjoja ja vastaavia tunnuksia. Tunnus saadaan URL-osoitteesta, kun valitset ja avaat osoitekirjan. Lisätietoja on kohdassa [DotDigital-osoitekirjat](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="connect-to-dotdigital"></a>Yhdistäminen DotDigitaliin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.

1. Valitse **DotDigital**-kohdassa **Määritä**.

1. Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="DotDigital-viennin määritysruutu":::

1. Anna **DotDigitalin käyttäjänimi ja salasana**.

1. Anna **[DotDigital-osoitekirjan tunnus](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Käynnistä DotDigital-yhteys valitsemalla **Yhdistä**.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Määritä vienti valitsemalla **Next**.

## <a name="configure-the-connector"></a>Yhdistimen määrittäminen

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa. Toimi samalla tavalla muiden valinnaisten kenttien osalta. Näitä kenttiä ovat esimerkiksi **Etunimi**, **Sukunimi**, **Koko nimi**, **Sukupuoli** ja **Postinumero**.

1. Valitse segmentit, jotka haluat viedä. Voit viedä yhteensä enintään 1 000 000 asiakasprofiilia DotDigitaliin.

1. Valitse **Tallenna**.

## <a name="export-the-data"></a>Tietojen vieminen

Voit [viedä tietoja tarvittaessa](export-destinations.md). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä. DotDigitalissa voi etsiä nyt segmenttejä [DotDigital-osoitekirjoissa](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään 1 miljoona profiilia kussakin DotDigital-viennissä.
- DotDigital-vienti on rajoitettu segmentteihin.
- Yhteensä 1 miljoonan profiilin segmenttien vienti voi kestää 3 tuntia palveluntoimittajan rajoitusten vuoksi. 
- DotDigitaliin vietävien profiilien määrä määräytyy DotDigital-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys DotDigitaliin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että DotDigital noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]