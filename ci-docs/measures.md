---
title: Mittarien yleiskatsaus
description: Tietoja siitä, miten mittarit auttavat analysoimaan yrityksen toimintaa ja näyttämään sen tuloksia.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: ead57ccbdcaf9f86ee54d1f15de71a63f2e1081b
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170816"
---
# <a name="measures-overview"></a>Mittarien yleiskatsaus

Mittarien avulla ymmärrät paremmin asiakkaiden käyttäytymistä ja liiketoiminnan suorituskykyä. Ne näyttävät olennaiset arvot [yhtenäisistä profiileista](data-unification.md). Ajatellaan, että yrityksessä halutaan nähdä esimerkiksi *kokonaiskulutus asiakasta kohden* yksittäisen asiakkaan ostohistorian tai *yrityksen kokonaismyynti* koko yrityksen yhdistetyn tason tuoton selvittämiseksi.

Laadi mittareita liiketoiminta-aktiviteettien suunnittelemiseen tekemällä kyselyjä asiakastiedoista ja poimimalla tietoja. Esimerkiksi *asiakaskohtainen kokonaiskulutus*- ja *asiakaskohtainen kokonaispalautus* -mittarin luominen auttaa tunnistamaan asiakkaat, jotka ostavat paljon mutta tekevät myös paljon palautuksia. Voit luoda näiden mittarien perusteella [segmentin](segments.md), joka edistää seuraavia parhaita toimintoja.

## <a name="create-a-measure"></a>Luo mittari

Valitse, miten kohdeyleisön perusteella luodaan mittari.

# <a name="individual-consumers-b-to-c"></a>[Yksittäiset kuluttajat (kuluttajakauppa)](#tab/b2c)

- Mittarin muodostimen avulla alusta asti: [oman rakentaminen](measure-builder.md).
- Usein käytetyistä mittareista: [ennalta määritettyjen mallien käyttö](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Yritystilit (yritysten väliset)](#tab/b2b)

Mittarin muodostimen avulla alusta asti: [oman rakentaminen](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Aiemmin luotujen mittareiden hallinta

Siirry **Mittarit**-sivulle, kun haluat tarkastella luomiasi mittareita, niiden tilaa, mittarin tyyppiä ja tietojen viimeisintä päivittämisaikaa. Mittariluetteloa voi lajitella minkä tahansa sarakkeen perustella. Hallittavan mittarin voi etsiä myös hakuruutua käyttämällä.

Voit tarkastella käytettävissä olevia toimintoja valitsemalla mittarin vieressä olevan painikkeen. Kun valitset mittarin nimen, voit esikatsella tulosta ja ladata CSV-tiedoston.

:::image type="content" source="media/measures-actions.png" alt-text="Yksittäisten mittareiden hallintatoiminnot."lightbox="media/measures-actions.png":::

- **Muokkaa** mittaria, jos haluat muuttaa sen ominaisuuksia.
- **Päivitä** mittari siten, että se sisältää uusimmat tiedot.
- **Nimeä uudelleen** mitta.
- **Aktivoi** mittari tai **Poista aktivointi**. Passiiviset mittarit eivät päivity [aikataulutetun päivityksen](system.md#schedule-tab) aikana, ja passiivisten segmenttien **Tila**-arvo on **Ohitettu**, mikä osoittaa, että päivitystä ei edes yritetty.
- **Tunniste** mittarin [tunnisteiden hallintaa varten](work-with-tags-columns.md#manage-tags).
- **Poista** mitta.
- **Sarakkeet** [sarakkeiden mukauttamiseksi](work-with-tags-columns.md#customize-columns) näyttämistä varten.
- **Suodatin** [tunnisteiden suodattamiseksi](work-with-tags-columns.md#filter-on-tags).
- **Hae nimi** mittarin nimen mukaan tehtävää hakua varten.

## <a name="refresh-measures"></a>Päivitä mittarit

Mittarit voidaan päivittää automaattisen aikataulun mukaan tai manuaalisesti tarvittaessa. Mittarit päivitetään manuaalisesti valitsemalla ensin ne ja sitten **Päivitä**. [Automaattinen päivitys ajoitetaan](system.md#schedule-tab) valitsemalla **Hallinta** > **Järjestelmä** > **Aikatauluta**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
