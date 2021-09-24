---
title: Entiteettien yhdistäminen tietoja yhtenäistettäessä
description: Yhtenäisten asiakasprofiilien luominen yhdistämällä entiteettejä.
ms.date: 09/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b038cd3f5b433fedf918d34bbfaf2261e11c5c17
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494315"
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

1.  Voit lisätä yhdistämisprosessiin osallistumista varten lisää kenttiä.

1.  Voit nimetä yhdistetyn kentän uudelleen.

1. Ota muutokset käyttöön valitsemalla **Valmis**.

1. Valitse **Tallenna** ja **Suorita** muutosten käsittelemiseksi. 

## <a name="manually-combine-fields"></a>Yhdistä kentät manuaalisesti

Määritä yhdistetty määrite manuaalisesti. 

1. Valitse **Yhdistä**-sivulla **Yhdistä kentät**.

1. Määritä yhdistämisen voittajakäytäntö avattavassa **Yhdistä kentät** -luettelossa.

1. Valitse lisättävä kenttä. Valitse **Lisää kenttiä** yhdistääksesi useampia kenttiä.

1. Anna **Nimi** ja **Tulostekentän nimi**.

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

Asiakas-entiteetin CustomerId-tunnus perustuu ensisijaisen arvon hajautusarvo, joka ei-tyhjäarvoisen voittajan perusavaimilla on. Nämä avaimet tulevat vastine- ja yhdistämisvaiheessa käytetyistä entiteeteistä, ja vastinejärjestys vaikuttaa niihin. Luotu CustomerID voi siis muuttua, kun perusavaimen arvo muuttuu vastinetilauksen ensisijaisessa entiteetissä. Tästä syystä perusavaimen arvo ei aina vastaa samaa asiakasta.

Määrittämällä vakaan asiakastunnuksen voit välttää tämän käyttäytymisen.

**Määritä yksilöivä asiakastunnus**

1. Siirry kohtaan **Yhdenmukaista** > **Yhdistä**.

1. Valitse **Yhdistä**-sivulla **Avaimet**-välilehti. 

1. Vie hiiren osoitin **CustomerId**-riville ja valitse **Määritä**-vaihtoehto.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Tunnuksen luonnin mukauttamisen hallinta.":::

1. Valitse enintään viisi kenttää, jotka sisältävät yksilöllisen asiakastunnuksen ja ovat vakaampia. Tietueet, jotka eivät vastaa kokoonpanoa, käyttävät sen sijaan järjestelmän luomaa määritystunnusta.  

1. Ota muutokset käyttöön valitsemalla **Valmis** ja suorita yhdistämisprosessi.

## <a name="run-your-merge"></a>Suorita yhdistäminen

Jos yhdistät määritteet manuaalisesti tai annat järjestelmän yhdistää ne, voit aina suorittaa yhdistämisen. Valitse **Suorita** **Yhdistäminen**-sivulla, jos haluat aloittaa prosessin.

> [!div class="mx-imgBorder"]
> ![Tietojen yhdistämisen tallennus- ja suoritustoiminto.](media/configure-data-merge-save-run.png "Tietojen yhdistämisen tallennus- ja suoritustoiminto")

Valitse **Suorita vain yhdistämistoiminto**, jos haluat, että tulos näkyy vain yhdistetyssä asiakasentiteetissä. Jatkoprosessit päivittyvät [päivitysaikataulun mukaan](system.md#schedule-tab).

Valitse **Suorita yhdistäminen ja jatkoprosessit**, kun haluat päivittää muutokset järjestelmään. Kaikki prosessit, kuten rikastus, segmentit ja mittarit, käynnistyvät uudelleen automaattisesti. Kun kaikki jatkoprosessit on suoritettu loppuun, asiakasprofiilit vastaavat tehtyjä muutoksia.

Jos haluat tehdä lisää muutoksia ja suorittaa vaiheen uudelleen, voit peruuttaa käynnissä olevan yhdistämisen. Valitse **Pävitetään...**-teksti ja valitse sitten **Peruuta työ** näkyviin tulevassa reunaruudussa.

> [!TIP]
> Kun olet suorittanut yhdistämisprosessin, avaa **Tehtävän tiedot** -ruutu valitsemalla prosessin tila. Se antaa yleiskuvan käsittelyajasta, viimeisestä käsittelypäivästä sekä kaikista tehtävään liittyvistä virheistä ja varoituksista. Valitse **Näytä tiedot**, jos haluat nähdä, mitkä entiteetit osallistuivat vastaavuusprosessiin, onnistuiko konfliktinratkaisu ja onko päivitysten julkaiseminen onnistunut.  
> Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types). Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Porautumispolku, jonka avulla voit käsitellä tehtävän tilalinkin tietoja.":::

## <a name="next-step"></a>Seuraava vaihe

Määritä [aktiviteetit](activities.md), [rikastaminen](enrichment-hub.md) tai [suhteet](relationships.md), jos haluat lisää merkityksellisiä tietoja asiakkaista.

Jos olet jo määrittänyt aktiviteetteja, rikastuksia tai segmenttejä, ne käsitellään automaattisesti uusimpien asiakastietojen perusteella.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
