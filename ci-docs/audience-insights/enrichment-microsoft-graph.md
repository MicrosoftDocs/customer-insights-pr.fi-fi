---
title: Asiakasprofiilien rikastaminen Microsoft Graphin avulla
description: Käytä Microsoft Graphin tarjoamia tietoja, kun haluat rikastuttaa asiakastietoja tuotemerkkien ja kiinnostuksen kohteiden tiedoilla.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405591"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Asiakasprofiilien täydentäminen tuotemerkillä ja kiinnostuksen kohteilla (esiversio)

Käytä Microsoft Graphin tarjoamia tietoja, kun haluat rikastuttaa asiakastietoja tuotemerkkien ja kiinnostuksen kohteiden tiedoilla. Nämä affiniteetit määritetään asiakkaiden demografiatietoja muistuttavia ihmisiä koskevien tietojen perusteella. Nämä tiedot auttavat ymmärtämään ja segmentoimaan asiakkaita paremmin sen perusteella, mikä on heidän affiniteettinsa tiettyjen brändien ja kiinnostuksenkohteiden osalta.

Voit [määrittää ja näyttää rikastamiset](enrichment-hub.md) valitsemalla käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Rikastaminen**.

Jos haluat määrittää tuotemerkin affiniteettien täydentämisen, siirry **Tutustu**-välilehteen ja valitse **Täydennä omat tiedot** **Tuotemerkit**-ruudussa.

Jos haluat määrittää kiinnostuksen kohteen affiniteettien täydentämisen, siirry **Tutustu**-välilehteen ja valitse **Täydennä omat tiedot** **Kiinnostuksen kohteet** -ruudussa.

   > [!div class="mx-imgBorder"]
   > ![Tuotemerkit- ja Kiinnostuksen kohteet -ruudut](media/BrandsInterest-tile-Hub.png "Tuotemerkit- ja Kiinnostuksen kohteet -ruudut")

## <a name="about-microsoft-graph"></a>Tietoja Microsoft Graphista

Microsoft Graphissa käytetään online-hakutietoja, joiden avulla voit etsiä erilaisia tuotemerkkejä ja kiinnostuksen kohteita eri demografisista segmenteistä (iän, sukupuolen tai sijainnin mukaan). Tuotemerkin tai kiinnostuksen kohteiden online-hakujen määrä määrittää, kuinka paljon demografisessa segmentissä on verrattuna muihin segmentteihin kyseisen tuotemerkin tai kiinnotuksen kohteen merkitystä.

[Lisätietoja Microsoft Graphista](https://docs.microsoft.com/graph/overview)

## <a name="affinity-score-and-confidence"></a>Affiniteetin pistemäärä ja luotettavuus

**Affiniteetin pistemäärä** lasketaan 100 pisteen asteikolla, jossa 100 ilmaisee segmentin, jonka affiniteetti brändiin tai kiinnostuksenkohteen osalta on korkein.

**Affiniteetin luottamus** lasketaan myös 100 pisteen asteikolla. Se osoittaa järjestelmän luotettavuustason, jolla segmentillä on tuotemerkin tai kiinnostuksen affiniteetti. Luotettavuustaso perustuu segmentin kokoon ja rakeisuuteen. Segmentin koko määräytyy tiettyä segmenttiä koskevien tietojen määrän mukaan. Segmentin rakeisuus määräytyy sen mukaan, kuinka monta määritettä (ikä, sukupuoli, sijainti) on käytettävissä profiilissa.

Tietojoukko pistemääriä ei normalisoida. Tämän vuoksi kaikki mahdolliset tietojoukon affiniteetti pistemäärät eivät ehkä ole näkyvissä. Esimerkiksi tiedoissasi ei ehkä ole rikastettua asiakasprofiilia, jonka affiniteettipisteet olisivat 100. Se on mahdollista silloin, kun demografisesta segmentistä ei löydy asiakkaita, jotka saivat 100 pistettä tietyn tuotemerkin tai kiinostksen kohteen vuoksi.

> [!TIP]
> Kun [segmenttejä luodaan](segments.md) käyttämällä affiniteetin pistemääriä, affiniteetin pistemäärien jakautuminen tietojoukossa on syytä tarkistaa ennen käytettävien pisterajojen määrittämistä. Esimerkiksi affiniteetin pistemäärää 10 voidaan pitää merkittävänä tietojoukossa, jonka korkein annetun brändin tai kiinnostuksenkohteen affiniteetin pistemäärä on 25.

## <a name="supported-countriesregions"></a>Tuetut maat ja alueet

Seuraavia maita ja alueita tuetaan tällä hetkellä: Australia, Kanada (englanti), Ranska, Saksa, Yhdistyneet kuningaskunta tai Yhdysvallat (englanti).

Valitse maa avaamalla **Tuotemerkkien rikastus** tai **Kiinnostuksen kohteiden rikastus** ja valitse **Vaihda** **Maa tai alue** -kohdan vieressä. Valitse **Maa- ja alueasetukset** -ruudussa vaihtoehto ja valitse **Käytä**.

### <a name="implications-related-to-country-selection"></a>Maan valintaan liittyvät vaikutukset

- Kun [valitset omia tuotemerkkejä](#define-your-brands-or-interests), saat ehdotuksia valitun maan tai alueen perusteella.

- [Toimialaa valittaessa](#define-your-brands-or-interests) määritetään kiinnostavimmat brändit tai kiinnostuksenkohteet valitun maan tai alueen perusteella.

- Kun [yhdistät kenttiä](#map-your-fields) eikä Maa tai alue -kenttä ole yhdistetty, asiakasprofiileja rikastetaan valitun maan tai alueen Microsoft Graph data -tietojen perusteella. Kyseisellä valinnalla rikastetaan myös asiakasprofiileja, joiden maa- tai aluetietoja ei ole saatavana.

- Kun [profiileja rikastetaan](#refresh-enrichment), kaikkia niitä asiakasprofiileja rikastetaan, joissa valittujen tuotemerkkien ja kiinnostuksen kohteiden Microsoft Graph -tiedot ovat käytettävissä. Tämä koskee myös profiileja, jotka eivät ole valitussa maassa tai valitulla alueella. Jos valitsit esimerkiksi Saksan, Yhdysvalloissa sijaitsevat profiilit rikastetaan, jos valittujen yhdysvaltalaisten tuotemerkkien ja kiinnostuksen kohteiden Microsoft Graph -tiedot ovat käytettävissä.

## <a name="configure-enrichment"></a>Rikastaminen määritys

Tuotemerkkien tai kiinnostuksen kohteiden täydentämisen määrittäminen sisältää seuraavat kaksi vaihetta:

### <a name="define-your-brands-or-interests"></a>Määritä tuotemerkit tai kiinnostuksen kohteet

Mahdolliset vaihtoehdot:

- **Toimiala**: Järjestelmä tunnistaa alasi tärkeimmät tuotemerkit tai kiinnostuksen kohteet ja täydentää asiakastietoja niiden kanssa.
- **Valitse omasi**: Valitse enintään viisi kohdetta niiden tuotemerkkien tai kiinnostuksen kohteiden luettelosta, jotka ovat organisaation kannalta tärkeimmät.

Voit lisätä tuotemerkin tai kiinnostuksen kohteen kirjoittamalla sen syötealueeseen, jolloin saat ehdotuksia hakuehtojen perusteella. Jos etsimääsi tuotemerkkiä tai kiinnostuksen kohteita ei luetella, lähetä meille palautetta **Ehdota**-linkin avulla.

### <a name="map-your-fields"></a>Yhdistä kenttäsi

Yhdistä yhdistetyn asiaksentiteetin kentät vähintään kahteen määritteeseen, jotta voit määrittää demografisen segmentin, jota haluat käyttää asiakastietojen rikastuttamisessa. Määritä kenttien yhdistämismääritykset valitsemalla **Yhdistä**. Valitse **Käytä**, kun olet valmis. Viimeistele kenttien yhdistäminen valitsemalla **Tallenna**.

Seuraavia muotoja ja arvoja tuetaan, kirjainkokoa ei oteta huomioon arvoissa:

- **Syntymäaika**: Syntymäaika kannattaa muuntaa DateTime-tyypiksi tietojen käsittelyn aikana. Vaihtoehtoisesti se voi olla [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) -muotoinen merkkijono vvvv-KK-pp tai vvvv-KK-ppTHH:mm:ssZ".
- **Sukupuoli**: mies, nainen, tuntematon
- **Postinumero**: Yhdysvalloissa viisinumeroinen postinumero, vakiopostinumero kaikkialla muualla
- **Kaupunki**: kaupungin englanninkielinen nimi
- **Osavaltio/provinssi** : Kahden kirjaimen lyhenne Yhdysvalloissa ja Kanadassa. Kahden tai kolmen kirjaimen lyhenne Australiassa. Ei koske Ranskaa, Saksaa tai Yhdistynyttä kuningaskuntaa.
- **Maa tai alue**:

  - US: Amerikan Yhdysvallat, Yhdysvallat, USA, US, Amerikka
  - CA: Kanada, CA
  - GB: Yhdistynyt kuningaskunta, UK, Iso-Britannia, GB, Ison-Britannian ja Pohjois-Irlannin yhdistynyt kuningaskunta, Ison-Britannian yhdistynyt kuningaskunta.
  - AU: Australia, AU, Australian liittovaltio
  - FR: Ranska, FR, Ranskan tasavalta
  - DE: Saksa, saksa, Deutschland, Allemagne, DE, Saksan liittotasavalta, Saksan tasavalta

## <a name="refresh-enrichment"></a>Rikastuksen päivittäminen

Suorita rikastus, kun olet konfiguroinut tuotemerkit, kiinnostuksen kohteet ja demografisten tietojen kenttien yhdistämismääritykset. Aloita prosessi valitsemalla tuotemerkin tai kiinnostuksen kohteen määrityssivulla **Suorita**. Voit lisäksi jättää rikastamisen suoritettavaksi automaattisesti aikataulutetun päivityksen osana.
Asiakastietojen koon mukaan rikastusaika voi kestää useita minuutteja.

> [!TIP]
> Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types). Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies). Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja. Kun työn jossakin tehtävissä on valittu **Näytä tiedot**, saat lisätietoja: käsittelyajan, viimeisimmän käsittelypäivämäärän sekä kaikki tehtävään liitetyt virheet ja varoitukset.

## <a name="enrichment-results"></a>Rikastamisen tulokset

Kun täydennysprosessia suoritetaan, siirry **Omat täydennykset** -kohtaan ja tarkista niiden asiakkaiden kokonaismäärä, joiden tietoja on täydennetty, sekä tuotemerkkien tai kiinnostuksen kohteiden erittely täydennetyissä asiakasprofiileissa.

:::image type="content" source="media/my-enrichments.png" alt-text="Tulosten esikatselu rikastamisprosessin suorittamisen jälkeen":::

Tarkastele rikastettuja tietoja valitsemalla kaaviossa **Näytä rikastetut tiedot**. Tuotemerkkien rikastetut tiedot siirtyvät **BrandAffinityFromMicrosoft**-entiteettiin. Kiinnostuksen kohteiden tiedot ovat **InterestAffinityFromMicrosoft**-entiteetissä. Nämä entiteetit ilmoitetaan myös **Rikastaminen**-ryhmässä kohdassa **Tiedot** > **Entiteetit**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Rikastamistietojen tarkasteleminen asiakaskortissa

Brändien ja kiinnostuksenkohteiden affiniteetteja voi tarkastella myös yksittäisissä asiakaskorteissa. Valitse ensin **Asiakkaat** ja sitten asiakasprofiili. Asiakaskortissa on tietoja kaavioista tuotemerkkejä tai kiinnostuksen kohteita varten, joita kohtaan henkilöillä asiakkaiden demografisessa profiilissa on affiniteetti.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Asiakaskortin rikastetut tiedot":::

## <a name="next-steps"></a>Seuraavat vaiheet

Voit hyödyntää rikastettuja asiakastietoja. Voit tarjota asiakkaille mukautettuja kokemuksia luomalla [segmenttejä](segments.md) ja [mittoja](measures.md) sekä [viemällä tietoja](export-destinations.md).
