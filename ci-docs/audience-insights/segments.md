---
title: Segmenttien luonti ja hallinta
description: Luo asiakassegmenttejä ja ryhmittele ne eri määritteiden perusteella.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270352"
---
# <a name="create-and-manage-segments"></a>Segmenttien luonti ja hallinta

Segmenttien avulla asiakkaita ryhmitellä demografia-, tapahtuma- tai toimintamääritteiden perusteella. Segmenttejä käyttämällä voit kohdistaa markkinointikampanjoita, myyntiaktiviteetteja ja asiakastukitoimintoja liiketoiminnan tavoitteiden saavuttamiseksi.

Voit määrittää asiakasprofiilientiteetin ja sen liittyvien entiteettien ympärille monimutkaisia suodattimia. Kukin segmentti luo käsittelyn jälkeen joukon asiakastietueita, joita voit viedä ja joihin voit tehdä toimintoja. Käytössä on jotakin [palvelurajoituksia](service-limits.md).

Ellei toisin mainita, kaikki segmentit ovat **dynaamisia segmenttejä**, jotka päivitetään toistuvan aikataulun mukaisesti.

Seuraava esimerkki kuvaa segmentointiominaisuutta. Olemme määritelleet segmentin asiakkaille, jotka tilasivat vähintään 500 dollarilla tavaraa viimeisen 90 päivän aikana *ja* jotka olivat mukana eskaloidussa asiakaspalvelupuhelussa.

> [!div class="mx-imgBorder"]
> ![Useita ryhmiä](media/segmentation-group1-2.png "Useita ryhmiä")

## <a name="create-a-new-segment"></a>Luo uusi segmentti

Segmenttejä hallitaan **Segmentit**-sivulla.

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Segmentit**-sivu.

2. Valitse **Uusi** > **Tyhjä segmentti**.

3. Valitse **Uusi segmentti** -ruudussa segmentin tyyppi ja anna **nimi**.

   Vaihtoehtoisesti voit antaa näyttönimen ja kuvauksen, joiden avulla segmentin voi tunnistaa.

4. Kun valitset **Seuraava**, näyttöön avautuu **Segmentin muodostin** -sivu, jolla voit määrittää ryhmän. Ryhmä on joukko asiakkaita.

5. Valitse sen määritteen sisältävä entiteetti, jonka mukaan segmentointi tehdään.

6. Valitse segmentointiperusteen määrite. Tällä määritteellä voi olla jokin neljästä arvotyypistä: numeerinen, merkkijono, päivämäärä tai totuusarvo.

7. Valitse operaattori ja arvo valitulle määritteelle.

   > [!div class="mx-imgBorder"]
   > ![Mukautettu ryhmäsuodatin](media/customer-group-numbers.png "Asiakkaan ryhmäsuodatin")

   |Luku |Määritelmä  |
   |---------|---------|
   |1     |Entity          |
   |2     |Määrite          |
   |3    |Operaattori         |
   |4    |Arvo         |

8. Jos entiteetti on yhdistetty yhdistettyyn asiakaskohteeseen [suhteen](relationships.md) kautta , sinun täytyy määrittää suhdepolku, jotta voit luoda kelvollisen segmentin. Lisää entiteetit suhdepolusta, kunnes voit valita **Asiakas : CustomerInsights** -entiteetin avattavasta luettelosta. Valitse sitten jokaisessa ehdossa **Kaikki tietueet**.

   > [!div class="mx-imgBorder"]
   > ![Suhdepolku segmentin luonnin aikana](media/segments-multiple-relationships.png "Suhdepolku segmentin luonnin aikana")

9. Tallenna segmentti valitsemalla **Tallenna**. Segmentti tallennetaan ja käsitellään, jos kaikki vaatimukset on vahvistettu. Muussa tapauksessa se tallennetaan luonnoksena.

10. Valitse **Palaa segmentteihin**, jos haluat siirtyä takaisin **Segmentit**-sivulle.

## <a name="manage-existing-segments"></a>Aiemmin luotujen segmenttien hallinta

**Segmentit**-sivulla voit tarkastella kaikkia tallennettuja segmenttejä ja hallita niitä.

Jokaista segmenttiä edustaa rivi, joka sisältää segmentin lisätietoja.

Voit lajitella sarakkeen segmentit valitsemalla sarakeotsikon.

Voit suodattaa segmenttejä oikeassa yläkulmassa olevan **Haku**-ruudun avulla.

> [!div class="mx-imgBorder"]
> ![Aiemmin luodun segmentin hallintavaihtoehdot](media/segments-selected-segment.png "Aiemmin luodun segmentin hallintavaihtoehdot")

Seuraava toiminto on käytettävissä, kun valitse segmentin:

- **Näytä** segmentin tietoja, mukaan lukien jäsenmäärän trendi, segmentin jäsenten esikatselu.
- **Muokkaa** segmenttiä, jos haluat muuttaa sen ominaisuuksia.
- **Päivitä** segmentti siten, että se sisältää uusimmat tiedot.
- **Aktivoi** segmentti tai **Poista aktivointi**. Segmenteillä on kaksi mahdollista tilaa: aktiivinen ja passiivinen. Näistä tiloista on hyötyä segmenttiä muokattaessa. Passiivisissa segmenteissä on segmentin määritelmä, mutta se ei sisällä vielä asiakkaita. Kun segmentti aktivoidaan, tila muuttuu passiivisesta aktiivisesti ja se aloittaa segmentin määritelmää vastaavien asiakkaiden etsimisen. Jos [aikataulutettu päivitys](system.md#schedule-tab) on määritetty, passiivisten segmenttien **Tila**-arvon on **Ohitettu**, mikä osoittaa, että päivitystä ei edes yritetty. Kun passiivinen segmentti aktivoidaan, se päivittyy ja se sisällytetään aikataulutettuihin päivityksiin.
  Voit vaihtoehtoisesti määrittää tulevan päivämäärän ja kellonajan tietyn segmentin aktivointiin ja aktivoinnin poistamiseen avattavan **Aktivoi / Poista aktivointi** -valikon **Ajoita myöhemmin** -toiminnolla.
- **Nimeä uudelleen** segmentti.
- **Lataa** jäsenten luettelo CSV-tiedostona.
- **Lisää kohteeseen** -vaihtoehto lähettää segmentin asiakastunnusten luettelon toiseen sovelluksen käsiteltäväksi.
- **Poista** segmentti.

## <a name="refresh-segments"></a>Päivitä segmentit

Voit päivittää kaikki segmentit kerralla valitsemalla **Päivitä kaikki** **Segmentit**-sivulla. Halutessasi voit päivittää yhden tai useita segmenttejä, kun valitset ne ja valitse sitten **Päivitä** asetuksista. Voit myös määrittää toistuvan päivityksen kohdassa **Järjestelmänvalvoja** > **Järjestelmä** > **Ajoita**.

> [!TIP]
> Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types). Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies). Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja. Kun työn jossakin tehtävissä on valittu **Näytä tiedot**, saat lisätietoja: käsittelyajan, viimeisimmän käsittelypäivämäärän sekä kaikki tehtävään liitetyt virheet ja varoitukset.

## <a name="download-and-export-segments"></a>Segmenttien lataaminen ja vieminen

Voit ladata segmenttejäsi CSV-tiedostoon tai viedä ne Dynamics 365 Salesiin.

### <a name="download-segments-to-a-csv-file"></a>Segmenttien lataaminen CSV-tiedostoon

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Segmentit**-sivu.

2. Valitse tietyn segmentin ruudussa kolme pistettä.

3. Valitse **Lataa CSV-tiedostona** toimintojen avattavasta luettelosta.

### <a name="export-segments-to-dynamics-365-sales"></a>Segmenttien vieminen Dynamics 365 Salesiin

Ennen segmenttien viemistä Dynamics 365 Salesiin järjestelmänvalvojan on [luotava vientikohde](export-destinations.md) Dynamics 365 Salesille.

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Segmentit**-sivu.

2. Valitse tietyn segmentin ruudussa kolme pistettä.

3. Valitse **Lisää kohteeseen** avattavasta toimintoluettelosta ja valitse sitten vientikohde, johon haluat lähettää tiedot.

## <a name="draft-mode-for-segments"></a>Segmenttien luonnostila

Jos kaikkia segmentin käsittelyssä tarvittavat vaatimukset eivät täyty, voit tallentaa segmentin luonnoksena ja käyttää sitä **Segmentit**-sivulla.

Se tallennetaan passiivisena segmenttinä, eikä sitä voi aktivoida, ennen kuin se on kelvollinen.

## <a name="add-more-conditions-to-a-group"></a>Lisää ryhmään ehtoja

Jos haluat lisätä ryhmään ehtoja, voit käyttää seuraavaa kahta loogista operaattoria:

- **JA**-operaattori: Molempien ehtojen on täytyttävä segmentointiprosessin aikana. Tämä vaihtoehto on hyödyllinen, kun määrität ehtoja eri entiteeteille.

- **TAI**-operaattori: Jommankumman ehdoista on täytyttävä segmentointiprosessin aikana. Tämä vaihtoehto on hyödyllinen, kun määrität useita ehtoja samalle entiteetille.

   > [!div class="mx-imgBorder"]
   > ![TAI-operaattori, jossa jommankumman ehdoista on täytyttävä](media/segmentation-either-condition.png "TAI-operaattori, jossa jommankumman ehdoista on täytyttävä")

Tällä hetkellä on mahdollista upottaa **TAI**-operaattoria **JA**-operaattorin sisään, mutta ei toisin päin.

## <a name="combine-multiple-groups"></a>Yhdistä useita ryhmiä

Kukin ryhmä tuottaa tietyn asiakasjoukon. Voit yhdistää nämä ryhmät niin, että ne sisältävät liiketoimintatapaukseesi tarvittavat asiakkaat.

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Segmentit**-sivu ja valitse sitten segmentti.

2. Valitse **Lisää ryhmä**.

   > [!div class="mx-imgBorder"]
   > ![Asiakasryhmä - lisää ryhmä](media/customer-group-add-group.png "Asiakasryhmä - lisää ryhmä")

3. Valitse jokin seuraavista operaattoreista: **Unioni**, **Leikkaus** tai **Lukuun ottamatta**.

   > [!div class="mx-imgBorder"]
   > ![Asiakasryhmä - lisää liitos](media/customer-group-union.png "Asiakasryhmä - lisää liitos")

   Määritä uusi ryhmä valitsemalla joukko-operaattori. Eri ryhmien tallentaminen määrittää säilytettävät tiedot:

   - **Liitos** yhdistää kaksi ryhmää.

   - **Leikkaa** asettaa kaksi ryhmää päällekkäin. Vain molemmille ryhmille *yhteiset* tiedot säilytetään yhdistetyssä ryhmässä.

   - **Lukuun ottamatta** yhdistää kaksi ryhmää. Vain ryhmän A tiedot, jotka *eivät ole yhteisiä* ryhmän B tietojen kanssa, säilytetään.

## <a name="view-processing-history-and-segment-members"></a>Tarkastele käsittelyhistoriaa ja segmentin jäseniä

Voit tarkastella segmentin yhdistettyjä tietoja tarkastelemalla sen tietoja.

Valitse **Segmentit**-sivulla segmentti, jota haluat tarkastella.

Sivun yläosassa on trendikaavio, joka visualisoi jäsenmäärän muutokset. Vie kohdistin arvopisteiden päälle, jos haluat nähdä tietyn päivämäärän jäsenmäärän.

Voit päivittää visualisoinnin aikavälin.

> [!div class="mx-imgBorder"]
> ![Segmentin aikaväli](media/segment-time-range.png "Segmentin aikaväli")

Alaosassa on luettelo segmentin jäsenistä.

> [!NOTE]
> Tässä luettelossa näkyvät kentät perustuvat segmentin entiteettien määritteisiin.
>
>Luettelo on täsmäävien segmentin jäsenten esikatselu. Siinä näkyvät segmentin ensimmäiset 100 tietuetta, joten voit nopeasti arvioida segmentin ja tarkistaa sen määritykset tarpeen mukaan. Jos haluat nähdä kaikki täsmäävät tietueet, sinun on [vietävä segmentti](export-destinations.md).

## <a name="quick-segments"></a>Pikasegmentit

Segmentin muodostimen lisäksi segmenttejä voi luoda myös toisella tavalla. Pikasegmenttien avulla voit luoda yksinkertaisia segmenttejä yhdellä operaattorilla nopeasti ja saat analyysit heti käyttöösi.

1. Valitse **Segmentit**-sivulla **Uusi** > **Pikaluontilomake**.

   - Valitse **Profiilit**-vaihtoehto, jos haluat muodostaa segmentin, joka perustuu yhdistettyyn asiakasentiteettiin.
   - Valitse **Mittarit**-vaihtoehto, jos haluat muodostaa segmentin kunkin aiemmin **Mittarit**-sivulla luotujen asiakasmääritetyyppisten mittareiden ympärille.
   - Valitse **Analytiikka**-asetus, jos haluat luoda segmentin, joka on luotu käyttämällä joko **Ennusteet**-tai **Mukautetut mallit** -ominaisuuden avulla luotuja tuloskohteita.

2. Valitse **Uusi pikasegmentti** -valintaikkunasta määrite avattavasta **Kenttä**-valikosta.

3. Järjestelmä tarjoaa lisätietoja, joiden avulla voit aiempaa helpommin luoda asiakkaille segmenttejä.
   - Luokkakentille näytetään 10 parasta asiakasmäärää. Valitse **Arvo** ja valitse sitten **Tarkista**.

   - Jos määrite on numeerinen, järjestelmä näyttää, mikä määrite kuuluu mihinkin asiakasprosenttipisteeseen. Valitse **Operaattori** ja **Arvo** ja valitse sitten **Tarkista**.

4. Järjestelmä näyttää **arvioidun segmentin koon**. Voit määrittää, luodaanko määritetty segmentti vai avataanko sen ensin, jolloin voit määrittää toisen segmentin koon.

    > [!div class="mx-imgBorder"]
    > ![Nopean segmentin nimi ja arvioi](media/quick-segment-name.png "Nopean segmentin nimi ja arvioi")

5. Anna segmentille **nimi**. Vaihtoehtoisesti voit antaa **näyttönimen**.

6. Luo segmentti valitsemalla **Tallenna**.

7. Kun segmentin käsittely on valmis, voit tarkistaa sen kuten minkä tahansa luodun segmentin.

Seuraavissa skenaarioissa suosittelemme käyttämään segmentin muodostinta suositeltujen segmentin ominaisuuksien sijaan seuraavalla tavalla:

- Luodaan segmenttejä suodattimien avulla kategorisissa kentissä, joissa operaattori on eri kuin **On**-operaattori
- Luodaan segmenttejä suodattimien avulla numeerisissa kentissä, joissa operaattori on eri kuin **Välissä**, **Suurempi kuin**- ja **Pienempi kuin** -operaattorit
- Sellaisten segmenttien luominen, joissa on suodattimia päivämäärätyyppikentissä

## <a name="next-steps"></a>Seuraavat vaiheet

[Vie segmentti](export-destinations.md) ja tutustu [asiakaskorttiin](customer-card-add-in.md) ja [yhdistimiin](export-power-bi.md), jotta saat asiakastason tietoja.


[!INCLUDE[footer-include](../includes/footer-banner.md)]