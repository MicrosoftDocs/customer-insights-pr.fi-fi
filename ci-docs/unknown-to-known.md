---
title: Mukauta käyttökokemustasi tunnettujen ja tuntemattomien käyttäjien tietojen avulla
description: Liitä mukaan aiemmin tuntematonta käyttäjää koskevat tiedot, kun tiedät hänen henkilöllisyytensä.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224291"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Mukauta käyttökokemustasi tunnettujen ja tuntemattomien käyttäjien tietojen avulla

Asiakastietojen hallinta ei ole uusi asia, mutta siitä on tulossa yhä vaikeampaa, kun käyttäjät käyttävät eri digitaalisten kanavien tuotemerkkejä. Käyttäjästä, joka on tunnettu (todennettu) jossakin kanavassa, tulee tuntematon (todentamaton) toisessa, jos hän ei ole kirjautunut sisään. Ongelmana on usein se, että todentamattomilla (tuntematon) käyttäjillä ei ole yhteistä tunnusta. Sen avulla voidaan liittää merkityksellisiä profiilimääritteitä ja luoda yhtenäisiä asiakasprofiileja. Customer Insights auttaa tämän ongelman ratkaisemisessa keräämällä tietoja lähdejärjestelmien seurantatavoista. Konsolidoidut tuntemattomat ja tunnetut profiilit tarjoavat organisaatioille täydellisen näkymän uusista profiileista sekä niiden historiatapahtumista, käyttäytymisistä ja demografiatiedoista. Lisäksi siinä tarjotaan tunnistetietojen ratkaisu, jonka avulla voit yhdistää asiakasaktiviteetin useissa kanavissa, kuten verkkosivustossasi, myymälässä tehtävässä ostossa ja kanta-asiakasohjelmissa.

## <a name="sample-scenario"></a>Näyteskenaario

Ajatellaanpa kahvilaketjua, jolla on laaja asiakaspohja, joka ostaa kahvia ja tuotteita myymälöistä ja tilaa tuotteita verkosta. Verkkovierailuja ei todenneta usein tuotteita selattaessa, joten niistä tulee ”tuntemattomia käyttäjiä”. Kahvilaketjun on vaikea tuottaa mukautettuja tarjouksia ja käyttökokemusta, jos käyttäjät ovat tuntemattomia. Asiakkaat voivat puolestaan kirjautua tililleen ja tulla yritykseen ”tunnetuiksi käyttäjiksi” liittymällä kanta-asiakasjärjestelmään, joka puolestaan sallii entistä mukautetumpia käyttökokemuksia. Customer Insights voi auttaa kahvilaketjua saamaan tietoja tunnetuista ja aiemmin tuntemattomista käyttäjistä.

Customer Insightsin avulla yritys voi yhdistää asiakasprofiilit aktiviteettitietoihin todentamattomista (tuntematon) istunnoista sen jälkeen, kun käyttäjä on kirjautunut sisään ja tulee tunnetuksi. Kahvilaketju voi tuoda tietoja muista tietolähteistä Customer Insights -liittimien avulla asiakkaiden eri kanavista peräisin olevia identiteettejä.

## <a name="prerequisites"></a>edellytykset

- Verkkotiedot kerätään ja sisältävät vierailijatunnukset kaikille vierailijoille.
- Verkkotiedot sisältävät ”todennetut käyttäjätunnukset” kirjautuneille vierailijoille. Nämä tunnukset linkitetään kanta-asiakasjärjestelmään.
- Arvotapahtumia koskevat tiedot, kuten Tuotenäkymä ja Uloskuittaus, määritetään ja sisällytetään lähdetietoihin tapahtuman aikaleiman ja tapahtumatunnuksen kanssa.

Seuraavassa taulukossa on esitetty yksinkertaistettu esimerkki siitä, miten arvotapahtumia voidaan siepata.

|Tapahtuman tunnus|Tapahtuman aikaleima|Käyttäjätunnus|Kanta-asiakastunnus|Tapahtuman nimi|
|--|--|--|--|--|
|1|23.7.2022 10.00.00|abc123|--|Tuotenäkymä|
|2|23.7.2022 10.05.00|abc123|707|Kanta-asiakkaan kirjautuminen|
|3|23.7.2022 10.10.00|abc123|707|Uloskuittaus|
|4|23.7.2022 10.20.00|xyz789|--|Tuotenäkymä|

## <a name="data-ingestion"></a>Tietojen käsittely

Asiakkaisiin liittyvät tiedot voivat olla peräisin verkkosivustostasi tapahtumatiedoista, ja ne voidaan tallentaa yrityksen omiin tai kolmansien osapuolien tietoanalytiikkapalveluihin. Verkkotiedot sisältävät tunnettuja ja tuntemattomia käyttäjiä, jos sivustossa on todennustyönkulku, joka integroituu todennuspalveluun. Esimerkiksi verkkokauppajärjestelmä, joka edellyttää, että käyttäjät antavat täydelliset tietonsa ostotapahtuman suorittamista varten. Tai kanta-asiakasjärjestelmä, joka edellyttää todennusta palkintoalennusten kelvollisen vastaanottajan vahvistusta varten.

Yllä olevassa esimerkissämme olevat tapahtumatiedot sisältävät tunnettujen ja tuntemattomien käyttäjien erilliset profiilitunnukset. Tapahtumassa 1 ja 4 käyttäjät ovat tuntemattomia, kun tapahtumassa 2 ja 3 käyttäjä, jolla on abc123-tunnus, kirjautuu kanta-asiakasohjelmaan.

:::image type="content" source="media/website-data-source.png" alt-text="Tietolähteet, mukaan lukien Contoson verkkosivusto.":::

Lisätietoja tietojen käsittelyn vaihtoehdoista on kohdassa [Tietolähteiden yleiskatsaus](data-sources.md).

## <a name="data-unification"></a>Tietojen yhdistäminen

Kun tunnistat tuntemattomia identiteettejä ja tunnettuja identiteettejä, mukauttaminen voidaan ottaa käyttöön käyttäjien käyttäytymisen mukaan heidän profiilitilastaan (tunnettu tai tuntematon) huolimatta. Mukautettu sisältö kaikille käyttäjille auttaa asiakkaita pääsemään käyttämään kullakin hetkellä kiinnostavimpia tuotteita tai palveluita.

Koska jotkin tietojemme käyttäjistä ovat tiedossa, voimme yhdistää tiedot käyttäjän profiiliin Customer Insightsin avulla. Lisätietoja asiakasprofiilien yhdistämisestä on kohdassa [Tietojen yhdistämisen yleiskatsaus](data-unification.md).

1. Valitse tietoentiteetin lähdekentät. Käytä verkkotietoihin tallennettuja profiilitietoja ja valitse kentät, jotka edustavat demografisia tietoja sisältäviä tunnuksia.

   :::image type="content" source="media/website-source-fields.png" alt-text="Lähdekentät verkkotietolähdettä varten.":::

1. Lisää sääntöjä tietueiden kaksoiskappaleiden yhdistämistä varten. Valitse verkkotietoja varten täytetyimmät tiedot.

1. Määritä vastaavuuden säännöt ja ehdot. Tämän esimerkin verkkoprofiilien tapahtumatiedot yhdistetään muiden asiakastietoja sisältävien tietolähteiden profiilien tunnuksiin. Määritä tunnuksille tarkat vastaavuussäännöt erillisiksi säännöiksi kaikkien muiden profiilientiteettien kanssa, joilla on vastaava perusavaimen tai tunnuksen vastine. Esimerkissä verkkotapahtumaprofiilin tietoja käytetään viimeisenä vastaavana entiteettinä niin, että muut profiilitiedot yhdistetään ensin.
   1. Jos **Sisällytä kaikki tietueet -ruutua** ei ole valittu, järjestelmä luo yhtenäisiä profiileja tunnetuille käyttäjille ja sisällyttää niiden vastaavat tuntemattomat käyttäjätunnukset. Se on hyödyllinen tilanteissa, joissa olet kiinnostunut tarkastelemaan tunnettujen käyttäjien aiempia käyttäytymisaktiviteetteja ajalta, kun he olivat vielä tuntemattomia.
   1. Jos valitset **Sisällytä kaikki tietueet** -ruudun, erilliset profiilitietueet tuntemattomia käyttäjiä varten luodaan. Tuntemattomat käyttäjät saavat yksilöllisen asiakastunnuksen. Tulevaisuudessa, kun tunnettu profiili on liitetty verkkotapahtumien profiilitietoihin, uuden tunnetun käyttäjän matkaa voidaan tarkastella ja käyttää myös aiempiin tuntemattomiin käyttäytymistietoihin perustuvien mukauttamistietojen tarkastelemiseen.

:::image type="content" source="media/website-match-rule.png" alt-text="Sivuston tietolähteen vastaavuussääntö.":::

## <a name="get-insights"></a>Hanki tiedot

Jos asiakasprofiileja luodaan tuntemattomia ja tunnettuja käyttäjiä varten, arvokkaita verkkotapahtumatietoja voidaan käyttää [aktiviteetteina](activities.md). Näiden aktiviteettien avulla voidaan luoda enemmän tietoja. Esimerkiksi asiakkaat, jotka kävivät verkkosivustolla kuusi kuukautta aiemmin (kun he olivat vielä tuntemattomia), tai asiakkaat, joilla ei ole kanta-asiakastunnusta, eivät ole vielä suorittaneet uloskuittausta.

:::image type="content" source="media/website-known-unknown.png" alt-text="Näyttökuva asiakassivusta, jossa on tunnettuja ja tuntemattomia asiakkaita.":::

[Rikasta](enrichment-hub.md) tietojasi, kokoa [mittareita](measures.md) ja luo [segmenttejä](segments.md) lisäaktivointiin.

Voit esimerkiksi luoda segmenttejä tunnetuista käyttäjistä, jotka ovat tarkastelleet joitakin tuotteita mutta eivät suorittaneet uloskuittausta.

Lisätietoja on kohdassa [Segmenttien yleiskatsaus](segments.md).

## <a name="activate-insights"></a>Aktivoi merkitykselliset tiedot

Voit viedä tietoja ja toimia taustalla olevien tietojen perusteella useilla eri tavoilla.

Lisätietoja on kohdassa [Vientien yleiskatsaus](export-destinations.md).
