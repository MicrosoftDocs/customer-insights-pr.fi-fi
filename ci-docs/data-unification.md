---
title: Tietojen yhdistämisen yleiskatsaus
description: Käy tietojen yhdistämisprosessi läpi tietojen kanssa ja luo unified customer profiles -profiilien yksittäinen tietojoukko.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: 0dbc3b2c75365e94758a1b6330e8cb557e6bd768
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081004"
---
# <a name="data-unification-overview"></a>Tietojen yhdistämisen yleiskatsaus

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Kun [tietolähteet on määritetty](data-sources.md), tiedot voidaan yhdistää. Tietojen yhdistämisen avulla voit yhdistää aiemmin erilliset tietolähteet yhdeksi päätietojoukoksi, joka tarjoaa yhtenäisen näkymän kyseisistä tiedoista. Yksittäisille kuluttajille (B-to-C), joissa tiedot on yhdistetty yksittäisiin henkilöihin, yhdistäminen tarjoaa yhtenäisen näkymän asiakkaistasi. Yritystileille (B-to-B), joissa tiedot on keskitetty tileihin, yhdistäminen tarjoaa yhtenäisen näkymän tileistäsi.

Tiedot voidaan yhtenäistää yhdessä entiteetissä tai useassa entiteetissä. Yhdistäminen suoritetaan seuraavassa järjestyksessä:

1. [Lähdekentät](map-entities.md) (joita on aiemmin kutsuttu nimellä Yhdistä): Valitse lähdekenttien vaiheessa entiteetit ja kentät, jotka sisällytetään yhdistämisprosessiin. Yhdistä kentät yleiseen semanttiseen tyyppiin, joka kuvaa kentän tarkoitusta.

1. [Tietueiden kaksoiskappaleet](remove-duplicates.md) (aiemmin Vastineen osa): Voit määrittää tietueiden kaksoiskappaleiden vaiheessa säännöt, jotka poistavat asiakastietueiden kaksoiskappaleet kustakin entiteetistä.

1. [Ehtojen vastaavuus](match-entities.md) (jota on aiemmin kutsuttu Vastine): Määritä ehtoja vastaavassa vaiheessa säännöt, jotka vastaavat entiteettien välisiä asiakastietueita. Kun asiakas löytyy vähintään kahdesta entiteetistä, luodaan yksi yhdistetty tietue, jossa on kaikki kunkin entiteetin sarakkeet ja tiedot.

1. [Yhdistetyt asiakaskentät](merge-entities.md) (joita on aiemmin kutsuttu Yhdistämiseksi): Määritä yhdistetyn asiakaskentän vaiheessa, mitkä lähdekentät tulisi sisällyttää, sulkea pois tai yhdistää unified customer profiles -profiiliin.  

1. [Tarkista](review-unification.md) ja luo yhtenäinen profiili.

Tietojen yhdistämisen jälkeen voit valinnaisesti:

- [Määrittää entiteettien väliset suhteet](relationships.md), joilla luodaan edistyneitä segmenttejä.
- [Rikastaa tietoja](enrichment-hub.md), joiden avulla saat enemmän merkityksellisiä tietoja asiakkaista.
- [Määrittää aktiviteetteja](activities.md) joistakin käytetyistä määritteistä.
- [Luoda mittareita](measures.md) ymmärtääksesi paremmin asiakkaiden käyttäytymistä ja liiketoiminnan suorituskykyä.

[!INCLUDE [footer-include](includes/footer-banner.md)]
