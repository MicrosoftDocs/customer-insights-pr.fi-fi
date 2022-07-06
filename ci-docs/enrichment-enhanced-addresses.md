---
title: Asiakasprofiilien rikastaminen parannettujen osoitteiden avulla (sisältää videon)
description: Rikasta ja normalisoi asiakasprofiilien osoitetietoja Microsoftin malleilla.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080969"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>Asiakasprofiilien rikastaminen parannettujen osoitteiden avulla

Tietojen osoitteet voivat olla rakenteettomia, epätäydellisiä tai virheellisiä. Microsoftin mallien avulla voit normalisoida ja rikastaa osoitteita [Common Data Model -muotoon](/common-data-model/schema/core/applicationcommon/address) tarkkuuden ja merkityksellisten tietojen parantamiseksi.

Voit myös [rikastaa osoitteita tietolähteissä](data-sources-enrichment.md), mikä parantaa vastaavuuksien tarkkuutta tietojen yhdistämisprosessissa. 

## <a name="how-we-enhance-addresses"></a>Miten parannamme osoitteita

Mallimme käy läpi kaksivaiheisen prosessin osoitteen parantamiseksi. Ensinnäkin se jäsentää osoitteen tunnistaakseen sen komponentit ja asettaa ne jäsenneltyyn muotoon. Tämän jälkeen osoitteen arvot voi korjata, määrittää valmiiksi ja standardisoida tekoälyn avulla.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Esimerkiksi

Osoitetiedot voivat olla muussa kuin standardimuodossa. Niissä voi myös olla kirjoitusvirheitä. Malli voi korjata nämä ongelmat ja luoda yhdenmukaisia osoitteita yhtenäisiin asiakasprofiileihin.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Rajoitukset

Parannettuja osoitteita voi käyttää vain käsitellyissä tiedoissa jo olevien arvojen kanssa. Malli ei:

1. Tarkista, onko osoite kelvollinen osoite.
2. Tarkista, onko mitkään arvoista, kuten postinumerot tai katujen nimet, kelvollisia.
3. Muuta arvoja, joita se ei tunnista.

Malli käyttää koneoppimiseen perustuvia tekniikoita osoitteiden parantamiseen. Samoin kuin muissa koneoppimiseen perustuvissa malleissa, täydellistä tarkkuutta ei voi taata.

## <a name="supported-countries-or-regions"></a>Tuetut maat tai alueet

Tuemme tällä hetkellä rikastavia osoitteita näissä maissa tai näillä alueilla:

- Australia
- Kanada
- Ranska
- saksa
- Italia
- Japani
- Yhdistynyt kuningaskunta
- Yhdysvallat

## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.

1. Valitse **Rikasta tietojani** **Rikasta osoitteita** -ruudussa.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Näyttökuva Parannetut osoitteet -ruudusta.":::

1. Tutustu yleiskatsaukseen ja valitse **Seuraava**.

1. Valitse ensin **Asiakkaan tietojoukko** ja sitten rikastettava profiili tai segmentti. *Asiakas*-entiteetti rikastaa kaikkia asiakasprofiileja, kun taas segmentti rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

1. Valitse, kuinka osoitteet muotoillaan tietojoukossa. Valitse **Yksimääritteinen osoite**, jos tietojen osoitteet käyttävät yhtä kenttää. Valitse **Monimääritteinen osoite**, jos tietojen osoitteet käyttävät useampaa kuin yhtä kenttää.

1. Valitse **Seuraava** ja yhdistä yhtenäisestä asiakasentiteetistä saadut osoitekentät.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Parannetun osoitteen kenttien yhdistämissivu.":::

   > [!NOTE]
   > Maa ja alue ovat pakollisia sekä yhden määritteen että useiden määritteiden osoitteissa. Osoitteita, jotka eivät sisällä kelvollisia tai tuettuja maan tai alueen arvoja, ei rikasteta.

1. Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**.

1. Anna **Nimi** rikastusta ja **Tulosentiteettiä** varten.

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.

## <a name="view-enrichment-results"></a>Rikastamisen tulosten tarkasteleminen

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Rikastettujen asiakkaiden määrä kentän mukaan** antaa mahdollisuuden porautua kuhunkin rikastettuun kenttään.

### <a name="overview-card"></a>Yleiskatsauskortti

**Asiakkaiden muutosten yleiskuvaus** -kortissa on tietoja rikastamisen kattavuudesta:

- **Käsitellyt ja muuttuneet osoitteet**: niiden asiakasprofiilien määrä osoitteilla, joiden rikastaminen onnistui.
- **Käsitellyt mutta muuttumattomat osoitteet**: Niiden asiakasprofiilien määrä osoitteilla, jotka tunnistettiin mutta joita ei muutettu. Tämä tapahtuu yleensä, kun syötetiedot ovat kelvolliset eikä niitä voi parantaa rikastamalla.
- **Osoitteet, joita ei ole käsitelty eikä muutettu**: Niiden asiakasprofiilien määrä osoitteilla, joita ei tunnistettu. Kyse on yleensä siitä, että syötetiedot eivät kelpaa tai niiden rikastamista ei tueta.

## <a name="next-steps"></a>Seuraavat vaiheet

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
