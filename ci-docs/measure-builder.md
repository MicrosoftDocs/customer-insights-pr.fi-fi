---
title: Mittareiden luominen mittarin muodostimella
description: Voit analysoida yrityksesi tärkeitä mittareita luomalla mittareita alusta alkaen.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170845"
---
# <a name="create-measures-with-measure-builder"></a>Mittareiden luominen mittarin muodostimella

Mittarin muodostimen avulla voit määrittää laskutoimituksia käyttämällä vastaavuusoperaattoreita, koostamistoimintoja ja suodattimia. Määritä mittareita määritteillä, jotka ovat peräisin entiteeteistä, jotka liittyvät yhdistettyyn *Asiakas*-entiteettiin.

Mittarien luominen B2C- ja B2B-ympäristöissä toimii samalla tavalla. Jos kuitenkin B2B-ympäristö [käyttää hierarkkisia tilejä](relationships.md#set-up-account-hierarchies), voit valita, koostetaanko mittari siihen liittyvistä alitileistä.

# <a name="individual-consumers-b-to-c"></a>[Yksittäiset kuluttajat (kuluttajakauppa)](#tab/b2c)

Voit luoda mittareita yksittäisten asiakkaiden tasolla (asiakasmäärite, asiakasmittari) tai yrityksen/organisaation tasolla (liiketoimintamittari). Asiakasmääritteen ja asiakasmittarin avulla voit seurata asiakaskohtaista suorituskykyä. Esimerkiksi kunkin asiakkaan käyttämä kokonaissumma. Liiketoimintamittareiden avulla voit seurata yrityksen suorituskykyä. Esimerkiksi yrityksen kokonaistuotto.

- Asiakasmäärite: Luo tulostiedot uutena määritteenä, joka tallentuu uutena sarakkeena järjestelmän luomassa entiteetissä, jonka nimi on *Customer_Measure*. Kun asiakasmäärite päivitetään, kaikki muut *Customer_Measure*-entiteetin asiakasmääritteet päivittyvät samalla kertaa. Lisäksi asiakasmääritteet näkyvät asiakasprofiilikortissa. Kun asiakasmäärite on suoritettu tai tallennettu, sitä ei voi muuttaa asiakasmittariksi.

- Asiakasmittari: Luo tulostiedot omana entiteettinään, etkä voi muuttaa sitä asiakasmääritteeksi, kun se suoritetaan tai tallennetaan. Asiakasmittarit eivät näy asiakasprofiilikortissa.

- Liiketoimintamittari: Luo tulostiedot omana entiteettinään ja näkyy Customer Insights -ympäristön kotisivulla.

1. Siirry **Mittarit**-kohtaan.

1. Valitse **Uusi** > **Luo oma**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Tyhjä määritysnäyttö B2C-mittaria varten. " lightbox="media/measure-b2c.png":::

1. Valitse nimettömän mittarin vieressä oleva **Muokkaa tietoja** -kohta. Anna mittarin nimi. Vaihtoehtoisesti voit lisätä mittariin [tunnisteita](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Muokkaa tietoja -valintaikkuna.":::

1. Valitse **Valmis**.

1. Voit seurata liiketoimintatason suorituskykyä vaihtamalla **mittarin tyypiksi** **Liiketoimintataso**. **Asiakastaso** on oletusarvoisesti valittuna. **Asiakastaso** lisää automaattisesti dimensioihin *CustomerId*-määritteen, kun taas **Liiketoimintataso** automaattisesti poistaa sen.

1. Valitse määritysalueessa koontitoiminto avattavasta **Valitse toiminto** -valikosta. Koostetoimintoja ovat seuraavat:
   - **Sum**
   - **Keskiarvo**
   - **Määrä**
   - **Yksilöllinen määrä**
   - **Enintään**
   - **Min**
   - **Ensimmäinen**: ottaa tietueen ensimmäisen arvon
   - **Viimeinen**: ottaa tietueeseen lisätyn viimeisen arvon
   - **ArgMax**: etsii tietotietueen, joka antaa suurimman arvon kohdetoiminnolla
   - **ArgMin**: etsii tietotietueen, joka antaa pienimmän arvon kohdetoiminnolla

1. Valitse **Lisää määrite**, jos haluat valita tälle mittarille luotavat tiedot.

   1. Valitse **Määritteet**-välilehti.
   1. Tietoentiteetti: valitse entiteetti, joka sisältää mitattavan määritteen.
   1. Tietomäärite: valitse määrite, jota haluat käyttää koostetoiminnossa mittarin laskemiseksi. Voit valita vain yhden määritteen kerrallaan.
   1. Voit valita myös tietomääritteen olemassa olevasta mittarista valitsemalla **Mittarit**-välilehden tai voit hakea mitä tahansa entiteetin tai mittarin nimeä.
   1. Valitse **Lisää**.

1. Jos haluat luoda monimutkaisia mittareita, voit lisätä määritteiden määrää tai käyttää mittarin toiminnossa matemaattisia operaattoreita.

1. Jos haluat lisätä suodattimia, valitse määritysalueen **Suodatin**-kohta. Suodattimien käyttäminen käyttää vain tietueita, jotka vastaavat suodattimia, kun lasketaan mittaria.
  
   1. Valitse **Suodattimet**-ruudun **Lisää määrite** -osassa määrite, jota haluat käyttää suodattimien luomisessa.
   1. Aseta suodatinoperaattorit, jos haluat määrittää jokaiselle valitulle määritteelle suodattimen.
   1. Valitse **Käytä**.

1. Valitse **Dimensio**, jos haluat valita lisää kenttiä, jotka lisätään sarakkeina mittarin tulosentiteettiin.

   1. Valitse **Muokkaa dimensioita**, jos haluat lisätä tietomääritteitä, joiden mukaan mittarin arvot ryhmitellään. Tämä voi olla esimerkiksi kaupunki tai sukupuoli.
      > [!TIP]
      > Jos valitset **Asiakastaso** **mittarin tyypin** arvoksi, *CustomerId*-määrite on jo lisätty. Jos poistat määritteen, **mittarin tason** arvoksi vaihdetaan **Liiketoimintataso**.
   1. Valitse **Valmis**.

1. Jos tiedoissasi on arvoja, jotka on korvattava kokonaisluvulla, valitse **Säännöt**. Määritä sääntö ja varmista, että valitset korvaavaksi arvoksi vain kokonaislukuja. Voit esimerkiksi korvata arvon *tyhjä* arvolla *0*.

1. Jos yhdistetyn tietoentiteetin ja *asiakas*-entiteetin välillä on useita polkuja, tulee valita jokin määritetyistä [entiteettisuhteen poluista](relationships.md). Mittarin tulokset voivat vaihdella valitun polun mukaan.

   1. Valitse **Suhdepolku** ja valitse entiteettipolku, jota tulee käyttää mittarisi tunnistamiseen. Jos *Asiakas*-entiteetissä on vain yksi polku, ohjausobjektia ei näy.
   1. Valitse **Valmis**.

1. Jos haluat lisätä mittarille lisää laskelmia, valitse **Uusi laskelma**. Uusissa laskelmissa voi käyttää vain saman entiteettipolun entiteettejä. Lisälaskelmat näkyvät uusina sarakkeina mittarin tulosentiteetissä. Voit myös luoda laskutoimitukselle nimen valitsemalla **Muokkaa nimeä**.

1. Valitse laskutoimituksessa kolme pystysuuntaista pistettä (&vellip;) luodaksesi **kaksoiskappaleen** tai **poistaaksesi** laskutoimituksen mittarista.

1. **Esiversio**-alueessa on näkyvissä mittarin tulosentiteetin tietorakenne, myös suodattimet ja dimensiot. Esiversio reagoi dynaamisesti määrityksen muutoksiin.

1. Laske määritetyn mittarin tulokset valitsemalla **Suorita**. Valitse **Tallenna ja sulje**, jos haluat pitää nykyisen määrityksen ja suorittaa mittarin myöhemmin. **Mittarit**-sivu avautuu.

# <a name="business-accounts-b-to-b"></a>[Yritystilit (yritysten väliset)](#tab/b2b)

Voit luoda mittareita yksittäisten asiakkuuksien tasolla (asiakasmittari) tai kaikkien asiakkuuksien tasolla (liiketoimintamittari).

- Asiakasmittari: Luo tulostiedot omana entiteettinään. Asiakasmittarit eivät näy asiakasprofiilikortissa.

- Liiketoimintamittari: Luo tulostiedot omana entiteettinään ja näkyy Customer Insights -ympäristön kotisivulla.

1. Siirry **Mittarit**-kohtaan.

1. Valitse **Uusi**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Tyhjä määritysnäyttö B2B-mittaria varten. ":::

1. Valitse nimettömän mittarin vieressä oleva **Muokkaa tietoja** -kohta. Anna mittarin nimi. Vaihtoehtoisesti voit lisätä mittariin [tunnisteita](work-with-tags-columns.md#manage-tags). 
   :::image type="content" source="media/measures_edit_details.png" alt-text="Muokkaa tietoja -valintaikkuna.":::

1. Valitse **Valmis**.

1. Valitse määritysalueessa koontitoiminto avattavasta **Valitse toiminto** -valikosta. Koostetoimintoja ovat seuraavat:
   - **Sum**
   - **Keskiarvo**
   - **Määrä**
   - **Yksilöllinen määrä**
   - **Enintään**
   - **Min**
   - **Ensimmäinen**: ottaa tietueen ensimmäisen arvon
   - **Viimeinen**: ottaa tietueeseen lisätyn viimeisen arvon

1. Valitse **Lisää määrite**, jos haluat valita tälle mittarille luotavat tiedot.

   1. Valitse **Määritteet**-välilehti.
   1. Tietoentiteetti: valitse entiteetti, joka sisältää mitattavan määritteen.
   1. Tietomäärite: valitse määrite, jota haluat käyttää koostetoiminnossa mittarin laskemiseksi. Voit valita vain yhden määritteen kerrallaan.
   1. Voit valita myös tietomääritteen olemassa olevasta mittarista valitsemalla **Mittarit**-välilehden tai voit hakea mitä tahansa entiteetin tai mittarin nimeä.
   1. Valitse **Lisää**, jos haluat lisätä valitun määritteen mittariin.

1. Jos haluat luoda monimutkaisia mittareita, voit lisätä määritteiden määrää tai käyttää mittarin toiminnossa matemaattisia operaattoreita.

1. Jos haluat lisätä suodattimia, valitse määritysalueen **Suodatin**-kohta. Suodattimien käyttäminen käyttää vain tietueita, jotka vastaavat suodattimia, kun lasketaan mittaria.
  
   1. Valitse **Suodattimet**-ruudun **Lisää määrite** -osassa määrite, jota haluat käyttää suodattimien luomisessa.
   1. Aseta suodatinoperaattorit, jos haluat määrittää jokaiselle valitulle määritteelle suodattimen.
   1. Valitse **Käytä**, jos haluat lisätä suodattimet mittariin.

1. Valitse **Dimensio**, jos haluat valita lisää kenttiä, jotka lisätään sarakkeina mittarin tulosentiteettiin.

   1. Valitse **Muokkaa dimensioita**, jos haluat lisätä tietomääritteitä, joiden mukaan mittarin arvot ryhmitellään. Tämä voi olla esimerkiksi kaupunki tai sukupuoli.
      > [!TIP]
      > *CustomerId*-määrite on jo lisätty, mikä osoittaa, että tämä on asiakastason mittarityyppi. Jos poistat määritteen, mittarin tyypiksi vaihtuu liiketoimintataso.
   1. Valitse **Valmis**, jos haluat lisätä dimensiot mittariin.

1. Jos tiedoissasi on arvoja, jotka on korvattava kokonaisluvulla, valitse **Säännöt**. Määritä sääntö ja varmista, että valitset korvaavaksi arvoksi vain kokonaislukuja. Voit esimerkiksi korvata arvon *tyhjä* arvolla *0*.

1. Jos [käytät tilejä, joissa on hierarkioita](relationships.md#set-up-account-hierarchies), tarkastele käyttöpainiketta **Kokoa aliasiakkaat**.
   - Jos se on määritetty arvoon **Ei käytössä**, mittari lasketaan jokaiselle tilille. Jokaisella tilillä on oma tulos.
   - Jos se määritetty arvoon **Käytössä**, valitse **Muokkaa**, jotta voit valita tilihierarkian käytettyjen hierarkioiden mukaan. Mittari tuottaa vain yhden tuloksen, koska siihen koostetaan aliasiakkaat.

1. Jos yhdistetyn tietoentiteetin ja *asiakas*-entiteetin välillä on useita polkuja, tulee valita jokin määritetyistä [entiteettisuhteen poluista](relationships.md). Mittarin tulokset voivat vaihdella valitun polun mukaan.

   1. Valitse **Suhdepolku** ja valitse entiteettipolku, jota tulee käyttää mittarisi tunnistamiseen. Jos *Asiakas*-entiteetissä on vain yksi polku, ohjausobjektia ei näy.
   1. Ota valinta käyttöön valitsemalla **Valmis**.

1. Valitse laskutoimituksessa kolme pystysuuntaista pistettä (&vellip;) luodaksesi **kaksoiskappaleen** tai **poistaaksesi** laskutoimituksen mittarista.

1. **Esiversio**-alueessa on näkyvissä mittarin tulosentiteetin tietorakenne, myös suodattimet ja dimensiot. Esiversio reagoi dynaamisesti määrityksen muutoksiin.

1. Laske määritetyn mittarin tulokset valitsemalla **Suorita**. Valitse **Tallenna ja sulje**, jos haluat pitää nykyisen määrityksen ja suorittaa mittarin myöhemmin. **Mittarit**-sivu avautuu.

---

## <a name="next-step"></a>Seuraava vaihe

Voit luoda [asiakassegmentin](segments.md) olemassa olevien mittareiden avulla.

[!INCLUDE [footer-include](includes/footer-banner.md)]
