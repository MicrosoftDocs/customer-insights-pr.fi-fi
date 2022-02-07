---
title: Yritystietojen parantaminen
description: Rikasta ja normalisoi yritystietoja Microsoftin malleilla.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
---

# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Yritysprofiilien rikastaminen parannettujen yritystietojen avulla

Microsoftin mallien ja koottujen yritystietojen avulla voit korjata, täydentää ja standardoida yritysprofiileja. [Common Data Model -muotoa](/common-data-model/schema/core/applicationcommon/account) käytetään saamaan parempi tarkkuus ja oivallukset.

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

Parannettuihin tietoihin liittyy joitakin rajoituksia. Malli ei tue alla olevassa luettelossa olevia kohteita.

1.  Yrityksen identiteetin vahvistaminen. Syötettä ei tarkisteta aiemmin luodun organisaation osalta tai sen osalta, käyttääkö yritys tulostetta vakionimenä.
2.  Yritysten täysi kattavuus maailmanlaajuisesti. Microsoftin koottujen yritystietojen kattavuus on globaali, mutta se tarjoaa parhaan kattavuuden Australiassa, Kanadassa, Yhdistyneessä kuningaskunnassa ja Yhdysvalloissa.
3.  Standardoi yritysten osoitteet maailmanlaajuisesti. Tällä hetkellä osoitteiden standardisoimista tuetaan seuraavissa maissa ja seuraavilla alueilla: Australia, Kanada, Ranska, Saksa, Italia, Japani, Yhdistynyt kuningaskunta ja Yhdysvallat.
4.  Takuu tietojen täsmällisyydestä tai tuoreudesta. Liiketoimintatiedot muuttuvat usein, emmekä voi taata, että parannetut yritystiedot ovat aina täsmälliset tai ajan tasalla.

## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Siirry kohtaan **Tiedot** > **Täydentäminen**.

1. Valitse **Rikasta tiedot** **Parannetut yritystiedot** -ruudussa.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Yritystietojen rikastuskeskuksen rikastusruutu.":::

1. Valitse **Asiakkaan tietojoukko** ja valitse entiteetti, joka sisältää rikastettavat osoitteet. Voit valita *Asiakas*-entiteetin rikastaaksesi kaikkien asiakasprofiiliesi osoitteita, tai valita segmenttientiteetin rikastaaksesi osoitteita vain segmentin sisältämissä asiakasprofiileissa.

1. Valitse, minkä tyyppisiä kenttiä yritysprofiileistasi tulisi käyttää vastaavuuden etsimiseen Microsoftin koottujen yritystietojen kanssa. Valinta vaikuttaa seuraavassa vaiheessa käytettävissä oleviin yhdistämiskenttiin.

1.  Yhdistä yrityskentät yhdistetystä asiakasentiteetistä. Mitä enemmän avaintunnuksia ja kenttiä yhdistät, sitä todennäköisempää on, että vastineiden määrä on parempi.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Tietojen yhdistämisvaihe yritystietojen rikastusta määritettäessä.":::

1. Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**.

1. Anna rikastuksen ja tulosentiteetin nimi.

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.

## <a name="enrichment-results"></a>Rikastamisen tulokset

Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**. Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana. Käsittelyaika riippuu asiakastietojen koosta.

Kun rikastamisprosessi on valmis, voit tarkastella juuri rikastettujen asiakasprofiilien tietoja valitsemalla **Omat rikastukset**. Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.

**Rikastetut asiakkaat -esikatseluruudussa** näkyy näyte rikastetuista tiedoista. Valitse **Näytä lisää** ja valitse **Tiedot**-välilehti, jos haluat tarkastella kunkin rikastetun profiilin yksityiskohtaista näkymää.

### <a name="overview-card"></a>Yleiskatsauskortti

Yleiskatsauskortissa on tietoja rikastamisen kattavuudesta. 

* **Käsitellyt ja muuttuneet yritykset**: niiden asiakasyritysprofiilien määrä, joiden rikastaminen onnistui.

* **Käsitellyt mutta muuttumattomat yritykset**: Niiden asiakasyritysprofiilien määrä, jotka tunnistettiin mutta joita ei muutettu. Tämä tapahtuu yleensä, kun syötetiedot ovat kelvolliset eikä niitä voi parantaa rikastamalla.

* **Yritykset, joita ei ole käsitelty eikä muutettu**: Niiden asiakasyritysprofiilien määrä, joita ei tunnistettu. Tämä tapahtuu yleensä, kun syötetiedot eivät kelpaa tai niiden rikastamista ei tueta.

## <a name="next-steps"></a>Seuraavat vaiheet

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
