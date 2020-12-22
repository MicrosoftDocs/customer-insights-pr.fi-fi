---
title: Järjestelmän määrittäminen käyttäjäryhmän merkityksellisissä tiedoissa
description: Tietoja Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuuden järjestelmäasetuksista.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405623"
---
# <a name="system-configuration"></a>Järjestelmän kokoonpano

**Järjestelmä**-sivulla on neljä välilehteä: **Tila**, **Ajoitus**, **Tietoja** ja **Yleiset**.

> [!div class="mx-imgBorder"]
> ![Järjestelmä-sivu](media/system-tabs.png "Järjestelmä-sivu")

## <a name="status-tab"></a>Tila-välilehti

**Tila**-välilehden avulla voit seurata tietojen käyttämisen edistymistä, tietojen vientejä ja useita tärkeitä tuoteprosesseja. Tarkistamalla tämän välilehden tiedot voit varmistaa, että aktiiviset prosessit ovat valmiita.

Tämä välilehti sisältää tilataulukot **Tietolähteille**, **Järjestelmäprosesseille** ja **Tietojen valmistelulle**. Kukin taulukko seuraa tehtävän **nimeä** ja sen vastaavaa entiteettiä, **tilaa**, jossa se on useimmiten suoritettu ja sen **edellistä päivityspäivää**.

Tarkastele tehtävän viimeisimpien suoritusten tietoja valitsemalla tehtävän nimi.

### <a name="status-types"></a>Tilatyypit

Tehtävillä on kuusi tilatyyppiä. Seuraavat tilatyypit näkyvät myös sivuilla *Täsmäytä*, *Yhdistä*, *Tietolähteet*, *Segmentit*, *Mittarit*, *Rikastaminen*, *Aktiviteetit* ja *Ennusteet*:

- **Käsittelyssä:** Tehtävä on meneillään. Tilaksi voi muuttua Onnistunut tai Epäonnistunut.
- **Onnistunut:** tehtävä suoritettiin onnistuneesti.
- **Ohitettu:** Tehtävä ohitettiin. Vähintään yksi palvelimelta siirrettävä prosessi, josta tämä tehtävä on riippuvainen, on epäonnistumassa tai se ohitettiin.
- **Epäonnistunut:** tehtävän käsitteleminen epäonnistui.
- **Peruutettu:** Käyttäjä peruutti käsittelyn, ennen kuin se valmistui.
- **Jonossa:** käsittely on jonossa ja käynnistyy, kun kaikki loppuvaiheen tehtävät on suoritettu. Lisätietoja: [Päivityskäytännöt](#refresh-policies).

### <a name="refresh-policies"></a>Päivityskäytännöt

Tässä luettelossa on kunkin pääprosessin päivityskäytännöt.

- **Tietolähteet:** Suoritetaan [määritetyn aikataulun mukaisesti](#schedule-tab). Ei riipu mistään muusta prosessista. Vastaavuus riippuu tämän prosessin onnistuneesta suorittamisesta.
- **Täsmäytys:** Suoritetaan [määritetyn aikataulun mukaisesti](#schedule-tab). Määräytyy vastaavuusmäärityksessä käytettyjen tietolähteiden käsittelyn mukaan. Yhdistäminen riippuu tämän prosessin onnistuneesta suorittamisesta.
- **Yhdistä**: Suoritetaan [määritetyn aikataulun mukaisesti](#schedule-tab). Riippuu täsmäytysprosessin suorittamisesta. Segmentit, mittarit, rikastus, haku, aktiviteetit, ennusteet ja tietojen valmistelu riippuvat tämän prosessin onnistuneesta suorittamisesta.
- **Segmentit**: Suoritetaan manuaalisesti (kertapäivitys) ja [määritetyn aikataulun mukaisesti](#schedule-tab). Määräytyy Yhdistä-prosessin mukaan. Merktiykselliset tiedot riippuvat sen käsittelystä.
- **Mittarit**: Suoritetaan manuaalisesti (kertapäivitys) ja [määritetyn aikataulun mukaisesti](#schedule-tab). Määräytyy Yhdistä-prosessin mukaan.
- **Aktiviteetit**: Suoritetaan manuaalisesti (kertapäivitys) ja [määritetyn aikataulun mukaisesti](#schedule-tab). Määräytyy Yhdistä-prosessin mukaan.
- **Rikastaminen**: Suoritetaan manuaalisesti (kertapäivitys) ja [määritetyn aikataulun mukaisesti](#schedule-tab). Määräytyy Yhdistä-prosessin mukaan.
- **Haku**: Suoritetaan manuaalisesti (kertapäivitys) ja [määritetyn aikataulun mukaisesti](#schedule-tab). Määräytyy Yhdistä-prosessin mukaan.
- **Tietojen valmistelu**: Suoritetaan [määritetyn aikataulun mukaisesti](#schedule-tab). Määräytyy Yhdistä-prosessin mukaan.
- **Merkitykseliset tiedot**: Suoritetaan manuaalisesti (kertapäivitys) ja [määritetyn aikataulun mukaisesti](#schedule-tab). Riippuu Segmentit-prosessista.

Valitse tehtävän tila, jos haluat tarkastella koko työn edistymistietoja. Yllä olevat päivityskäytännöt voivat auttaa ymmärtämään, mitä voit tehdä **ohitettujen** tai **jonossa** olevien tehtävien käsittelemiseksi.

## <a name="schedule-tab"></a>Aikataulut-välilehti

**Ajoitus**-välilehdessä voi ajoittaa kaikkien [käsiteltyjen tietolähteiden](data-sources.md) automaattiset päivitykset. Automaattisten päivitysten avulla voit varmistaa, että tietolähteiden päivitykset näkyvät yhtenäisessä asiakasprofiilissa.

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Järjestelmä** ja valitse sitten **Ajoitus**-välilehti.

2. Ajoitetun päivityksen oletustila on **Ei käytössä**. Jos haluat ottaa ajoitetut päivitykset käyttöön, vaihda näytön yläreunassa olevan kohdan arvoksi **Käytössä**.

3. Valitse päivitysväliksi **Viikoittain** (oletusarvo) tai **Päivittäin**. Jos aiot aikatauluttaa viikoittaiset päivitykset, valitse vähintään yksi päivä, jolloin haluat suorittaa päivityksen.

4. Määritä **Aikavyöhyke** ja määritä sitten avattava **Aika**-luettelo, jos haluat määrittää päivityksen ajoituksen. Kun olet valmis, valitse **Määritä**. Jos haluat aikatauluttaa useita päivityksiä yhdelle päivälle, valitse **Lisää toinen aika**.

5. Ota muutokset käyttöön valitsemalla **Tallenna**.

## <a name="about-tab"></a>Tietoja-välilehti

**Tietoja**-välilehdessä on tietoja organisaation **näyttönimestä**, aktiivisen **ympäristön tunnuksesta**, **alueesta** ja **istunnon tunnuksesta**. Jos työympäristöjä on useita, kullekin on annettava helposti tunnistettava näyttönimi.

## <a name="general-tab"></a>Yleiset-välilehti

**Yleiset**-välilehdessä on kaksi asetusta, **Kieli** ja **Maan/alueen muoto**.

Sovellus [useita kieliä](supported-languages.md). Jos haluat vaihtaa ensisijaista kieltä, valitse **Kieli** avattavasta luettelosta.

Jos haluat muuttaa päivämäärien, kellonaikojen ja lukujen muotoilua, käytä avattavaa **Maan/alueen muoto** -valikkoa. Tämän kentän alapuolella näkyy muotoilun esikatselu. Järjestelmä ehdottaa automaattisesti valintaa, kun valitset uuden kielen.

Valitse **Tallena** valintojen vahvistamiseksi.

## <a name="api-usage-tab"></a>Ohjelmointirajapinnan käyttö -välilehti

Etsi tietoja reaaliaikaisesta ohjelmointirajapinnan käytöstä ja katso, mitä tapahtumia annetulla aikavälillä on ollut. Lisätietoja on kohdassa [Reaaliaikainen tietojen käyttö](real-time-data-ingestion.md).
