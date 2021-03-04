---
title: Järjestelmän määrittäminen käyttäjäryhmän merkityksellisissä tiedoissa
description: Tietoja Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuuden järjestelmäasetuksista.
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: a9c9e258da49b8f452550794539962d48b856829
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267336"
---
# <a name="system-configuration"></a>Järjestelmän kokoonpano

**Järjestelmä**-sivu sisältää seuraavat välilehdet:
- [Tila](#status-tab)
- [Aikatauluta](#schedule-tab)
- [Ohjelmointirajapinnan käyttö](#api-usage-tab)
- [Tietoja](#about-tab)
- [Yhteiset](#general-tab)

> [!div class="mx-imgBorder"]
> ![Järjestelmä-sivu](media/system-tabs.png "Järjestelmä-sivu")

## <a name="status-tab"></a>Tila-välilehti

**Tila-välilehdessä** voit seurata tietojen käsittelyn, tietojen vientien ja useiden muiden tärkeiden tuoteprosessien edistymistä. Tarkistamalla tämän välilehden tiedot voit varmistaa, että aktiiviset prosessit ovat valmiita.

Tässä välilehdessä on taulukoita, joissa on tila- ja käsittelytietoja eri prosesseja varten. Kukin taulukko seuraa tehtävän **nimeä** ja sen vastaavaa entiteettiä, **tilaa**, jossa se on useimmiten suoritettu ja sen **edellistä päivityspäivää**.

Tarkastele tehtävän viimeisimpien suoritusten tietoja valitsemalla tehtävän nimi.

### <a name="status-types"></a>Tilatyypit

Tehtävillä on kuusi tilatyyppiä. Seuraavat tilatyypit näkyvät myös sivuilla *Täsmäytä*, *Yhdistä*, *Tietolähteet*, *Segmentit*, *Mittarit*, *Rikastaminen*, *Aktiviteetit* ja *Ennusteet*:

- **Käsittelyssä:** Tehtävä on meneillään. Tilaksi voi muuttua Onnistunut tai Epäonnistunut.
- **Onnistunut:** tehtävä suoritettiin onnistuneesti.
- **Ohitettu:** Tehtävä ohitettiin. Vähintään yksi palvelimelta siirrettävä prosessi, josta tämä tehtävä on riippuvainen, on epäonnistumassa tai se ohitettiin.
- **Epäonnistunut:** tehtävän käsitteleminen epäonnistui.
- **Peruutettu:** Käyttäjä peruutti käsittelyn, ennen kuin se valmistui.
- **Jonossa:** Käsittely asetetaan jonoon, ja se käynnistyy, kun kaikki yläpuolella olevat tehtävät on suoritettu. Lisätietoja: [Päivityskäytännöt](#refresh-policies).

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

Etsi reaaliaikaisen ohjelmointirajapinnan käyttöä koskevat tiedot ja katso, mitä tapahtumia tiettynä aikavälinä on suoritettu. Aikaväli valitaan avattavassa **Valitse aikaväli** -valikossa. 

**Ohjelmointirajapinnan käyttö** sisältää seuraavat kolme osaa: 
- **Ohjelmointirajapinnan kutsut** - kaavio, joka visualisoi ohjelmointirajapinnan koostettujen kutsujen määrän valittuna aikavälinä.

- **Tietojen siirto** - kaavio, joka näyttää valitun ohjelmointirajapinnan kautta siirrettyjen tietojen määrän valittuna aikavälinä.

-  **Toiminnot** - taulukko, jossa on rivejä kullekin käytettävissä olevalle ohjelmointirajapinnan toiminnolle sekä toimintojen käyttöä koskevat tiedot. Voit valita toiminnon nimen ja siirtyä [ohjelmointirajapinnan viitteeseen](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Toiminnot, joissa käytetään [reaaliaikaista tietojen käsittelyä](real-time-data-ingestion.md), sisältävät kiikarisymbolin. Sen avulla voi tarkastella reaaliaikaista ohjelmointirajapinnan käyttöä. Painikkeen valitseminen avaa sivuruudun, jossa on reaaliaikaisen ohjelmointirajapinnan käyttötiedot nykyisessä ympäristössä.   
   Voit valita parhaan esitystavan reaaliaikaiselle vuorovaikutukselle **Reaaliaikainen ohjelmointirajapinnan käyttö** -ruudun **Ryhmittely**-ruudun avulla. Voit ryhmitellä tiedot ohjelmointirajapintamenetelmän, entiteetin hyväksytyn nimen (sisällytetty entiteetti), luojan (tapahtuman lähde), tuloksen (onnistuminen tai epäonnistuminen) tai virhekoodien mukaan. Tiedot ovat käytettävissä historiakaaviona ja taulukkona.


[!INCLUDE[footer-include](../includes/footer-banner.md)]