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
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170723"
---
# <a name="find-similar-customers-with-ai-preview"></a>Samankaltaisten asiakkaiden etsiminen (esiversio)

Etsi samankaltaisia asiakkaita asiakaskunnasta tekoälyn avulla. Tämän ominaisuuden käyttäminen edellyttää vähintään yhden segmentin luomista. Laajentamalla aiemmin luodun segmentin ehtoja voit etsiä segmentin kanssa samankaltaisia asiakkaita.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Etsi samankaltaiset asiakkaat* käyttää automaattisia tietoja arvioidakseen tietoja ja tehdäkseen ennusteita näiden tietojen perusteella. Siksi sitä voidaan käyttää profilointimenetelmänä, koska tämä termi on määritetty yleisessä tietosuoja-asetuksessa (”tietosuoja-asetus”). Asiakkaat käyttävät tätä toimintoa tietojen käsittelyyn. GDPR tai muut lait tai säädökset saattavat ohjata toiminnon käyttöä. Olet vastuussa siitä, että Dynamics 365 Customer Insightsin käyttäminen, myös ennusteiden käyttäminen, on kaikkien lakien ja säädösten mukaista. Näihin kuuluvat yksityisyyteen, henkilökohtaisiin tietoihin, biometrisiin tietoihin, tietosuojaan ja viestintäsalaisuuteen liittyvät lait.

## <a name="find-similar-customers"></a>Etsi samankaltaisia asiakkaita

1. Siirry **Segmentteihin** ja valitse segmentti, johon haluat perustaa uuden segmentin. Tämä on *lähdesegmentti*.

1. Valitse **Etsi samankaltaisia asiakkaita**.

1. Tarkista uuden segmentin ehdotettu nimi ja muuta sitä tarvittaessa.

1. Vaihtoehtoisesti voit lisätä uuteen segmenttiin [tunnisteita](work-with-tags-columns.md#manage-tags).

1. Tarkista kentät, jotka määrittävät uuden segmentin. Näissä kentissä määritetään, millä perusteella järjestelmä yrittää etsiä samanlaisia asiakkaita lähdesegmentistä. Järjestelmä valitsee oletusarvoisesti suositellut kentät. Lisää kenttiä tarvittaessa.
  Kentät, jotka voivat merkittävästi vähentää mallin tehokkuutta, jätetään automaattisesti pois:
  
   - Kentät, joiden tieto tyyppi on jokin seuraavista: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Kentät, joiden kardinaliteetti (kentän elementtien määrä) on alle 2 tai yli 30

1. Valitse, haluatko sisällyttää **Kaikki asiakkaat** pois lukien lähdesegmentti vai vain **eri segmentin** asiakkaat uuteen segmenttiin.

1. Oletusarvon mukaan järjestelmä ehdottaa, että tulosteessa on vain 20 prosenttia kohdeyleisöstä. Muokkaa tätä raja-arvoa tarpeen mukaan. Kynnyksen suurentaminen vähentää tarkkuutta.

1. Sisällytä lähdesegmenttiin asiakkaita valitsemalla **Sisällytä jäseniä lähdesegmentistä niiden asiakkaiden lisäksi, joilla on samanlaiset määritteet** -valintaruutu.

1. Aloita [binaarisen luokituksen tehtävä](#about-similarity-scores) (koneoppimisen menetelmä), joka analysoi tietojoukon, valitsemalla sivun alareunasta **Suorita**.

## <a name="view-the-similar-segment"></a>Samanlaisen segmentin tarkasteleminen

Kun olet käsitellyt samankaltaisen segmentin, löydät uuden segmentin **Segmentit**-sivulta tyypillä **Laajennus**.

Valitse **Näytä,** jos haluat nähdä tuloksen jakautumisen [samankaltaisuuspistemääriin](#about-similarity-scores) ja samankaltaisuuspistemäärän arvot **Segmentin jäsenten esikatselussa**.

:::image type="content" source="media/expanded-segment.png" alt-text="Samankaltainen asiakassegmentti.":::

## <a name="manage-a-similar-segment"></a>Samanlaisen segmentin hallinta

Voit [käsitellä ja hallita samanlaisen segmentin tulosta](segments.md#manage-existing-segments) samalla tavalla kuin muitakin segmenttejä. Voit esimerkiksi viedä segmentin tai luoda mittarin.

Samanlaisen segmentin muokkaaminen, päivittäminen, uudelleennimeäminen, lataaminen ja poistaminen. Jos muokkaat samankaltaista segmenttiä, tiedot käsitellään uudelleen. Aiemmin luotu segmentti päivittyy päivitetyillä tiedoilla.

## <a name="about-similarity-scores"></a>Tietoja samanlaisuuden pisteytyksestä

Binaariluokittelun koneoppimismalli määrittää pistemäärän samanlaisessa segmentissä oleville asiakkaille. Pistemäärä perustuu lähdesegmentin asiakkaiden samankaltaisuuteen.

- Ne asiakkaat, joiden samankaltaisuuspisteet ovat alle 0,55, ovat asiakkaita, jotka luokitellaan lähdesegmentin asiakkaiden kanssa määritteellä *ei samankaltainen*.
- Samankaltaisuuspisteet välillä 0,55–0,7 luokitellaan *hieman samankaltaisiksi*
- Samankaltaisuuspisteet välillä 0,7–0,85 luokitellaan *samankaltaisiksi*
- Samankaltaisuuspisteet välillä 0,85–1 ovat asiakkaita, jotka luokitellaan *hyvin samankaltaisiksi*

Asiakkaat, joilla samankaltaisuutta koskevia pisteitä on alle 0,4, eivät sisälly mallin tuotokseen. Järjestelmä ei pidä niitä tarpeeksi samankaltaisina lähdesegmentin kanssa.

[!INCLUDE [footer-include](includes/footer-banner.md)]
