---
title: Aiemmin luotujen segmenttien segmentin merkitykselliset tiedot
description: Aiemmin luotujen segmenttien merkityksellisten tietojen erot ja yhteneväisyydet ovat nähtävissä.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 526b593ba9b038de3d3c27f6a7683ca76b3f2319
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646103"
---
# <a name="segment-insights-preview"></a>Segmentin merkitykselliset tiedot (esiversio)

Tutustu olemassa olevien segmenttien tärkeisiin ja merkityksellisiin tietoihin. Selvitä, mikä erottaa toisistaan kaksi segmenttiä tai mitä yhteistä niillä on.

## <a name="segment-overlap"></a>Segmenttien päällekkäisyys

Segmenttien päällekkäisyysanalyysi osoittaa, kuinka monta ja mitkä asiakkaat ovat yhteisiä kahdelle tai useammalle segmentille. Esimerkiksi se, miten säännöllisesti ostavat asiakkaat ovat päällekkäisiä sellaisen segmentin kanssa, joka sisältää palvelua tai tuotetta koskevia tyytyväisiä asiakkaita.
Voit myös analysoida, miten päällekkäisyys muuttuu tietyillä määritteillä.

### <a name="run-an-overlap-analysis"></a>Päällekkäisyys analyysin suorittaminen

1. Siirry kohtaan **Segmentit** ja valitse **Merkitykselliset havainnot (esiversio)** -välilehti.

1. Valitse **Uusi** ja valitse sitten **Päällekkäisyys**-asetus **Valitse merkityksellisten havaintojen tyyppi** -ruudussa.

1. Valitse kiinnostavat segmentit ja valitse sitten **Seuraava**.

1. Valitse vaihtoehtoisesti yksi tai useampi kiinnostava kenttä, jos haluat analysoida jokaisen mahdollisen kentän arvon päällekkäisyydet ja valitse **Seuraava**.

1. Anna nimi päällekkäisyysanalyysille, valinnainen näyttönimi ja kuvaus.

1. Aloita analyysi valitsemalla **Tallenna**. Päällekkäisyysanalyysi on valmis, kun tila muuttuu tilasta Päivittää tilaan Onnistui.

### <a name="view-and-optimize-an-overlap-analysis"></a>Päällekkäisyysanalyysin tarkasteleminen ja optimointi

Kun analyysi on valmis, etsi tietoja segmenttejä koskevista merkityksellisistä havainnoista kohdassa **Segmentit** > **Merkitykselliset tiedot (esiversio)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Segmentin päällekkäisyysoivallusten tiedot.":::

Valitse merkityksellinen tieto, kun haluat nähdä analyysin tulokset:

- Niiden jäsenten määrä, jotka ovat päällekkäisiä analysoitavaksi valittujen segmenttien kanssa.
- Niiden jäsenien määrä, jotka sisältyvät yhteen segmentteihin mutta eivät muihin segmentteihin.
- Jos valitsit kenttiä päällekkäisyyden määrityksen määrittämisen aikana, ne löytyvät vastaavista välilehdistä. Voit valita minkä tahansa määritteen kiinnostuksen tason suodattimen avattavan valikon avulla. Alla olevassa taulukossa näkyvät vastaavat tiedot.

## <a name="segment-differentiators"></a>Segmentin erottimet

Segmentin erot auttaa sinua saamaan selville, mikä erottaa segmentin muista asiakkaista tai toisesta segmentistä. Sinun täytyy vain valita segmentti, niin järjestelmä tunnistaa profiilimääritteet ja mittarit, jotka erottavat valitun segmentin.

### <a name="run-a-differentiator-analysis"></a>Erilaisuussanalyysin suorittaminen

1. Siirry kohtaan **Segmentit** ja valitse **Merkitykselliset havainnot (esiversio)** -välilehti.

1. Valitse **Uusi** ja valitse sitten **Päällekkäisyys**-asetus **Valitse merkityksellisten havaintojen tyyppi** -ruudussa.

1. Valitse segmentti, jonka haluat analysoida **ensisijaiseksi segmentiksi**, ja valitse **Seuraava**.

1. Voit verrata ensisijaista segmenttiäsi valitsemalla **Kaikki asiakkaat** tai **Toissijainen segmentti** ja valitsemalla sitten **Seuraava**.

1. Voit vaihtoehtoisesti valita yhden tai useita kiinnostavia kenttiä, jos haluat tarkentaa analyysin tiettyihin määritteisiin ja valita **Seuraava**.

1. Anna nimi päällekkäisyysanalyysille, valinnainen näyttönimi ja kuvaus.

1. Aloita analyysi valitsemalla **Tallenna**. Päällekkäisyysanalyysi on valmis, kun tila muuttuu tilasta Päivittää tilaan Onnistui.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Erilaisuusanalyysin tarkasteleminen ja optimointi

Kun analyysi on valmis, etsi tietoja segmenttejä koskevista merkityksellisistä havainnoista kohdassa **Segmentit** > **Merkitykselliset tiedot (esiversio)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Segmentin erilaisuusoivallusten tiedot.":::

Valitse merkityksellinen tieto, kun haluat nähdä analyysin tulokset. Erilaisuusanalyysi sisältää kaksi välilehteä. **Määritteet**-välilehdessä on luettelo profiilimääritteistä, joita pidetään erottavinä tekijöinä. **Mittarit**-välilehdessä on lueteltu erottavat tekijät. Jokaisessa välilehdessä on seuraavat tiedot:

- Paremmuusjärjestykseen jaoteltu luettelo erottavista tekijöistä eropisteiden järjestyksessä.
- Kun erottavan tekijän **erilaisuuspisteet**. Erilaisuuspisteet edustavat kahden segmentin välisen määritteen eron astetta. Mitä suurempi ero on, sitä enemmän määritteet eroavat toisistaan segmenttien välillä. Valitsemalla pistemäärän voit avata **Erilaisuuspisteet**-ruudun, jossa on kyseisen määritteen arvojen jakaumat.

## <a name="manage-segment-insights"></a>Segmentin merkityksellisten tietojen hallinta

Voit käyttää seuraavia vaihtoehtoja komentopalkissa oivallusten käsittelyyn:

- **Palaa**, kun haluat palauta mekrkityksellisten tietojen luetteloon
- **Päivitä**, jos haluat suorittaa analyysin uudelleen
- **Poista**, jos haluat poistaa tämän merkityksellisen tiedon


[!INCLUDE [footer-include](includes/footer-banner.md)]
