---
title: Asiakasprofiilien haku- ja suodatinindeksin hallinta
description: Tietojen löytäminen nopeasti yhtenäisistä asiakasprofiileista ja määritettyjen määritteiden suodattaminen.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187905"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Asiakasprofiilien haku- ja suodatinindeksin hallinta

Asiakastietojen yhtenäistämisen tuloksena on *asiakasentiteetti*, jolla koko asiakaskannasta saadaan yhtenäinen näkymä. Käyttäjät voivat [etsiä nopeasti tietoja tietystä asiakkaasta tai asiakasryhmästä](customer-profiles.md) siten, että järjestelmänvalvoja määrittää **Haku**- ja **Suodatin**-ominaisuudet **Asiakkaat**-sivulla.

   :::image type="content" source="media/search-filter.png" alt-text="Hakusuodatin":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Haettavissa olevat määritteet ja indeksoidut kentät

Jos määrität haettavia määritteitä ensimmäistä kertaa järjestelmänvalvojana, indeksoidut kentät on määritettävä ensin. Kaikki ne määritteet, joilla käyttäjät voivat hakea ja suodattaa asiakkaita **Asiakkaat**-sivulla, kannattaa valita. Voit määrittää vain niitä määritteitä, joita on tietojen yhtenäistämisprosessin aikana luodussa *asiakasentiteetissä*.

1. Mene kohtaan **Asiakkaat** ja valitse **Hae ja suodata indeksi**.

1. Valitse **+ Lisää**.

1. Valitse luettelosta indeksoituina kenttinä lisättävät määritteet ja napsauta **Käytä**.

1. Jos haluat lisätä määritteitä, valitse **Lisää**. Jos haluat poistaa määritteen, valitse määrite ja valitse **Poista**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Haku- ja suodatusindeksisivu":::

1. Valitse **Suorita**, kun olet valmis ottamaan haku- ja suodatusasetukset käyttöön. Kun muutokset on käsitelty, ne ovat [Asiakas-sivun asiakaskorteissa](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Tietyn määritteen suodatusvaihtoehtojen määrittäminen

Määritä **Asiakkaat**-sivulla asiakkaiden suodatuksessa käytettävät kentät.

1. Mene kohtaan **Asiakkaat** ja valitse **Hae ja suodata indeksi**.

1. Valitse määrite ja **Lisää suodatin**. Määritä tulosten määrä ja tapa, jolla ne järjestetään. Määritteen tietotyypin mukaan jokin seuraavista ruuduista avautuu.

   - Merkkijonotyyppiset määritteet: Määritä tulosten määrä **Merkkijonon suodatus**-ruudussa ja käytäntö, jonka mukaan ne järjestetään.

   - Numerotyyppiset määritteet: Määritä **Numeron suodatus**-ruutuun sisältyvät välit ja käytäntö, jonka mukaan ne järjestetään.

   - Päivämäärätyyppiset määritteet: Määritä **Päivämäärän suodatus**-ruutuun sisältyvät välit ja käytäntö, jonka mukaan ne järjestetään.

1. Valitse **OK**. Toista nämä toimet kaikille määritteille, jotka haluat suodattaa.

1. Valitse **Suorita**, kun olet valmis ottamaan haku- ja suodatusasetukset käyttöön. Kun muutokset on käsitelty, ne ovat [Asiakas-sivun asiakaskorteissa](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Näytä indeksoidut asiakaskentät

**Haku- ja suodatusindeksi** -sivulla näkyvät seuraavat tiedot:

- **Nimi**: ilmaisee määritteen nimen siinä muodossa kuin se näkyy *asiakas* entiteetissä.
- **Tietotyyppi**: määrittää, onko tietotyyppi merkkijono, numero vai päivämäärä.
- **Sisältyy hakuun**: määrittää, voidaanko määritettä käyttää asiakkaiden hakemiseen **Asiakkaat**-sivun **Haku**-kentässä.
- **Lisää suodatin**: ohjausobjekti, jolla määritetään, miten määritettä käytetään suodattamiseen **Asiakkaat**-sivulla.

## <a name="next-steps"></a>Seuraavat vaiheet

Tarkista [yhdistetyt profiilit -sivu](customer-profiles.md), jos haluat hakea profiileja tai tarkastella kaikkien yhtenäisten profiilien alijoukkoa indeksoiduissa kentissä.

[!INCLUDE [footer-include](includes/footer-banner.md)]
