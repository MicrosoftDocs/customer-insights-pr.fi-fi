---
title: Asiakasprofiilien hakeminen ja suodattaminen
description: Tietojen löytäminen nopeasti yhtenäisistä asiakasprofiileista ja määritettyjen määritteiden suodattaminen.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405626"
---
# <a name="customer-profiles-search--filter-index"></a>Asiakasprofiilit: haku- ja suodatusindeksi

Asiakastietojen yhtenäistämisen tuloksena on asiakasprofiilientiteetti, joilla koko asiakaskannasta saadaan yhtenäinen näkymä. Voit [etsiä nopeasti tietoja tietystä asiakkaasta tai asiakasryhmästä](customer-profiles.md) määrittämällä **Haku**- ja **Suodatin**-ominaisuudet **Asiakkaat**-sivulla. Lue lisää siitä, miten järjestelmänvalvojat voivat muokata määritteitä **Hae ja suodata indeksi** -sivulla. Käyttäjät voivat käyttää niitä hakemiseen ja suodattamiseen.

> [!div class="mx-imgBorder"]
> ![Hakusuodatin](media/search-filter.png "Hakusuodatin")

## <a name="add-fields-and-specify-attributes"></a>Kenttien lisääminen ja määritteiden määrittäminen

Jos määrität haettavia määritteitä ensimmäistä kertaa järjestelmänvalvojana, indeksoidut kentät on määritettävä ensin. Kaikki ne määritteet, joilla käyttäjät voivat hakea ja suodattaa asiakkaita **Asiakkaat**-sivulla, kannattaa valita. Voit määrittää vain niitä määritteitä, joita on tietojen yhtenäistämisprosessin aikana luodussa asiakasprofiilientiteetissä.

1. Avaa **Asiakkaat**-sivu ja valitse **Hae ja suodata indeksi**.

> [!NOTE]
> Luodaan oletushakuindeksin määritys käytettävistä määritteistä asiakasentiteetissä Yhdistämismääritys-sivulla määritettyjen seuraavien semanttisten tyyppien avulla.
> - Henkilö etunimi, sukunimi, toinen nimi, koko nimi
> - Organisaation nimi
> - Sähköpostiosoite
> - Puhelin
> - Sijainnin tiedot

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

3. Valitse **Suorita**, kun olet valmis ottamaan asetukset käyttöön.
