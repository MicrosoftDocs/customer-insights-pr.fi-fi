---
title: Entiteettien yhdistäminen tietoja yhtenäistettäessä
description: Yhtenäisten asiakasprofiilien luominen yhdistämällä entiteettejä.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4ad06a0baf57e612fc0e0214dfd23d28e7d2b6be
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896507"
---
# <a name="merge-entities"></a>Entiteettien yhdistäminen

Yhdistämisvaihe on tietojen yhdistämisprosessin viimeinen vaihe. Sen tarkoitus on täsmäyttää ristiriitaiset tiedot. Esimerkkejä ristiriitaisista tiedoista ovat esimerkiksi asiakkaan nimi, joka on kahdessa tietojoukossa hieman eri tavalla (esimerkiksi Grant Marshall ja Grant Marshal) ja puhelinnumero, jonka muodot ovat erilaiset (esimerkiksi 617-803-091X ja 617803091X). Näiden ristiriitaisten arvopisteiden yhdistäminen tapahtuu määrite kerrallaan.

Kun [täsmäytysvaihe](match-entities.md) on suoritettu, voit aloittaa yhdistämisvaiheen valitsemalla **Yhdistä**-ruudun **Yhdistäminen**-sivulla.

## <a name="review-system-recommendations"></a>Tarkista järjestelmän suositukset

**Yhdistäminen**-sivulla voit valita määritteitä yhdistettäväksi yhdistettyä asiakasprofiilientiteettiä (määritysprosessin tulos) varten tai poistaa määritteitä yhdistämisprosessista. Järjestelmä yhdistää jotkin määritteet automaattisesti.

### <a name="view-merged-attributes"></a>Tarkastele yhdistettyjä määritteitä

Voit tarkastella määritteitä, jotka sisältyvät yhteen automaattisesti yhdistettyyn määritteeseen valitsemalla kyseisen yhdistetyn määritteen. Kaksi määritettä, jotka muodostavat yhdistetyn määritteen, näkyvät yhdistetyn määritteen alapuolella kahdella uudelle rivillä.

> [!div class="mx-imgBorder"]
> ![Valitse yhdistetty määrite](media/configure-data-merge-profile-attributes.png "Valitse yhdistetty määrite")

### <a name="separate-merged-attributes"></a>Erottele yhdistetyt määritteet

Jos haluat erotella automaattisesti yhdistettyjä määritteitä tai poistaa niiden yhdistämisen, etsi määrite **Profiilimääritteet**-taulukosta.

1. Valitse kolme pistettä (...) -painike.
  
2. Valitse avattavasta luettelosta **Erottele kentät**.

### <a name="remove-merged-attributes"></a>Poista yhdistetyt määritteet

Jos haluat poistaa määritteen lopullisesta asiakasprofiilientiteetistä, etsi se **Profiilimääritteet**-taulukosta.

1. Valitse kolme pistettä (...) -painike.
  
2. Valitse avattavasta luettelosta **Älä yhdistä**.

   Määrite siirretään **Poistettu asiakastietueesta** -osaan.

## <a name="manually-add-a-merged-attribute"></a>Lisää yhdistetty määrite manuaalisesti

Jos haluat lisätä yhdistetyn määritteen, siirry **Yhdistäminen**-sivulle.

1. Valitse **Lisää yhdistetty määrite**.

2. Anna **nimi**, joka määrittää määritteen **Yhdistäminen**-sivulla myöhemmin.

3. Vaihtoehtoisesti voit myös antaa **näyttönimen**, joka näkyy yhdistetyssä asiakasprofiilientiteetissä.

4. Määritä **Valitse määritteiden kaksoiskappaleet**, jos haluat valita määritteet, jotka haluat yhdistää täsmäytetyistä entiteeteistä. Voit myös hakea määritteitä.

5. Määritä **Arvioi tärkeyden mukaan**, jos haluat määrittää jonkin määritteen tärkeämmäksi kuin toiset. Jos esimerkiksi *WebAccountCSV*-entiteetti sisältää tarkat tiedot *Täydelliset nimet* -määritteestä, voit määrittää tämän entiteetin tärkeämmäksi kuin *ContactCSV* valitsemalla *WebAccountCSV*-entiteetin. Tuloksena *WebAccountCSV* siirtyy ensimmäiseksi prioriteetin mukaan, kun taas *ContactCSV* siirretään toiseksi prioriteetin mukaan, kun haetaan ovat *Täydellinen nimi* -määritteen arvot.

## <a name="run-your-merge"></a>Suorita yhdistäminen

Jos yhdistät määritteet manuaalisesti tai annat järjestelmän yhdistää ne, voit aina suorittaa yhdistämisen. Valitse **Suorita** **Yhdistäminen**-sivulla, jos haluat aloittaa prosessin.

> [!div class="mx-imgBorder"]
> ![Tietojen yhdistämisen tallennus- ja suoritustoiminto](media/configure-data-merge-save-run.png "Tietojen yhdistämisen tallennus- ja suoritustoiminto")

Jos haluat tehdä lisää muutoksia ja suorittaa vaiheen uudelleen, voit peruuttaa meneillään olevan yhdistämisen. Valitse **Pävitetään...**-teksti ja valitse sitten **Peruuta työ** näkyviin tulevassa reunaruudussa.

Kun **Päivitetään...** -teksti muuttuu tekstiksi **Onnistui**, yhdistäminen on suorittanut ja ratkaissut ristiriidat tiedoissa määritettyjen käytäntöjen mukaisesti. Yhdistetyt ja yhdistämättömät määritteet sisällytetään yhdistettyyn profiilientiteettiin. Pois jätettyjä määritteitä ei sisällytetä yhdistettyyn profiilientiteettiin.

Jos yhdistäminen oli suoritettu onnistunessti jo aiemmin, kaikki loppupään prosessit, kuten rikastus, segmentointi ja mittaaminen, suoritetaan automaattisesti uudelleen. Kun kaikki loppupään prosessit on suoritettu uudelleen, asiakasprofiilit vastaavat tekemiäsi muutoksia.

> [!TIP]
> Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types). Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies). Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja. Kun työn jossakin tehtävissä on valittu **Näytä tiedot**, saat lisätietoja: käsittelyajan, viimeisimmän käsittelypäivämäärän sekä kaikki tehtävään liitetyt virheet ja varoitukset.

## <a name="next-step"></a>Seuraava vaihe

Määritä [aktiviteetit](activities.md), [rikastaminen](enrichment-hub.md) tai [suhteet](relationships.md), jos haluat lisää merkityksellisiä tietoja asiakkaista.

Jos aktiviteetit, rikastaminen tai suhteet on jo määritetty tai jos segmentit on määritetty, ne käsitellään automaattisesti käyttämään uusia asiakastietoja.




[!INCLUDE[footer-include](../includes/footer-banner.md)]