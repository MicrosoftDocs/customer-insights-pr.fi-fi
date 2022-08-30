---
title: Tietojen yhdistämisen yhtenäisten asiakaskenttien avulla
description: Yhtenäisten asiakasprofiilien luominen yhdistämällä entiteettejä.
recommendations: false
ms.date: 07/27/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: 7ebd6ab8fa6ae141f33295a5d7723e96c8dc70ca
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304009"
---
# <a name="unify-customer-fields"></a>Yhdenmukaista asiakaskentät

Valitse yhdistämisprosessin tässä vaiheessa yhdistetyn profiilin entiteettiin yhdisteltävat määritteet tai sulje niitä pois. Jos esimerkiksi kolmella entiteetillä on sähköpostitietoja, haluat ehkä säilyttää kaikki kolme erillistä sähköpostikenttää tai yhdistää ne yhdeksi yhdistetyn profiilin sähköpostikentäksi. Järjestelmä yhdistää automaattisesti jotkin määritteet. Voit luoda vakaita ja yksilöllisiä asiakastunnuksia. Yksittäisille asiakkaille voit ryhmitellä liittyvät profiilit klusteriksi.

:::image type="content" source="media/m3_unify.png" alt-text="Tietojen yhtenäistämisprosessin Yhdenmukaista asiakaskentät -sivu, jossa on taulukossa yhdistettyjä kenttiä, jotka määrittävät yhtenäisen asiakasprofiilin.":::

## <a name="review-and-update-the-customer-fields"></a>Tarkista ja päivitä asiakasprofiilin kenttiä

1. Tarkista luettelo kentistä, jotka on yhtenäistetty taulukon **Asiakaskentät**-välilehdessä. Tee tarvittavat muutokset.

   1. Voit suorittaa seuraavat toimenpiteet yhdistetyille kentille:
      - [Muokkaa](#edit-a-merged-field)
      - [Nimeä uudelleen](#rename-fields)
      - [Erota](#separate-merged-fields)
      - [Jätä pois](#exclude-fields)
      - [Siirrä ylös- tai alaspäin](#change-the-order-of-fields)

   1. Voit suorittaa seuraavat toimenpiteet yksittäisille kentille:
      - [Yhdistä kentät](#combine-fields-manually)
      - [Yhdistä kenttien ryhmä](#combine-a-group-of-fields)
      - [Nimeä uudelleen](#rename-fields)
      - [Jätä pois](#exclude-fields)
      - [Siirrä ylös- tai alaspäin](#change-the-order-of-fields)

1. Voit myös [luoda asiakastunnuksen määrityksen](#configure-customer-id-generation).

1. Vaihtoehtoisesti voit B2C-tilanteessa [ryhmitellä profiileja kotitalouksiksi tai klustereiksi](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Seuraava vaihe: Tarkista yhdistäminen](review-unification.md)

### <a name="edit-a-merged-field"></a>Muokkaa yhdistettyä kenttää

1. Valitse yhdistetty kenttä ja valitse sitten **Muokkaa**. Kenttien yhdistäminen -ruutu tulee näkyviin.

1. Määritä, miten kentät yhdistetään kolmesta vaihtoehdosta:
    - **Tärkeys**: määrittää voittajan arvon osallistuvien kenttien tärkeyden mukaan. Se on yhdistämisen oletusasetus. Määritä tärkeysjärjestys valitsemalla **Siirrä ylöspäin/alaspäin**.

      > [!NOTE]
      > Customer Insights käyttää ensimmäistä arvoa, joka ei ole tyhjäarvo. Jos esimerkiksi järjestys on entiteetit A, B ja C, A.Name ja B.Name ovat tyhjäarvoja, käytetään C.Name-arvoa.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Tärkeysasetus yhdistämiskenttien valintaikkunassa.":::

    - **Uusin**: määrittää voittajan arvon uusimpien arvojen perusteella. Tasaus edellyttää päivämäärää tai numeerista kenttää jokaiselle yhdistämiskenttien osallistujaentiteetille.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Viimeaikaisuusasetus yhdistämiskenttien valintaikkunassa.":::

    - **Vähiten uusin**: määrittää voittajan arvon vähiten uusien arvojen perusteella. Tasaus edellyttää päivämäärää tai numeerista kenttää jokaiselle yhdistämiskenttien osallistujaentiteetille.

1. Voit lisätä kenttiä osallistuaksesi yhdistämisprosessiin.

1. Voit nimetä yhdistetyn kentän uudelleen.

1. Ota muutokset käyttöön valitsemalla **Valmis**.

### <a name="rename-fields"></a>Kenttien nimeäminen uudelleen

Voit muuttaa yhdistettyjen tai erillisten kenttien näyttönimeä. Tuloste-entiteetin nimeä ei voi muuttaa.

1. Valitse kenttä ja valitse **Nimeä uudelleen**.

1. Syötä uusi näyttönimi.

1. Valitse **Valmis**.

### <a name="separate-merged-fields"></a>Erota yhdistetyt kentät

Jos haluat erottaa yhdistetyt kentät, etsi määrite taulukosta. Erotetut kentät näkyvät erillisinä arvopisteinä yhdistetyssä asiakasprofiilissa.

1. Valitse yhdistetty kenttä ja valitse **Erota kentät toisistaan**.

1. Vahvista erottelu.

### <a name="exclude-fields"></a>Jätä kenttiä pois

Jätä yhdistetty tai erillinen kenttä pois unified customer profile -profiilista. Jos kenttää käytetään muissa prosesseissa, esimerkiksi segmentissä, poista se näistä prosesseista, ennen kuin poistat kentän asiakasprofiilista.

1. Valitse kenttä ja valitse **Jätä pois**.

1. Vahvista käytöstä poisto.

Jos haluat nähdä luettelon kaikista poisjätetyistä kentistä, valitse **Poisjätetyt kentät**. Voit tarvittaessa lukea poisjätetyn kentän.

### <a name="change-the-order-of-fields"></a>Kenttien järjestyksen muuttaminen

Jotkin entiteetit sisältävät enemmän tietoja kuin toiset. Jos entiteetti sisältää kentän uusimmat tiedot, voit priorisoida sen muita entiteettejä korkeammalle arvojen yhdistämisessä.

1. Valitse kenttä.
  
1. Valitse **Siirrä ylös- tai alaspäin** järjestyksen määrittämiseksi tai vedä ja pudota ne haluttuun kohtaan.

### <a name="combine-fields-manually"></a>Yhdistä kentät manuaalisesti

Yhdistä erotettuja kenttä luodaksesi yhdistetyn määritteen.

1. Valitse **Yhdistä** > **Kenttiä**. Kenttien yhdistäminen -ruutu tulee näkyviin.

1. Määritä yhdistämisen voittajakäytäntö avattavassa **Yhdistä kentät** -luettelossa.

1. Valitse **Lisää kenttä** yhdistääksesi lisää kenttiä.

1. Anna **Nimi** ja **Tulostekentän nimi**.

1. Ota muutokset käyttöön valitsemalla **Valmis**.

### <a name="combine-a-group-of-fields"></a>Yhdistä kenttien ryhmä

Käsittele kenttäryhmää yhtenä yksikkönä. Jos tietueet sisältävät esimerkiksi kentät Osoite1, Osoite2, Kaupunki, Osavaltio ja Postinumero, emme halua yhdistää tietoja toisen tietueen Osoite2-kenttään sillä perusteellaa, että se tekisi tiedoistamme täydellisemmät.

1. Valitse **Yhdistä** > **Kenttäryhmä**.

1. Määritä yhdistämisen voittajakäytäntö avattavassa **Ryhmien lajitteluperuste** -luettelossa.

1. Valitse **Lisää** ja valitse, haluatko lisätä kenttiä vai ryhmiä kenttiin.

1. Anna jokaiselle yhdistetylle kentälle **Nimi** ja **Tulosteen nimi**.

1. Anna kenttien ryhmälle **Nimi**.

1. Ota muutokset käyttöön valitsemalla **Valmis**.

## <a name="configure-customer-id-generation"></a>Määritä asiakastunnuksen luonti

Määritä, miten luodaan asiakkaan tunnusarvoja ja yksilöllisiä asiakasprofiilin tunnisteita. Tietojen yhdistämisprosessin kenttien yhdistämisvaihe luo yksilöllisen asiakasprofiilin tunnuksen. Tunnus on *CustomerId*-tunnus *Asiakas*-entiteetissä, joka on tulos tietojen yhdistämisprosessista.

*CustomerId* perustuu ei-tyhjäarvoisen voittajan perusavaimien ensimmäisen arvon hajautusarvoon. Nämä avaimet ovat peräisin tietojen yhdistämisissä käytetyistä entiteeteistä, ja vastinejärjestys vaikuttaa niihin.Luotu asiakastunnus voi siis muuttua, kun perusavaimen arvo muuttuu vastinejärjestyksen ensisijaisessa entiteetissä. Perusavaimen arvo ei välttämättä aina edusta samaa asiakasta.

Määrittämällä vakaan asiakastunnuksen voit välttää tämän käyttäytymisen.

1. Valitse **Avaimet**-välilehti.

1. Vie hiiren osoitin **CustomerId**-riville ja valitse **Määritä**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Tunnuksen luonnin mukauttamisen hallinta.":::

1. Valitse enintään viisi kenttää, jotka sisältävät yksilöllisen asiakastunnuksen ja ovat vakaampia. Tietueet, jotka eivät vastaa kokoonpanoa, käyttävät sen sijaan järjestelmän luomaa määritystunnusta.  

1. Valitse **Valmis**.

## <a name="group-profiles-into-households-or-clusters"></a>Profiilien ryhmitteleminen kotitalouksiksi tai klustereiksi

Yksittäisille asiakkaille voit määrittää sääntöjä, jotka ryhmittelevät liittyvät profiilit klusteriksi. Käytettävissä on tällä hetkellä kahdentyyppisiä klustereita: kotitalousklusterit ja mukautetut klusterit. Järjestelmä valitsee automaattisesti kotitalouden ennalta määritetyin säännöin, jos *Asiakas*-entiteetti sisältää semanttiset kentät *Person.LastName* ja *Location.Address*. Voit myös luoda klusterin omilla säännöilläsi ja ehdoillasi, samoin kuin [vastaavuussäännöissä](match-entities.md#define-rules-for-match-pairs).

1. Valitse **Lisäasetukset** > **Luo klusteri**.

   :::image type="content" source="media/create-cluster.png" alt-text="Uuden klusterin luomisen ohjausobjekti.":::

1. Valitse joko **Kotitalous** tai **Mukautettu** klusteri. Jos semanttiset kentät *Person.LastName* ja *Location.Address* ovat olemassa *Asiakas*-entiteetissä, kotitalous valitaan automaattisesti.

1. Anna klusterille nimi ja valitse **Valmis**.

1. Valitse **Klusterit**-välilehti löytääksesi luomasi klusterin.

1. Määritä klusteri luomalla säännöt ja ehdot.

1. Valitse **Valmis**. Klusteri luodaan, kun yhdistämisprosessi on valmis. Klusterien tunnisteet lisätään uusiksi kentiksi *Asiakas*-entiteettiin.

> [!div class="nextstepaction"]
> [Seuraava vaihe: Tarkista yhdistäminen](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
