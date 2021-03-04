---
title: Asiakasprofiilien hakeminen ja suodattaminen
description: Tietojen löytäminen nopeasti yhtenäisistä asiakasprofiileista ja määritettyjen määritteiden suodattaminen.
ms.date: 01/19/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d675738c43cbdb5f9b478d53d6124db38ba3004d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270062"
---
# <a name="customer-profiles-search--filter-index"></a>Asiakasprofiilit: haku- ja suodatusindeksi

Asiakastietojen yhtenäistämisen tuloksena on asiakasprofiilientiteetti, joilla koko asiakaskannasta saadaan yhtenäinen näkymä. Voit [etsiä nopeasti tietoja tietystä asiakkaasta tai asiakasryhmästä](customer-profiles.md) määrittämällä **Haku**- ja **Suodatin**-ominaisuudet **Asiakkaat**-sivulla. Lue lisää siitä, miten järjestelmänvalvojat voivat muokata määritteitä **Hae ja suodata indeksi** -sivulla. Käyttäjät voivat käyttää niitä hakemiseen ja suodattamiseen.

> [!div class="mx-imgBorder"]
> ![Hakusuodatin](media/search-filter.png "Hakusuodatin")

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

3. Valitse **Suorita**, kun olet valmis ottamaan asetukset käyttöön.

## <a name="next-steps"></a>Seuraavat vaiheet

Siirry **Asiakkaat**-sivulle, jos haluat etsiä asiakasprofiileja tai käyttää indeksoituja kenttiä ja katsoa kaikkien asiakasprofiilien osajoukkoa.


[!INCLUDE[footer-include](../includes/footer-banner.md)]