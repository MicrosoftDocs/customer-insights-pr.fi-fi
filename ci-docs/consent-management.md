---
title: Asiakkaan suostumuksen käyttäminen
description: Asiakkaan Customer Insightsissa tekemien suostumusvalintojen noudattaminen tuomalla suostumustiedot.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 77b09b6eb0a916e724542d503d96d19c5581aca1
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/14/2022
ms.locfileid: "8947496"
---
# <a name="use-customer-consent"></a>Asiakkaan suostumuksen käyttäminen

Tietosuoja- ja tietoturvasäädökset antavat yksittäisille henkilöille oikeuden hallita tapaa, jolla organisaatiot käyttävät kyseisten henkilöiden henkilökohtaisia tietoja. Tällaisia säädöksiä ovat esimerkiksi Euroopan unionin yleinen tietosuoja-asetus ja Kalifornian kuluttajansuojalaki Yhdysvalloissa. Nämä säädökset antavat henkilöille mahdollisuuden kieltää sen, että kolmannet osapuolet keräävät, käsittelevät tai jakavat henkilötietoja.  

Asiakkaat voivat peruuttaa tietyntyyppisille yhteydenotoille annetun suostumuksen tai kieltää tällaiset yhteydenotot. He voivat myös pyytää, ettei heidän henkilötietojaan kerätä, tallenneta, käytetä tai myydä. On tärkeää, että organisaatio kunnioittaa asiakkaiden kaikkia suostumus- ja tietosuoja-asetuksia.  

Dynamics 365 Customer Insights auttaa kunnioittamaan asiakkaiden pyyntöjä tuomalla ja tallentamalla asiakkaiden asetukset yhdistettyjen asiakasprofiilien osana.

Jos suostumustiedot tallennetaan erillään asiakasprofiileista, [suostumustiedot lisätään uutena tietolähteenä](#import-and-unify-consent-data). Suostumustiedot sisältävät tietolähde lisätään tietojen yhdistämisprosessiin: Suostumustietojen ja asiakasprofiilien onnistunut yhdistäminen johtaa suostumustiedot sisältäviin yhdistettyihin asiakasprofiileihin. Jos asiakasprofiilit sisältävät jo suostumustiedot, voidaan siirtyä suoraan [suostumustietojen käyttöä](#use-consent-data) koskevaan osaan.

## <a name="prerequisites"></a>edellytykset

Suostumustietojen yhdistäminen muihin asiakasprofiileihin edellyttää, että seuraavat tiedot ovat käytettävissä lähdetiedoissa:

- Vaihtoehtoinen avain suostumustietojen yhdistämiseen Customer Insightsin asiakasprofiileihin. Kyse on esimerkiksi sähköpostiosoitteesta tai puhelinnumerosta.
- Suostumuksen arvo asiakkaan suostumustilan määrittämiseen.

Lisäksi kannattaa harkita seuraavien *valinnaisten* tietojen lisäämistä:

- Perusavain suostumuksen tilan päivittämistä varten, jos asiakas pyytää muutosta.
- Suostumuksen tyyppi, jos asiakastietoja voidaan käsitellä eri tavoin.
- Suostumuksen päivämäärä tai muut tietotyyppi, joilla on merkitystä suostumusskenaarioissa.

Esimerkki yksinkertaisesta suostumustietokannan taulukosta, jossa on useita suostumusvaihtoehtoja:

|Suostumuksen tunnus (perusavain)   |Sähköposti (vaihtoehtoinen avain)  |Suostumusvaihtoehto  |Suostumuksen arvo  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Uutiskirje       |  Epätosi       |
|2    |  holly@contoso.com       |  Tuotepäivitykset       |  Tosi       |
|3    |  frank@contoso.com       |  Uutiskirje       | Tosi        |
|4    |  frank@contoso.com       |  Tuotepäivitykset       |  Epätosi       |

## <a name="import-and-unify-consent-data"></a>Suostumustietojen tuominen ja yhdistäminen

Suostumustiedot tuodaan samalla tavalla kuin muitakin tietolähteitä käsitellään Customer Insightsiin. Lisätietoja tuetuista tietolähteistä ja niiden tuonnista on kohdassa [Tietolähteiden yleiskatsaus](data-sources.md).

Lisätietoja tietolähteiden yhdistämisestä on kohdassa [Tietojen yhdistämisen yleiskatsaus](data-unification.md).

## <a name="use-consent-data"></a>Suostumustietojen käyttö

Kun suostumustiedoista on tullut osa yhdistettyjä asiakasprofiileja, niitä voidaan käyttää Customer Insightsissa. Voidaan esimerkiksi luoda segmentti, jonka säännön avulla varmistaa, että asiakkaiden tietosuoja- ja tietoturva-asetuksia noudatetaan. Suostumusvalintoja tukevien sääntöjen avulla käyttäjiä voidaan jättää segmentin ulkopuolelle profiilimääritteiden perusteella. Segmenttiin lisätään sääntö, joka jättää segmentin ulkopuolelle asiakasprofiilit, jos ne eivät ole suostuneet yhteydenottoihin.

Edellä olevassa mallitaulukossa segmentissä olisi silloin seuraava sääntö: `Consent option=Newsletter & Consent value=True`. Tämän määrityksen tuloksena on segmentti, joka kunnioittaa yhteyshenkilön uutiskirjeen lähettämistä koskevaa valintaa.

Lisätietoja segmenttien muodostamisesta on kohdassa [Segmenttien luominen](segment-builder.md).

Kun segmentti on luotu, segmenttiä voi käyttää muissa sovelluksia käyttämällä sopivia [vientiasetuksia](export-destinations.md).

## <a name="ensure-updated-consent-status"></a>Suostumuksen tilan päivityksen varmistaminen

On tärkeää, että asiakkaiden suostumuksen tila pysyy päivitettynä. Customer Insightsin aikataulutettu päivitys tuo aina tietolähteiden viimeisimmän tilan. Nämä tiedot käsitellään tietojen yhdistämisessä ja tuloksena on päivitetyt asiakasprofiilit. Segmentit päivitetään sitten näiden päivitettyjen profiilien avulla, ja näin varmistetaan, että käsiteltävinä on viimeisimmät tiedot.

Toisin sanoen on siis varmistettava, että Customer Insightsiin tuotavat lähdetiedot sisältävät aina uusimmat tiedot.

Lisätietoja on kohdissa [Segmenttien manuaalinen päivitys](segments.md#refresh-segments) tai [Aikataulutetun päivityksen määrittäminen](system.md#schedule-tab).
