---
title: Customer Insightsin tietojen vieminen Marketoon
description: Tietoja yhteyden määrittämisestä ja viennistä Marketoon.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0d5eaa769973c861d89287bba0ed29509ab2efc653bdd8e177cc49b3560c698e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033489"
---
# <a name="export-segments-to-marketo-preview"></a>Segmenttien vieminen Marketoon (esiversio)

Viemällä yhtenäisten asiakasprofiilien segmenttejä voit luoda kampanjoita, tuottaa sähköpostimarkkinointia ja käyttää tiettyjä asiakasryhmiä Marketon avulla.

## <a name="prerequisites-for-connection"></a>Yhteyden edellytykset

-   [Marketo-tili](https://login.marketo.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
-   Marketossa on aiemmin luotuja luetteloja ja vastaavia tunnuksia. Lisätietoja on kohdassa [Marketo-luettelot](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   [Segmentit on määritetty](segments.md).
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään 1 miljoona profiilia kussakin Marketo-viennissä.
- Marketo-vienti on rajoitettu segmentteihin
- Yhteensä 1 miljoonan profiilin segmenttien vienti voi kestää 3 tuntia. 
- Marketoon vietävien profiilien määrä määräytyy Marketo-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.

## <a name="set-up-connection-to-marketo"></a>Määritä yhteys Marketoon

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Marketo**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna **[Marketon asiakastunnus, asiakasohjelman salasana ja REST-päätepisteen isäntänimi](https://developers.marketo.com/rest-api/authentication/)**. REST-päätepisteen hostname on vain isäntänimi ilman `https://`. Esimerkki: `xyz-abc-123.mktorest.com`. 

1. Vahvista **Tietojen yksityisyys ja vaatimustenmukaisuus** valitsemalla **Hyväksyn** ja käynnistä Marketo-yhteys valitsemalla **Yhdistä**.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Marketo-osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Syötä **[Marketo-luettelon tunnus](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**. Luettelon tunnus on pelkästään numeerinen arvo. Jos esimerkiksi Marketo-luettelon tunnus on ST12345A7, poista merkki numeroiden edestä ja jäljestä ja kirjoita `12345`. 

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa. 

1. Voit myös viedä **etunimen**, **sukunimen**, **paikkakunnan**, **osavaltion** ja **maan/alueen** yksilöllisempien sähköpostiviestien luomiseksi. Yhdistä nämä kenttä valitsemalla **Lisää määrite**.

1. Valitse segmentit, jotka haluat viedä. Voit viedä yhteensä enintään 1 000 000 asiakasprofiilia Marketoon.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). Marketon segmentit ovat nyt [Marketo-luetteloissa](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Marketoon otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Marketo noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
