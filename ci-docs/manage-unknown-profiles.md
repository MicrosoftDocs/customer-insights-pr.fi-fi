---
title: Hallitse tuntemattomia profiileja Customer Insightsin avulla
description: Käytä tuntemattomia asiakasprofiileja, joita luodaan ja hallitaan Dynamics 365 Customer Insightsissa.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: d7e5050ee5832df5ecf40a352f7ea8d42830fa45
ms.sourcegitcommit: f6b6a4c4ce9cf12e449488b24aab80a2cbfe0c47
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/21/2022
ms.locfileid: "9556392"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Hallitse tuntemattomia profiileja Customer Insightsin avulla

Internetin käyttäjät ovat usein tunnistamattomia ja nimettömiä online-tilassa. Jos he eivät ole kirjautuneet sisään, koska he käyttävät eri laitteita tai kanavia, se koskee jopa uskollisimpia asiakkaita. Koska kolmansien osapuolten evästeet todennäköisesti poistuvat pian, käyttäjien mieltymysten hallinta ensimmäisen osapuolen tietojen perusteella on erittäin tärkeää, jotta yksilölliset käyttökokemukset voidaan erottaa toisistaan. Monissa tuotemerkeissä tunnetut tai todennetut käyttäjät ovat vähemmistö, vaikka asiakkaiden yksilöllistyminen on kasvamassa. Yritysten on hyvä tuntea asiakkaansa luotettavan, yksityiskohtaisen ja yhtenäisen tiedon perusteella.

Mieleenjäävä mukauttaminen riippuu asiakastietojen kattavuudesta ja täydellisyydestä, ja Customer Insights auttaa saavuttamaan nämä tavoitteet. Sinun ei tarvitse rajoittaa tai lopettaa niiden tietojen käyttöä, joka on kerätty asiakassiirtymän alussa. Customer Insightsin avulla voit tuoda omia tietojasi ja luoda asiakasprofiilin tuntemattomille käyttäjille. Profiilia voi käyttää lisätoimintoja varten puuttuvista yhteystiedoista huolimatta. Tuo ensimmäisen osapuolen tietoja esimerkiksi verkko-, mobiili- tai CRM-järjestelmistä Customer Insights -tietoihin, jotta asiakasprofiileja voi täydentää jatkuvasti. Kun yhdenmukaistat useampia vuorovaikutuksia, [muuta *tuntematon* asiakas *tunnetuksi* asiakkaaksi](unknown-to-known.md).

## <a name="sample-scenario"></a>Näyteskenaario

Sähköinen kaupankäynti on nopeimmin kasvava kanava viime vuosikymmeninä. Oletetaan, että käyttäjä selaa sähköisen kaupankäynnin sivustoa mobiililaitteen avulla. Verkkosivusto määrittää vierailijalle yksilöllisen “mobile_guest123”-tunnisteen, ja aloitat käyttäytymisaktiviteettien keräämisen verkkoaktiviteettien perusteella. Esimerkiksi millä sivuilla he kävivät, kuinka paljon aikaa he käyttivät kyseisillä sivuilla tai mitä linkkejä he napsauttivat. Et tiedä heidän nimeään tai sähköpostiosoitettaan, mutta näiden tietojen avulla tuotemerkit saavat merkityksellistä tietoa tästä tietystä käyttäjästä. Voit puolestaan määrittää nämä tiedot toimimaan seuraavan kerran, kun käyttäjä käy sivustossa. Suorita kysely Customer Insightsissa “mobile_guest123”-käyttäjälle saadaksesi käyttäjän segmenttiluettelon, kuten "orgaaninen", "mobiilit esitilausasiakkaat", "korkean arvon asiakkaat" jne tai nouda profiili luodaksesi personoituja verkkokokemuksia. Voit myös viedä tiedot mihin tahansa aktivointijärjestelmään, jotta voit tehdä samoin.

## <a name="prerequisites"></a>edellytykset

- Tuo ensimmäisen osapuolen tiedot Customer Insightsiin
- Kullakin entiteetilla on yksilöllinen tunnus, joka on määritetty perusavaimeksi
- Jokainen entiteetti, jolla on mukauttamista varten perusavain, on yhtenäinen
- Verkkosivuston sisällönhallintajärjestelmä voi käyttää ohjelmointirajapintoja (www-mukauttamista varten, joka perustuu suoraan viestintään Customer Insightsin kanssa)

Seuraavassa taulukossa on esitetty yksinkertaistettu esimerkki siitä, miten arvotapahtumia voidaan siepata.

|Tapahtuman tunnus|Tapahtuman aikaleima|Käyttäjätunnus|PrimaryKey|Tapahtuman nimi|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|Tuotenäkymä|
|2|09-18-2022 10:05:00|abc123|CookieID1|Tuotenäkymä|
|3|09-18-2022 10:10:00|abc123|CookieID1|Lisää ostoskoriin|
|4|09-21-2022 09:05:00|abc123|CookieID1|Tuotenäkymä|

## <a name="data-ingestion"></a>Tietojen käsittely

Lisätietoja tietojen käsittelyn vaihtoehdoista on kohdassa [Tietolähteiden yleiskatsaus](data-sources.md).

## <a name="data-unification"></a>Tietojen yhdistäminen

Lisätietoja asiakasprofiilien yhdistämisestä on kohdassa [Tietojen yhdistämisen yleiskatsaus](data-unification.md).

## <a name="get-insights"></a>Hanki tiedot

[Rikasta](enrichment-hub.md) tietojasi, kokoa [mittareita](measures.md) ja luo [segmenttejä](segments.md) lisäaktivointiin.

Voit esimerkiksi luoda segmenttejä tuntemattomia käyttäjiä varten, jotka selasivat samoja tuotesivuja mutta eivät koskaan suorittaneet ostoa loppuun.

## <a name="activation"></a>Aktivoiminen

Customer Insights -tietojen ja käyttövalmiiden tietojen avulla voit käyttää Customer Insights -tietoja räätälöinnissä:

1. [OData-ohjelmointirajapinnan](apis.md) avulla voit hakea segmentin jäsenyyden tai asiakasprofiilin. Lisää esimerkkejä on [OData-kyselyn esimerkeissä Customer Insights -ohjelmointirajapintoja varten](odata-examples.md).

1. [Vie](export-destinations.md) tiedot aktivointijärjestelmiin.

Esimerkki: tuntematon käyttäjä käy verkkosivustossa useita kertoja ja vierailee tuotesivuilla, joilla on eri nahkakenkiä. Näiden käytettävissä olevien Customer Insights -tietojen avulla voit sisällyttää tuntemattoman käyttäjän segmenttiin ihmisistä, joita kiinnostavat nahkakengät. Tämän segmentin avulla voit kertoa verkkosivustollesi, että palaaville vierailijoille on luotava mukautus. Seuraavan vierailun aikana sivusto tunnistaa tuntemattoman käyttäjän ja voi tarjota hänelle 10 prosentin alennuskupongin nahkakengistä.

[!INCLUDE [footer-include](includes/footer-banner.md)]