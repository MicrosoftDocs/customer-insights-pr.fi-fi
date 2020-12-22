---
title: Tilauksen vaihtuvuusennuste
description: Ennusta riski sille, että asiakas ei enää käytä yrityksesi tilaustuotteita tai -palveluja.
ms.date: 08/19/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 03178fc1bfe611b1b0ced08bbbef876035875825
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643724"
---
# <a name="subscription-churn-prediction-preview"></a>Tilausten vaihtuvuusennuste (esikatselu)

Tilausten vaihtuvuusennuste auttaa ennustamaan riskin sille, että asiakas ei enää käytä yrityksesi tilaustuotteita tai -palveluja. Voit luoda uuden tilausten vaihtuvuusennusteen valitsemalla **Älykäs toiminto** > **Ennusteet**-sivu. Valitse **Omat ennusteet**, kun haluat nähdä muita luomiasi ennusteita.

> [!TIP]
> Kokeile tilauksen vaihtuvuusennusteen opasohjelmaa näytetietojen avulla: [Tilauksen vaihtuvuusennusteen näyteopas](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Edellytykset

- Ainakin [osallistujan käyttöoikeudet](permissions.md).
- Liiketoiminnan tietämys, jonka avulla tiedät, mitä vaihtuvuus merkitsee yrityksellesi. Aikaperustaisia vaihtuvuusmäärityksiä tuetaan. Tämä tarkoittaa sitä, että asiakasta pidetään menetettynä, kun tilauksen päättymisestä on kulunut tietty aika.
- Tietoja tilauksistasi ja tilaushistoriasta:
    - Tilaustunnisteet, joiden avulla tilaukset erotetaan toisistaan.
    - Asiakastunnisteet, jotka vastaavat asiakkaiden tilauksia.
    - Tilaustapahtuman päivämäärät, jotka määrittävät alkamis- ja päättymispäivät sekä tilaustapahtumien päivämäärät.
    - Tilauksen tiedot, jotka määrittävät tilauksen toistuvuuden ja uusimisvälin.
    - Tilausten semanttinen tietorakenne edellyttää seuraavien tietojen määrittämistä:
        - **Tilauksen tunnus:** Tilauksen yksilöivä tunniste.
        - **Tilauksen päättymispäivä:** Päivämäärä, jona asiakkaan tilaus päättyy.
        - **Tilauksen alkamispäivä:** Päivämäärä, jona asiakkaan tilaus alkaa.
        - **Tapahtumapäivä:** Tilauksen muutoksen päivämäärä. Esimerkiksi tapahtuma, jossa asiakas ostaa tai peruuttaa tilauksen.
        - **Onko kyseessä toistuva tilaus:** Totuusarvon Tosi/epätosi-kenttä, joka määrittää, uusitaanko tilaus samalla tilaustunnuksella ilman asiakkaan toimia
        - **Toistumisväli (kuukausina):** Toistuvien tilausten kausi, jonka jälkeen tilaus uusitaan. Se ilmaistaan kuukausina. Esimerkiksi asiakkaalle automaattisesti vuosittain uusittavan tilauksen arvo on 12.
        - (Valinnainen) **Tilausmäärä:** Summa, jonka asiakas maksaa tilauksen uusimisesta. Sen avulla voidaan määrittää tilausten eri tasojen mallit.
- Tietoja asiakasaktiviteeteista:
    - Aktiviteetin tunnisteet, joiden avulla saman tyypin aktiviteetit erotetaan toisistaan.
    - Asiakastunnisteet, joiden avulla aktiviteetit yhdistetään asiakkaisiin.
    - Aktiviteetin tiedot, jotka sisältävät aktiviteetin nimen ja päivämäärän.
    - Asiakasaktiviteettien semanttinen tietorakenne sisältää seuraavat tiedot:
        - **Perusavain:** Aktiviteetin yksilöllinen tunniste. Esimerkiksi verkkosivustokäynti tai käyttötietue, jossa näkyy asiakkaan katsoma TV-sarjan jakso.
        - **Aikaleima:** Ensisijaisen avaimen tunnistaman tapahtuman päivämäärä ja aika.
        - **Tapahtuma:** Sen tapahtuman nimi, jota haluat käyttää. Esimerkiksi suoratoistovideopalvelussa kenttä, jonka nimi on Käyttäjän toiminto, voi saada arvon Katsottu.
        - **Tiedot:** Tapahtuman yksityiskohtaiset tiedot. Esimerkiksi suoratoistovideopalvelussa kenttä, jonka nimi on Ohjelman nimi, voi saada arvoksi asiakkaan katsoman videon.
   > [!NOTE]
   > Tarvitset vähintään kaksi aktiviteettitietuetta 50 prosentille asiakkaista, joiden vaihtuvuuden haluat laskea.

## <a name="create-a-subscription-churn-prediction"></a>Tilausten vaihtuvuusennusteen luominen

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Analytiikka** > **Ennusteet**.
1. Valitse **Tilausten vaihtuvuusennuste (esikatselu)** -ruutu ja valitse sitten **Käytä tätä mallia**.
   > [!div class="mx-imgBorder"]
   > ![Tilauksen vaihtuvuusmalli -ruutu ja Käytä tätä mallia -painike](media/subscription-churn-usethismodel.PNG "Tilauksen vaihtuvuusmalli -ruutu ja Käytä tätä mallia -painike")

### <a name="name-model"></a>Nimimalli

1. Anna mallille nimi, joka erottaa sen muista malleista.
1. Anna tulosentiteetille nimi käyttämällä vain kirjaimia ja numeroita. Välilyöntejä ei voi käyttää. Se on nimi, jota mallientiteetti käyttää. Valitse sitten **Seuraava**.

### <a name="define-customer-churn"></a>Määritä asiakasvaihtuvuus

1. Anna **Päivät tilauksen päättymisestä** -kohtaan arvo, jonka jälkeen yritys pitää asiakasta menetettynä. Tämä kausi linkittyy yleensä yrityksen aktiviteetteihin, kuten tarjouksiin tai muihin markkinointitoimintoihin, joiden avulla yritetään estää asiakkaiden menettäminen.
1. Määritä **Vaihtuvuuden ennustamisessa huomioon otettavat päivät** -määrä määrittääksesi aikavälin vaihtuvuuden ennustamiselle. Voit esimerkiksi ennustaa asiakkaiden vaihtuvuusriskin seuraavan 90 päivän aikana, jotta voit mukauttaa asiakkaiden säilyttämiseen tähtääviä markkinointiponnistelujasi. Vaihtuvuusriskin ennustaminen pidemmillä tai lyhyemmillä aikaväleillä voi vaikeuttaa asiakasvaihtuvuuden riskiprofiilin tekijöiden käsittelemistä, mutta tämä määräytyy pitkälti omien liiketoimintatarpeidesi perustella. Jatka valitsemalla **Seuraava**
   >[!TIP]
   > Voit valita **Tallenna ja sulje** milloin tahansa, jos haluat tallentaa ennusteen luonnokseksi. Näkyviin tulee ennusteluonnos **Omat ennusteet** -välilehdessä.

### <a name="add-required-data"></a>Lisää pakolliset tiedot

1. Valitse **Lisää tiedot** **Tilaushistoria**-kohtaan ja valitse entiteetti, joka sisältää tilaushistorian [edellytyksissä](#prerequisites) kerrotulla tavalla.
1. Jos alla olevia kenttiä ei ole täytetty, määritä suhde tilaushistoriasta asiakasentiteettiin.
    1. Valitse **Tilaushistoriaentiteetti**.
    1. Valitse **kenttä**, joka määrittää asiakkaan tilaushistoriaentiteetissä. Sen on liityttävä ensisijaisen asiakkaan tunnukseen asiakasentiteetissä.
    1. Valitse **Asiakasentiteetti**, joka vastaa ensisijaista asiakasentiteettiä.
    1. Anna suhdetta kuvaava nimi.
       > [!div class="mx-imgBorder"]
       > ![Tilaushistoria-sivu, joka sisältää suhteen luomisen asiakkaaseen](media/subscription-churn-subscriptionhistoryrelationship.PNG "Tilaushistoria-sivu, joka sisältää suhteen luomisen asiakkaaseen")
1. Valitse **Seuraava**.
1. Yhdistä semanttiset kentät määritteisiin tilaushistoriaentiteetissä ja valitse **Tallenna**. Lisätietoja kentistä on [edellytyksissä](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Tilausten historia -sivu, jolla näkyvät valitun tilauksen historian entiteetin kenttiin yhdistetyt semanttiset määritteet](media/subscription-churn-subscriptionhistorymapping.PNG "Tilausten historia -sivu, jolla näkyvät valitun tilauksen historian entiteetin kenttiin yhdistetyt semanttiset määritteet")
1. Valitse **Lisää tiedot** **Asiakkaan aktiviteetit** -kohdassa ja valitse entiteetti, joka sisältää asiakkaan aktiviteetin tiedot edellytyksissä kerrotulla tavalla.
1. Valitse aktiviteettityyppi, joka vastaa määrittämiesi asiakkaan aktiviteetin tyyppiä.  Valitse **Luo uusi** ja anna nimi, jos et näe tarvittavaa aktiviteettityyppiä vastaavaa vaihtoehtoa.
1. Sinun täytyy määrittää suhde asiakkaan aktiviteetin entiteetistä asiakasentiteettiin.
    1. Valitse kenttä, joka määrittää asiakkaan asiakkaan aktiviteetin taulukossa. Se voi liittyä suoraan asiakasentiteetin ensisijaisen asiakkaan tunnukseen.
    1. Valitse asiakasentiteetti, joka vastaa ensisijaista asiakasentiteettiä.
    1. Anna suhdetta kuvaava nimi.
1. Valitse **Seuraava**.
1. Yhdistä semanttiset kentät määritteisiin asiakkaan aktiviteetin entiteetissä ja valitse **Tallenna**. Lisätietoja kentistä on [edellytyksissä](#prerequisites).
1. (Valinnainen) Jos tiedossa on muita asiakkaan aktiviteetteja, jotka haluat sisällyttää, toista edellä olevat vaiheet.
   > [!div class="mx-imgBorder"]
   > ![Entiteettisuhteen määrittäminen](media/subscription-churn-customeractivitiesmapping.PNG "Asiakkaan aktiviteetit -sivu, jolla näkyvät valitun asiakkaan aktiviteetin entiteetin kenttiin yhdistetyt semanttiset määritteet")
1. Valitse **Seuraava**.

### <a name="set-schedule-and-review-configuration"></a>Määritä aikataulu ja tarkista määritys

1. Määritä mallin uudelleenkouluttamistiheys. Tämä asetus on tärkeä ennusteiden tarkkuuden päivityksessä käsiteltäessä uusia tietoja käyttäjäryhmän merkityksellisissä tiedoissa. Useimmat yritykset voivat uudelleenkouluttaa kerran kuukaudessa ja saada hyvän tarkkuuden ennusteille.
1. Valitse **Seuraava**.
1. Tarkista määritys. Voit palata mihin tahansa ennustemäärityksen osaan valitsemalla **Muokkaa** annetun arvon kohdassa. Voit myös valita määritysvaiheen edistymisen ilmaisimesta.
1. Jos kaikki arvot on määritetty oikein, aloita ennusteprosessi valitsemalla **Tallenna ja suorita**. **Omat ennusteet** -välilehdessä voit tarkastella ennusteiden tilaa. Prosessin valmistumiseen voi kulua useita tunteja ennusteessa käytettyjen tietojen määrästä riippuen.

## <a name="review-a-prediction-status-and-results"></a>Ennusteen tilan ja tulosten tarkasteleminen

1. Siirry **Omat ennusteet** -välilehteen kohdassa **Älykäs toiminto** > **Ennusteet**.
   > [!div class="mx-imgBorder"]
   > ![Omat ennusteet -sivun tarkasteleminen](media/subscription-churn-mypredictions.PNG "Omat ennusteet -sivun tarkasteleminen")
1. Valitse ennuste, jota haluat tarkastella.
   - **Ennusteen nimi:** Ennusteelle luomisen yhteydessä annettu nimi.
   - **Ennustetyyppi:** Ennusteessa käytetyn mallin tyyppi.
   - **Tulosentiteetti:** Sen entiteetin nimi, johon ennusteen tulos tallennetaan. Tämänniminen entiteetti löytyy kohdasta **Tiedot** > **Entiteetit**.
   - **Ennustettu-kenttä:** Tämä kenttä täytetään vain tietyn tyyppisille ennusteille. Sitä ei käytetä tilausten vaihtuvuusennusteessa.
   - **Tila:** Ennusteen suoritumisen nykyinen tila.
        - **Jonossa:** Ennuste odottaa parhaillaan muiden prosessien suorittamista.
        - **Päivitys:** Ennusteessa suoritetaan parhaillaan käsittelyn tulosvaihetta. Sen avulla saadaan tulokset, jotka siirretään tulosentiteettiin.
        - **Epäonnistui:** Ennuste on epäonnistunut. Jos haluat lisätietoja, valitse **Lokit**.
        - **Onnistui:** Ennuste on onnistunut. Valitse allekkaisten pisteiden alla oleva **Tarkastele**-kohta, jos haluat tarkastella ennustetta.
   - **Muokattu:** Ennusteen määrityksen muutospäivämäärä.
   - **Viimeinen päivitys:** Päivämäärä, jona ennuste päivitti tulokset tulosentiteettiin.
1. Valitse sen ennusteen vieressä olevat allekkaiset pisteet, jonka tuloksia haluat tarkastella, ja valitse **Näytä**.
   > [!div class="mx-imgBorder"]
   > ![Tarkastele allekkaisten pisteiden valikon vaihtoehtoja, esimerkiksi muokkausta, päivittämistä, tarkastelemista, lokeja ja poistamista](media/subscription-churn-verticalellipses.PNG "Tarkastele allekkaisten pisteiden valikon vaihtoehtoja, esimerkiksi muokkausta, päivittämistä, tarkastelemista, lokeja ja poistamista")
1. Tulossivulla on seuraavat kolme ensisijaista tieto-osaa:
    1. **Opetusmallin suorituskyky:** A, B ja C ovat mahdollisia pistemääriä. Tämä pistemäärä osoittaa ennusteen suorituskyvyn. Sen avulla voit tehdä päätöksen tulosentiteettiin tallennettujen tulosten käyttämisestä.
        - Pistemäärät määritetään seuraavien sääntöjen perusteella:
            - **A** – Kun malli on oikein ennustettu vähintään 50 prosentissa kaikista ennusteista, ja kun prosenttiosuus tarkoille vaihtuneiden asiakkaiden ennusteille on vähintään 10 % suurempi kuin historiallisen vaihtuvuusprosentin keskiarvo.
            - **B** – Kun malli on oikein ennustettu vähintään 50 prosentissa kaikista ennusteista, ja kun prosenttiosuus tarkoille vaihtuneiden asiakkaiden ennusteille on korkeintaan 10 % suurempi kuin historiallisen vaihtuvuusprosentin keskiarvo.
            - **C** – Kun malli on oikein ennustettu vähintään 50 prosentissa kaikista ennusteista, tai kun prosenttiosuus tarkoille vaihtuneiden asiakkaiden ennusteille on pienempi kuin historiallisen vaihtuvuusprosentin keskiarvo.
               > [!div class="mx-imgBorder"]
               > ![Tarkastele mallin suorituskyvyn tulosta](media/subscription-churn-modelperformance.PNG "Tarkastele mallin suorituskyvyn tulosta")
    1. **Vaihtuvuuden todennäköisyys (asiakkaiden määrä):** Asiakasryhmät ennustetun vaihtuvuusriskin perusteella. Nämä tiedot auttavat myöhemmin, jos haluat luoda asiakassegmentin, jolla on suuri vaihtuvuusriski. Tällaiset segmentit auttavat ymmärtämään, missä segmentin jäsenyyden rajan on oltava.
       > [!div class="mx-imgBorder"]
       > ![Kaavio, jossa näkyvät vaihtuvuuden tulosten jakelu eriteltynä välille 0 - 100 %](media/subscription-churn-resultdistribution.PNG "Kaavio, jossa näkyvät vaihtuvuuden tulosten jakelu eriteltynä välille 0 - 100 %")
    1. **Tärkeimmät tekijät:** Ennusteen luomisessa otetaan huomioon useita tekijöitä. Kunkin tekijän tärkeys on laskettu mallin luomille yhdistellyille ennusteille. Näiden tekijöiden avulla voit tarkistaa ennusteen tulokset. Tai voit käyttää näitä tietoja myöhemmin ja [luoda segmenttejä](segments.md), joiden avulla voit vaikuttaa asiakkaiden vaihtuvuusriskiin.
       > [!div class="mx-imgBorder"]
       > ![Luettelo, jossa on vaikuttavat tekijät ja niiden tärkeys vaihtuuvuustulosten ennustamisessa](media/subscription-churn-influentialfactors.PNG "Luettelo, jossa on vaikuttavat tekijät ja niiden tärkeys vaihtuuvuustulosten ennustamisessa")

## <a name="fix-a-failed-prediction"></a>Epäonnistuneen ennusteen korjaaminen

1. Siirry **Omat ennusteet** -välilehteen kohdassa **Älykäs toiminto** > **Ennusteet**.
1. Valitse ennuste, jonka virhelokeja haluat tarkastella. Valitse sitten **Lokit**.
   > [!div class="mx-imgBorder"]
   > ![Tarkastele tulosten valikkoriviä, jolla ovat esimerkiksi Sulje-, Muokkaa mallia- ja Lokit-painikkeet](media/subscription-churn-logsbutton.PNG "Tarkastele tulosten valikkoriviä, jolla ovat esimerkiksi Sulje-, Muokkaa mallia- ja Lokit-painikkeet")
1. Tarkastele kaikkia virheitä. Mahdollisia virhe tyyppejä on useita. Ne osoittavat, mikä ehto aiheutti virheen. Esimerkiksi virhe, jonka mukaan tietoja ei ole riittävästi tarkkaan ennusteeseen, ratkaistaan tyypillisesti lataamalla lisää tietoja.

## <a name="refresh-a-prediction"></a>Ennusteen päivittäminen

Ennusteet päivittyvät automaattisesti saman [aikataulun mukaan kuin tiedot päivitetään](system.md#schedule-tab) asetuksissa määritetyllä tavalla.

1. Siirry **Omat ennusteet** -välilehteen kohdassa **Älykäs toiminto** > **Ennusteet**.
1. Valitse päivitettävän ennusteen vieressä olevat allekkaiset pisteet.
1. Valitse **Päivitä**.

## <a name="delete-a-prediction"></a>Ennusteen poistaminen

1. Siirry **Omat ennusteet** -välilehteen kohdassa **Älykäs toiminto** > **Ennusteet**.
1. Valitse poistettavan ennusteen vieressä olevat allekkaiset pisteet.
1. Valitse **Poista**.

> [!NOTE]
> Ennusteen poistaminen poistaa sen tulosentiteetin.
