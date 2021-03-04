---
title: Customer Insightsin tietojen vieminen Marketoon
description: Tietoja yhteyden määrittämisestä Marketoon.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267077"
---
# <a name="connector-for-marketo-preview"></a>Marketo-yhdistin (esiversio)

Viemällä yhtenäisten asiakasprofiilien segmenttejä voit luoda kampanjoita, tuottaa sähköpostimarkkinointia ja käyttää tiettyjä asiakasryhmiä Marketon avulla.

## <a name="prerequisites"></a>Edellytykset

-   [Marketo-tili](https://login.marketo.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
-   Marketossa on aiemmin luotuja luetteloja ja vastaavia tunnuksia. Lisätietoja on kohdassa [Marketo-luettelot](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   [Segmentit on määritetty](segments.md).
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="connect-to-marketo"></a>Yhteyden muodostaminen Marketoon

1. Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.

1. Valitse **Marketo**-kohdassa **Määritä**.

1. Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.

1. Anna **[Marketon asiakastunnus, asiakasohjelman salasana ja REST-päätepisteen isäntänimi](https://developers.marketo.com/rest-api/authentication/)**.

1. Anna **[Marketo-luettelon tunnus](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Vahvista **Tietojen yksityisyys ja vaatimustenmukaisuus** valitsemalla **Hyväksyn** ja käynnistä Marketo-yhteys valitsemalla **Yhdistä**.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Näyttökuva viennin Marketo-yhteydestä":::

1. Määritä vienti valitsemalla **Next**.

## <a name="configure-the-connector"></a>Yhdistimen määrittäminen

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa. 

1. Vaihtoehtoisesti voit viedä **Etunimi**-, **Sukunimi**-, **Kaupunki**-, **Osavaltio**- ja **Maa tai alue** -kentät lisäkenttinä, joiden avulla sähköposteja voidaan mukauttaa. Yhdistä nämä kenttä valitsemalla **Lisää määrite**.

1. Valitse segmentit, jotka haluat viedä. Voit viedä yhteensä enintään 1 000 000 asiakasprofiilia Marketoon.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Marketoon vietävien kenttien ja segmenttien valitseminen":::

1. Valitse **Tallenna**.

## <a name="export-the-data"></a>Tietojen vieminen

Voit [viedä tietoja tarvittaessa](export-destinations.md). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä. Marketon segmentit ovat nyt [Marketo-luetteloissa](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään 1 miljoona profiilia kussakin Marketo-viennissä.
- Marketo-vienti on rajoitettu segmentteihin
- Yhteensä 1 miljoonan profiilin segmenttien vienti voi kestää 3 tuntia. 
- Marketoon vietävien profiilien määrä määräytyy Marketo-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Marketoon otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Marketo noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]