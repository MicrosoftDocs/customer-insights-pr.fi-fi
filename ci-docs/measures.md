---
title: Mittarien ymmärtäminen ja hallinta
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
ms.openlocfilehash: 84a3a10a2517258c1f895800882b9c67391ec3de
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646153"
---
# <a name="measures-overview"></a>Mittarien yleiskatsaus

Mittarien avulla ymmärrät paremmin asiakkaiden käyttäytymistä ja liiketoiminnan suorituskykyä. Ne näyttävät olennaiset arvot [yhtenäisistä profiileista](data-unification.md). Ajatellaan, että yrityksessä halutaan nähdä esimerkiksi *kokonaiskulutus asiakasta kohden* yksittäisen asiakkaan ostohistorian tai *yrityksen kokonaismyynti* koko yrityksen yhdistetyn tason tuoton selvittämiseksi.  

Mittarit luodaan käyttämällä [mittareiden luontiohjelmaa](measure-builder.md). Se on tietojen kysely-ympäristö, jossa on useita operaattoreita ja yksinkertaiset yhdistämisvalinnat. Sen avulla voi suodattaa tietoja, ryhmitellä tuloksia, havaita [entiteettisuhteiden polkuja](relationships.md) ja esikatsella tulosta. [Ennalta määritettyjen mallien](measure-templates.md) avulla voit määrittää usein käytettyjä mittareita tehokkaasti.

Käytä mittarin luontiohjelmaa liiketoiminta-aktiviteettien suunnittelemisessa tekemällä kyselyjä asiakastiedoista ja poimimalla tietoja. Esimerkiksi *asiakaskohtainen kokonaiskulutus*- ja *asiakaskohtainen kokonaispalautus* -mittarin luominen auttaa tunnistamaan asiakkaat, jotka ostavat paljon, mutta tekevät myös paljon palautuksia. Voit luoda näiden mittarien perusteella [segmentin](segments.md), joka edistää seuraavia parhaita toimintoja.

## <a name="manage-your-measures"></a>Hallitse mittoja

**Mittarit**-sivulla on mittarien luettelo.

Saat tietoja mittarityypistä, tekijästä, luontipäivästä ja tilasta. Kun valitset mittarin luettelosta, voit esikatsella tulosta ja ladata CSV-tiedoston.

:::image type="content" source="media/measures-actions.png" alt-text="Yksittäisten mittareiden hallintatoiminnot."lightbox="media/measures-actions.png":::

Seuraavat toiminnot ovat käytettävissä, kun valitset mittarin:

- **Muokkaa** mitan määritystä.
- **Monista** mittari. Voit muokata sen ominaisuuksia heti tai tallentaa kaksoiskappaleen.
- **Päivitä** mittari uusimpien tietojen perusteella. Jos haluat päivittää kaikki mittarit samanaikaisesti, valitse kaikki mittarit ja valitse sitten **Päivitä**.
- **Nimeä uudelleen** mitta.
- **Aktivoi** tai **poista aktivointi**. Passiivisia mittareita ei päivitetä [aikataulutetun päivityksen](system.md#schedule-tab) aikana.
- **Tunniste** segmentin [tunnisteiden hallintaa varten](work-with-tags-columns.md#manage-tags).
- **Poista** mitta.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Seuraava vaihe

Voit luoda [asiakassegmentin](segments.md) olemassa olevien mittareiden avulla.

[!INCLUDE [footer-include](includes/footer-banner.md)]
