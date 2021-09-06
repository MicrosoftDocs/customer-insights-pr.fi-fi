---
title: Asiakasprofiilien näyttäminen
description: Yhtenäisten asiakastietojen yhdistelmänäkymän hakeminen.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 87323d15c44ef82ae8bc3cc971be6c36356121571cb9a9630be699ac2d157bf6
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032800"
---
# <a name="customer-profiles"></a>Asiakasprofiilit

**Asiakas**-sivulla on asiakkaiden yhdistelmänäkymä, joka perustuu [kaikista tietolähteistä](data-sources.md) kerättyihin profiilitietoihin. Asiakasprofiilit ovat käytettävissä sen jälkeen kun [luot yhdistetyn asiakasentiteetin](data-unification.md). Varmista, että tietojen yhdistämisprosessi on valmis, jotta asiakkaat saavat entistä monipuolisempia näkymiä. Sivun avulla voit myös hakea asiakkaita.

Asiakkaat voivat olla henkilöitä tai organisaatioita (esikatselu). Jokaista asiakas- tai organisaatioprofiilia edustaa ruutu. Valitse ruutu, jos haluat nähdä lisätietoja tietystä asiakkaasta tai organisaatiosta. Sivun alaosassa olevien sivutusohjausobjektien avulla voit tarkastella muita tietueita.

> [!div class="mx-imgBorder"] 
> ![Kuluttajakaupan asiakasprofiilit.](media/profiles-customers.png "Kuluttajakaupan asiakasprofiilit")

Organisaatiot (esikatselu)
> [!div class="mx-imgBorder"] 
> ![Kuluttajakaupan asiakasprofiilit.](media/profile-customers-b2b.png "Yritysten väliset asiakasprofiilit")

> [!NOTE]
> Jos ruutuja ei näy, kun valitset **Asiakkaat** -siirtymisnäkymässä, järjestelmänvalvojan on [määritettävä vähintään yksi haettavissa oleva määrite](search-filter-index.md) kohdassa **Hae ja suodata indeksi**.

## <a name="search-for-customers"></a>Hae asiakkaita

Voit hakea asiakkaita kirjoittamalla nimen tai jonkin muun määritteen hakuruutuun. Haku toimii vain tietojen yhdistämisprosessin aikana luodussa asiakasprofiilientiteetissä.

Järjestelmänvalvojana voit määrittää haettavat määritteet käyttämällä **Indeksin hakeminen ja suodattaminen** -sivua. Lisätietoja on kohdassa [Indeksin hakemisen ja suodattamisen hallinta](search-filter-index.md).

## <a name="filter-customers"></a>Suodata asiakkaat

Voit suodattaa asiakkaita asiakasprofiilientiteetin kenttien mukaan. Kuten haussa, järjestelmänvalvojan täytyy ensin määrittää kentät suodatettaviksi **Indeksin hakeminen ja suodattaminen** -sivun avulla.

1. Valitse **Suodatus** **Asiakkaat**-sivulla.

2. Valitse niiden määritteiden vieressä olevat ruudut, joiden mukaan haluat suodattaa asiakkaat.

   > [!div class="mx-imgBorder"] 
   > ![Asiakasprofiilit.](media/profiles-customers3.png "Asiakasprofiilit")

3. Poista kaikki suodattimet valitsemalla **Tyhjennä suodattimet** **Asiakkaat**-sivulla.

##  <a name="customer-details-page"></a>Asiakastiedot-sivu

Avaa **Asiakastiedot-sivu** valitsemalla jokin asiakasruuduista. Tässä näkymässä on valitun asiakkaan yhdistetyt tiedot.

Asiakastietoja ovat esimerkiksi seuraavat:

-   **Asiakasprofiili-ruutu**: Tässä ruudussa ovat yhdistetyn asiakasprofiilin entiteetin eri arvot. Näitä tietoja ovat esimerkiksi sähköpostiosoite, nimi ja kaupunki. 

-   **Mahdolliset kiinnostuksen kohteet, mahdolliset tuotemerkit**: Osoittaa, onko ensimmäisen osapuolen rikastaminen määritetty. Ilmaisee mahdolliset kiinnostuksen kohteet ja brändiaffiniteetit, joita voi olla tämän asiakkaan profiilia muistuttavalla asiakkaalla. Lisätietoja on kohdassa [Asiakasprofiilien rikastaminen brändin ja kiinnostuksen kohteiden affiniteeteillä](enrichment-microsoft.md).

-   **Mittarit**: Näyttää, onko vähintään yksi Asiakasmäärite-tyyppinen mittari määritetty. Ne sisältävät asiakkaisiin liittyvät lasketut tunnusluvut yksittäisen asiakkaan tasolla. Lisätietoja on kohdassa [Mittarien määrittäminen ja hallinta](measures.md).

-   **Aktiviteetin aikajana**: Näyttää mahdolliset määritetyt aktiviteetit. Aikajananäkymässä on kyseisen asiakkaan kronologisesti lajitellut aktiviteetit viimeisimmistä aktiviteetista alkaen. Lisätietoja on kohdassa [Asiakasaktiviteetit](activities.md).

Palaa asiakkaan hakusivulla valitsemalla **Palaa Asiakkaat-kohtaan**.

## <a name="next-steps"></a>Seuraavat vaiheet

Voit [lisätä tietolähteitä](data-sources.md), [täydentää yhtenäisiä profiileja](enrichment-hub.md) tai [luoda segmenttejä](segments.md), joilla voi käyttää yhtenäisiä profiileja muissa sovelluksissa.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
