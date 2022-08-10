---
title: Asiakasprofiilien näyttäminen
description: Yhdistettyjen asiakastietojen näyttäminen sekä haun ja suodatuksen käyttäminen
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 6cdf47e6997f230811dcb0f2cf5542f3a6db2367
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188089"
---
# <a name="view-customer-profiles"></a>Asiakasprofiilien näyttäminen

Asiakasprofiilit ovat käytettävissä sen jälkeen kun [luot yhdistetyn *asiakasentiteetin*](data-unification.md). **Asiakkaat** -sivu näyttää yhdistetyn näkymän yhtenäisistä asiakasprofiileista. Asiakkaat voivat olla yksityishenkilöitä tai organisaatioita.

**Asiakkaat**-sivulla voit tarkastella asiakkaitasi ja heidän profiilejaan. Kutakin asiakasprofiilia edustaa ruutu. Voit käyttää sivutuksen ohjausobjekteja, kun haluat saada lisää tietueita. Kortti näyttää kentät *Asiakas*-entiteetistä **Haku- ja suodatinindeksi** -määritysten mukaan. Järjestelmä poimii kunkin kortin kenttien järjestyksen.

> [!NOTE]
> Jos et näe ruutuja, kun valitset kohdan **Asiakkaat**, järjestelmänvalvojasi on [määritettävä vähintään yksi haettava määrite](search-filter-index.md) kohdassa **Haku- ja suodatinindeksi**.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Asiakkaan sivu, joka näyttää tulosruudut.":::

Valitse jokin seuraavista toiminnoista:
- [Näytä asiakastiedot](#view-customer-details)
- [Haku- ja suodatinindeksin hallinta](search-filter-index.md) (vain järjestelmänvalvojat)
- [Suodata asiakkaat](#filter-customers)
- **Laajenna kortteja** tai **tiivistä kortteja**, jos haluat laajentaa tai tiivistää asiakasruudussa näkyviä tietoja
- **Lajitteleminen tietyn** määritteen mukaan
- [Hae asiakkaita](#search-for-customers)

  > [!NOTE]
  > Haun ja suodattimen käyttöä varten järjestelmänvalvojan on määritettävä haettavat määritteet ja määritettävä suodatettavat kentät haku- ja suodatinindeksin avulla.

## <a name="search-for-customers"></a>Hae asiakkaita

Voit hakea asiakkaita kirjoittamalla nimen tai jonkin muun määritteen hakuruutuun **Hae asiakkaita**. Järjestelmänvalvoja määrittää haettavat määritteet ja ne tulevat yhdistetystä *Asiakas*-entiteetistä.

> [!NOTE]
> **Merkkijono** on ainoa hakuun sisältyvä tietotyyppi. Käytä sitä Asiakkaat-sivun **Etsi asiakkaita** -kentässä, kun haluat hakea asiakkaita.

## <a name="filter-customers"></a>Suodata asiakkaat

Voit suodattaa asiakkaita *Asiakas*-entiteetin kenttien mukaan. Järjestelmänvalvoja määrittää suodatettavat kentät.

1. Valitse **Näytä suodattimet** **Asiakkaat**-sivulla. Suodatinruutu ilmestyy näkyviin.

1. Valitse niiden määritteiden vieressä olevat ruudut, joiden mukaan haluat suodattaa asiakkaat.

1. Poista kaikki suodattimet valitsemalla **Poista suodattimet** tai poistamalla valintaruudun valinta valitun määritteen vierestä.

1. Voit sulkea suodatinruudun valitsemalla **Piilota suodattimet**.

1. Jos haluat tallentaa suodattimen tulokset [segmenttinä](segments.md), valitse **Tallenna suodattimet segmenttinä**.
   1. Anna segmentille nimi.
   1. Tallenna segmentti valitsemalla **Tallenna**.
   1. Valitse, suoritetaanko segmentti nyt, valitsemalla **Aktivoi** vai suoritetaanko se **myöhemmin**.

## <a name="view-customer-details"></a>Näytä asiakastiedot

Valitse **Asiakkaat-sivulla** asiakasruutu, jossa voit tarkastella valitun asiakkaan tietoja.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Asiakastiedot-sivu.":::

Asiakastietoja ovat esimerkiksi seuraavat:

**Asiakasprofiilin ruutu** näyttää eri arvot yhtenäisestä *Asiakas*-entiteetistä. Jos kentällä ei ole arvoa valitulle asiakasprofiilille, näkyvissä on vain osoitekenttä. Ruudun rakenne koostuu osista:

- Ensimmäisessä osassa näkyy ennalta määritetty kenttäjoukko, jota seuraavat kaikki haku- ja suodatinindeksiin kuuluvat kentät. Kaikki osoitteeseen liittyvät kentät yhdistetään yksittäiseksi riviksi, joka näkyy myös silloin, jos profiilissa ei ole osoitetietoja.
- **Tämän asiakkaan yhteystiedot** näkyvät yritystiliympäristöissä. Kukin yhteyshenkilö näytetään kenttiensä kanssa. Tyhjät kentät piilotetaan.
- **Lisäkentät** näyttää valitun asiakkaan jäljellä olevat kentät tunnuksia lukuun ottamatta.
- **Tunnukset**: Luetteloi kaikki tunnukset vastaavaan entiteetin nimen alla. Kentät tunnistetaan tunnuksiksi semantiikkansa perusteella.

**Aktiviteetin aikajana**: Näyttää tiedot, jos sinulla on määritettyjä [aktiviteetteja](activities.md). Aikajananäkymä sisältää valitun asiakkaan kronologisesti lajiteltuja aktiviteetteja alkaen uusimmasta aktiviteetista.

**Näkemykset**:

- **Mittarit**: Näyttää, oletko määrittänyt yhden tai useamman [asiakkaan määritteen mittarin](measures.md). Ne sisältävät asiakkaisiin liittyvät lasketut tunnusluvut yksittäisen asiakkaan tasolla.

- **Mahdolliset kiinnostuksen kohteet, mahdolliset tuotemerkit**: Näyttää, oletko määrittänyt rikastukseksi [tuotemerkin tai kiinnostuksen kohteen](enrichment-microsoft.md). Se edustaa mahdollisia kiinnostuksen kohteita ja tuotemerkkien sukulaisuuksia perustuen muihin asiakkaisiin, joiden profiili on samanlainen kuin valitun asiakasprofiilin.

Palaa **asiakassivulle** valitsemalla **Palaa Asiakkaat-kohtaan**.

## <a name="next-steps"></a>Seuraavat vaiheet

[Lisää tietolähteitä](data-sources.md), [rikasta yhtenäisiä profiileja](enrichment-hub.md) tai [luo segmenttejä](segments.md), jotta voit käsitellä yhtenäisiä asiakasprofiileja muissa sovelluksissa.

[!INCLUDE [footer-include](includes/footer-banner.md)]
