---
title: Asiakasprofiilien rikastaminen Microsoftin tuotemerkkien ja kiinnostuksen kohteiden tiedoilla (esiversio)
description: Käytä Microsoftin omistusoikeudellisia tietoja asiakastietojen rikastamisessa merkkimieltymyksillä ja osuudella kirjoituksista.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: e1827adca10a3b193c02a20c4abccacf73194a77
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081113"
---
# <a name="enrich-customer-profiles-with-brands-and-interests-data-from-microsoft-preview"></a>Asiakasprofiilien rikastaminen Microsoftin tuotemerkkien ja kiinnostuksen kohteiden tiedoilla (esiversio)

Käytä Microsoftin omistusoikeudellisia tietoja asiakastietojen rikastamisessa tuotemerkkimieltymyksillä, kiinnostuksen kohteilla ja osuudella kirjoituksista. Nämä mieltymykset ja osuus kirjoituksista perustuvat niiden henkilöiden tietoihin, jotka edustavat samanlaista väestöä kuin asiakkaasi. Näiden tietojen avulla saat lisätietoja asiakkaista ja voit segmentoida heidät mieltymysten tai kirjoitusten osuuksien perusteella tiettyihin tuotemerkkeihin ja kiinnostuksen kohteisiin.

## <a name="how-we-determine-affinities-and-sov"></a>Miten mieltymykset ja osuus kirjoituksista määritetään

Käytetään Microsoftin online-hakujen tietoja etsittäessä mieltymyksiä ja osuutta kirjoituksista tuotemerkeille ja kiinnostuksen kohteille eri demografissa segmenteissä (määritetään iän, sukupuolen tai sijainnin mukaan). Tuotemerkin tai kiinnostuksen kohteen online-hakujen määrä muodostaa perustan mieltymykselle tai osuudelle kirjoituksista. Kaikki kuitenkin määrittävät erilaisen näkökulman asiakkaiden ymmärtämiseen.

- Mieltymys on vertailukelpoinen eri demografisissa segmenteissä. Näiden tietojen avulla voit määrittää demografiset segmentit, joilla on korkein mieltymys tiettyä tuotemerkkiä tai kiinnostuksen kohdetta kohtaan muihin segmentteihin verrattuna.

- Osuus kirjoituksista o vertailukelpoinen valituissa tuotemerkeissä tai kiinnostuksen kohteissa. Voit käyttää näitä tietoja määrittäessäsi tuotemerkin tai kiinnostuksen kohteen, jolla on korkein osuus kirjoituksista tietyssä demografisessa segmentissä verrattuna muihin valitsemiisi tuotemerkkeihin tai kiinnostuksen kohteisiin.

## <a name="affinity-level-and-score"></a>Affiniteettitaso ja pistemäärä

Jokaisessa rikastetussa asiakasprofiilissa on kaksi toisiinsa liittyvää arvoa: affiniteettitaso ja affiniteettipisteet. Nämä arvot määrittävät, miten vahva tuotemerkin tai kiinnostuksen kohteen kyseisen profiilin demografisen segmentin affiniteetti on verrattuna muihin demografisiin segmentteihin.

*Affiniteettitaso* koostuu neljästä tasosta. *Affiniteettipisteet* lasketaan 100 pisteen aseteikolla, joka yhdistetään affiniteettitasoihin.

|Affiniteettitaso |Affiniteetin pistemäärä  |
|---------|---------|
|Erittäin korkea     | 85–100       |
|Suuri     | 70–84        |
|Keskikokoinen     | 35–69        |
|Matala     | 1–34        |

Affiniteettia mittaavan tarkkuuden mukaan voit käyttää affiniteettitasoa tai pistemäärää. Affiniteettipisteet antavat aiempaa tarkemman hallinnan.

## <a name="share-of-voice-sov"></a>Osuus kirjoituksista

Osuus kirjoituksista lasketaan 100 pisteen asteikolla. Jokaisen rikastetun asiakasprofiilin kaikkien tuotemerkkien ja kiinnostuksen kohteiden kokonaisosuus kirjoituksista on yhteensä 100. Toisin kuin mieltymykset, osuus kirjoituksista on suhteellinen valittuihin tuotemerkkeihin ja kiinnostuksen kohteisiin nähden. Esimerkiksi sanan 'Microsoft' arvot osuudelle kirjoituksista voi olla erilainen, jos valitut tuotemerkit ovat ('Microsoft', 'GitHub') ja ('Microsoft', 'LinkedIn').

## <a name="supported-countriesregions"></a>Tuetut maat ja alueet

Seuraavia maita ja alueita tuetaan tällä hetkellä: Australia, Kanada (englanti), Ranska, Saksa, Yhdistyneet kuningaskunta tai Yhdysvallat (englanti).

## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.

   - Tuotemerkkimieltymyksiä ja ääniosuuksien rikastus määritetään valitsemalla **Rikasta tiedot** **Tuotemerkit**-ruudussa.

   - Kiinnostuksen kohteiden mieltymyksiä ja ääniosuuksien rikastus määritetään valitsemalla **Rikasta tiedot** **Kiinnostuksen kohteet**-ruudussa.

   > [!div class="mx-imgBorder"]
   > ![Tuotemerkit- ja Kiinnostuksen kohteet -ruudut.](media/BrandsInterest-tile-Hub.png "Tuotemerkit- ja Kiinnostuksen kohde -ruudut")

1. Tutustu yleiskatsaukseen ja valitse **Seuraava**.

1. Maan tai alueen voi vaihtaa valitsemalla **Vaihda** **Maa tai alue** -kohdan vieressä. Valitse **Maan tai alueen asetukset** -ruudussa [tuettu maa tai alue](#supported-countriesregions) ja valitse sitten **Käytä**.

   > [!NOTE]
   > Kun valitset omia tuotemerkkejä, järjestelmä antaa ehdotuksia valitun maan tai alueen perusteella. Kun valitset toimialaa, saat tärkeimmät tuotemerkit tai kiinnostusten kohteet valitun maan tai alueen perusteella.

1. Valitse enintään viisi tuotemerkkiä tai kiinnostuksen kohdetta käyttämällä yhtä tai molempia seuraavista vaihtoehdoista:

   - **Toimiala**: Valitse avattavasta luettelosta toimiala ja valitse sitten kyseisen toimialan suosituimmat tuotemerkit tai kiinnostuksen kohteet.
   - **Valitse oma**: kirjoita organisaatiotasi kiinnostava tuotemerkki tai kiinnostuksen kohde ja valitse sitten vastaavat ehdotukset. Jos etsimääsi tuotemerkkiä tai kiinnostuksen kohteita ei luetella, lähetä meille palautetta **Ehdota**-linkin avulla.

1. Valitse **Seuraava**. Tutustu rikastuksen oletusasetuksiin ja päivitä ne tarvittaessa.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Näyttökuva rikastusasetusten ikkunasta.":::

1. Valitse **Seuraava**.

1. Valitse ensin **Asiakkaan tietojoukko** ja sitten Microsoftin tietojen avulla rikastettava profiili tai segmentti. *Asiakas*-entiteetti rikastaa kaikkia asiakasprofiileja, kun taas segmentti rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

1. Valitse **Seuraava**.

1. Yhdistä yhdistetyn asiakasentiteetit kentät Microsoftin tietoihin.

   > [!NOTE]
   > Ainakin syntymäpäivä- ja sukupuolimääritteet ovat pakollisia. Maa tai alue sekä ainakin kaupunki (ja osavaltio/provinssi) tai postinumero ovat pakollisia. Syntymäpäivä kannattaa muuntaa DateTime-tyypiksi tietojen käsittelyn aikana. Vaihtoehtoisesti se voi olla merkkijono [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) -muodossa, eli vvvv-KK-pp tai vvvv-KK-ppTHH:mm:ss.

1. Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**.

1. Kirjoita rikastuksen nimi. **Tulosentiteetin nimi** valitaan automaattisesti.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Kiinnostuksen kohteiden tarkistuksen ja nimeämisen sivu.":::

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.

1. Aloita rikastamisprosessi valitsemalla **Suorita** tai sulje ja palaa **Rikastukset**-sivulle.

   Profiileja rikastettaessa rikastetaan kaikki asiakasprofiilit, joihin haetaan tietoja valittuja tuotemerkkejä ja kiinnostuksen kohteita varten. Näihin kuuluvat myös profiilit, jotka eivät kuulu valittuun maahan tai alueeseen. Jos esimerkiksi valitsit Saksa, Yhdysvalloissa sijaitsevat profiilit rikastetaan, jos valituista tuotemerkeistä ja kiinnostuksen merkeistä on saatavilla tietoja Yhdysvalloissa.

## <a name="view-enrichment-results"></a>Rikastamisen tulosten tarkasteleminen

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Tulosten esikatselu rikastamisprosessin suorittamisen jälkeen.":::

Tulokset sisältävät **Affiniteettitaso**- tai **Äänen jakaminen** -kaaviot.

Rikastuksista luodut entiteetit ovat **Rikastus**-ryhmän luettelossa, johon päästään valitsemalla **Tiedot** > **Entiteetit**. Tuotemerkkien rikastetut tiedot siirretään **BrandAffinityFromMicrosoft**- tai **BrandShareOfVoiceFromMicrosoft**-entiteetteihin. Kiinnostuksen kohteiden tiedot ovat **InterestAffinityFromMicrosoft**- ja **InterestShareOfVoiceFromMicrosoft**-entiteeteissä.

## <a name="see-enrichment-data-on-the-customer-card"></a>Rikastamistietojen tarkasteleminen asiakaskortissa

Tuotemerkkiä ja kiinnostuksen kohteen osuutta kirjoituksissa voi tarkastella myös yksittäisissä asiakaskorteissa. Valitse ensin **Asiakkaat** ja sitten asiakasprofiili. Asiakaskortissa ovat kaaviot, joissa on tuotemerkin tai kiinnostuksen kohteen osuus kirjoituksista kyseisen asiakkaan demografisen profiilin henkilöiden mukaan.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Asiakaskortin rikastetut tiedot.":::

## <a name="next-steps"></a>Seuraavat vaiheet

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
