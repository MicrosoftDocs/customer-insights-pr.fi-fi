---
title: Tapahtuman vaihtuvuusennuste
description: Sen riskin ennustaminen, että asiakas ei enää osta yrityksen tuotteita tai palveluja.
ms.date: 11/12/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f3cbbf99a6cecba2aab2cf85428d53e5df8346e4
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644399"
---
# <a name="transactional-churn-prediction-preview"></a>Tapahtuman vaihtuvuusennuste (esiversio)

Tapahtuman vaihtuvuusennuste auttaa ennustamaan, ostaako asiakas vielä tuotteita tai palveluja annetulla ajanjaksolla. Voit luoda uusia vaihtuvuusennusteita valitsemalla **Analytiikka** > **Ennusteet**. Valitse **Omat ennusteet**, kun haluat nähdä muita luomiasi ennusteita.

> [!TIP]
> Kokeile tapahtuman vaihtuvuusennusteen opasohjelmaa näytetietojen avulla: [Tapahtuman vaihtuvuusennusteen (esiversion) näyteopas](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Edellytykset

- Vähintään [osallistujan oikeudet](permissions.md) Customer Insightsissa.
- Liiketoiminnan tietämys, jonka avulla tiedät, mitä vaihtuvuus merkitsee yrityksellesi. Aikaperusteista vaihtuvuusmääritelmiä tuetaan, joten asiakkaan katsotaan vaihtuneen tietyn ostamattoman ajanjakson jälkeen.
- Tietoja tapahtumista ja ostoista sekä niiden historiasta:
    - Tapahtumatunnisteet erottavat ostot ja tapahtumat toisistaan.
    - Asiakastunnisteet, joilla tapahtumat yhdistetään asiakkaisiin.
    - Tapahtuman tapahtumapäivämäärät, jotka määrittävät tapahtuman tapahtumispäivämäärät.
    - Ostojen ja tapahtumien semanttiseen tietorakenteeseen tarvitaan seuraavat tiedot:
        - **Tapahtuma tunnus:** oston tai tapahtuman yksilöivä tunnus.
        - **Tapahtuman päivämäärä:** oston tai tapahtuman päivämäärä.
        - **Tapahtuman arvo:** tapahtuman tai nimikkeen valuutta tai numeroarvoinen summa.
        - (Valinnainen) **Yksilöivä tuotetunnus:** ostetun tuotteen tai palvelun tunnus, jos tieto on rivitasolla.
        - (Valinnainen) **Tieto siitä, oliko tämä tapahtuma palautus:** Tosi/epätosi-kenttä ilmaisee, oliko tapahtuma palautus vai ei. Jos **Tapahtuman arvo** on negatiivinen, myös tällä tiedolla viitataan palautukseen.
- (Valinnainen) Tietoja asiakkaan aktiviteeteista:
    - Aktiviteetin tunnisteet, joiden avulla saman tyypin aktiviteetit erotetaan toisistaan.
    - Asiakastunnisteet, joiden avulla aktiviteetit yhdistetään asiakkaisiin.
    - Aktiviteetin tiedot, jotka sisältävät aktiviteetin nimen ja päivämäärän.
    - Asiakasaktiviteettien semanttinen tietorakenne sisältää seuraavat tiedot:
        - **Perusavain:** Aktiviteetin yksilöllinen tunniste. Esimerkiksi sivustovierailu tai käyttötietue, joka osoittaa, että asiakas kokeile tuotenäytettä.
        - **Aikaleima:** Ensisijaisen avaimen tunnistaman tapahtuman päivämäärä ja aika.
        - **Tapahtuma:** Sen tapahtuman nimi, jota haluat käyttää. Esimerkiksi elintarvikemyymälän UserAction-kenttä voisi olla asiakkaan käyttämä kuponki.
        - **Tiedot:** Tapahtuman yksityiskohtaiset tiedot. Esimerkiksi elintarvikemyymälän CouponValue-kenttä voisi olla kupongin valuutta-arvo.

## <a name="create-a-transactional-churn-prediction"></a>Tapahtuman vaihtuvuusennusteen luominen

1. Siirry Customer Insightsissa kohtaan **Älykäs toiminto** > **Ennusteet**.

1. Valitse **Asiakasvaihtuvuusmalli (esiversio)** -ruudussa **Käytä tätä mallia**.
   
1. Valitse **Asiakasvaihtuvuusmalli** -ruudussa ensin **Tapahtuma** ja sitten **Aloita**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Näyttökuva, jos on valittu tapahtumavaihtoehto Asiakasvaihtuvuusmalli-ruudussa.":::

### <a name="name-model"></a>Nimimalli

1. Anna mallille nimi, joka erottaa sen muista malleista.

1. Anna tulosentiteetille nimi käyttämällä vain kirjaimia ja numeroita. Välilyöntejä ei voi käyttää. Se on nimi, jota mallientiteetti käyttää. 

1. Valitse **Seuraava**.

### <a name="define-customer-churn"></a>Määritä asiakasvaihtuma

1. Määritä vaihtuvuusennusteen aikaikkuna **Tunnista asiakkaat, jotka saattavat vaihtaa tilauksen seuraavassa** -kentässä. Ennustetaan esimerkiksi asiakkaiden vaihtuvuusriski seuraavan 90 päivän aikana siten, että se on linjassa markkinoinnin säilyttämispyrkimysten kanssa. Vaihtuvuusriskin ennusteen pituus voi hankaloittaa vaihtuvuusriskiprofiilissa olevien seikkojen huomioon ottamista; tämä kuitenkin määräytyy liiketoimintakohtaisten tarpeiden mukaan. 
   >[!TIP]
   > Voit valita **Tallenna ja sulje** milloin tahansa, jos haluat tallentaa ennusteen luonnokseksi. Näkyviin tulee ennusteluonnos **Omat ennusteet** -välilehdessä.

1. Anna vaihtuvuuden määrittävän päivien määrä **Asiakkaan katsotaan vaihtuneen, jos hän ei ole tehnyt ostoksia:** -kentässä. Jos asiakas ei ole esimerkiksi tehnyt ostoja 30 päivän aikana, heidän voidaan katsoa vaihtuneen liiketoiminnassa. 

1. Jatka valitsemalla **Seuraava**

### <a name="add-required-data"></a>Lisää pakolliset tiedot

1. Valitse **Lisää tiedot** **Ostohistoria**-kohdassa ja valitse entiteetti, josta saadaan tapahtuma- tai ostohistorian tiedot [edellytyksissä](#prerequisites) kuvatulla tavalla.

1. Yhdistä semanttiset kentät määritteisiin ostohistoriaentiteetissä ja valitse **Seuraava**. Lisätietoja kentistä on [edellytyksissä](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Ostohistorian semanttisten kenttien yhdistäminen":::

1. Jos alla olevia kenttiä ei ole täytetty, määritä ostohistoriaentiteetin suhde asiakasentiteettiin.
    1. Valitse **Ostohistorian entiteetti**.
    1. Valitse **kenttä**, joka määrittää asiakkaan ostohistorian entiteetissä. Sen on liityttävä ensisijaisen asiakkaan tunnukseen asiakasentiteetissä.
    1. Valitse **Asiakasentiteetti**, joka vastaa ensisijaista asiakasentiteettiä.
    1. Anna suhdetta kuvaava nimi.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Ostohistoriasivu, jossa näkyy suhteen luonti asiakkaaseen":::
   
1. Valitse **Seuraava**.

1. Vaihtoehtoisesti voit valita **Lisää tiedot** **Asiakasaktiviteetit**-kohdassa. Valitse entiteetti, jossa on asiakasaktiviteetin tiedot, edellytyksissä kuvatulla tavalla.

1. Yhdistä semanttiset kentät määritteisiin asiakasaktiviteettientiteetissä ja valitse **Seuraava**. Lisätietoja kentistä on [edellytyksissä](#prerequisites).

1. Valitse aktiviteettityyppi, joka vastaa määrittämiesi asiakkaan aktiviteetin tyyppiä. Valitse **Luo uusi** ja valitse käytettävissä oleva aktiviteettityyppi tai luo uusi tyyppi.

1. Sinun täytyy määrittää suhde asiakkaan aktiviteetin entiteetistä asiakasentiteettiin.
    1. Valitse kenttä, joka määrittää asiakkaan asiakasaktiviteettitaulukossa. Se voi liittyä suoraan asiakasentiteetin ensisijaiseen asiakastunnukseen.
    1. Valitse asiakasentiteetti, joka vastaa ensisijaista asiakasentiteettiä.
    1. Anna suhdetta kuvaava nimi.

1. Valitse **Tallenna**.

1. Jos haluat sisällyttää muita asiakasaktiviteetteja, toista edellä olevat vaiheet.

1. Valitse **Seuraava**.

### <a name="set-schedule-and-review-configuration"></a>Määritä aikataulu ja tarkista määritys

1. Määritä mallin uudelleenkouluttamistiheys. Tämä asetus on tärkeä ennusteiden tarkkuuden päivityksessä uusia tietoja käsiteltäessä. Useimmat yritykset voivat uudelleenkouluttaa kerran kuukaudessa ja saada hyvän tarkkuuden ennusteille.

1. Valitse **Seuraava**.

1. Tarkista ennusteen määritys. Voit palata edellisiin vaiheisiin valitsemalla **Muokkaa** näytetyssä arvossa. Voit myös valita määritysvaiheen edistymisen ilmaisimesta.

1. Jos kaikki arvot on määritetty oikein, aloita ennusteprosessi valitsemalla **Tallenna ja suorita**. **Omat ennusteet** -välilehdessä voit tarkastella ennusteiden tilaa. Prosessin valmistumiseen voi kulua useita tunteja ennusteessa käytettyjen tietojen määrästä riippuen.

## <a name="review-a-prediction-status-and-results"></a>Ennusteen tilan ja tulosten tarkasteleminen

1. Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.

1. Valitse ennuste, jota haluat tarkastella.
   - **Ennusteen nimi:** ennusteelle luotaessa annettu nimi.
   - **Ennustetyyppi:** ennusteessa käytetyn mallin tyyppi
   - **Tulosentiteetti:** Sen entiteetin nimi, johon ennusteen tulos tallennetaan. Tämänniminen entiteetti löytyy kohdasta **Tiedot** > **Entiteetit**.
   - **Ennustettu kenttä:** tämä kenttä täytetään vain tietyissä ennustetyypeissä eikä sitä käytetä vaihtuvuusennusteessa.
   - **Tila:** ennusten suorituksen tila.
        - **Jonossa:** ennuste odottaa muiden prosessien suorittamista.
        - **Päivittyy:** suoritettavan ennusteen tulokset siirretään tuloste-entiteettiin.
        - **Epäonnistui:** Ennusteen suorittaminen epäonnistui. Lisätietoja saa [lokeja tarkastelemalla](#troubleshoot-a-failed-prediction).
        - **Onnistui:** Ennuste onnistui. Valitse allekkaisten pisteiden alla oleva **Tarkastele**-kohta, jos haluat tarkastella ennustetta.
   - **Muokattu:** Ennusteen määrityksen muutospäivämäärä.
   - **Viimeinen päivitys:** Päivämäärä, jona ennuste päivitti tulokset tulosentiteettiin.

1. Valitse sen ennusteen vieressä olevat allekkaiset pisteet, jonka tuloksia haluat tarkastella, ja valitse **Näytä**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Ennusteen tulosten näyttäminen näkymän ohjausobjektilla":::   

1. Tulossivulla on seuraavat kolme ensisijaista tieto-osaa:
    1. **Opetusmallin suorituskyky:** A, B ja C ovat mahdollisia pistemääriä. Tämä pistemäärä osoittaa ennusteen suorituskyvyn. Sen avulla voit tehdä päätöksen tulosentiteettiin tallennettujen tulosten käyttämisestä. Pistemäärät määritetään seuraavien sääntöjen perusteella:
         
         - **A**, kun mallin tarkkuudeksi on ennustettu vähintään 50 % ennusteesta yhteensä ja kun vaihtuvuusasiakkaiden tarkka ennusteprosentti on ainakin 10 % suurempi kuin lähtöarvo.
            
         - **B**, kun mallin tarkkuudeksi on ennustettu vähintään 50 % ennusteesta yhteensä ja kun vaihtuvuusasiakkaiden tarkka ennusteprosentti on enintään 10 % suurempi kuin lähtöarvo.
            
         - **C**, kun mallin tarkkuudeksi on ennustettu alle 50 % ennusteesta yhteensä tai kun vaihtuvuusasiakkaiden tarkka ennusteprosentti on pienempi kuin lähtöarvo.
               
         - **Lähtöarvo** käyttää mallin ennusteen aikaikkunan (kuten yhden vuoden) ja malli luo eri aikajakoja jakamalla sen kahdella, kunnes tuloksena on yksi kuukausi tai sitä lyhyempi jakso. Se luo liiketoimintasäännön näiden osien avulla asiakkaille, jotka eivät ole tehneet ostona kyseisellä aikavälillä. Näiden asiakkaiden katsotaan vaihtuneen. Lähtöarvomalliksi valitaan aikaperusteinen liiketoimintasääntö, joka ennustaa parhaiten todennäköisen vaihtuvuuden.
            
    1. **Vaihtuvuuden todennäköisyys (asiakkaiden määrä):** Asiakasryhmät ennustetun vaihtuvuusriskin perusteella. Nämä tiedot auttavat myöhemmin, jos haluat luoda asiakassegmentin, jolla on suuri vaihtuvuusriski. Tällaiset segmentit auttavat ymmärtämään, missä segmentin jäsenyyden rajan on oltava.
       
    1. **Tärkeimmät tekijät:** Ennusteen luomisessa otetaan huomioon useita tekijöitä. Kunkin tekijän tärkeys lasketaan mallin luomille kooste-ennusteille. Näiden tekijöiden avulla voit tarkistaa ennusteen tulokset. Tai voit käyttää näitä tietoja myöhemmin ja [luoda segmenttejä](segments.md), joiden avulla voit vaikuttaa asiakkaiden vaihtuvuusriskiin.

## <a name="troubleshoot-a-failed-prediction"></a>Epäonnistuneen ennusteen vianmääritys

1. Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.

1. Valitse kolme allekkain olevaa pistettä sen ennusteen vieressä, jonka virhelokeja haluat tarkastella.

1. Valitse **Lokit**.

1. Tarkastele kaikkia virheitä. Mahdollisia virhe tyyppejä on useita. Ne osoittavat, mikä ehto aiheutti virheen. Esimerkiksi virhe, joka osoittaa olemassa olevien tietojen olevan riittämättömät tarkan ennusteen luomiseksi, ratkaistaan yleensä lataamalla lisää tietoja Customer Insightsiin.

## <a name="refresh-a-prediction"></a>Ennusteen päivittäminen

Ennusteet päivittyvät automaattisesti saman [aikataulun mukaan kuin tiedot päivitetään](system.md#schedule-tab) asetuksissa määritetyllä tavalla. Voit päivittää ne myös manuaalisesti.

1. Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.

1. Valitse päivitettävän ennusteen vieressä olevat allekkaiset pisteet.

1. Valitse **Päivitä**.

## <a name="delete-a-prediction"></a>Ennusteen poistaminen

Ennusteen poistaminen poistaa myös sen tuloste-entiteetin.

1. Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.

1. Valitse poistettavan ennusteen vieressä olevat allekkaiset pisteet.

1. Valitse **Poista**.
