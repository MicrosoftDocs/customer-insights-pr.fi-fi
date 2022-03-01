---
title: Osoitteen parannusten rikastus (sisältää videon)
description: Rikasta ja normalisoi asiakasprofiilien osoitetietoja Microsoftin malleilla.
ms.date: 12/16/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: afb1a6b4805702697889bb91ca36a96a714cba3d
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934919"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Asiakasprofiilien rikastaminen parannetuilla osoitteilla

Tietojen osoitteet voivat olla rakenteettomia, epätäydellisiä tai virheellisiä. Microsoftin mallien avulla voit normalisoida ja rikastaa osoitteita [Common Data Model -muotoon](/common-data-model/schema/core/applicationcommon/address) tarkkuuden ja merkityksellisten tietojen parantamiseksi.

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

Parannetut osoitteet toimivat vain niiden arvojen kanssa, joka ovat jo olemassa käsitellyissä osoitetiedoissa. Malli ei: 

1. Tarkista, onko osoite kelvollinen osoite.
2. Tarkista, onko mitkään arvoista, kuten postinumerot tai katujen nimet, kelvollisia.
3. Muuta arvoja, joita se ei tunnista.

Malli käyttää koneoppimiseen perustuvia tekniikoita osoitteiden parantamiseen. Käytössä on korkea luotettavuusraja. Se tarkoittaa sitä, että kun mallin syöttöarvo muuttuu, kuten missä tahansa koneoppimiseen perustuvassa mallissa, 100 prosentin tarkkuutta ei taata.

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

Osoitteissa on oltava maa- tai aluearvo. Emme käsittele osoitteita maille tai alueille, joita ei tueta, eikä osoitteille, joille ei ole annettu maata tai aluetta.

## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Siirry kohtaan **Tiedot** > **Täydentäminen**.

1. Valitse **Rikasta tietojani** **Rikasta osoitteita** -ruudussa.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Näyttökuva Parannetut osoitteet -ruudusta.":::

1. Valitse **Asiakkaan tietojoukko** ja valitse entiteetti, joka sisältää rikastettavat osoitteet. Voit valita *Asiakas*-entiteetin rikastaaksesi kaikkien asiakasprofiiliesi osoitteita, tai valita segmenttientiteetin rikastaaksesi osoitteita vain segmentin sisältämissä asiakasprofiileissa.

1. Valitse, kuinka osoitteet muotoillaan tietojoukossa. Valitse **Yksimääritteinen osoite**, jos tietojen osoitteet käyttävät yhtä kenttää. Valitse **Monimääritteinen osoite**, jos tietojen osoitteet käyttävät useampaa kuin yhtä kenttää.

   > [!NOTE]
   > Maa ja alue ovat pakollisia sekä yhden määritteen että useiden määritteiden osoitteissa. Osoitteita, jotka eivät sisällä kelvollisia tai tuettuja maan tai alueen arvoja, ei rikasteta.

1.  Yhdistä yhdistetyn asiakasentiteetin osoitekentät.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Parannetun osoitteen kenttien yhdistämissivu.":::

1. Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**.

1. Anna rikastuksen ja tulosentiteetin nimi.

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.

## <a name="enrichment-results"></a>Rikastamisen tulokset

Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**. Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana. Käsittelyaika riippuu asiakastietojen koosta.

Kun rikastamisprosessi on valmis, voit tarkastella juuri rikastettujen asiakasprofiilien tietoja valitsemalla **Omat rikastukset**. Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.

Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.

### <a name="overview-card"></a>Yleiskatsauskortti

Yleiskatsauskortissa on tietoja rikastamisen kattavuudesta. 

* **Käsitellyt ja muuttuneet asiakkaat**: niiden asiakasprofiilien määrä, joiden rikastaminen onnistui.

* **Käsitellyt mutta muuttumattomat asiakkaat**: Niiden asiakasprofiilien määrä, jotka tunnistettiin mutta joita ei muutettu. Tämä tapahtuu yleensä, kun syötetiedot ovat kelvolliset eikä niitä voi parantaa rikastamalla.

* **Asiakkaita ei ole käsitelty eikä muutettu**: Niiden profiilien määrä, joita ei tunnistettu. Kyse on yleensä siitä, että syötetiedot eivät kelpaa tai niiden rikastamista ei tueta.

## <a name="next-steps"></a>Seuraavat vaiheet

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
