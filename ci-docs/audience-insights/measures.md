---
title: Mittarien ymmärtäminen ja hallinta
description: Tietoja siitä, miten mittarit auttavat analysoimaan yrityksen toimintaa ja näyttämään sen tuloksia.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359769"
---
# <a name="measures-overview"></a>Mittarien yleiskatsaus

Mittarien avulla ymmärrät paremmin asiakkaiden käyttäytymistä ja liiketoiminnan suorituskykyä. Ne näyttävät olennaiset arvot [yhtenäisistä profiileista](data-unification.md). Ajatellaan, että yrityksessä halutaan nähdä esimerkiksi *kokonaiskulutus asiakasta kohden* yksittäisen asiakkaan ostohistorian tai *yrityksen kokonaismyynti* koko yrityksen yhdistetyn tason tuoton selvittämiseksi.  

Mittarit luodaan käyttämällä [mittareiden luontiohjelmaa](measure-builder.md). Se on tietojen kysely-ympäristö, jossa on useita operaattoreita ja yksinkertaiset yhdistämisvalinnat. Sen avulla voi suodattaa tietoja, ryhmitellä tuloksia, havaita [entiteettisuhteiden polkuja](relationships.md) ja esikatsella tulosta. [Ennalta määritettyjen mallien](measure-templates.md) avulla voit määrittää usein käytettyjä mittareita tehokkaasti.

Käytä mittarin luontiohjelmaa liiketoiminta-aktiviteettien suunnittelemisessa tekemällä kyselyjä asiakastiedoista ja poimimalla tietoja. Esimerkiksi *asiakaskohtainen kokonaiskulutus*- ja *asiakaskohtainen kokonaispalautus* -mittarin luominen auttaa tunnistamaan asiakkaat, jotka ostavat paljon, mutta tekevät myös paljon palautuksia. Voit luoda näiden mittarien perusteella [segmentin](segments.md), joka edistää seuraavia parhaita toimintoja. 

## <a name="manage-your-measures"></a>Hallitse mittoja

**Mittarit**-sivulla on mittarien luettelo.

Saat tietoja mittarityypistä, tekijästä, luontipäivästä ja tilasta. Kun valitset mittarin luettelosta, voit esikatsella tulosta ja ladata CSV-tiedoston.

Jos haluat päivittää kaikki mitat samalla kertaa, valitse **Päivitä kaikki** valitsematta tiettyä mittaa.

:::image type="content" source="media/measure-actions.png" alt-text="Yksittäisten mittareiden hallintatoiminnot.":::

Valitse seuraaville vaihtoehdoille mittari luettelosta:

- Voit tarkastella tietoja valitsemalla mitan nimen.
- **Muokkaa** mitan määritystä.
- **Päivitä** mittari uusimpien tietojen perusteella.
- **Nimeä uudelleen** mitta.
- **Poista** mitta.
- **Aktivoi** tai **poista aktivointi**. Passiivisia mittareita ei päivitetä [aikataulutetun päivityksen](system.md#schedule-tab) aikana.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Seuraava vaihe

Voit luoda [asiakassegmentin](segments.md) olemassa olevien mittareiden avulla.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
