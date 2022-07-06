---
title: Järjestelmän kokoonpano
description: Lisätietoja Dynamics 365 Customer Insightsin järjestelmän asetuksista.
ms.date: 04/21/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 0ef84d8e286d8135eb8938e72f1319925e948bed
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050667"
---
# <a name="system-configuration"></a>Järjestelmän kokoonpano

Jos haluat käyttää järjestelmämäärityksiä, siirry kohtaan **Järjestelmänhallinta** > **Järjestelmä** tarkastellaksesi järjestelmätehtävien ja -prosessien luetteloa.

**Järjestelmä**-sivu sisältää seuraavat välilehdet:
- [Tila](#status-tab)
- [Aikatauluta](#schedule-tab)
- [Ohjelmointirajapinnan käyttö](#api-usage-tab)
- [Tietoja](#about-tab)
- [Yhteiset](#general-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Järjestelmäsivun asetusten välilehdet":::

## <a name="status-tab"></a>Tila-välilehti

**Tila-välilehdessä** voit seurata tehtävien etenemistä, tietojen käyttöä, tietojen vientiä ja monia muita tärkeitä tuoteprosesseja. Tarkista tämän välilehden tiedot ja varmista, että aktiiviset tehtävät ja prosessit ovat täydellisiä.

Tässä välilehdessä on taulukoita, joissa on tila- ja käsittelytietoja eri prosesseja varten. Kukin taulukko seuraa tehtävän **nimeä** ja sen vastaavaa entiteettiä, **tilaa**, jossa se on useimmiten suoritettu ja sen **edellistä päivityspäivää**. Voit tarkastella useiden viime suoritusten tietoja valitsemalla tehtävän tai prosessin nimen. 

Valitse tila tehtävän tai prosessin vieressä **Tila**-sarakkeessa, jos haluat avata **Edistymisen tiedot** -ruudun.

   :::image type="content" source="media/system-progress-details.png" alt-text="Järjestelmän Edistymisen tiedot -ruutu":::

### <a name="status-definitions"></a>Tilamääritykset

Järjestelmä käyttää tehtäviä ja prosesseja varten seuraavia tiloja:

|Tila  |Määritelmä  |
|---------|---------|
|Peruutettu |Käyttäjä on peruuttanut käsittelyn, ennen kuin se valmistui.   |
|Epäonnistunut   |Tietojen käsittelyssä havaittiin virheitä.         |
|Virhe  |Käsittely epäonnistui.  |
|Ei aloitettu   |Tietolähteessä ei ole vielä käsiteltyjä tietoja tai se on edelleen luonnostilassa.         |
|Käsittely  |Tehtävä tai prosessi on käynnissä.  |
|Päivittää    |Tietoja käsittely on meneillään. Voit peruuttaa tämän toiminnon valitsemalla **Pysäytä päivittäminen** **Toiminnot**-sarakkeessa. Tietolähteen päivittämisen pysäyttäminen palauttaa sen tilaan, jossa se on viimeksi päivitetty.       |
|Ohitettu  |Tehtävä tai prosessi ohitettiin. Vähintään yksi palvelimelta siirrettävä prosessi, josta tämä tehtävä on riippuvainen, on epäonnistumassa tai se ohitettiin.|
|Onnistui  |Tehtävä tai prosessi on suoritettu. Tietolähteiden osalta ilmaisee, että tiedot on käsitelty onnistuneesti, jos **Päivitetty**-sarakkeessa mainitaan aika.|
|Jonossa | Käsittely asetetaan jonoon, ja se käynnistyy, kun kaikki alkuvaiheen tehtävät ja prosessit on suoritettu. Lisätietoja on aiheessa [Prosessien päivittäminen](#refresh-processes).|

### <a name="refresh-processes"></a>Prosessien päivittäminen

Tehtävien ja prosessien päivitys suoritetaan [määritetyn aikataulun](#schedule-tab) mukaisesti. 

|Prosessi  |Kuvaus  |
|---------|---------|
|Aktiviteetti  |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu yhdistämisprosessista. Merktiykselliset tiedot riippuvat sen käsittelystä.|
|Analyysin linkitys |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu segmenteistä.  |
|Analyysin valmistelu |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu segmenteistä.  |
|Tietojen valmistelu   |Entiteetti on suoritettava. Tietolähde-entiteetit määräytyvät käsittelyn mukaan. Rikastetut entiteetit määräytyvät rikastusten mukaan. Asiakas-entiteetti määräytyy yhdistämisen mukaan.  |
|Tietolähteet   |Ei riipu mistään muusta prosessista. Vastaavuus riippuu tämän prosessin onnistuneesta suorittamisesta.  |
|Rikastukset   |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu yhdistämisprosessista. |
|Vientikohteet |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu segmenteistä.  |
|Näkemykset |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu segmenteistä.  |
|Analytiikka   |Määräytyy yhdistämisen mukaan.   |
|Täsmäytä |Määräytyy vastaavuusmäärityksessä käytettyjen tietolähteiden käsittelyn mukaan.      |
|Mittarit  |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu yhdistämisprosessista.  |
|Yhdistä   |Riippuu täsmäytysprosessin suorittamisesta. Segmentit, mittarit, rikastus, haku, aktiviteetit, ennusteet ja tietojen valmistelu riippuvat tämän prosessin onnistuneesta suorittamisesta.   |
|Profiilit   |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu yhdistämisprosessista. |
|Hae   |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu yhdistämisprosessista. |
|Segmentit  |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu yhdistämisprosessista. Merktiykselliset tiedot riippuvat sen käsittelystä.|
|Järjestelmä   |Riippuu täsmäytysprosessin suorittamisesta. Segmentit, mittarit, rikastus, haku, aktiviteetit, ennusteet ja tietojen valmistelu riippuvat tämän prosessin onnistuneesta suorittamisesta.   |
|Käyttäjä  |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu entiteeteistä.  |

Valitse prosessin tila, jos haluat nähdä koko työn edistymistiedot. Yllä olevien päivitysprosessien avulla saat tietoja siitä, miten voit käsitellä **ohitettua** tai **jonoon määritettyä** tehtävää tai prosessia.

## <a name="schedule-tab"></a>Aikataulut-välilehti

**Ajoitus**-välilehdessä voi ajoittaa kaikkien [käsiteltyjen tietolähteiden](data-sources.md) automaattiset päivitykset. Automaattisten päivitysten avulla voit varmistaa, että tietolähteiden päivitykset näkyvät yhtenäisessä asiakasprofiilissa.

> [!NOTE]
> Hallitsemasi tietolähteet päivittyvät omien aikataulujensa mukaan. Voit ajoittaa hallitsemiesi tietolähteiden päivitykset määrittämällä päivitysasetukset kyseiselle tietolähteelle **Tietolähteet**-sivulla.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform – tietovuon päivitysasetukset.":::

1. Siirry kohtaan **Järjestelmänvalvoja** > **Järjestelmä** ja valitse **Aikataulu**-välilehti.

2. Ajoitetun päivityksen oletustila on **Ei käytössä**. Jos haluat ottaa ajoitetut päivitykset käyttöön, vaihda näytön yläreunassa olevan kohdan arvoksi **Käytössä**.

3. Valitse päivitysväliksi **Viikoittain** (oletusarvo) tai **Päivittäin**. Jos aiot aikatauluttaa viikoittaiset päivitykset, valitse vähintään yksi päivä, jolloin haluat suorittaa päivityksen.

4. Määritä **Aikavyöhyke** ja määritä sitten avattava **Aika**-luettelo, jos haluat määrittää päivityksen ajoituksen. Kun olet valmis, valitse **Määritä**. Jos haluat aikatauluttaa useita päivityksiä yhdelle päivälle, valitse **Lisää toinen aika**.

5. Ota muutokset käyttöön valitsemalla **Tallenna**.

## <a name="about-tab"></a>Tietoja-välilehti

**Tietoja**-välilehdessä on tietoja organisaation **näyttönimestä**, aktiivisen **ympäristön tunnuksesta**, **alueesta** ja **istunnon tunnuksesta**. Jos työympäristöjä on useita, kullekin on annettava helposti tunnistettava näyttönimi.

## <a name="general-tab"></a>Yleiset-välilehti

Kieltä ja maa- tai aluemuotoa voi vaihtaa **Yleiset**-välilehdessä.

Customer Insights [tukee useita kieliä](/dynamics365/get-started/availability). Sovellus käyttää kieliasetuksia näyttämään elementit, kuten valikon, selitetekstin ja järjestelmän sanomat, ensisijaisella kielellä.

Tuotuja tietoja ja manuaalisesti annettuja tietoja ei käännetä.

### <a name="update-the-settings"></a>Asetusten päivittäminen

Jos haluat vaihtaa ensisijaista kieltä, valitse **Kieli** avattavasta luettelosta.

Jos haluat muuttaa päivämäärien, kellonaikojen ja lukujen muotoilua, käytä avattavaa **Maan/alueen muoto** -valikkoa. Tämän kentän alapuolella näkyy muotoilun esikatselu. Järjestelmä ehdottaa automaattisesti valintaa, kun valitset uuden kielen.

Valitse **Tallena** valintojen vahvistamiseksi.

## <a name="api-usage-tab"></a>Ohjelmointirajapinnan käyttö -välilehti

Etsi reaaliaikaisen ohjelmointirajapinnan käyttöä koskevat tiedot ja katso, mitä tapahtumia tiettynä aikavälinä on suoritettu. Valitse aikaväli avattavasta **Valitse aikaväli** -valikosta. 

**Ohjelmointirajapinnan käyttö** sisältää seuraavat kolme osaa: 
- **Ohjelmointirajapinnan kutsut** - kaavio, joka visualisoi ohjelmointirajapinnan koostettujen kutsujen määrän valittuna aikavälinä.

- **Tietojen siirto** - kaavio, joka näyttää valitun ohjelmointirajapinnan kautta siirrettyjen tietojen määrän valittuna aikavälinä.

-  **Toiminnot** - taulukko, jossa on rivejä kullekin käytettävissä olevalle ohjelmointirajapinnan toiminnolle sekä toimintojen käyttöä koskevat tiedot. Voit valita toiminnon nimen ja siirtyä [ohjelmointirajapinnan viitteeseen](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   [Reaaliaikaista tietojen käsittelyä](real-time-data-ingestion.md) käyttävät toiminnot sisältävät painikkeen, jolla näkyy reaaliaikaisen ohjelmointirajapinnan käytön kiikarisymboli. Painikkeen valitseminen avaa sivuruudun, jossa on reaaliaikaisen ohjelmointirajapinnan käyttötiedot nykyisessä ympäristössä.   
   Voit valita parhaan esitystavan reaaliaikaiselle vuorovaikutukselle **Reaaliaikainen ohjelmointirajapinnan käyttö** -ruudun **Ryhmittely**-ruudun avulla. Voit ryhmitellä tiedot ohjelmointirajapintamenetelmän, entiteetin hyväksytyn nimen (sisällytetty entiteetti), luojan (tapahtuman lähde), tuloksen (onnistuminen tai epäonnistuminen) tai virhekoodien mukaan. Tiedot ovat käytettävissä historiakaaviona ja taulukkona.


[!INCLUDE [footer-include](includes/footer-banner.md)]
