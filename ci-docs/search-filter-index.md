---
title: Asiakasprofiilien hakeminen ja suodattaminen
description: Tietojen löytäminen nopeasti yhtenäisistä asiakasprofiileista ja määritettyjen määritteiden suodattaminen.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: 35bfd6530b9b80a4b0ec8ff992d9014534721907
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646286"
---
# <a name="customer-profiles-search--filter-index"></a>Asiakasprofiilit: haku- ja suodatusindeksi

Asiakastietojen yhtenäistämisen tuloksena on asiakasprofiilientiteetti, joilla koko asiakaskannasta saadaan yhtenäinen näkymä. Voit [etsiä nopeasti tietoja tietystä asiakkaasta tai asiakasryhmästä](customer-profiles.md) määrittämällä **Haku**- ja **Suodatin**-ominaisuudet **Asiakkaat**-sivulla. Lue lisää siitä, miten järjestelmänvalvojat voivat muokata määritteitä **Hae ja suodata indeksi** -sivulla. Käyttäjät voivat käyttää niitä hakemiseen ja suodattamiseen.

   :::image type="content" source="media/search-filter.png" alt-text="Hakusuodatin":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="add-fields-and-specify-attributes"></a>Kenttien lisääminen ja määritteiden määrittäminen

Jos määrität haettavia määritteitä ensimmäistä kertaa järjestelmänvalvojana, indeksoidut kentät on määritettävä ensin. Kaikki ne määritteet, joilla käyttäjät voivat hakea ja suodattaa asiakkaita **Asiakkaat**-sivulla, kannattaa valita. Voit määrittää vain niitä määritteitä, joita on tietojen yhtenäistämisprosessin aikana luodussa asiakasprofiilientiteetissä.

1. Avaa **Asiakkaat**-sivu ja valitse **Hae ja suodata indeksi**.

2. Valitse **+ Lisää**, jos haluat määrittää indeksoidut kentät.

3. Valitse luettelosta indeksoituina kenttinä lisättävät määritteet. Voit aina lisätä uusia määritteitä valitsemalla **Lisää**. Voit myös poistaa valitsemasi määritteet valitsemalla **Poista**-symbolin.

## <a name="explore-the-indexed-customer-fields-table"></a>Indeksoidut asiakaskentät -taulukkoon tutustuminen

Taulukossa on seuraavat tiedot.

- **Nimi**: ilmaisee määritteen nimen siinä muodossa kuin se näkyy asiakasprofiilientiteetissä.
- **Tietotyyppi**: määrittää, onko tietotyyppi merkkijono, numero vai päivämäärä.
- **Sisältyy hakuun**: määrittää, voidaanko määritettä käyttää asiakkaiden hakemiseen **Asiakkaat**-sivun **Haku**-kentässä.
- **Lisää suodatin**: ohjausobjekti, jolla määritetään, miten määritettä käytetään suodattamiseen **Asiakkaat**-sivulla.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Tietyn määritteen suodatusvaihtoehtojen muokkaaminen

**Asiakkaat**-sivun **Suodatin**-valikossa voi olla useita määritetasoja (kuten asiakkaiden suodattamiseen käytettäviä asiakasryhmiä).

1. Valitse tietyn määritteen **Lisää suodatin** **Hae ja suodata indeksi** -sivulla. Voit määrittää tulosten määrän ja tavan, jolla ne järjestetään. Määritteen tietotyypin mukaan jokin seuraavista ruuduista avautuu.

- Merkkijonotyyppiset määritteet: Määritä tulosten määrä **Merkkijonon suodatusasetukset**-ruudussa ja käytäntö, jonka mukaan ne järjestetään.

- Numerotyyppiset määritteet: Määritä **Numeron suodatusasetukset**-ruutuun sisältyvät välit ja käytäntö, jonka mukaan ne järjestetään.

- Päivämäärätyyppiset määritteet: Määritä **Päivämäärän suodatusasetukset**-ruutuun sisältyvät välit ja käytäntö, jonka mukaan ne järjestetään.

2. Ota muutokset käyttöön valitsemalla **Tallenna**.

3. Valitse **Suorita**, kun olet valmis ottamaan asetukset käyttöön. Kun muutokset on käsitelty, ne ovat [Asiakas-sivun asiakaskorteissa](customer-profiles.md). 

## <a name="next-steps"></a>Seuraavat vaiheet

Tarkista [yhdistetyt profiilit -sivu](customer-profiles.md), jos haluat hakea profiileja tai tarkastella kaikkien yhtenäisten profiilien alijoukkoa indeksoiduissa kentissä.


[!INCLUDE [footer-include](includes/footer-banner.md)]
