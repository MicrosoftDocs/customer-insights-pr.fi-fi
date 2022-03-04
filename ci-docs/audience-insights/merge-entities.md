---
title: Entiteettien yhdistäminen tietoja yhtenäistettäessä
description: Yhtenäisten asiakasprofiilien luominen yhdistämällä entiteettejä.
ms.date: 01/28/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: c7743104bf89d9a2a741f1b358a89ed0240be024
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355841"
---
# <a name="merge-entities"></a>Entiteettien yhdistäminen

Yhdistämisvaihe on tietojen yhdistämisprosessin viimeinen vaihe. Sen tarkoitus on täsmäyttää ristiriitaiset tiedot. Esimerkkejä ristiriitaisista tiedoista ovat esimerkiksi asiakkaan nimi, joka on kahdessa tietojoukossa hieman eri tavalla (esimerkiksi Grant Marshall ja Grant Marshal) ja puhelinnumero, jonka muodot ovat erilaiset (esimerkiksi 617-803-091X ja 617803091X). Näiden ristiriitaisten arvopisteiden yhdistäminen tapahtuu määrite kerrallaan.

:::image type="content" source="media/merge-fields-page.png" alt-text="Tietojen yhdistämisprosessin yhdistämissivu, jossa on taulukossa yhdistettyjä kenttiä, jotka määrittävät yhtenäisen asiakasprofiilin.":::

Kun [täsmäytysvaihe](match-entities.md) on suoritettu, voit aloittaa yhdistämisvaiheen valitsemalla **Yhdistä**-ruudun **Yhdistäminen**-sivulla.

## <a name="review-system-recommendations"></a>Tarkista järjestelmän suositukset

Voit valita ja poistaa käytöstä määritteitä, jotka yhdistetään yhdistetyn asiakasprofiilin entiteettiin kohdassa **Tiedot** > **Yhdistäminen** > **Yhdistä**. Yhtenäinen asiakasprofiili on tietojen yhdistämisprosessin tulos. Järjestelmä yhdistää jotkin määritteet automaattisesti.

Jos haluat tarkastella määritteitä, jotka sisältyvät automaattisesti yhdistettyyn määritteeseen, valitse kyseinen yhdistetty määrite taulukon **Asiakaskentät**-välilehdessä. Määritteet, jotka muodostavat yhdistetyn määritteen, näkyvät yhdistetyn määritteen alapuolella kahdella uudelle rivillä.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Erota, nimeä uudelleen, poista käytöstä ja muokkaa yhdistettyjä kenttiä

Voit muuttaa sitä, miten järjestelmä käsittelee yhdistettyjä määritteitä muodostaakseen yhtenäisen asiakasprofiilin. Valitse **Näytä lisää** ja valitse, mitä haluat muuttaa.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Avattavan Näytä lisää -valikon vaihtoehdot, joiden avulla voi hallita yhdistettyjä määritteitä.":::

Lisätietoja on seuraavissa osissa.

## <a name="separate-merged-fields"></a>Erota yhdistetyt kentät

Jos haluat erottaa yhdistetyt kentät, etsi määrite taulukosta. Erotetut kentät näkyvät erillisinä arvopisteinä yhdistetyssä asiakasprofiilissa. 

1. Valitse yhdistetty kenttä.
  
1. Valitse **Näytä lisää** ja valitse sitten **Erota kentät**.
 
1. Vahvista erottelu.

1. Valitse **Tallenna** ja **Suorita** muutosten käsittelemiseksi.

## <a name="rename-merged-fields"></a>Yhdistettyjen kenttien nimeäminen uudelleen

Yhdistettyjen määritteiden näyttönimen muuttaminen. Tuloste-entiteetin nimeä ei voi muuttaa.

1. Valitse yhdistetty kenttä.
  
1. Valitse **Näytä lisää** ja valitse sitten **Nimeä uudelleen**.

1. Vahvista muutettu näyttönimi. 

1. Valitse **Tallenna** ja **Suorita** muutosten käsittelemiseksi.

## <a name="exclude-merged-fields"></a>Poista yhdistettyjä kenttiä käytöstä

Poista määrite käytöstä yhdistetyssä asiakasprofiilissa. Jos kenttää käytetään muissa prosesseissa, esimerkiksi segmentissä, poista se näistä prosesseista, ennen kuin poistat kentän asiakasprofiilista. 

1. Valitse yhdistetty kenttä.
  
1. Valitse **Näytä lisää** ja valitse **Poista käytöstä**.

1. Vahvista käytöstä poisto.

1. Valitse **Tallenna** ja **Suorita** muutosten käsittelemiseksi. 

Valitse **Yhdistä**-sivulla **Käytöstä poistetut kentät** nähdäksesi luettelon kaikista käytöstä poistetuista kentistä. Tämän ruudun avulla käytöstä poistettuja kenttiä voidaan lisätä takaisin.

## <a name="edit-a-merged-field"></a>Muokkaa yhdistettyä kenttää

1.  Valitse yhdistetty kenttä.

1.  Valitse **Näytä lisää** ja valitse sitten **Muokkaa**.

1.  Määritä, miten kentät yhdistetään kolmesta vaihtoehdosta:
    - **Tärkeys**: määrittää voittajan arvon osallistuvien kenttien tärkeyden mukaan. Se on yhdistämisen oletusasetus. Määritä tärkeysjärjestys valitsemalla **Siirrä ylöspäin/alaspäin**.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Tärkeysasetus yhdistämiskenttien valintaikkunassa."::: 
    - **Uusin**: määrittää voittajan arvon uusimpien arvojen perusteella. Tasaus edellyttää päivämäärää tai numeerista kenttää jokaiselle yhdistämiskenttien osallistujaentiteetille.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Viimeaikaisuusasetus yhdistämiskenttien valintaikkunassa.":::
    - **Vähiten uusin**: määrittää voittajan arvon vähiten uusien arvojen perusteella. Tasaus edellyttää päivämäärää tai numeerista kenttää jokaiselle yhdistämiskenttien osallistujaentiteetille.

1.  Voit lisätä kenttiä osallistuaksesi yhdistämisprosessiin.

1.  Voit nimetä yhdistetyn kentän uudelleen.

1. Ota muutokset käyttöön valitsemalla **Valmis**.

1. Valitse **Tallenna** ja **Suorita** muutosten käsittelemiseksi. 

## <a name="combine-fields-manually"></a>Yhdistä kentät manuaalisesti

Määritä yhdistetty määrite manuaalisesti.

1. Valitse **Yhdistä**-sivulla **Jatka**.

1. Valitse **Kentät**-vaihtoehto.

1. Määritä yhdistämisen voittajakäytäntö avattavassa **Yhdistä kentät** -luettelossa.

1. Valitse lisättävä kenttä. Valitse **Lisää kenttiä** yhdistääksesi useampia kenttiä.

1. Anna **Nimi** ja **Tulostekentän nimi**.

1. Ota muutokset käyttöön valitsemalla **Valmis**.

1. Valitse **Tallenna** ja **Suorita** muutosten käsittelemiseksi. 

## <a name="combine-a-group-of-fields"></a>Yhdistä kenttien ryhmä

Käsittele kenttäryhmää yhtenä yksikkönä. Jos tietueet sisältävät esimerkiksi kentät Osoite1, Osoite2, Kaupunki, Osavaltio ja Postinumero. Emme todennäköisesti halua yhdistää tietoja toiseen tietueen Osoite2-kohtaan ajatellen, että se voisi tehdä tiedoistamme täydellisempiä

1. Valitse **Yhdistä**-sivulla **Jatka**.

1. Valitse **Kenttien ryhmä** -vaihtoehto.

1. Määritä yhdistämisen voittajakäytäntö avattavassa **Ryhmien lajitteluperuste** -luettelossa.

1. Valitse **Lisää** ja valitse, haluatko lisätä kenttiä tai lisää ryhmiä kenttiin.

1. Anna jokaiselle yhdistetylle kentälle **Nimi** ja **Tulosteen nimi**.

1. Anna kenttien ryhmälle **Nimi**. 

1. Ota muutokset käyttöön valitsemalla **Valmis**.

1. Valitse **Tallenna** ja **Suorita** muutosten käsittelemiseksi.

## <a name="change-the-order-of-fields"></a>Kenttien järjestyksen muuttaminen

Jotkin entiteetit sisältävät enemmän tietoja kuin toiset. Jos entiteetti sisältää kentän uusimmat tiedot, voit priorisoida sen muita entiteettejä korkeammalle arvojen yhdistämisessä.

1. Valitse yhdistetty kenttä.
  
1. Valitse **Näytä lisää** ja valitse sitten **Muokkaa**.

1. Valitse **Yhdistä kentät** -ruudussa **Siirrä ylös/alas** järjestyksen määrittämiseksi, tai vedä ja pudota niitä haluttuun sijaintiin.

1. Vahvista muutos.

1. Valitse **Tallenna** ja **Suorita** muutosten käsittelemiseksi.

## <a name="configure-customer-id-generation"></a>Määritä asiakastunnuksen luonti 

Kun olet määrittänyt yhdistämiskentät, voit määrittää, miten CustomerId-arvot luodaan, yksilölliset asiakasprofiilin tunnukset. Tietojen yhdistämisprosessin yhdistämisvaihe luo yksilöllisen asiakasprofiilin tunnisteen. Tunnus on *Asiakas*-entiteetin CustomerId-tunnus, joka on tulosta tietojen yhdistämisprosessista. 

Asiakas-entiteetin CustomerId-tunnus perustuu ensisijaisen arvon hajautusarvo, joka ei-tyhjäarvoisen voittajan perusavaimilla on. Nämä avaimet tulevat vastine- ja yhdistämisvaiheessa käytetyistä entiteeteistä, ja vastinejärjestys vaikuttaa niihin. Luotu CustomerID voi siis muuttua, kun perusavaimen arvo muuttuu vastinetilauksen ensisijaisessa entiteetissä. Perusavaimen arvo ei välttämättä aina edusta samaa asiakasta.

Määrittämällä vakaan asiakastunnuksen voit välttää tämän käyttäytymisen.

**Määritä yksilöivä asiakastunnus**

1. Siirry kohtaan **Yhdenmukaista** > **Yhdistä**.

1. Valitse **Avaimet**-välilehti. 

1. Vie hiiren osoitin **CustomerId**-riville ja valitse **Määritä**-vaihtoehto.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Tunnuksen luonnin mukauttamisen hallinta.":::

1. Valitse enintään viisi kenttää, jotka sisältävät yksilöllisen asiakastunnuksen ja ovat vakaampia. Tietueet, jotka eivät vastaa kokoonpanoa, käyttävät sen sijaan järjestelmän luomaa määritystunnusta.  

1. Ota muutokset käyttöön valitsemalla **Valmis** ja suorita yhdistämisprosessi.

## <a name="group-profiles-into-households-or-clusters"></a>Profiilien ryhmitteleminen kotitalouksiksi tai klustereiksi

Osana asiakasprofiilin luonnin määritysprosessia voit määrittää sääntöjä, jotka ryhmittelevät liittyvät profiilit klusteriin. Käytettävissä on tällä hetkellä kahdentyyppisiä klustereita: kotitalousklusterit ja mukautetut klusterit. Järjestelmä valitsee automaattisesti kotitalouden ennalta määritetyin säännöin, jos *Asiakas*-entiteetti sisältää semanttiset kentät *Person.LastName* ja *Location.Address*. Voit myös luoda klusterin omilla säännöilläsi ja ehdoillasi, samoin kuin [vastaavuussäännöissä](match-entities.md#define-rules-for-match-pairs).

**Määritä kotitalous tai klusteri**

1. Siirry kohtaan **Yhdenmukaista** > **Yhdistä**.

1. Valitse **Yhdistä**-välilehdessä **Lisäasetukset** > **Luo klusteri**.

   :::image type="content" source="media/create-cluster.png" alt-text="Uuden klusterin luomisen ohjausobjekti.":::

1. Valitse joko **Kotitalous** tai **Mukautettu** klusteri. Jos semanttiset kentät *Person.LastName* ja *Location.Address* ovat olemassa *Asiakas*-entiteetissä, kotitalous valitaan automaattisesti.

1. Anna klusterille nimi ja valitse **Valmis**.

1. Valitse **Klusterit**-välilehti löytääksesi luomasi klusterin.

1. Määritä klusteri luomalla säännöt ja ehdot.

1. Valitse **Suorita** suorittaaksesi yhdistämisprosessin ja luodaksesi klusterin.

Kun yhdistämisprosessi on suoritettu, klusterin tunnisteet lisätään uusiksi kentiksi *Asiakas*-entiteetissä.

## <a name="run-your-merge"></a>Suorita yhdistäminen

Jos yhdistät määritteet manuaalisesti tai annat järjestelmän yhdistää ne, voit aina suorittaa yhdistämisen. Valitse **Suorita** **Yhdistäminen**-sivulla, jos haluat aloittaa prosessin.

> [!div class="mx-imgBorder"]
> ![Tietojen yhdistämisen tallennus- ja suoritustoiminto.](media/configure-data-merge-save-run.png "Tietojen yhdistämisen tallennus- ja suoritustoiminto")

Valitse **Suorita vain yhdistämistoiminto**, jos haluat, että tulos näkyy vain yhdistetyssä asiakasentiteetissä. Jatkoprosessit päivittyvät [päivitysaikataulun mukaan](system.md#schedule-tab).

Valitse **Suorita yhdistäminen ja jatkoprosessit**, kun haluat päivittää muutokset järjestelmään. Kaikki prosessit, kuten rikastus, segmentit ja mittarit, käynnistyvät uudelleen automaattisesti. Kun kaikki jatkoprosessit on suoritettu loppuun, asiakasprofiilit vastaavat tehtyjä muutoksia.

Jos haluat tehdä lisää muutoksia ja suorittaa vaiheen uudelleen, voit peruuttaa käynnissä olevan yhdistämisen. Valitse **Pävitetään...**-teksti ja valitse sitten **Peruuta työ** näkyviin tulevassa reunaruudussa.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Porautumispolku, jonka avulla voit käsitellä tehtävän tilalinkin tietoja.":::

## <a name="next-step"></a>Seuraava vaihe

Määritä [aktiviteetit](activities.md), [rikastaminen](enrichment-hub.md) tai [suhteet](relationships.md), jos haluat lisää merkityksellisiä tietoja asiakkaista.

Jos olet jo määrittänyt aktiviteetteja, rikastuksia tai segmenttejä, ne käsitellään automaattisesti uusimpien asiakastietojen perusteella.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
