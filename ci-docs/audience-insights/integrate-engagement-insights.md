---
title: Vuorovaikutuksen verkkotietojen integroiminen kohdeyleisön tietojen kanssa
description: Asiakkaiden verkkotietojen tuominen vuorovaikutuksen tiedoista kohdeyleisön tietoihin.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a4cb77bb4c6ef0d88b3f00802f66baab5520a07
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896415"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Vuorovaikutuksen verkkotietojen integroiminen kohdeyleisön tietojen kanssa

Asiakkaat tekevät usein päivittäisiä tapahtumia verkossa sivustojen avulla. Dynamics 365 Customer Insightsin vuorovaikutusominaisuus on kätevä ratkaisu verkkotietojen integroimiseksi lähteenä. Tapahtuma- ja toimintatietojen ja demografisten tietojen lisäksi aktiviteetteja nähdään verkossa yhdistetyissä asiakasprofiileissa. Profiilin avulla voi hankkia lisää tietoja, kuten segmenttejä, mittareita tai ennusteita käyttäjäryhmän aktivoinnista.

Tässä artikkelissa kuvataan asiakkaiden verkkoaktiviteettitietojen tuominen vuorovaikutuksen tietoihin olemassa olevan käyttäjäryhmän tietojen ympäristöstä.

Tässä esimerkissä oletetaan, että ympäristössä on yhdistettyjä asiakasprofiileja. Profiilit yhdistettiin lähteisiin kyselyissä, vähittäismyynnissä ja pääsylippujärjestelmässä. Siinä näkyvät myös asiakkaisiin liittyvät aktiviteetit. 

Haluamme nyt tietää, käyttääkö asiakas verkossa olevia ominaisuuksia ja onko tällä tietoja aktiviteeteista. Aktiviteetteja ovat esimerkiksi sivustot, joilla on käyty, ja sähköpostitse vastaanotettujen linkkien avulla tarkastellut tuotesivut.

## <a name="prerequisites"></a>Edellytykset

Tietojen integroiminen vuorovaikutuksen tiedoista vaatii seuraavien edellytysten täyttämistä: 

- Vuorovaikutuksen tietojen SDK on integroitava sivustossa. Lisätietoja on kohdassa [Verkon SDK:n käytön aloittaminen](../engagement-insights/instrument-website.md).
- Verkkotapahtumien vieminen vuorovaikutuksen tiedoista edellyttää ADLS Gen 2:n tallennustilin käyttämistä. Käyttäjäryhmän tietojen verkkotapahtumat siirretään tilille. Lisätietoja on aiheessa [Tapahtumien vieminen](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Tarkennettujen tapahtumien määrittäminen vuorovaikutuksen tiedoissa

Kun järjestelmänvalvoja muokkaa sivustoa, jolla on vuorovaikutuksen tietojen SDK, *perustapahtumat* kerätään käyttäjän tarkastellessa verkkosivua tai napsauttaessa sivun jotain osaa. Perustapahtumat sisältävät yleensä runsaasti yksityiskohtia. Tapauksesta riippuen tarvitaan vain perustapahtuman tietojen alijoukko. Vuorovaikutuksen tietojen avulla voit luoda *tarkennettuja tapahtumia*, jotka sisältävät vain valitun perustapahtuman ominaisuuksia.     

Lisätietoja on kohdassa [Tarkennettujen tapahtumien luominen ja muokkaaminen](../engagement-insights/refined-events.md).

Tarkennettujen tapahtumien luomisessa huomioon otettavia seikkoja: 

- Anna tarkennetulle tapahtumalle merkityksellinen nimi. Sitä käytetään käyttäjäryhmän tietojen aktiviteetin nimenä.
- Valitse vähintään seuraavat ominaisuudet, jos haluat luoda aktiviteetin käyttäjäryhmän tiedoissa: 
    - Signal.Action.Name - osoittaa aktiviteetin tiedot
    - Signal.User.Id - käytetään asiakastunnuksen yhdistämisessä
    - Signal.View.Uri - käytetään verkko-osoitteessa segmenttien tai mittareiden perustana
    - Signal.Export.Id - käytetään tapahtumien ensisijaisena avaimena
    - Signal.Timestamp - aktiviteetin päivämäärän ja ajan määrittäminen

Valitse käyttötapauksen tapahtumien ja sivujen suodattimet. Tässä esimerkissä käytetään Sähköpostikampanja-toiminnon nimeä.

## <a name="export-the-refined-web-events"></a>Tarkennettujen verkkotapahtumien vieminen 

Kun tarkennettu tapahtuma on määritetty, tapahtuman tietojen vienti on määritettävä Azure Data Lake Storageen. Tämä voidaan määrittää tietolähteeksi käyttäjäryhmän tietojen siirtämistä varten. Vientiä tapahtuu jatkuvasti, kun tapahtumia siirretään verkko-ominaisuudesta.

Lisätietoja on aiheessa [Tapahtumien vieminen](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Tapahtuman tietojen siirtäminen käyttäjäryhmän tietoihin

Nyt, kun tarkennettu tapahtuma ja sen vienti on määritetty, siirretään tietoja käyttäjäryhmän tietoihin. Luodaan uusi tietolähde Common Data Model -kansion perusteella. Syötä sen tallennustilin tiedot, johon tapahtumat viedään. Valitse *default.cdm.json*-tiedostossa tarkennettu tapahtuma siirtämistä varten ja luo entiteetti käyttäjäryhmän tietoihin.

Lisätietoja on kohdassa [Yhteyden muodostaminen Common Data Model -kansioon Azure Data Lake -tilin avulla](connect-common-data-model.md)


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Tarkennetun tapahtuman tietojen liittäminen asiakasprofiiliin aktiviteettina

Kun entiteetti on siirretty, voit määrittää aktiviteetin asiakasprofiilia varten.

Lisätietoja on kohdassa [Asiakasaktiviteetit](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Aktiviteetit-sivu ja laajennettu Muokkaa aktiviteettia -ruutu sekä täytetyt kentät.":::

Määritä uusi aktiviteetti seuraavilla yhdistämismäärityksillä: 

- **Perusavain:** Signal.Export.Id, yksilöllinen tunnus, joka on käytettävissä jokaisessa tapahtumatietueessa vuorovaikutuksen tiedoissa. Tämä ominaisuus luodaan automaattisesti.

- **Aikaleima:** Signal.Timestamp tapahtuman ominaisuudessa.

- **Tapahtuma:** Signal.Name, seurattavan tapahtuman nimi.

- **WWW-osoite:** Signal.View.Uri viittaa tapahtuman luoneen sivun URI-tunnukseen.

- **Tiedot:** Signal.Action.Name esittää tapahtumaan liitettävät tiedot. Tässä tapauksessa valittu ominaisuus osoittaa, että tapahtuma liittyy sähköpostikampanjaan.

- **Aktiviteettityyppi:** Tässä esimerkissä valitaan olemassa olevan aktiviteettityyppi Verkkoloki. Tämä valinta on hyödyllinen suodatusvaihtoehto, jos suoritetaan ennustemallit tai luodaan segmenttejä tämän aktiviteettityypin perusteella.

- **Määritä suhde:** Tämä tärkeä asetus yhdistää aktiviteetin olemassa oleviin asiakasprofiileihin. **Signal.User.Id** on SDK:ssa määritetty kerättävä tunnus. Se liittyy käyttäjätunnukseen muissa tietolähteissä, jotka on määritetty käyttäjäryhmän tiedoissa. Tässä esimerkissä määritetään suhde Signal.User.Id- ja RetailCustomers:CustomerRetailId-tunnuksen välille. Jälkimmäinen on ensisijainen avain, joka määritettiin tietojen yhdistämisprosessin yhdistämisvaiheessa.


Aktiviteettien käsittelemisen jälkeen voit tarkastella asiakastietueita ja avata asiakaskortin. Näin näet vuorovaikutuksen tietojen aktiviteetit aikajanalla. 

> [!TIP]
> Jos haluat etsiä asiakastunnuksen, jolla on vuorovaikutuksen tietojen aktiviteetti, siirry kohtaan **Entiteetit** ja esikatsele UnifiedActivity-entiteetin tietoja. ActivityTypeDisplay = WebLog sisältää yllä olevassa esimerkissä määritetyn vuorovaikutuksen tietojen aktiviteetin. Kopioi asiakastunnus jostain tietueesta **Asiakkaat** -sivun tunnukseksi.

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt voit luoda [segmenttejä](segments.md), [mittareita](measures.md) ja [ennusteita](predictions.md). Niiden avulla voit luoda merkityksellisen suhteen asiakkaisiin.


[!INCLUDE[footer-include](../includes/footer-banner.md)]