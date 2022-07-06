---
title: Samankaltaisten asiakkaiden etsiminen tekoälyn avulla (esiversio) (sisältää videon)
description: Etsi samankaltaisia asiakassegmenttejä tekoälyn avulla.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: d58b2e424fd81ad691db4b2576bdf5655038ed89
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054797"
---
# <a name="find-similar-customers-with-ai-preview"></a>Samankaltaisten asiakkaiden etsiminen (esiversio)

Tämän ominaisuuden avulla voit etsiä samanlaisia asiakkaita asiakaskunnasta käyttämällä tekoälyä. Tämän ominaisuuden käyttäminen edellyttää vähintään yhden segmentin luomista. Laajentamalla aiemmin luodun segmentin ehtoja voit etsiä segmentin kanssa samankaltaisia asiakkaita.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Etsi samankaltaiset asiakkaat* käyttää automaattisia menetelmiä tietojen arviointiin ja ennusteissa, joten sitä voidaan käyttää profilointimenetelmänä, koska kyseinen käsite on määritetty yleisessä tietosuoja-asetuksessa (GDPR). Asiakkaat käyttävät tätä toimintoa tietojen käsittelyyn. GDPR tai muut lait tai säädökset saattavat ohjata toiminnon käyttöä. Olet vastuussa siitä, että Dynamics 365 Customer Insightsin käyttäminen, myös ennusteiden käyttäminen, on kaikkien lakien ja säädösten mukaista. Näihin kuuluvat yksityisyyteen, henkilökohtaisiin tietoihin, biometrisiin tietoihin, tietosuojaan ja viestintäsalaisuuteen liittyvät lait.

## <a name="finding-similar-customers"></a>Samankaltaisten asiakkaiden löytäminen

1. Siirry **Segmentteihin** ja valitse segmentti, johon haluat perustaa uuden segmentin. Tämä on *lähdesegmentti*.

1. Valitse toimintoriviltä **Etsi samankaltaisia asiakkaita**.

1. Tarkista uuden segmentin ehdotettu nimi ja muuta sitä tarvittaessa.

1. Vaihtoehtoisesti voit lisätä uuteen segmenttiin [tunnisteita](work-with-tags-columns.md#manage-tags).

1. Tarkista kentät, jotka määrittävät uuden segmentin. Näissä kentissä määritetään, millä perusteella järjestelmä yrittää etsiä samanlaisia asiakkaita lähdesegmentistä. Järjestelmä valitsee oletusarvoisesti suositellut kentät.
  Kentät, jotka voivat merkittävästi vähentää mallin tehokkuutta, jätetään automaattisesti pois:
  
   - Kentät, joiden tieto tyyppi on jokin seuraavista: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Kentät, joiden kardinaliteetti (kentän elementtien määrä) on alle 2 tai yli 30

1. Valitse, haluatko sisällyttää **Kaikki asiakkaat** vai vain **tietyn aiemmin luodun segmentin** asiakkaat uuteen segmenttiin.

1. Oletusarvon mukaan järjestelmä ehdottaa, että tulosteessa on vain 20 prosenttia kohdeyleisöstä. Muokkaa tätä raja-arvoa tarpeen mukaan. Kynnyksen suurentaminen vähentää tarkkuutta.

1. Sisällytä lähdesegmenttiin asiakkaita valitsemalla **Sisällytä jäseniä lähdesegmentistä niiden asiakkaiden lisäksi, joilla on samanlaiset määritteet** -valintaruutu.

1. Aloita binaarisen luokituksen tehtävä (koneoppimisen menetelmä), joka analysoi tietojoukon, valitsemalla sivun alareunasta **Suorita**.

## <a name="view-the-similar-segment"></a>Samanlaisen segmentin tarkasteleminen

Kun olet käsitellyt samankaltaisen segmentin, löydät uuden segmentin **Segmentit**-sivulta.

> [!div class="mx-imgBorder"]
> ![Samankaltainen asiakassegmentti.](media/expanded-segment.png "Samankaltainen asiakassegmentti")

Avaa segmentin erittely valitsemalla toiminto palkissa **Näytä**. Tässä näkymässä on tietoja [samankaltaisuuksien tulosten](#about-similarity-scores) jakautumisesta. Löydät myös samankaltaisuuksien pistearvot kohdassa **Segmentin jäsenten esikatselu**.

## <a name="use-the-output-of-a-similar-segment"></a>Samankaltaisen segmentin tuloksen käyttäminen

Voit [käsitellä samanlaisen segmentin tulosta](segments.md) samalla tavalla kuin muitakin segmenttejä. Voit esimerkiksi viedä segmentin tai luoda mittarin.

## <a name="refresh-and-edit-a-similar-segment"></a>Samanlaisen segmentin päivittäminen ja muokkaaminen

Jos haluat päivittää samanlaisen segmentin, valitse se **Segmentit**-sivulla ja valitse toimintoriviltä **Päivitä**.

Jos muokkaat samankaltaista segmenttiä, tiedot käsitellään uudelleen. Aiemmin luotu segmentti päivittyy päivitetyillä tiedoilla.
Jos haluat muokata samanlaisen segmentin, valitse se **Segmentit**-sivulla ja valitse toimintoriviltä **Muokkaa**. Ota muutokset käyttöön ja aloita käsittely valitsemalla **Suorita**.

## <a name="delete-a-similar-segment"></a>Samanlaisen segmentin poistaminen

Jos haluat poistaa samanlaisen segmentin, valitse se **Segmentit**-sivulla ja valitse toimintoriviltä **Poista**. Vahvista sitten poisto.

## <a name="about-similarity-scores"></a>Tietoja samanlaisuuden pisteytyksestä

Binaariluokittelun koneoppimismalli määrittää pistemäärän samanlaisessa segmentissä oleville asiakkaille. Pistemäärä perustuu lähdesegmentin asiakkaiden samankaltaisuuteen.

- Ne asiakkaat, joiden samankaltaisuuspisteet ovat alle 0,55, ovat asiakkaita, jotka luokitellaan lähdesegmentin asiakkaiden kanssa määritteellä *ei samankaltainen*.
- Samankaltaisuuspisteet välillä 0,55–0,7 luokitellaan *hieman samankaltaisiksi*
- Samankaltaisuuspisteet välillä 0,7–0,85 luokitellaan *samankaltaisiksi*
- Samankaltaisuuspisteet välillä 0,85–1 ovat asiakkaita, jotka luokitellaan *hyvin samankaltaisiksi*

Asiakkaat, joilla samankaltaisuutta koskevia pisteitä on alle 0,4, eivät sisälly mallin tuotokseen. Järjestelmä ei pidä niitä tarpeeksi samankaltaisina lähdesegmentin kanssa.

[!INCLUDE [footer-include](includes/footer-banner.md)]
