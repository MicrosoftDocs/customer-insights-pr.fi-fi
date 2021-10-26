---
title: Asiakasprofiilien näyttäminen
description: Yhtenäisten asiakastietojen yhdistelmänäkymän hakeminen.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 07d2206372f89cd7dcd9df84c87024a6f87d5eac
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623265"
---
# <a name="customer-profiles"></a>Asiakasprofiilit

**Asiakkaat** -sivu näyttää yhdistetyn näkymän yhtenäisistä asiakasprofiileista. Asiakasprofiilit ovat käytössä, kun olet [luonut yhtenäisen asiakasentiteetin](data-unification.md). Sivulla voit hakea asiakkaita ja määrittää haun indeksin.

Asiakkaat voivat olla yksityishenkilöitä tai organisaatioita. Kutakin asiakasprofiilia edustaa ruutu. Voit käyttää sivutuksen ohjausobjekteja, kun haluat saada lisää tietueita. Kortti näyttää kentät *Asiakas*-entiteetistä **Haku- ja suodatinindeksi** -määritysten mukaan. Valitse ruutu nähdäksesi valitun asiakkaan tiedot erillisellä sivulla nimeltä [Asiakkaan tietosivu](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Asiakkaan sivu, joka näyttää tulosruudut](media/customers-page-result-tiles-B2C.png "Asiakkaan sivu, joka näyttää tulosruudut")

> [!NOTE]
> Jos et näe ruutuja, kun valitset siirtymisessä kohdan **Asiakkaat**, järjestelmänvalvojasi on [määritettävä vähintään yksi haettava määrite](search-filter-index.md) kohdassa **Haku- ja suodatinindeksi**.

## <a name="search-for-customers"></a>Hae asiakkaita

Voit hakea asiakkaita kirjoittamalla nimen tai jonkin muun määritteen hakuruutuun. Haku toimii vain _Asiakas_-entiteetissä, joka luotiin tietojen yhtenäistämisen prosessin aikana.

Järjestelmänvalvojana voit määrittää haettavat määritteet käyttämällä **Indeksin hakeminen ja suodattaminen** -sivua. Lisätietoja löytyy kohdasta [Haku- ja suodatinindeksin hallinta](search-filter-index.md).

## <a name="filter-customers"></a>Suodata asiakkaat

Voit suodattaa asiakkaita _Asiakas_-entiteetin kenttien mukaan. Kuten haussa, järjestelmänvalvojan täytyy ensin määrittää kentät suodatettaviksi **Indeksin hakeminen ja suodattaminen** -sivun avulla.

1. Valitse **Näytä suodattimet** **Asiakkaat**-sivulla.

1. Valitse niiden määritteiden vieressä olevat ruudut, joiden mukaan haluat suodattaa asiakkaat.

1. Poista kaikki suodattimet valitsemalla **Tyhjennä suodattimet** **Asiakkaat**-sivulla.

## <a name="customer-details-page"></a>Asiakastiedot-sivu

Avaa **Asiakastiedot-sivu** valitsemalla jokin asiakasruuduista. Tässä näkymässä on valitun asiakkaan yhdistetyt tiedot. Asiakkaan tiedoissa on seuraava sisältö:

**Asiakasprofiilin ruutu**: Tämä ruutu näyttää eri arvot yhtenäisestä _Asiakas_-entiteetistä. Jos kentällä ei ole arvoa valitulle asiakasprofiilille, se ei näy. Ruudun rakenne koostuu osista:  
  - Ensimmäisessä osassa näkyy ennalta määritetty kenttäjoukko, jota seuraavat kaikki haku- ja suodatinindeksiin kuuluvat kentät. Kaikki osoitteeseen liittyvät kentät yhdistetään yksittäiseksi riviksi, jos profiili sisältää tällaisia kenttiä. 
  - **Tämän asiakkaan yhteyshenkilöt**: Yritystiliympäristöissä asiakkaan kaikki liittyvät yhteyshenkilöt näkyvät toisena osana. Kukin yhteyshenkilö näytetään kenttiensä kanssa. Tyhjät kentät piilotetaan.
  - **Lisäkentät**: Näyttää valitun asiakkaan jäljellä olevat kentät tunnuksia lukuun ottamatta. 
  - **Tunnukset**: Luetteloi kaikki tunnukset vastaavaan entiteetin nimen alla. Kentät tunnistetaan tunnuksiksi semantiikan mukaan, koska semantiikka luokittelee ne tunnuksiksi.

**Aktiviteetin aikajana**: Näyttää tiedot, jos sinulla on määritettyjä aktiviteetteja. Aikajananäkymä sisältää valitun asiakkaan kronologisesti lajiteltuja aktiviteetteja alkaen uusimmasta aktiviteetista. Lisätietoja löytyy kohdasta [Asiakkaan aktiviteetit](activities.md).

**Näkemykset**:  
  - **Mittarit**: Näyttää, oletko määrittänyt yhden tai useamman asiakkaan määritteen mittarin. Ne sisältävät asiakkaisiin liittyvät lasketut tunnusluvut yksittäisen asiakkaan tasolla. Lisätietoja löytyy kohdasta [Mittarien määritteleminen ja hallinta](measures.md).

  - **Mahdolliset kiinnostuksen kohteet, mahdolliset tuotemerkit**: Näytää, oletko määrittänyt rikastukseksi tuotemerkin tai kiinnostuksen kohteen. Se edustaa mahdollisia kiinnostuksen kohteita ja tuotemerkkien sukulaisuuksia perustuen muihin asiakkaisiin, joiden profiili on samanlainen kuin valitun asiakasprofiilin. Lisätietoja löytyy kohdasta [Asiakasprofiilien rikastaminen tuotemerkeillä ja kiinnostuksen kohteilla](enrichment-microsoft.md).

Palaa asiakashakusivulle valitsemalla **Takaisin asiakkaisiin**.

## <a name="next-steps"></a>Seuraavat vaiheet

[Lisää tietolähteitä](data-sources.md), [rikasta yhtenäisiä profiileja](enrichment-hub.md) tai [luo segmenttejä](segments.md), jotta voit käsitellä yhtenäisiä asiakasprofiileja muissa sovelluksissa.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
