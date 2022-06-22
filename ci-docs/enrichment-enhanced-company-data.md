---
title: Yritystietojen parantaminen
description: Rikasta ja normalisoi yritystietoja Microsoftin malleilla.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4247d59806468907d93fc7848231ec5a2985580e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953945"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Yritysprofiilien rikastaminen parannettujen yritystietojen avulla

Microsoftin mallien ja koottujen yritystietojen avulla voit korjata, täydentää ja standardoida yritysprofiileja. [Common Data Model -muotoa](/common-data-model/schema/core/applicationcommon/account) käytetään saamaan parempi tarkkuus ja oivallukset.

Voit myös [rikastaa yrityksen tietoja tietolähteissä](data-sources-enrichment.md), mikä parantaa vastaavuuksien tarkkuutta tietojen yhdistämisprosessissa.

Yhdysvaltalaisista osakeyhtiöistä on saatavilla tietoja, kuten tuotto, osakekurssi, toimiala ja muuta.  

## <a name="how-we-enhance-company-data"></a>Miten parannamme yritystietoja?

Mallimme käy läpi kaksivaiheisen prosessin, joka parantaa yrityksen profiilia. Ensin se normalisoi yrityksen nimen. Esimerkiksi *Microsoft Corp* korjataan ja standardoidaan arvoksi *Microsoft Corporation*. Se yrittää löytää vastineen Microsoftin kootuista yritystiedoista. Jos vastine löytyy, täydennämme yrityksen profiilia kerätyistä yritystiedoista yrityksen nimi mukaan lukien.

### <a name="example"></a>Esimerkiksi

Yrityksesi tiedot eivät ehkä ole vakiomuodossa ja sisältävät kirjoitusvirheitä. Malli yrittää korjata nämä ongelmat ja luoda yhdenmukaisia tietoja.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Rajoitukset

Malli ei:

- Yrityksen identiteetin vahvistaminen. Syötettä ei tarkisteta aiemmin luodun organisaation osalta tai sen osalta, käyttääkö yritys tulostetta vakionimenä.
- Yritysten täysi kattavuus maailmanlaajuisesti. Microsoftin koottujen yritystietojen kattavuus on globaali, mutta se tarjoaa parhaan kattavuuden Australiassa, Kanadassa, Yhdistyneessä kuningaskunnassa ja Yhdysvalloissa.
- Standardoi yritysten osoitteet maailmanlaajuisesti. Tällä hetkellä osoitteiden standardisoimista tuetaan seuraavissa maissa ja seuraavilla alueilla: Australia, Kanada, Ranska, Saksa, Italia, Japani, Yhdistynyt kuningaskunta ja Yhdysvallat.
- Takuu tietojen täsmällisyydestä tai tuoreudesta. Liiketoimintatiedot muuttuvat usein, emmekä voi taata, että parannetut yritystiedot ovat aina täsmälliset tai ajan tasalla.

## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.

1. Valitse **Rikasta tiedot** **Parannetut yritystiedot** -ruudussa.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Yritystietojen rikastuskeskuksen rikastusruutu.":::

1. Tutustu yleiskatsaukseen ja valitse **Seuraava**.

1. Valitse ensin **Asiakkaan tietojoukko** ja sitten rikastettava profiili tai segmentti. *Asiakas*-entiteetti rikastaa kaikkia asiakasprofiileja, kun taas segmentti rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

1. Valitse, mitä yritysprofiilien kenttätyyppejä käytetään vastaavuuden etsimiseen Microsoftin koottujen yritystietojen kanssa. Valinta vaikuttaa seuraavassa vaiheessa käytettävissä oleviin yhdistämiskenttiin.

1. Valitse **Seuraava**.

1. Yhdistä yrityksen kentät Microsoftin yritystietoihin. Vastaavuutta voi parantaa lisäämällä muita kenttiä.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Tietojen yhdistämisvaihe yritystietojen rikastusta määritettäessä.":::

1. Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**.

1. Anna **Nimi** rikastusta ja **Tulosentiteettiä** varten.

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.

1. Aloita rikastamisprosessi valitsemalla **Suorita** tai sulje ja palaa **Rikastukset**-sivulle.

## <a name="enrichment-results"></a>Rikastamisen tulokset

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Yleiskatsauskortti

**Asiakkaiden muutosten yleiskuvaus** -ruudussa on tietoja rikastamisen kattavuudesta.

- **Käsitellyt ja muuttuneet yritykset**: niiden asiakasyritysprofiilien määrä, joiden rikastaminen onnistui.
- **Käsitellyt mutta muuttumattomat yritykset**: Niiden asiakasyritysprofiilien määrä, jotka tunnistettiin mutta joita ei muutettu. Tämä tapahtuu yleensä, kun syötetiedot ovat kelvolliset eikä niitä voi parantaa rikastamalla.
- **Yritykset, joita ei ole käsitelty eikä muutettu**: Niiden asiakasyritysprofiilien määrä, joita ei tunnistettu. Tämä tapahtuu yleensä, kun syötetiedot eivät kelpaa tai niiden rikastamista ei tueta.

## <a name="next-steps"></a>Seuraavat vaiheet

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
