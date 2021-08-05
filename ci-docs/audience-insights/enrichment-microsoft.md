---
title: Rikasta asiakasprofiileja Microsoftin tietojen avulla
description: Microsoftin omistamista tiedoista voit rikastaa asiakastietoja tuotemerkkien ja kiinnostuksen kohteiden tiedoilla.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 3b10fb23cca03ed918aa7fd46478b568d5ebbf1a
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555487"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Asiakasprofiilien täydentäminen tuotemerkillä ja kiinnostuksen kohteilla (esiversio)

Microsoftin omistamista tiedoista voit rikastaa asiakastietoja tuotemerkkien ja kiinnostuksen kohteiden tiedoilla. Nämä affiniteetit perustuvat sellaisten henkilöiden tietoihin, joilla on samanlaiset demografiatiedot kuin asiakkailla. Nämä tiedot auttavat ymmärtämään ja segmentoimaan asiakkaita paremmin sen perusteella, mikä on heidän affiniteettinsa tiettyjen brändien ja kiinnostuksenkohteiden osalta.

Valitse käyttäjäryhmän merkityksillisissä tiedoissa **Tiedot** > **Rikastaminen**, jos haluat [määrittää ja tarkastella rikastuksia](enrichment-hub.md).

Jos haluat määrittää tuotemerkin affiniteettien täydentämisen, siirry **Tutustu**-välilehteen ja valitse **Täydennä omat tiedot** **Tuotemerkit**-ruudussa.

Jos haluat määrittää kiinnostuksen kohteen affiniteettien täydentämisen, siirry **Tutustu**-välilehteen ja valitse **Täydennä omat tiedot** **Kiinnostuksen kohteet** -ruudussa.

   > [!div class="mx-imgBorder"]
   > ![Tuotemerkit- ja Kiinnostuksen kohteet -ruudut.](media/BrandsInterest-tile-Hub.png "Tuotemerkit- ja Kiinnostuksen kohde -ruudut")

## <a name="how-we-determine-affinities"></a>Miten määritetään affiniteetit

Microsoftin online-hakutietojen avulla voidaan etsiä affiniteetteja tuotemerkkejä ja kiinnostuksen kohteita varten eri demografisille segmenteille (jotka on määritetty iän, sukupuolen tai sijainnin mukaan). Tuotemerkin tai kiinnostuksen kohteiden online-hakujen määrä määrittää, kuinka paljon demografisessa segmentissä on verrattuna muihin segmentteihin kyseisen tuotemerkin tai kiinnotuksen kohteen merkitystä.

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

Valitse **Rikastettu entiteetti** ja valitse tietojoukko, jonka haluat rikastaa Microsoftin yritystiedoilla. Voit valita asiakasentiteetin, joka rikastaa kaikkia asiakasprofiileja, tai segmenttientiteetin, joka rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

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

> [!TIP]
> Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types). Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies). Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja. Kun olet valinnut jollekin työn tehtävälle **Katso tiedot** -kohdan, näkyvissä ovat lisätiedot. Niitä ovat käsittelyaika, edellinen käsittelypäivä ja kaikki tehtävään liittyvät virheet ja varoitukset.

## <a name="enrichment-results"></a>Rikastamisen tulokset

Kun täydennysprosessia suoritetaan, siirry **Omat täydennykset** -kohtaan ja tarkista niiden asiakkaiden kokonaismäärä, joiden tietoja on täydennetty, sekä tuotemerkkien tai kiinnostuksen kohteiden erittely täydennetyissä asiakasprofiileissa.

:::image type="content" source="media/my-enrichments.png" alt-text="Tulosten esikatselu rikastamisprosessin suorittamisen jälkeen.":::

Tarkastele rikastettuja tietoja valitsemalla kaaviossa **Näytä rikastetut tiedot**. Tuotemerkkien rikastetut tiedot siirtyvät **BrandAffinityFromMicrosoft**-entiteettiin. Kiinnostuksen kohteiden tiedot ovat **InterestAffinityFromMicrosoft**-entiteetissä. Nämä entiteetit ilmoitetaan myös **Rikastaminen**-ryhmässä kohdassa **Tiedot** > **Entiteetit**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Rikastamistietojen tarkasteleminen asiakaskortissa

Brändien ja kiinnostuksenkohteiden affiniteetteja voi tarkastella myös yksittäisissä asiakaskorteissa. Valitse ensin **Asiakkaat** ja sitten asiakasprofiili. Asiakaskortissa on tietoja kaavioista tuotemerkkejä tai kiinnostuksen kohteita varten, joita kohtaan henkilöillä asiakkaiden demografisessa profiilissa on affiniteetti.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Asiakaskortin rikastetut tiedot.":::

## <a name="next-steps"></a>Seuraavat vaiheet

Voit hyödyntää rikastettuja asiakastietoja. Voit luoda [segmenttejä](segments.md) ja [mittareita](measures.md) ja jopa [viedä tietoja](export-destinations.md), jos haluat tarjota asiakkaille mukautettuja käyttökokemuksia.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
