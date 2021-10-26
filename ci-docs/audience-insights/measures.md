---
title: Mittareiden luominen ja hallinta
description: Määritä yrityksen suorituskyvyn analysoimiseen ja kuvaamiseen liittyvät mittarit.
ms.date: 09/30/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 39acca78c022bc15ebc15dc80f21fe175da04d4d
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622855"
---
# <a name="define-and-manage-measures"></a>Mittojen määrittäminen ja hallinta

Mittarien avulla ymmärrät paremmin asiakkaiden käyttäytymistä ja liiketoiminnan suorituskykyä. Ne näyttävät olennaiset arvot [yhtenäisistä profiileista](data-unification.md). Ajatellaan, että yrityksessä halutaan nähdä esimerkiksi *kokonaiskulutus asiakasta kohden* yksittäisen asiakkaan ostohistorian tai *yrityksen kokonaismyynti* koko yrityksen yhdistetyn tason tuoton selvittämiseksi.  

Mittarit luodaan käyttämällä mittareiden luontiohjelmaa. Se on tietojen kysely-ympäristö, jossa on useita operaattoreita ja yksinkertaiset yhdistämisvalinnat. Sen avulla voi suodattaa tietoja, ryhmitellä tuloksia, havaita [entiteettisuhteiden polkuja](relationships.md) ja esikatsella tulosta.

Käytä mittarin luontiohjelmaa liiketoiminta-aktiviteettien suunnittelemisessa tekemällä kyselyjä asiakastiedoista ja poimimalla tietoja. Esimerkiksi *asiakaskohtainen kokonaiskulutus*- ja *asiakaskohtainen kokonaispalautus* -mittarin luominen auttaa tunnistamaan asiakkaat, jotka ostavat paljon, mutta tekevät myös paljon palautuksia. Voit [luoda segmentin](segments.md) seuraavien parhaiden toimintojen suorittamiseksi. 

## <a name="build-your-own-measure-from-scratch"></a>Rakenna oma mittari tyhjästä

Tässä osassa kerrotaan uuden mittarin luomisesta alusta alkaen. Voit tehdä tietomääritteiden avulla mittarin tietoentiteeteistä, jotka voivat suhteen kautta muodostaa yhteyden yhtenäiseen asiakasprofiilientiteettiin.

# <a name="individual-customers-b2c"></a>[Yksittäiset asiakkaat (B2C)](#tab/b2c)

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Mittarit**.

1. Valitse **Uusi** ja valitse **Luo oma**.

1. Valitse **Muokkaa nimeä** ja anna mittarille **nimi**. 

1. Valitse määritysalueessa koontitoiminto avattavasta **Valitse toiminto** -valikosta. Koostetoimintoja ovat seuraavat: 
   - **Sum**
   - **Keskiarvo**
   - **Määrä**
   - **Yksilöllinen määrä**
   - **Enintään**
   - **Min**
   - **Ensimmäinen**: ottaa tietueen ensimmäisen arvon
   - **Viimeinen**: ottaa tietueeseen lisätyn viimeisen arvon

   :::image type="content" source="media/measure-operators.png" alt-text="Mittarin laskelmien operaattorit.":::

1. Valitse **Lisää määrite**, jos haluat valita tälle mittarille luotavat tiedot.
   
   1. Valitse **Määritteet**-välilehti. 
   1. Tietoentiteetti: valitse entiteetti, joka sisältää mitattavan määritteen. 
   1. Tietomäärite: valitse määrite, jota haluat käyttää koostetoiminnossa mittarin laskemiseksi. Voit valita vain yhden määritteen kerrallaan.
   1. Voit valita myös tietomääritteen olemassa olevasta mittarista valitsemalla **Mittarit**-välilehden tai voit hakea mitä tahansa entiteetin tai mittarin nimeä. 
   1. Valitse **Lisää**, jos haluat lisätä valitun määritteen mittariin.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Valitse laskelmissa käytettävä määrite.":::

1. Jos haluat luoda monimutkaisia mittareita, voit lisätä määritteiden määrää tai käyttää mittarin toiminnossa matemaattisia operaattoreita.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Luo monimutkainen mittari, jossa on matemaattisia operaattoreita.":::

1. Jos haluat lisätä suodattimia, valitse määritysalueen **Suodatin**-kohta. 
  
   1. Valitse **Suodattimet**-ruudun **Lisää määrite** -osassa määrite, jota haluat käyttää suodattimien luomisessa.
   1. Aseta suodatinoperaattorit, jos haluat määrittää jokaiselle valitulle määritteelle suodattimen.
   1. Valitse **Käytä**, jos haluat lisätä suodattimet mittariin.

1. Jos haluat lisätä dimensioita, valitse määritysalueen **Dimensio**-kohta. Dimensiot näkyvät mittarin tulosentiteetin sarakkeina.
 
   1. Valitse **Muokkaa dimensioita**, jos haluat lisätä tietomääritteitä, joiden mukaan mittarin arvot ryhmitellään. Tämä voi olla esimerkiksi kaupunki tai sukupuoli. Oletusarvoisesti valitaan *CustomerID*-dimensio *asiakastason mittareiden* luomiseksi. Voit poistaa oletusdimension, jos haluat luoda *yritystason mittareita*.
   1. Valitse **Valmis**, jos haluat lisätä dimensiot mittariin.

1. Jos tiedoissasi on arvoja, jotka on korvattava kokonaisluvulla, valitse **Säännöt**. Määritä sääntö ja varmista, että valitset korvaavaksi arvoksi vain kokonaislukuja. Voit esimerkiksi korvata arvon *tyhjä* arvolla *0*.

1. Jos yhdistetyn tietoentiteetin ja *asiakas*-entiteetin välillä on useita polkuja, tulee valita jokin määritetyistä [entiteettisuhteen poluista](relationships.md). Mittarin tulokset voivat vaihdella valitun polun mukaan. 
   
   1. Valitse **Suhdepolku** ja valitse entiteettipolku, jota tulee käyttää mittarisi tunnistamiseen. Jos *Asiakas*-entiteetissä on vain yksi polku, ohjausobjektia ei näy.
   1. Ota valinta käyttöön valitsemalla **Valmis**. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Valitse mittarin entiteettipolku.":::

1. Jos haluat lisätä mittarille lisää laskelmia, valitse **Uusi laskelma**. Uusissa laskelmissa voi käyttää vain saman entiteettipolun entiteettejä. Lisälaskelmat näkyvät uusina sarakkeina mittarin tulosentiteetissä.

1. Valitse laskelman **...**-kohta, jos haluat **monistaa**, **uudelleennimetä** tai **poistaa** laskelman mittarista.

1. **Esiversio**-alueessa on näkyvissä mittarin tulosentiteetin tietorakenne, myös suodattimet ja dimensiot. Esiversio readoi dynaamisesti määrityksen muutoksiin.

1. Laske määritetyn mittarin tulokset valitsemalla **Suorita**. Valitse **Tallenna ja sulje**, jos haluat pitää nykyisen määrityksen ja suorittaa mittarin myöhemmin.

1. Siirry **Mittarit**-kohtaan, jos haluat nähdä juuri luodun mittarin luettelossa.

# <a name="business-accounts-b2b"></a>[Yritystilit (B2B)](#tab/b2b)

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Mittarit**.

1. Valitse **Uusi** ja valitse **Luo oma**.

1. Valitse **Muokkaa nimeä** ja anna mittarille **nimi**. 

1. Valitse määritysalueessa koontitoiminto avattavasta **Valitse toiminto** -valikosta. Koostetoimintoja ovat seuraavat: 
   - **Sum**
   - **Keskiarvo**
   - **Määrä**
   - **Yksilöllinen määrä**
   - **Enintään**
   - **Min**
   - **Ensimmäinen**: ottaa tietueen ensimmäisen arvon
   - **Viimeinen**: ottaa tietueeseen lisätyn viimeisen arvon

   :::image type="content" source="media/measure-operators.png" alt-text="Mittarin laskelmien operaattorit.":::

1. Valitse **Lisää määrite**, jos haluat valita tälle mittarille luotavat tiedot.
   
   1. Valitse **Määritteet**-välilehti. 
   1. Tietoentiteetti: valitse entiteetti, joka sisältää mitattavan määritteen. 
   1. Tietomäärite: valitse määrite, jota haluat käyttää koostetoiminnossa mittarin laskemiseksi. Voit valita vain yhden määritteen kerrallaan.
   1. Voit valita myös tietomääritteen olemassa olevasta mittarista valitsemalla **Mittarit**-välilehden tai voit hakea mitä tahansa entiteetin tai mittarin nimeä. 
   1. Valitse **Lisää**, jos haluat lisätä valitun määritteen mittariin.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Valitse laskelmissa käytettävä määrite.":::

1. Jos haluat luoda monimutkaisia mittareita, voit lisätä määritteiden määrää tai käyttää mittarin toiminnossa matemaattisia operaattoreita.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Luo monimutkainen mittari, jossa on matemaattisia operaattoreita.":::

1. Jos haluat lisätä suodattimia, valitse määritysalueen **Suodatin**-kohta. 
  
   1. Valitse **Suodattimet**-ruudun **Lisää määrite** -osassa määrite, jota haluat käyttää suodattimien luomisessa.
   1. Aseta suodatinoperaattorit, jos haluat määrittää jokaiselle valitulle määritteelle suodattimen.
   1. Valitse **Käytä**, jos haluat lisätä suodattimet mittariin.

1. Jos haluat lisätä dimensioita, valitse määritysalueen **Dimensio**-kohta. Dimensiot näkyvät mittarin tulosentiteetin sarakkeina.
 
   1. Valitse **Muokkaa dimensioita**, jos haluat lisätä tietomääritteitä, joiden mukaan mittarin arvot ryhmitellään. Tämä voi olla esimerkiksi kaupunki tai sukupuoli. Oletusarvoisesti valitaan *CustomerID*-dimensio *asiakastason mittareiden* luomiseksi. Voit poistaa oletusdimension, jos haluat luoda *yritystason mittareita*.
   1. Valitse **Valmis**, jos haluat lisätä dimensiot mittariin.

1. Jos tiedoissasi on arvoja, jotka on korvattava kokonaisluvulla, valitse **Säännöt**. Määritä sääntö ja varmista, että valitset korvaavaksi arvoksi vain kokonaislukuja. Voit esimerkiksi korvata arvon *tyhjä* arvolla *0*.

1. Voit käyttää **Kokoa aliasiakkaat** -käyttöpainiketta, jos [käytät tilejä, joissa on hierarkioita](relationships.md#set-up-account-hierarchies).
   - Jos se on määritetty arvoon **Ei käytössä**, mittari lasketaan jokaiselle tilille. Jokaisella tilillä on oma tulos.
   - Jos se määritetty arvoon **Käytössä**, valitse **Muokkaa**, jotta voit valita tilihierarkian käytettyjen hierarkioiden mukaan. Mittari tuottaa vain yhden tuloksen, koska siihen koostetaan aliasiakkaat.

1. Jos yhdistetyn tietoentiteetin ja *asiakas*-entiteetin välillä on useita polkuja, tulee valita jokin määritetyistä [entiteettisuhteen poluista](relationships.md). Mittarin tulokset voivat vaihdella valitun polun mukaan. 
   
   1. Valitse **Suhdepolku** ja valitse entiteettipolku, jota tulee käyttää mittarisi tunnistamiseen. Jos *Asiakas*-entiteetissä on vain yksi polku, ohjausobjektia ei näy.
   1. Ota valinta käyttöön valitsemalla **Valmis**. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Valitse mittarin entiteettipolku.":::

1. Valitse laskelman **...**-kohta, jos haluat **monistaa**, **uudelleennimetä** tai **poistaa** laskelman mittarista.

1. **Esiversio**-alueessa on näkyvissä mittarin tulosentiteetin tietorakenne, myös suodattimet ja dimensiot. Esiversio readoi dynaamisesti määrityksen muutoksiin.

1. Laske määritetyn mittarin tulokset valitsemalla **Suorita**. Valitse **Tallenna ja sulje**, jos haluat pitää nykyisen määrityksen ja suorittaa mittarin myöhemmin.

1. Siirry **Mittarit**-kohtaan, jos haluat nähdä juuri luodun mittarin luettelossa.

---

## <a name="use-a-template-to-build-a-measure"></a>Mittarin luominen mallin avulla

Voit luoda niitä käyttämällä ennalta määritettyjä malleja, joissa on usein käytettyjä mittoja. Mallien yksityiskohtaiset kuvaukset ja ohjattu kokemus auttavat mittarien tehokkaassa luomisessa. Mallit perustuvat *Yhdistetty aktiviteetti* -entiteetin yhdistettyihin tietoihin. Varmista siis, että olet määrittänyt [asiakasaktiviteetit](activities.md), ennen kuin luot mittarin mallista.

# <a name="individual-customers-b2c"></a>[Yksittäiset asiakkaat (B2C)](#tab/b2c)

Voit luoda niitä käyttämällä ennalta määritettyjä malleja, joissa on usein käytettyjä mittoja. Mallien yksityiskohtaiset kuvaukset ja ohjattu kokemus auttavat mittarien tehokkaassa luomisessa. Mallit perustuvat *Yhdistetty aktiviteetti* -entiteetin yhdistettyihin tietoihin. Varmista siis, että olet määrittänyt [asiakasaktiviteetit](activities.md), ennen kuin luot mittarin mallista.

Käytettävissä olevat mittarimallit: 
- Keskimääräinen tapahtuman arvo (ATV)
- Tapahtuman kokonaisarvo
- Keskimääräinen päivätuotto
- Keskimääräinen vuosituotto
- Tapahtumien määrä
- Ansaitut kanta-asiakaspisteet
- Lunastetut kanta-asiakaspisteet
- Kanta-asiakaspisteiden saldo
- Aktiivisen asiakkaan elinkaari
- Kanta-asiakkuuden kesto
- Aika viime ostosta

Seuraavassa ohjeessa on kuvattu, miten uusi mittari voidaan luoda mallin avulla.

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Mittarit**.

1. Valitse ensin **Uusi** ja sitten **Valitse malli**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Näyttökuva avattavasta valikosta luotaessa uutta mittaria, jonka korostus on mallissa.":::

1. Etsi tarpeisiisi sopiva malli ja valitse **Valitse malli**.

1. Tarkista tarvittavat tiedot ja valitse **Aloitus**, jos kaikki tiedot ovat paikoillaan.

1. Määritä **Muokkaa nimeä** -ruudussa mittarin ja tulosentiteetin nimi. 

1. Valitse **Valmis**.

1. Määritä **Määritä ajanjakso** -osassa aikaväli käytettäville tiedoille. Jos haluat uuden mittarin kattavan koko tietojoukon, valitse **Koko ajan**. Valitse **Tietty ajanjakso**, jos haluat mittarin keskittyvän tiettyyn ajanjaksoon.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Näyttökuva, jossa näkyy ajanjakso-osa, kun mittaria määritetään mallista.":::

1. Valitse seuraavassa osassa **Lisää tiedot**, jos haluat valita aktiviteetit ja yhdistää vastaavat *Yhdistetty aktiviteetti* -kohteen tiedot.

    1. Vaihe 1/2: Valitse **Aktiviteettityyppi**-kohdassa haluamasi entiteetin tyyppi. Valitse **Aktiviteetit**-kohdassa entiteetit, jotka haluat yhdistää.
    1. Vaihe 2/2: Valitse määrite *Yhdistetty aktiviteetti* -entiteetistä komponentille, jota kaava edellyttää. Esimerkiksi Keskimääräinen tapahtuman arvo on määrite, joka vastaa tapahtuman arvoa. Valitse **Aktiviteetin aikaleima** -kohdassa Yhdistetty aktiviteetti -kohteen määrite, joka kuvaa aktiviteetin päivämäärää ja aikaa.
   
1. Kun tietojen yhdistäminen on onnistunut, voit nähdä tilan **Valmis** ja yhdistettyjen aktiviteettien ja määritteiden nimen.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Näyttökuva valmiin mittarimallin määrityksestä.":::

1. Nyt voit laskea mittarin tulokset valitsemalla **Suorita**. Jos haluat tarkentaa sitä myöhemmin, valitse **Tallenna luonnos**.

# <a name="business-accounts-b2b"></a>[Yritystilit (B2B)](#tab/b2b)

Tämä ominaisuus on käytettävissä vain niissä ympäristöissä luoduille yksiköille, joissa yksittäiset asiakkaat ovat ensisijainen kohdeyleisö.

---

## <a name="manage-your-measures"></a>Hallitse mittoja

**Mittarit**-sivulla on mittarien luettelo.

Saat tietoja mittarityypistä, tekijästä, luontipäivästä ja tilasta. Kun valitset mittarin luettelosta, voit esikatsella tulosta ja ladata CSV-tiedoston.

Jos haluat päivittää kaikki mitat samalla kertaa, valitse **Päivitä kaikki** valitsematta tiettyä mittaa.

> [!div class="mx-imgBorder"]
> ![Yksittäisten mittareiden hallintatoiminnot.](media/measure-actions.png "Yksittäisten mittareiden hallintatoiminnot.")

Valitse seuraaville vaihtoehdoille mittari luettelosta:

- Voit tarkastella tietoja valitsemalla mitan nimen.
- **Muokkaa** mitan määritystä.
- **Päivitä** mittari uusimpien tietojen perusteella.
- **Nimeä uudelleen** mitta.
- **Poista** mitta.
- **Aktivoi** tai **poista aktivointi**. Passiivisia mittareita ei päivitetä [aikataulutetun päivityksen](system.md#schedule-tab) aikana.

> [!TIP]
> Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types). Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies). Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja. Kun olet valinnut jollekin työn tehtävälle **Katso tiedot** -kohdan, näkyvissä ovat lisätiedot. Niitä ovat käsittelyaika, edellinen käsittelypäivä ja kaikki tehtävään liittyvät virheet ja varoitukset.

## <a name="next-step"></a>Seuraava vaihe

Voit luoda [asiakassegmentin](segments.md) olemassa olevien mittareiden avulla.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
