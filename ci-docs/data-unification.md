---
title: Yhtenäisen näkymän luominen asiakkaille
description: Käy tietojen yhdistäminen läpi tietojen kanssa ja luo tili- tai asiakasprofiilien yksittäinen päätietojoukko.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304423"
---
# <a name="data-unification-overview"></a>Tietojen yhdistämisen yleiskatsaus

Kun [tietolähteet on määritetty](data-sources.md), tiedot voidaan yhdistää. Tietojen yhdistämisen avulla voit yhdistää aiemmin erilliset tietolähteet yhdeksi päätietojoukoksi, joka tarjoaa yhtenäisen näkymän kyseisistä tiedoista.

Yksittäisille kuluttajille (B-to-C), joissa tiedot on yhdistetty yksittäisiin henkilöihin, yhdistäminen tarjoaa yhtenäisen näkymän asiakkaistasi. Yritystileille (B-to-B), joissa tiedot on keskitetty tileihin, yhdistäminen tarjoaa yhtenäisen näkymän tileistäsi. [Yhteyshenkilöiden yhdistäminen (esiversio)](data-unification-contacts.md) mahdollistaa sen, että näiden tilien yhteyshenkilöt voidaan erikseen yhdistää ja liittää tileihin.

Tiedot voidaan yhtenäistää yhdessä entiteetissä tai useassa entiteetissä.

# <a name="individual-consumers-b-to-c"></a>[Yksittäiset kuluttajat (kuluttajakauppa)](#tab/b2c)

Yhdistäminen yhdistää asiakastiedot tietolähteistä, poistaa kaksoiskappaleet, täsmäyttää tiedot entiteettien välillä ja luo yhtenäisen profiilin. Yhdistäminen suoritetaan seuraavassa järjestyksessä:

1. [Lähdekentät](map-entities.md) (joita on aiemmin kutsuttu nimellä Yhdistä): Valitse lähdekenttien vaiheessa entiteetit ja kentät, jotka sisällytetään yhdistämisprosessiin. Yhdistä kentät yleiseen semanttiseen tyyppiin, joka kuvaa kentän tarkoitusta.

1. [Tietueiden kaksoiskappaleet](remove-duplicates.md) (aiemmin Vastineen osa): Voit määrittää tietueiden kaksoiskappaleiden vaiheessa säännöt, jotka poistavat asiakastietueiden kaksoiskappaleet kustakin entiteetistä.

1. [Ehtojen vastaavuus](match-entities.md) (jota on aiemmin kutsuttu Vastine): Määritä ehtoja vastaavassa vaiheessa säännöt, jotka vastaavat entiteettien välisiä asiakastietueita. Kun asiakas löytyy vähintään kahdesta entiteetistä, luodaan yksi yhdistetty tietue, jossa on kaikki kunkin entiteetin sarakkeet ja tiedot.

1. [Yhdistetyt asiakaskentät](merge-entities.md) (joita on aiemmin kutsuttu Yhdistämiseksi): Määritä yhdistetyn asiakaskentän vaiheessa, mitkä lähdekentät tulisi sisällyttää, sulkea pois tai yhdistää unified customer profiles -profiiliin.  

1. [Tarkista](review-unification.md) ja luo yhtenäinen profiili.

# <a name="business-accounts-b-to-b"></a>[Yritystilit (yritysten väliset)](#tab/b2b)

Yhdistäminen yhdistää tilitiedot tietolähteistä, poistaa kaksoiskappaleet, täsmäyttää tiedot entiteettien välillä ja luo yhtenäisen profiilin. Yhdistäminen suoritetaan seuraavassa järjestyksessä:

1. [Lähdekentät](map-entities.md) (joita on aiemmin kutsuttu nimellä Yhdistä): Valitse lähdekenttien vaiheessa entiteetit ja kentät, jotka sisällytetään tilien yhdistämisprosessiin. Yhdistä kentät yleiseen semanttiseen tyyppiin, joka kuvaa kentän tarkoitusta.

1. [Tietueiden kaksoiskappaleet](remove-duplicates.md) (aiemmin Vastineen osa): Voit määrittää tietueiden kaksoiskappaleiden vaiheessa säännöt, jotka poistavat tilitietueiden kaksoiskappaleet kustakin entiteetistä.

1. [Ehtojen vastaavuus](match-entities.md) (jota on aiemmin kutsuttu Vastine): Määritä ehtoja vastaavassa vaiheessa säännöt, jotka vastaavat entiteettien välisiä tilitietueita. Kun tili löytyy vähintään kahdesta entiteetistä, luodaan yksi yhdistetty tietue, jossa on kaikki kunkin entiteetin sarakkeet ja tiedot.

1. [Yhdistetyt asiakaskentät](merge-entities.md) (joita on aiemmin kutsuttu Yhdistämiseksi): Määritä yhdistetyn asiakaskentän vaiheessa, mitkä lähdekentät tulisi sisällyttää, sulkea pois tai yhdistää unified customer profiles -profiiliin.  

1. [Tarkista](review-unification.md) ja luo yhtenäinen profiili.

Kun olet yhdistänyt tilit, voit halutessasi [yhdistää kyseisten tilien yhteyshenkilöt (esiversio)](data-unification-contacts.md) ja linkittää yhdistetyt yhteyshenkilöt yhtenäistettyihin tileihin.

---

Tietojen yhdistämisen jälkeen voit valinnaisesti:

- [Määrittää entiteettien väliset suhteet](relationships.md), joilla luodaan edistyneitä segmenttejä.
- [Rikastaa tietoja](enrichment-hub.md), joiden avulla saat enemmän merkityksellisiä tietoja asiakkaista.
- [Määrittää aktiviteetteja](activities.md) joistakin käytetyistä määritteistä.
- [Luoda mittareita](measures.md) ymmärtääksesi paremmin asiakkaiden käyttäytymistä ja liiketoiminnan suorituskykyä.

[!INCLUDE [footer-include](includes/footer-banner.md)]
