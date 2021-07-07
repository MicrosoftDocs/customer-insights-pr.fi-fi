---
title: Vuorovaikutuksen verkkotietojen integroiminen kohdeyleisön tietojen kanssa
description: Asiakkaiden verkkotietojen tuominen vuorovaikutuksen tiedoista kohdeyleisön tietoihin.
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 76a53a897e90152707a7c1255ed5ed93a5f3b5a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305014"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Vuorovaikutuksen verkkotietojen integroiminen kohdeyleisön tietojen kanssa

Asiakkaat tekevät usein päivittäisiä tapahtumia verkossa sivustojen avulla. Dynamics 365 Customer Insightsin vuorovaikutuksen merkitykselliset tiedot (esiversio) on kätevä sovellus, jonka avulla verkkotiedot voi integroida lähteenä. Tapahtuma- ja toimintatietojen ja demografisten tietojen lisäksi aktiviteetteja nähdään verkossa yhdistetyissä asiakasprofiileissa. Näiden profiilien avulla voi hankkia merkityksellisiä tietoja, kuten tietoja segmenteistä, mittareista tai ennusteista käyttäjäryhmän aktivointia varten.

Tässä artikkelissa kuvataan asiakkaiden verkkoaktiviteettitietojen tuominen vuorovaikutuksen tietoihin olemassa olevan käyttäjäryhmän tietojen ympäristöstä.

Tässä esimerkissä oletetaan, että ympäristössä on yhdistettyjä asiakasprofiileja. Profiilit yhdistettiin lähteisiin kyselyissä, vähittäismyynnissä ja pääsylippujärjestelmässä. Siinä näkyvät myös asiakkaisiin liittyvät aktiviteetit. 

Haluamme nyt tietää, käyttääkö asiakas verkossa olevia ominaisuuksia ja onko tällä tietoja aktiviteeteista. Aktiviteetteja ovat esimerkiksi sivustot, joilla on käyty, ja sähköpostitse vastaanotettujen linkkien avulla tarkastellut tuotesivut.

## <a name="prerequisites"></a>Edellytykset

Tietojen integroiminen vuorovaikutuksen tiedoista vaatii seuraavien edellytysten täyttämistä: 

- Vuorovaikutuksen tietojen SDK on integroitava sivustossa. Lisätietoja on kohdassa [Kehittäjän resurssien yleiskatsaus](../engagement-insights/developer-resources.md).
- Verkkotapahtumien vieminen vuorovaikutuksen merkityksellisistä tiedoista edellyttää Azure Data Lake Storage -tilin käyttöoikeutta. Tilin avulla tuodaan verkkotapahtumien tiedot käyttäjäryhmän merkityksellisiin tietoihin. Lisätietoja on aiheessa [Tapahtumien vieminen](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Tarkennettujen tapahtumien määrittäminen vuorovaikutuksen tiedoissa

Kun järjestelmänvalvoja instrumentoi sivuston vuorovaikutuksen merkityksellisten tietojen SDK:n avulla, *perustapahtumat* kerätään käyttäjän tarkastellessa verkkosivua tai napsauttaessa jotakin kohtaa sivulla. Perustapahtumat sisältävät yleensä runsaasti yksityiskohtia. Tapauksesta riippuen tarvitaan vain perustapahtuman tietojen alijoukko. Vuorovaikutuksen tietojen avulla voit luoda *tarkennettuja tapahtumia*, jotka sisältävät vain valitun perustapahtuman ominaisuuksia.     

Lisätietoja on kohdassa [Tarkennettujen tapahtumien luominen ja muokkaaminen](../engagement-insights/refined-events.md).

Tarkennettujen tapahtumien luomisessa huomioon otettavia seikkoja: 

- Anna tarkennetulle tapahtumalle merkityksellinen nimi. Sitä käytetään aktiviteetin nimenä kohdeyleisön merkityksellisissä tiedoissa.
- Valitse vähintään seuraavat ominaisuudet, jos haluat luoda aktiviteetin käyttäjäryhmän tiedoissa: 
    - Signal.Action.Name – osoittaa aktiviteetin tiedot.
    - Signal.User.Id – käytetään asiakastunnuksen yhdistämisessä.
    - Signal.View.Uri – käytetään verkko-osoitteessa segmenttien tai mittareiden perustana.
    - Signal.Export.Id – käytetään tapahtumien perusavaimena.
    - Signal.Timestamp – määrittää aktiviteetin päivämäärän ja ajan.

Valitse käyttötapauksen tapahtumien ja sivujen suodattimet. Tässä esimerkissä käytetään Sähköpostikampanja-toiminnon nimeä.

## <a name="export-the-refined-web-events"></a>Tarkennettujen verkkotapahtumien vieminen 

Muutetun tapahtuman määrityksen jälkeen on määritettävä tapahtuman tietojen vienti Azure Data Lake Storageen. Se voidaan määrittää tietolähteeksi käyttäjäryhmän käsittelyä varten. Vientiä tapahtuu jatkuvasti, kun tapahtumia siirretään verkko-ominaisuudesta.

Lisätietoja on aiheessa [Tapahtumien vieminen](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Tapahtuman tietojen siirtäminen käyttäjäryhmän tietoihin

Nyt, kun tarkennettu tapahtuma ja sen vienti on määritetty, siirretään tietoja käyttäjäryhmän tietoihin. Luodaan uusi tietolähde Common Data Model -kansion perusteella. Syötä sen tallennustilin tiedot, johon tapahtumat viedään. Valitse *default.cdm.json*-tiedostossa tarkennettu tapahtuma siirtämistä varten ja luo entiteetti käyttäjäryhmän tietoihin.

Lisätietoja on kohdassa [Yhteyden muodostaminen Common Data Model -kansioon Azure Data Lake -tilin avulla](connect-common-data-model.md).


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Tarkennetun tapahtuman tietojen liittäminen asiakasprofiiliin aktiviteettina

Kun entiteetti on siirretty, voit määrittää aktiviteetin asiakasprofiilia varten.

Lisätietoja on kohdassa [Asiakasaktiviteetit](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Aktiviteetit-sivu ja laajennettu Muokkaa aktiviteettia -ruutu sekä täytetyt kentät.":::

Määritä uusi aktiviteetti seuraavilla yhdistämismäärityksillä: 

- **Perusavain**: Signal.Export.Id, yksilöllinen tunnus, joka on käytettävissä jokaisessa tapahtumatietueessa vuorovaikutuksen tiedoissa. Tämä ominaisuus luodaan automaattisesti.

- **Aikaleima**: Signal.Timestamp tapahtuman ominaisuudessa.

- **Tapahtuma**: Signal.Name, seurattavan tapahtuman nimi.

- **WWW-osoite**: Signal.View.Uri viittaa tapahtuman luoneen sivun URI-osoitteeseen.

- **Tiedot**: Signal.Action.Name esittää tapahtumaan liitettävät tiedot. Tässä tapauksessa valittu ominaisuus osoittaa, että tapahtuma liittyy sähköpostikampanjaan.

- **Aktiviteettityyppi**: Tässä esimerkissä valitsemme aiemmin luodun aktiviteettityypin WebLog. Tämä valinta on hyödyllinen suodatusvaihtoehto, jos suoritetaan ennustemallit tai luodaan segmenttejä tämän aktiviteettityypin perusteella.

- **Määritä suhde**: Tämä tärkeä asetus yhdistää aktiviteetin olemassa oleviin asiakasprofiileihin. **Signal.User.Id** on SDK:ssa määritetty kerättävä tunnus. Se liittyy käyttäjätunnukseen muissa tietolähteissä, jotka on määritetty käyttäjäryhmän tiedoissa. Tässä esimerkissä määritetään tunnusten Signal.User.Id ja RetailCustomers:CustomerRetailId välinen suhde. Se on perusavain, joka määritettiin tietojen yhdistämisprosessin yhdistämismääritysvaiheessa.

Aktiviteettien käsittelemisen jälkeen voit tarkastella asiakastietueita ja avata asiakaskortin. Näin näet vuorovaikutuksen tietojen aktiviteetit aikajanalla. 

> [!TIP]
> Jos haluat etsiä asiakastunnuksen, jolla on vuorovaikutuksen tietojen aktiviteetti, siirry kohtaan **Entiteetit** ja esikatsele UnifiedActivity-entiteetin tietoja. ActivityTypeDisplay = WebLog sisältää yllä olevassa esimerkissä määritetyn vuorovaikutuksen merkityksellisten tietojen aktiviteetin. Kopioi asiakastunnus jostain tietueesta **Asiakkaat** -sivun tunnukseksi.

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt voit luoda [segmenttejä](segments.md), [mittareita](measures.md) ja [ennusteita](predictions.md). Niiden avulla voit luoda merkityksellisen suhteen asiakkaisiin.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
