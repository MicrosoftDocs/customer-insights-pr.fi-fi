---
title: Viennit (esiversio) – yleiskatsaus
description: Jaa tietoja hallitsemalla vientejä.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: c580b6c01e1b4ac6b095733193d86ebd0b4005f2
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304055"
---
# <a name="exports-preview-overview"></a>Viennit (esiversio) – yleiskatsaus

 Vientien avulla voit jakaa tiettyjä tietoja eri sovellusten kanssa. Ne voivat sisältää asiakasprofiileja, entiteettejä, rakenteita ja yhdistämistietoja. Kukin vienti edellyttää [yhteyttä, jonka määrittää järjestelmänvalvoja todennuksen ja käytön hallitsemiseksi](connections.md). **Viennit**-sivulla näkyvät kaikki määritetyt viennit.

## <a name="export-types"></a>Vientityypit

Vienneissä on kaksi päätyyppiä:  

- **Lähtevät tiedot -vientien** avulla voit viedä kaikkien tyyppien entiteettejä, jotka ovat käytössä Customer Insightsissa. Vietäväksi valittujen entiteettien mukana viedään kaikki tietokentät, metatiedot, rakenteet ja yhdistämistiedot.
- **Segmenttivientien** avulla voit viedä segmenttientiteettejä Customer Insightsista. Yksittäisille kuluttajille (B2C) segmentit edustavat luetteloa asiakasprofiileista. Yrityksille (B2B) [segmentit voivat edustaa tili- tai yhteyshenkilöluetteloa](segment-builder.md#create-a-new-segment-with-segment-builder). Kun määrität vientiä, valitse sisältyvät tietokentät sen mukaan, mihin kohdejärjestelmään tiedot viedään.

### <a name="export-segments"></a>Segmenttien vienti

**Segmenttien vieminen yritystilien (yritystenvälinen) tai yksittäisten kuluttajien ympäristöissä (kuluttajakauppa)**  
Useimmat vientivaihtoehdot tukevat molempia ympäristöjä. Segmenttien viemisellä eri kohdejärjestelmiin on erityisvaatimuksia. 

**Segmenttien viennit yksittäisten kuluttajien ympäristöissä (kuluttajakauppa)**  
- Yksittäisten asiakkaiden ympäristöissä segmentit perustuvat *yhtenäinen asiakasprofiili* -entiteettiin. Kaikki segmentit, jotka vastaavat kohdejärjestelmien vaatimuksia (esimerkiksi sähköpostiosoite), voidaan viedä.

**Segmenttien vienti yritystiliympäristöissä (yritystenvälinen)**  
- Yritystilien ympäristöjen segmentit perustuvat *tili*-entiteettiin tai *yhteyshenkilö*-entiteettiin. Jotta tilin segmenttejä voidaan viedä sellaisenaan, kohdejärjestelmän on tuettava puhtaita tilin segmenttejä. Näin on [LinkedIn](export-linkedin-ads.md)issä, kun valitset **yritys**-vaihtoehdon määrittäessäsi vientiä.
- Kaikki muut kohdejärjestelmät edellyttävät yhteyshenkilöentiteetin kenttiä.
- Kun segmenttityyppejä (yhteyshenkilöitä ja tilejä) on kaksi, Customer Insights määrittää automaattisesti, minkä tyyppisiä segmenttejä voidaan viedä kohdejärjestelmän perusteella. Esimerkiksi yhteyshenkilöihin kohdistavassa kohdejärjestelmässä, kuten Mailchimp-järjestelmässä, Customer Insights sallii vain yhteyshenkilösegmenttien valitsemisen vietäväksi.

**Segmenttien viennin rajoitukset**  
- Kolmannen osapuolen kohdejärjestelmät voivat rajoittaa vietävien asiakasprofiilien määrää. 
- Yksittäisten asiakkaiden kohdalla näytetään segmentin jäsenten todellinen määrä, kun valitset segmentin vietäväksi. Jos segmentti on liian suuri, näyttöön tulee varoitus. 
- Yritystileille näet tilien tai yhteyshenkilöiden määrän segmentin mukaan. Jos segmentti on liian suuri, näyttöön tulee varoitus. Jos kohdejärjestelmän rajoitukset ylittyvät, vienti ohitetaan.

## <a name="set-up-a-new-export"></a>Määritä uusi vienti

Jotta voit määrittää tai muokata vientiä, sinulla on oltava käytettävissä yhteydet. Yhteydet määräytyvät [käyttäjäroolisi](permissions.md) mukaan:
- **Järjestelmänvalvojat** voivat käyttää kaikkia yhteyksiä. He voivat myös luoda uusia yhteyksiä viennin määrittämisen jälkeen.
- **Osallistujat** voivat käyttää tiettyjä yhteyksiä. Järjestelmänvalvojat voivat määrittää ja jakaa osallistujille yhteyksiä. Vientiluettelossa näkyvät osallistujat, voivatko he muokata tai vain tarkastella vientiä **Oikeutesi**-sarakkeessa. Lisätietoja löytyy kohdasta [Salli osallistujien käyttää yhteyksiä vientejä varten](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Katselijat** voivat tarkastella vain aiemmin luotuja vientejä, eivätkä he voi luoda niitä.

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti** luodaksesi uuden viennin.

1. Valitse **Määritä vienti** -ruudussa käytettävä [yhteys](connections.md).

1. Anna tarvittavat tiedot ja luo vienti valitsemalla **Tallenna**. Tarvittavat tiedot ovat tietyn viennin Customer Insights -dokumentaatiossa.

## <a name="manage-existing-exports"></a>Aiemmin luotujen vientien hallinta

Siirry kohtaan **Tiedot** > **vienti**, kun haluat tarkastella vientitietoja, niiden yhteyden nimeä, yhteystyyppiä ja tilaa. Kaikki käyttäjäroolit voivat tarkastella määritettyjä raportteja. Vientiluetteloa voi lajitella minkä tahansa sarakkeen perustella. Hallittavan viennin voi etsiä myös hakuruutua käyttämällä.

Voit tarkastella käytettävissä olevia toimintoja valitsemalla viennin.

:::image type="content" source="media/exports_showmore.png" alt-text="Vientisivu.":::

- **Tarkastele** tai **Muokkaa** vientiä. Käyttäjät, joilla ei ole muokkausoikeuksia, valitsevat **Näytä**-kohdan **Muokkaa**-kohdan sijaan, kun he haluavat katsoa viennin tietoja.
- **Suorita** vienti uusimpien tietojen viemiseksi.
- Luo viennin **kaksoiskappale**.
- **[Aikatauluta](#schedule-and-run-exports)** viennit.
- **Poista yhteys**, joka poistaa yhteyden tätä vientiä varten. Poistaminen ei poista yhteyttä, mutta poistaa viennin aktivoinnin. **Käytetty yhteys** -sarakkeessa näkyy Ei yhteyttä.
- Viennin **poistaminen**.

## <a name="schedule-and-run-exports"></a>Aikatauluta ja suorita useita vientejä

Jokaisella määritetyllä viennillä on päivitysaikataulu. Päivityksen aikana järjestelmä etsii uusia tai päivitettyjä tietoja, jotka sisällytetään vientiin. Vieminen suoritetaan oletusarvoisesti jokaisen [ajoitetun järjestelmän päivityksen](schedule-refresh.md) yhteydessä. Voit mukauttaa päivitysaikataulua tai poistaa sen käytöstä, jos haluat suorittaa viennit manuaalisesti.

Vientiaikataulut määräytyvät ympäristön tilan mukaan. Jos [riippuvuuksilla](system.md#refresh-processes) on käynnissä olevia päivityksiä ajoitetun viennin käynnistymisen aikana, järjestelmä tekee päivityksen valmiiksi ennen viennin suorittamista. Voit nähdä, milloin vienti on viimeksi päivitetty sarakkeessa **Päivitetty**.

### <a name="schedule-exports"></a>Aikataulun viennit

Voit määrittää mukautettuja päivitysaikatauluja yksittäiselle viennille tai usealle viennille samalla kertaa. Tällä hetkellä määritetty aikataulu näkyy vientiluettelon **Aikataulu**-sarakkeessa. Aikataulun muutosoikeus on sama kuin [viennin muokkaamiseen ja määrittämiseen](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse vienti, jonka haluat aikatauluttaa.

1. Valitse **Aikataulut**.

1. Määritä **Aikatauluta vienti** -ruudussa **Suoritettava aikataulu** -arvoksi **Käytössä**, jotta vienti voidaan suorittaa automaattisesti. Valitse **Ei käytössä**, jos haluat päivittää sen manuaalisesti.

1. Jos haluat päivittää viennit automaattisesti, valitse **Toistumisarvo** ja määritä sen tiedot. Määritetty aika koskee kaikkia toistumisen esiintymiä. Tämä on aika, jolloin viennin pitäisi alkaa päivittyä.

1. Valitse **Tallenna**.

Kun muokkaat useiden vientien aikataulua, valitse **Säilytä tai korvaa aikataulut** -kohdassa:

- **Säilytä yksittäiset aikataulut**: Jatka valitun viennin aiemmin määritettyä aikataulua ja poista ne vain käytöstä tai ota ne käyttöön.
- **Määritä uusi aikataulu kaikille valituille viennille**: ohita valittujen vientien aiemmin luodut aikataulut.

### <a name="run-exports-on-demand"></a>Suorita vientejä tarvittaessa

Jos haluat viedä tietoja odottamatta ajoitettua päivitystä, siirry kohtaan **Tiedot** > **Viennit**.

- Jos haluat suorittaa kaikki viennit, valitse komentopalkissa **Suorita kaikki**. Toiminto suorittaa vain viennit, joilla on aktiivisia aikatauluja. Jos haluat suorittaa viennin, joka ei ole aktiivinen, suorita yksi vienti.
- Jos haluat suorittaa yksittäisen viennin, valitse se luettelosta ja valitse komentopalkissa **Suorita**.

## <a name="troubleshooting"></a>Vianmääritys

### <a name="segment-not-eligible-for-export"></a>Segmentti ei ole vientikelpoinen

**Ongelma** Yritystilien ympäristössä vienti epäonnistuu ja näyttöön tulee seuraava virhesanoma: "Seuraava segmentti ei ole kelpaa seuraavaan vientikohteeseen: {segmentin nimi}. Valitse vain ContactProfile-tyypin segmentit ja yritä uudelleen."

**Ratkaisu** Tilisegmenttien lisäksi päivitettiin yritystilien Customer Insights -ympäristöt tukemaanyhteyshenkilösegmenttejä. Tämän muutoksen vuoksi yhteyshenkilötietoja tarvitsevat viennit toimivat vain yhteyshenkilöihin perustuvien segmenttien kanssa.

1. [Luo yhteyshenkilöihin perustuva segmentti](segment-builder.md), joka vastaa aiemmin käytettyä segmenttiä.

1. Kun yhteyshenkilösegmentti on suoritettu, muokkaa vastaavaa vientiä ja valitse uusi segmentti.

1. Valitse **Tallenna**, jos haluat tallentaa määrityksen tai **Tallenna ja suorita** tämän viennin testaamiseksi heti.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
