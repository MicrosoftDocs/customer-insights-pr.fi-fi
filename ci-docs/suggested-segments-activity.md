---
title: Aktiviteettiin perustuvat ehdotetut segmentit (esiversio)
description: Anna koneoppimisen auttaa sinua löytämään uusia ja mielenkiintoisia segmenttejä asiakasaktiviteettien perusteella.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170585"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Aktiviteettiin perustuvat ehdotetut segmentit (esiversio)

Löydä mielenkiintoisia asiakassegmenttejä asiakasaktiviteettitietojen perusteella, jota Customer Insights käsittelee. Esimerkkejä aktiviteettitiedoista ovat tapahtumat, tukipuhelun kesto, ostot tai palautukset. Aktiviteettitiedoista analysoidaan segmenttien ehdottamista varten niiden viimeaikaisuutta, toistuvuutta ja rahallista arvoa (tai kestoa). Vaihtoehtoisesti voidaan luoda [ehdotettuja segmenttejä mittarin parantamista varten tai ymmärryksen parantamiseksi siitä, mikä vaikuttaa määritteeseen](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Ehdotetut segmentit -välilehti, jossa näkyvät aktiviteettiin perustuvat ja määritteisiin perustuvat segmenttiehdotukset.":::

## <a name="categorize-customers-by-activity"></a>Luokittele asiakkaat aktiviteetin mukaan

Customer Insightsissa saatavilla olevien [aktiviteettitietojen](activities.md) avulla voimme luoda asiakasryhmiä edustavia ehdotuksia:

- aktiivisimmat asiakkaat 
- asiakkaat, jotka ovat tehneet eniten ostoksia 
- asiakkaat, jotka tuottivat eniten tuloja 
- asiakkaat, jotka eivät ole olleet aktiivisia viime aikoina 
- asiakkaat, jotka ovat usein vuorovaikutuksessa yrityksesi kanssa  

Jos sinulla on vähittäiskauppa, voit selvittää, mitkä asiakkaat tuovat eniten tuottoa, ja palkita heidät kupongilla. Voit myös tunnistaa satunnaisia asiakkaita ja tarjota heille liittymistä palkinto-ohjelmaan, jotta he vierailisivat yrityksessäsi useammin.
Jos tarjoat julkista terveydenhuoltoa ja haluat pienentää yksittäisten sairaanhoitovierailujen kuluja, voit yrittää vähentää toistuvia vierailuja tarjoamalla mahdollisimman hyvää hoitoa mahdollisimman vähillä käynneillä. Tässä tapauksessa tavoitteenasi on pitää käyntitiheys alhaisena ja minimoida potilaiden toistuvat kustannukset. Tai voit tunnistaa sellaisten potilaiden segmentit, joilla on usein toistuvia tapaamisia ja korkeat toistuvat kustannukset ja analysoida näitä tapauksia yksilön hoidon parantamiseksi.

## <a name="required-data"></a>Pakolliset tiedot

Ehdotukset luodaan valittujen syötetietojen perusteella.

- Asiakasprofiilit: Kaikki asiakkaat tai tietyn segmentin jäsenet.

- Ajanjakso: Viime kuussa, viime vuonna tai millä tahansa mukautetulla aikavälillä.

- Aktiviteettityyppi: ostot, vähittäismyyntitapahtumat, verkkotapahtumat, asiakastuen palvelupyynnöt, tilaukset ja niin edelleen.  

- Customer Insights -entiteetti, joka sisältää aktiviteettitiedot: UnifiedActivity-entiteetti tai tietyn aktiviteetin entiteetti.

- Sisällytettävät dimensiot: Viimeaikaisuus, toistuvuus tai rahallinen dimensio riippuen yrityksesi vaatimuksista.

## <a name="generate-suggested-segments"></a>Ehdotettujen segmenttien luominen

1. Siirry kohtaan **Segmentit** ja valitse **Ehdotukset (esiversio)** -välilehti.

1. Valitse **Etsi uusia ehdotuksia** ja valitse **Näytä tai ennakoi asiakkaan käyttäytymistä**. Valitse **Aloita**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Ohjatun määritystoiminnon ensimmäinen vaihe ehdotetulle segmentille aktiviteetin perusteella.":::

1. Anna tarvittavat syötetiedot ja valitse **Seuraava**.

   - Valitse asiakkaat: Sisällytä kaikki asiakkaat tai tietty segmentti.
   - Valitse aktiviteetti: Valitse aktiviteettityyppi ja aktiviteettia kuvaavat entiteetit.
   - Asetukset: Määritä huomioon otettava ajanjakso sekä ehdotuksiin vaikuttavat tekijät ja yhdistä määritteet.

1. Tarkista syötteesi ja valitse **Suorita** suorittaaksesi mallin ja luodaksesi ehdotuksia.

Asiakasprofiilien ja valittujen aktiviteettien määrästä riippuen sen suorittamiseen voi mennä muutama minuutti.

Ehdotusten luomisen jälkeen niitä voidaan suodattaa kiinnostavimman dimension tai arvon perusteella.

## <a name="manage-suggested-segments"></a>Hallitse ehdotettuja segmenttejä

Siirry **segmentteihin** ja valitse **Ehdotukset (esikatselu)** -välilehti. Valitse **Aktiviteettiin perustuvat ehdotukset** -osassa ehdotettu segmentti, jotta voit tarkastella käytettävissä olevia toimintoja.

- **Katso ehdotus**, niin näet lisätietoja kyseisestä segmentistä, kuten kunkin dimension laajuus kohderyhmään verrattuna. Segmentin mahdollisten jäsenten määrä ja vastaava prosenttiosuus kaikista asiakkaista näkyvät korostettuina.
- **Luo segmentti**, jotta voit tallentaa ehdotetun segmentin. Se näkyy **Kaikki segmentit** -välilehdessä, ja sen voi [päivittää tai poistaa](segments.md). Et voi muokata segmentin tietoja. Voit kuitenkin muuttaa ehdotusten syötteiden ehtoja ja luoda erilaisia ehdotuksia.
- **Muokkaa ehdotuksia** nykyiset ehdotukset poistavien määritettyjen ominaisuuksien muokkaamiseksi.
- **Päivitä ehdotukset**, jos haluat päivittää ehdotukset ja säilyttää määritetyt määritteet.

[!INCLUDE [footer-include](includes/footer-banner.md)]
