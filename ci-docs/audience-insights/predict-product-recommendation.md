---
title: Tuotesuosituksen ennuste
description: Ennusta tuotteet, joita asiakas todennäköisesti ostaa tai joiden kanssa asiakas on tekemisissä.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5ae78b6bbc51fd8a25bc408050a23479698a1414
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598059"
---
# <a name="product-recommendation-prediction-preview"></a>Tuotesuosituksen ennuste (esiversio)

Tuotesuositusmalli luo ennakoivia tuotesuositusjoukkoja. Suositukset perustuvat aiempaan ostokäyttäytymiseen ja asiakkaisiin, joilla on samanlaisia ostomalleja. Voit luoda uusia tuotesuosituksen ennusteita **Analytiikka** > **Ennusteet** -sivulla Valitse **Omat ennusteet**, kun haluat nähdä muita luomiasi ennusteita.

Tuotesuosituksia voivat koskea paikalliset lait ja säädökset sekä asiakkaiden odotukset. Tätä mallia ei ole erityisesti suunniteltu ottamaan näitä huomioon.  Tämän ennakoivan ominaisuuden käyttäjän **on tarkistettava suositukset ennen niiden toimittamista asiakkaille**. Näin varmistetaan, että ne noudattavat kaikkia lakeja ja säädöksiä sekä asiakkaan toiveita. 

Lisäksi tämän mallin tulos antaa suosituksia tuotetunnuksen perusteella. Toimitusmenetelmän on otettava ennustetut tuotetunnukset ja yhdistettävä ne asiakkaiden soveltuvaan sisältöön. Näin otetaan huomioon lokalisointi, kuvan sisältö ja muu yrityskohtainen sisältö tai toiminta.

## <a name="sample-guide"></a>Esimerkkiopas

Jos haluat kokeilla tätä ominaisuutta, mutta sinulla ei ole tietoja alla mainittujen vaatimusten täyttämiseksi, voit [luoda esimerkkitoteutuksen](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Edellytykset

- Vähintään [osallistujan oikeudet](permissions.md) Customer Insightsissa.
- Liiketoiminnan tietämystä, joka auttaa ymmärtämään liiketoiminnan tuotteiden erilaisia tyyppejä ja sitä, miten asiakkaat käyttävät niitä. Tuemme sellaisten tuotteiden suosittelemista, joita asiakkaat ovat ostaneet aiemmin, tai uusien tuotteiden suosittelemista.
- Tietoja tapahtumista ja ostoista sekä niiden historiasta:
    - Tapahtumatunnisteet erottavat ostot ja tapahtumat toisistaan.
    - Asiakastunnisteet, joilla tapahtumat yhdistetään asiakkaisiin.
    - Tapahtuman tapahtumapäivämäärät, jotka määrittävät tapahtuman tapahtumispäivämäärät.
    - (Valinnainen) Tapahtuman tuotetunnustiedot.
    - (Valinnainen) Määrittää, onko tapahtuma palautus vai ei.
    - Semanttiseen tietorakenteeseen tarvitaan seuraavat tiedot:
        - **Tapahtuma tunnus:** oston tai tapahtuman yksilöivä tunnus.
        - **Tapahtuman päivämäärä:** oston tai tapahtuman päivämäärä.
        - **Tapahtuman arvo:** oston tai tapahtuman numeroarvoinen summa.
        - **Yksilöivä tuotetunnus:** ostetun tuotteen tai palvelun tunnus, jos tieto on rivitasolla.
        - (Valinnainen) **Osto tai palautus:** tosi/epätosi-kenttä ilmaisee, oliko tapahtuma palautus vai ei. Jos **Tapahtuman arvo** on negatiivinen, myös tällä tiedolla viitataan palautukseen.


## <a name="create-a-product-recommendation-prediction"></a>Tuotesuosituksen ennusteen luominen

1. Siirry Customer Insightsissa kohtaan **Älykäs toiminto** > **Ennusteet**.

1. Valitse **Tuotesuositusten malli (esiversio)** -ruudussa **Käytä tätä mallia**.
   > [!div class="mx-imgBorder"]
   > ![Tuotesuositusmalli-ruutu ja Käytä tätä mallia -painike](media/product-recommendation-usethismodel.PNG "Tuotesuositusmalli-ruutu ja Käytä tätä mallia -painike")

1. Tutustu mallivaatimusten tietoihin. Jos sinulla on tarvittavat tiedot, valitse **Aloitus**.

### <a name="name-model"></a>Nimimalli

1. Anna mallille nimi, joka erottaa sen muista malleista.

1. Syötä tulosentiteetin nimi käyttämällä vain kirjaimia ja numeroita ilman välilyöntejä. Se on nimi, jota mallientiteetti käyttää. Valitse sitten **Seuraava**.

### <a name="define-product-recommendation-configuration"></a>Tuotesuositusmäärityksen määrittäminen

1. Määritä **Tuotteiden määrä**, jota haluat suositella asiakkaalle. Arvo riippuu siitä, miten toimitusmenetelmä täyttää tiedot. Jos voit suositella kolmea tuotetta, määritä tämä arvo vastaavasti.
   
   >[!TIP]
   > Voit valita **Tallenna ja sulje** milloin tahansa, jos haluat tallentaa ennusteen luonnokseksi. Ennusteluonnos on **Omat ennusteet** -välilehdessä.

1. Määritä, haluatko **ehdottaa tuotteita, jotka asiakkaat ovat äskettäin ostaneet**.

1. Jos olet määrittänyt, että äskettäin ostettuja tuotteita *ei* suositella, määritä arvoksi **Katso taaksepäin -ikkuna**. Tämä määritys määrittää aikavälin, jonka malli odottaa, ennen kuin suosittelee tuotetta käyttäjälle uudelleen. Voit esimerkiksi määrittää, että asiakas ostaa kannettavan tietokoneen joka toinen vuosi. Tässä ikkunassa näkyy kahden edellisen vuoden ostohistoria. Jos nimike löytyy, se suodatetaan suosituksista.

1. Valitse **Seuraava**

### <a name="add-required-data"></a>Lisää pakolliset tiedot

1. Valitse **Lisää tiedot** **Asiakkaan tapahtumahistoria** -kohdassa ja valitse entiteetti, josta saadaan tapahtuma- tai ostohistorian tiedot [edellytyksissä](#prerequisites) kuvatulla tavalla.

1. Yhdistä semanttiset kentät määritteisiin ostohistoriaentiteetissä ja valitse **Seuraava**. Lisätietoja kentistä on [edellytyksissä](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Entiteettisuhteen määrittäminen](media/product-recommendation-purchasehistorymapping.PNG "Ostohistoria-sivulla näkyvät semanttiset määritteet, jotka on yhdistetty valitun ostohistoriaentiteetin kenttiin")

1. Jos alla olevia kenttiä ei ole täytetty, määritä ostohistoriaentiteetin suhde *asiakasentiteettiin*.
    1. Valitse **Ostohistorian entiteetti**.
    1. Valitse **kenttä**, joka määrittää asiakkaan ostohistorian entiteetissä. Sen on liityttävä ensisijaisen asiakkaan tunnukseen *asiakasentiteetissä*.
    1. Valitse **Asiakasentiteetti**, joka vastaa ensisijaista asiakasentiteettiä.
    1. Anna suhdetta kuvaava nimi.
       > [!div class="mx-imgBorder"]
       > ![Ostohistoriasivu, jossa näkyy suhteen luominen asiakkaaseen](media/model-purchase-join.png "Ostohistoriasivu, jossa näkyy suhteen luominen asiakkaaseen")

1. Valitse **Tallenna**.

1. Valitse **Seuraava**.

### <a name="set-schedule-and-review-configuration"></a>Määritä aikataulu ja tarkista määritys

1. Määritä mallin uudelleenkouluttamistiheys. Tämä asetus on tärkeä ennusteiden tarkkuuden päivittämiseksi, kun Customer Insightsiin tuodaan uusia tietoja. Useimmat yritykset voivat uudelleenkouluttaa kerran kuukaudessa ja saada hyvän tarkkuuden ennusteille.

1. Valitse **Seuraava**.

1. Tarkista määritys. Voit palata mihin tahansa ennustemäärityksen osaan valitsemalla **Muokkaa** annetun arvon kohdassa. Voit myös valita määritysvaiheen edistymisen ilmaisimesta.

1. Jos kaikki arvot on määritetty oikein, aloita ennusteprosessi valitsemalla **Tallenna ja suorita**. **Omat ennusteet** -välilehdessä voit tarkastella ennusteiden tilaa. Prosessin valmistumiseen voi kulua useita tunteja ennusteessa käytettyjen tietojen määrästä riippuen.

## <a name="review-a-prediction-status-and-results"></a>Ennusteen tilan ja tulosten tarkasteleminen

1. Siirry **Omat ennusteet** -välilehteen kohdassa **Älykäs toiminto** > **Ennusteet**.
   > [!div class="mx-imgBorder"]
   > ![Omat ennusteet -sivun tarkasteleminen](media/product-recommendation-mypredictions.PNG "Omat ennusteet -sivun tarkasteleminen")

1. Valitse ennuste, jota haluat tarkastella.
   - **Ennusteen nimi:** Ennusteelle luomisen yhteydessä annettu nimi.
   - **Ennustetyyppi:** Ennusteessa käytetyn mallin tyyppi.
   - **Tulosentiteetti:** Sen entiteetin nimi, johon ennusteen tulos tallennetaan. Tämänniminen entiteetti löytyy kohdasta **Tiedot** > **Entiteetit**.
   - **Ennustettu kenttä:** tämä kenttä täytetään vain tietyissä ennustetyypeissä eikä sitä käytetä vaihtuvuusennusteessa.
   - **Tila:** Ennusteen suoritumisen nykyinen tila.
        - **Jonossa:** Ennuste odottaa parhaillaan muiden prosessien suorittamista.
        - **Päivitys:** Ennusteessa suoritetaan parhaillaan käsittelyn tulosvaihetta. Sen avulla saadaan tulokset, jotka siirretään tulosentiteettiin.
        - **Epäonnistui:** Ennuste on epäonnistunut. Jos haluat lisätietoja, valitse **Lokit**.
        - **Onnistui:** Ennuste on onnistunut. Valitse allekkaisten pisteiden alla oleva **Tarkastele**-kohta, jos haluat tarkastella ennustetta.
   - **Muokattu:** Ennusteen määrityksen muutospäivämäärä.
   - **Viimeinen päivitys:** Päivämäärä, jona ennuste päivitti tulokset tulosentiteettiin.

1. Valitse sen ennusteen vieressä olevat allekkaiset pisteet, jonka tuloksia haluat tarkastella, ja valitse **Näytä**.
   > [!div class="mx-imgBorder"]
   > ![Tarkastele allekkaisten pisteiden valikon vaihtoehtoja, esimerkiksi muokkausta, päivittämistä, tarkastelemista, lokeja ja poistamista](media/product-recommendation-verticalellipses.PNG "Tarkastele allekkaisten pisteiden valikon vaihtoehtoja, esimerkiksi muokkausta, päivittämistä, tarkastelemista, lokeja ja poistamista")

1. Tulossivulla on seuraavat kolme ensisijaista tieto-osaa:
    1. **Opetusmallin suorituskyky:** A, B ja C ovat mahdollisia pistemääriä. Tämä pistemäärä osoittaa ennusteen suorituskyvyn. Sen avulla voit tehdä päätöksen tulosentiteettiin tallennettujen tulosten käyttämisestä.
        - Pistemäärät määritetään seuraavien sääntöjen perusteella:
            - **A** Mallia pidetään **A**-laatuna, jos Menestys @ K -mittarin arvo on vähintään 10 % enemmän kuin perustaso. 
            - **B** Mallia pidetään **B**-laatuna, jos Menestys @ K -mittarin arvo on 0–10 % enemmän kuin perustaso.
            - **C** Mallia pidetään **C**-laatuna, jos Menestys @ K -mittarin arvo on vähemmän kuin perustaso.
               
               > [!div class="mx-imgBorder"]
               > ![Tarkastele mallin suorituskyvyn tulosta](media/product-recommendation-modelperformance.PNG "Tarkastele mallin suorituskyvyn tulosta")
            - **Perustaso**: Malli käyttää kaikkien asiakkaiden ostomäärien mukaisia suositelluimpia tuotteita ja mallin määrittämiä opittuja sääntöjä asiakkaiden suositusjoukon luomisessa. Ennusteita vertaillaan sen jälkeen myydyimpiin tuotteisiin tuotteen ostaneiden asiakkaiden määrän mukaan laskettuna. Jos asiakkaan suositelluissa tuotteissa on vähintään yksi tuote, joka on myös myydyimpien tuotteiden joukossa, heitä pidetään perustason asiakkaina. Jos 10 asiakasta yhteensä 100 asiakkaasta on suositellut ostettua tuotetta, perustaso on 10 %.
            - **Menestys @ K**: Suositukset luodaan kaikille asiakkaille käyttämällä tapahtumien ajanjakson tarkistusjoukkoa. Tämän jälkeen niitä verrataan tapahtumien tarkistusjoukkoihin. Esimerkiksi 12 kuukauden jakson aikana kuukausi 12 voidaan jättää pois tietojen tarkistusjoukoksi. Jos malli ennustaa vähintään yhden oston kuukauden 12 aikana edellisten 11 kuukauden tietojen perusteella, asiakas kasvattaa Menestys @ K -mittarin arvoa.
    
    1. **Useimmiten ehdotetut tuotteet (laskun mukaan):** Eniten myydyt 5 tuotetta, joita asiakkaille suositeltiin.
       > [!div class="mx-imgBorder"]
       > ![Kaavio, jossa on 5 eniten suositeltua tuotetta](media/product-recommendation-topproducts.PNG "Kaavio, jossa on 5 eniten suositeltua tuotetta")
    
    1. **Erittäin luotettavat tuotesuositukset:** Asiakkaille annettujen suositusten esimerkki tuotteista, joita malli olettaa asiakkaan ostavan.
       > [!div class="mx-imgBorder"]
       > ![Luettelo, jossa näkyvät erittäin luotettavat suositukset valitulle yksittäisten asiakkaiden joukolle](media/product-recommendation-highconfidence.PNG "Luettelo, jossa näkyvät erittäin luotettavat suositukset valitulle yksittäisten asiakkaiden joukolle")

## <a name="fix-a-failed-prediction"></a>Epäonnistuneen ennusteen korjaaminen

1. Siirry **Omat ennusteet** -välilehteen kohdassa **Älykäs toiminto** > **Ennusteet**.

1. Valitse ennuste, jonka virhelokeja haluat tarkastella. Valitse sitten **Lokit**.

1. Tarkastele kaikkia virheitä. Mahdollisia virhe tyyppejä on useita. Ne osoittavat, mikä ehto aiheutti virheen. Esimerkiksi virhe, joka osoittaa olemassa olevien tietojen olevan riittämättömät tarkan ennusteen luomiseksi, ratkaistaan yleensä lataamalla lisää tietoja Customer Insightsiin.

## <a name="refresh-a-prediction"></a>Ennusteen päivittäminen

Ennusteet päivittyvät automaattisesti asetuksissa määritetyllä [aikataululla, jolla tiedotkin päivitetään](system.md#schedule-tab).

1. Siirry **Omat ennusteet** -välilehteen kohdassa **Älykäs toiminto** > **Ennusteet**.

1. Valitse päivitettävän ennusteen vieressä olevat allekkaiset pisteet.

1. Valitse **Päivitä**.

## <a name="delete-a-prediction"></a>Ennusteen poistaminen

Ennusteen poistaminen poistaa myös sen tuloste-entiteetin.

1. Siirry **Omat ennusteet** -välilehteen kohdassa **Älykäs toiminto** > **Ennusteet**.

1. Valitse poistettavan ennusteen vieressä olevat allekkaiset pisteet.

1. Valitse **Poista**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]