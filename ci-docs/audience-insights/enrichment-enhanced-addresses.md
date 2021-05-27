---
title: Osoitteiden parannuksen rikastus
description: Rikasta ja normalisoi asiakasprofiilien osoitetietoja Microsoftin malleilla.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965574"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Asiakasprofiilien rikastaminen parannetuilla osoitteilla

Tietojen osoitteet voivat olla rakenteettomia, epätäydellisiä tai virheellisiä. Microsoftin mallien avulla voit normalisoida ja rikastaa osoitteita [Common Data Model -muotoon](/common-data-model/schema/core/applicationcommon/address) tarkkuuden ja merkityksellisten tietojen parantamiseksi.

## <a name="how-we-enhance-addresses"></a>Miten parannamme osoitteita

Mallimme käy läpi kaksivaiheisen prosessin osoitteen parantamiseksi. Ensinnäkin se jäsentää osoitteen tunnistaakseen sen komponentit ja asettaa ne jäsenneltyyn muotoon. Sitten käytämme tekoälyä osoitteen arvojen korjaamiseen, täydentämiseen ja standardointiin.

### <a name="example"></a>Esimerkiksi

Osoitetiedot saattavat olla epästandardissa muodossa ja sisältää kirjoitusvirheitä. Malli voi korjata nämä ongelmat ja luoda yhdenmukaisia osoitteita yhtenäisiin asiakasprofiileihin.

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

Malli käyttää koneoppimiseen perustuvia tekniikoita osoitteiden parantamiseen. Vaikka käytämme korkeaa luottamuskynnystä, kun malli muuttaa syöttöarvoa 100%: n tarkkuutta ei taata, kuten ei missään koneoppimismallissa.

## <a name="supported-countries-or-regions"></a>Tuetut maat tai alueet

Tuemme tällä hetkellä rikastavia osoitteita näissä maissa tai näillä alueilla: 

- Australia
- Kanada
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
   > Maa tai alue on pakollinen sekä yhden että usean määritteen osoitteessa. Osoitteita, jotka eivät sisällä kelvollisia tai tuettuja maan tai alueen arvoja, ei rikasteta

1.  Yhdistä yhdistetyn asiakasentiteetin osoitekentät.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Parannetun osoitteen kenttien yhdistämissivu.":::

1. Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**.

1. Anna rikastuksen ja tulosentiteetin nimi.

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.

## <a name="enrichment-results"></a>Rikastamisen tulokset

Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**. Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana. Käsittelyaika riippuu asiakastietojen koosta.

Kun rikastamisprosessi on valmis, voit tarkastella juuri rikastettujen asiakasprofiilien tietoja valitsemalla **Omat rikastukset**. Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.

Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.

## <a name="next-steps"></a>Seuraavat vaiheet

Voit hyödyntää rikastettuja asiakastietoja. Voit antaa asiakkaille mukautettuja kokemuksia luomalla [segmenttejä](segments.md) ja [mittoja](measures.md) sekä [viemällä tietoja](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
