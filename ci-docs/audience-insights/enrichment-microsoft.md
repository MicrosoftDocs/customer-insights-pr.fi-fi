---
title: Rikasta asiakasprofiileja Microsoftin tietojen avulla
description: Käytä Microsoftin omistusoikeudellisia tietoja asiakastietojen rikastamisessa merkkimieltymyksillä ja osuudella kirjoituksista.
ms.date: 11/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 346c79d0a4d5cd5c47e91c195a48d3a153db0dc0
ms.sourcegitcommit: 9d3c9e4eb2ce20996a4f4fb44c42e3fe020c5b48
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/11/2021
ms.locfileid: "7793700"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Asiakasprofiilien rikastaminen merkkimieltymyksillä ja osuudella kirjoituksista (esiversio)

Käytä Microsoftin omistusoikeudellisia tietoja asiakastietojen rikastamisessa tuotemerkkimieltymyksillä, kiinnostuksen kohteilla ja osuudella kirjoituksista. Nämä mieltymykset ja osuus kirjoituksista perustuvat niiden henkilöiden tietoihin, jotka edustavat samanlaista väestöä kuin asiakkaasi. Näiden tietojen avulla saat lisätietoja asiakkaista ja voit segmentoida heidät mieltymysten tai kirjoitusten osuuksien perusteella tiettyihin tuotemerkkeihin ja kiinnostuksen kohteisiin.

Valitse käyttäjäryhmän merkityksillisissä tiedoissa **Tiedot** > **Rikastaminen**, jos haluat [määrittää ja tarkastella rikastuksia](enrichment-hub.md).

Jos haluat määrittää tuotemerkkimieltymysten ja kirjoitusten osuuksien rikastuksen, siirry **Etsi**-välilehteen ja valitse **Rikasta tiedot** -kohta **Tuotemerkit**-ruudussa.

Jos haluat määrittää kiinnostuksen kohteiden ja kirjoitusten osuuksien rikastuksen, siirry **Etsi**-välilehteen ja valitse **Rikasta tiedot** -kohta **Kiinnostuksen kohteet**-ruudussa.

   > [!div class="mx-imgBorder"]
   > ![Tuotemerkit- ja Kiinnostuksen kohteet -ruudut.](media/BrandsInterest-tile-Hub.png "Tuotemerkit- ja Kiinnostuksen kohde -ruudut")

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

Jos haluat valita maan tai alueen, avaa **Tuotemerkkien rikastaminen** tai **Kiinnostuksen kohteen rikastaminen** ja valitse **Maa/alue**-kohdan vieressä oleva **Muuta**. Valitse **Maa- ja alueasetukset** -ruudussa vaihtoehto ja valitse **Käytä**.

### <a name="implications-related-to-country-selection"></a>Maan valintaan liittyvät vaikutukset

- Kun [valitset omia tuotemerkkejä](#define-your-brands-or-interests), järjestelmä antaa ehdotuksia valitun maan tai alueen perusteella.

- Kun [valitset toimialaa](#define-your-brands-or-interests), saat tärkeimmät tuotemerkit tai kiinnostusten kohteet valitun maan tai alueen perusteella.

- [Profiileja rikastettaessa](#refresh-enrichment) rikastetaan kaikki asiakasprofiilit, joihin haetaan tietoja valittuja tuotemerkkejä ja kiinnostuksen kohteita varten. Näihin kuuluvat myös profiilit, jotka eivät kuulu valittuun maahan tai alueeseen. Jos esimerkiksi valitsit Saksa, Yhdysvalloissa sijaitsevat profiilit rikastetaan, jos valituista tuotemerkeistä ja kiinnostuksen merkeistä on saatavilla tietoja Yhdysvalloissa.

## <a name="configure-enrichment"></a>Rikastamisen määrittäminen

Ohjattu kokemus auttaa sinua rikastuksien määrityksessä. 

### <a name="define-your-brands-or-interests"></a>Määritä tuotemerkit tai kiinnostuksen kohteet

Valitse enintään viisi tuotemerkkiä tai kiinnostuksen kohdetta käyttämällä yhtä tai molempia seuraavista vaihtoehdoista:

- **Toimiala**: Valitse avattavasta luettelosta toimiala ja valitse sitten kyseisen toimialan suosituimmat tuotemerkit tai kiinnostuksen kohteet.
- **Valitse oma**: kirjoita organisaatiotasi kiinnostava tuotemerkki tai kiinnostuksen kohde ja valitse sitten vastaavat ehdotukset. Jos etsimääsi tuotemerkkiä tai kiinnostuksen kohteita ei luetella, lähetä meille palautetta **Ehdota**-linkin avulla.

### <a name="review-enrichment-preferences"></a>Rikastusasetusten tarkasteleminen

Tarkista oletusarvoiset rikastusasetukset ja päivitä ne tarpeen mukaan.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Näyttökuva rikastusasetusten ikkunasta.":::

### <a name="select-entity-to-enrich"></a>Rikastettavan entiteetin valitseminen

Valitse **Rikastettu entiteetti** ja valitse tietojoukko, jonka haluat rikastaa Microsoftin tiedoilla. Voit valita asiakasentiteetin, joka rikastaa kaikkia asiakasprofiileja, tai segmenttientiteetin, joka rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

### <a name="map-your-fields"></a>Yhdistä kenttäsi

Yhdistä yhdistetyn asiakasentiteetin kentät, jos haluat määrittää demografisen segmentin, jota haluat järjestelmän käyttävän asiakastietojen rikastamisessa. Yhdistä maa/alue ja vähintään syntymäaika- tai sukupuolimääritteet. Lisäksi sinun on yhdistettävä vähintään yksi postitoimipaikka (ja osavaltio/provinssi) tai postinumero. Määritä kenttien yhdistämismääritykset valitsemalla **Yhdistä**. Valitse **Käytä**, kun olet valmis. Viimeistele kenttien yhdistäminen valitsemalla **Tallenna**.

Seuraavia muotoja ja arvoja tuetaan (kirjainkokoa ei oteta huomioon arvoissa):

- **Syntymäaika**: Syntymäaika kannattaa muuntaa DateTime-tyypiksi tietojen käsittelyn aikana. Vaihtoehtoisesti se voi olla merkkijono [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) -muodossa, eli vvvv-KK-pp tai vvvv-KK-ppTHH:mm:ss.
- **Sukupuoli**: mies, nainen, tuntematon.
- **Postinumero**: Viisinumeroinen postinumero Yhdysvalloissa, vakiopostinumero muualla.
- **Kaupunki**: Kaupungin englanninkielinen nimi.
- **Osavaltio/provinssi** : Kahden kirjaimen lyhenne Yhdysvalloissa ja Kanadassa. Kahden tai kolmen kirjaimen lyhenne Australiassa. Ei koske Ranskaa, Saksaa tai Yhdistynyttä kuningaskuntaa.
- **Maa tai alue**:

  - US: Amerikan Yhdysvallat, Yhdysvallat, USA, US, Amerikka
  - CA: Kanada, CA
  - GB: Yhdistynyt kuningaskunta, UK, Iso-Britannia, GB, Ison-Britannian ja Pohjois-Irlannin yhdistynyt kuningaskunta, Ison-Britannian yhdistynyt kuningaskunta.
  - AU: Australia, AU, Australian yhteisö
  - FR: Ranska, FR, Ranskan tasavalta
  - DE: Saksa, saksa, Deutschland, Allemagne, DE, Saksan liittotasavalta, Saksan tasavalta

## <a name="review-and-name-the-enrichment"></a>Rikastuksen tarkistaminen ja nimeäminen

Lopuksi pääset tarkistamaan tiedot ja antamaan rikastukselle nimen.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Kiinnostuksen kohteiden tarkistuksen ja nimeämisen sivu.":::

## <a name="refresh-enrichment"></a>Rikastuksen päivittäminen

Suorita rikastus, kun olet konfiguroinut tuotemerkit, kiinnostuksen kohteet ja demografisten tietojen kenttien yhdistämismääritykset. Aloita prosessi valitsemalla tuotemerkin tai kiinnostuksen kohteen määrityssivulla **Suorita**. Voit lisäksi jättää rikastamisen suoritettavaksi automaattisesti aikataulutetun päivityksen osana.

Asiakastietojen koon mukaan rikastusaika voi kestää useita minuutteja.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Rikastamisen tulokset

Kun täydennysprosessia suoritetaan, siirry **Omat täydennykset** -kohtaan ja tarkista niiden asiakkaiden kokonaismäärä, joiden tietoja on täydennetty, sekä tuotemerkkien tai kiinnostuksen kohteiden erittely täydennetyissä asiakasprofiileissa.

:::image type="content" source="media/my-enrichments.png" alt-text="Tulosten esikatselu rikastamisprosessin suorittamisen jälkeen.":::

Näet kaavion, jossa on rikastettujen asiakasprofiilien määrä ajan kuluessa sekä rikastettujen entiteettien esikatselut. Tarkista rikastetut tiedot valitsemalla **Katso lisää** **Affiniteettitaso**- tai **Osuus kirjoituksista** -kaavioissa. Tuotemerkkien rikastetut tiedot siirretään **BrandAffinityFromMicrosoft**- tai **BrandShareOfVoiceFromMicrosoft**-entiteetteihin. Kiinnostuksen kohteiden tiedot ovat **InterestAffinityFromMicrosoft**- ja **InterestShareOfVoiceFromMicrosoft**-entiteeteissä. Nämä entiteetit ilmoitetaan myös **Rikastaminen**-ryhmässä kohdassa **Tiedot** > **Entiteetit**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Rikastamistietojen tarkasteleminen asiakaskortissa

Tuotemerkkiä ja kiinnostuksen kohteen osuutta kirjoituksissa voi tarkastella myös yksittäisissä asiakaskorteissa. Valitse ensin **Asiakkaat** ja sitten asiakasprofiili. Asiakaskortissa ovat kaaviot, joissa on tuotemerkin tai kiinnostuksen kohteen osuus kirjoituksista kyseisen asiakkaan demografisen profiilin henkilöiden mukaan.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Asiakaskortin rikastetut tiedot.":::

## <a name="next-steps"></a>Seuraavat vaiheet

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
