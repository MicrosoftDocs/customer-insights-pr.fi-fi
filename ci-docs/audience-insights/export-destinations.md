---
title: Tietojen vieminen Customer Insightsista
description: Jaa tietoja hallitsemalla vientejä.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 61e95e47489495e367498547687b0065169519e6
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673319"
---
# <a name="exports-preview-overview"></a>Viennit (esiversio) – yleiskatsaus

**Viennit**-sivulla näkyvät kaikki määritetyt viennit. Viennit jakavat tiettyjä tietoja eri sovellusten kanssa. Ne voivat sisältää asiakasprofiileja, entiteettejä, rakenteita ja yhdistämistietoja. Kukin vienti edellyttää [yhteyttä, jonka määrittää järjestelmänvalvoja todennuksen ja käytön hallitsemiseksi](connections.md).

Siirry kohtaan **Tiedot** > **Viennit**, kun haluat tarkastella vientisivua. Kaikki käyttäjäroolit voivat tarkastella määritettyjä raportteja. Etsi komentopalkin hakukentän avulla vientejä nimen, yhteyden nimen tai yhteystyypin mukaan.

## <a name="export-types"></a>Vientityypit

Vienneissä on kaksi päätyyppiä:  

- **Lähtevät tiedot -vientien** avulla voit viedä kaikkien tyyppien entiteettejä, jotka ovat käytössä käyttäjäryhmän merkityksellisissä tiedoissa. Vietäväksi valittujen entiteettien mukana viedään kaikki tietokentät, metatiedot, rakenteet ja yhdistämistiedot. 
- **Segmenttivientien** avulla voit viedä segmenttientiteettejä käyttäjäryhmän merkityksellisistä tiedoista. Segmentit edustavat asiakasprofiilien luetteloa. Kun määrität vientiä, valitse sisältyvät tietokentät sen mukaan, mihin kohdejärjestelmään tiedot viedään. 

### <a name="export-segments"></a>Segmenttien vienti

**Segmenttien vieminen yritystilien (yritystenvälinen) tai yksittäisten kuluttajien ympäristöissä (kuluttajakauppa)**  
Useimmat vientivaihtoehdot tukevat molempia ympäristöjä. Segmenttien viemisellä eri kohdejärjestelmiin on erityisvaatimuksia. Yleisesti segmentin jäsen, asiakasprofiili, sisältää yhteyshenkilön tiedot. Vaikka näin on yleensä yksittäisille kuluttajille (kuluttajakauppa) perustuvien segmenttien tapauksessa, sama ei välttämättä päde segmentteihin, jotka perustuvat yritystileihin (yritystenvälinen). 

**Segmenttien vienti yritystiliympäristöissä (yritystenvälinen)**  
- Yritystilien ympäristöjen segmentit perustuvat *Asiakas*-entiteettiin. Jotta tilin segmenttejä voidaan viedä sellaisenaan, kohdejärjestelmän on tuettava puhtaita tilin segmenttejä. Näin on [LinkedIn](export-linkedin-ads.md)issä, kun valitset **yritys**-vaihtoehdon määrittäessäsi vientiä.
- Kaikki muut kohdejärjestelmät edellyttävät yhteyshenkilöentiteetin kenttiä. Jotta tilin segmentit voivat hakea tietoja liittyvistä yhteyshenkilöistä, segmentin määrityksen on projisoitava yhteyshenkilöentiteetin määritteet. Lisätietoja [segmenttien ja projektimääritteiden määrittämisestä](segment-builder.md).

**Segmenttien viennit yksittäisten kuluttajien ympäristöissä (kuluttajakauppa)**  
- Yksittäisten asiakkaiden ympäristöissä segmentit perustuvat *yhtenäinen asiakasprofiili* -entiteettiin. Kaikki segmentit, jotka vastaavat kohdejärjestelmien vaatimuksia (esimerkiksi sähköpostiosoite), voidaan viedä.

**Segmenttien viennin rajoitukset**  
- Kolmannen osapuolen kohdejärjestelmät voivat rajoittaa vietävien asiakasprofiilien määrää. 
- Yksittäisten asiakkaiden kohdalla näytetään segmentin jäsenten todellinen määrä, kun valitset segmentin vietäväksi. Jos segmentti on liian suuri, näyttöön tulee varoitus. 
- Yritystilien kohdalla näet segmentin tilien määrän. Mahdollisesti projisoitavien yhteyshenkilöiden määrää ei kuitenkaan näy. Joissakin tapauksissa tämä voi johtaa siihen, että vietävässsä segmentissä on enemmän asiakasprofiileja kuin mitä kohdejärjestelmä sallii. Jos kohdejärjestelmän rajoitukset ylittyvät, vienti ohitetaan. 

## <a name="set-up-a-new-export"></a>Määritä uusi vienti  
Jotta voit määrittää tai muokata vientiä, sinulla on oltava käytettävissä yhteydet. Yhteydet määräytyvät [käyttäjäroolisi](permissions.md) mukaan:
- **Järjestelmänvalvojat** voivat käyttää kaikkia yhteyksiä. He voivat myös luoda uusia yhteyksiä viennin määrittämisen jälkeen.
- **Osallistujat** voivat käyttää tiettyjä yhteyksiä. Järjestelmänvalvojat voivat määrittää ja jakaa osallistujille yhteyksiä. Vientiluettelossa näkyvät osallistujat, voivatko he muokata tai vain tarkastella vientiä **Oikeutesi**-sarakkeessa. Lisätietoja löytyy kohdasta [Salli osallistujien käyttää yhteyksiä vientejä varten](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Katselijat** voivat tarkastella vain aiemmin luotuja vientejä, eivätkä he voi luoda niitä.

### <a name="define-a-new-export"></a>Määritä uusi vienti

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti** luodaksesi uuden viennin.

1. Valitse **Määritä vienti** -ruudussa käytettävä yhteys. [Yhteydet](connections.md) ovat järjestelmänvalvojien hallitsemia. 

1. Anna tarvittavat tiedot ja luo vienti valitsemalla **Tallenna**.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Uuden viennin määritteleminen aiemmin luodun viennin perusteella

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse vientiluettelosta vienti, jonka haluat kopioida.

1. Valitse komentopalkissa **Luo kaksoiskappale**, jos haluat avata **Määritä vienti** -ruudun, jossa on valitun viennin tiedot.

1. Tarkista ja mukauta vienti ja valitse **Tallenna**, jos haluat luoda uuden viennin.

### <a name="edit-an-export"></a>Muokkaa vientiä

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse vientiluettelosta vienti, jonka haluat muokata.

1. Valitse komentopalkissa **Muokkaa**.

1. Muuta päivitettävät arvot ja valitse **Tallenna**.

## <a name="view-exports-and-export-details"></a>Viennin ja viennin tietojen tarkasteleminen

Kun olet luonut vientikohteet, ne näkyvät kohdassa **Tiedot** > **Viennit**. Kaikki käyttäjät näkevät jaetut tiedot ja niiden uusimman tilan.

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Käyttäjät, joilla ei ole muokkausoikeuksia, valitsevat **Näytä**-kohdan **Muokkaa**-kohdan sijaan, kun he haluavat katsoa viennin tietoja.

1. Sivuruudussa näkyy viennin määritys. Arvoja ei voi muuttaa ilman muokkausoikeutta. Palaa vientisivulle valitsemalla **Sulje**.

## <a name="schedule-and-run-exports"></a>Aikatauluta ja suorita useita vientejä

Jokaisella määritetyllä viennillä on päivitysaikataulu. Päivityksen aikana järjestelmä etsii uusia tai päivitettyjä tietoja, jotka sisällytetään vientiin. Vieminen suoritetaan oletusarvoisesti jokaisen [ajoitetun järjestelmän päivityksen](system.md#schedule-tab) yhteydessä. Voit mukauttaa päivitysaikataulua tai poistaa sen käytöstä, jos haluat suorittaa viennit manuaalisesti.

Vientiaikataulut määräytyvät ympäristön tilan mukaan. Jos [riippuvuuksilla](system.md#refresh-policies) on käynnissä olevia päivityksiä ajoitetun viennin käynnistymisen aikana, järjestelmä tekee päivityksen valmiiksi ennen viennin suorittamista. Voit nähdä, milloin vienti on viimeksi päivitetty sarakkeessa **Päivitetty**.

### <a name="schedule-exports"></a>Aikataulun viennit

Voit määrittää mukautettuja päivitysaikatauluja yksittäiselle viennille tai usealle viennille samalla kertaa. Tällä hetkellä määritetty aikataulu näkyy vientiluettelon **Aikataulu**-sarakkeessa. Aikataulun muutosoikeus on sama kuin [viennin muokkaamiseen ja määrittämiseen](export-destinations.md#set-up-a-new-export). 

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse vienti, jonka haluat aikatauluttaa.

1. Valitse komentopalkista **Aikatauluta**.

1. Määritä **Aikatauluta vienti** -ruudussa **Suoritettava aikataulu** -arvoksi **Käytössä**, jotta vienti voidaan suorittaa automaattisesti. Valitse **Ei käytössä**, jos haluat päivittää sen manuaalisesti.

1. Jos haluat päivittää viennit automaattisesti, valitse **Toistumisarvo** ja määritä sen tiedot. Määritetty aika koskee kaikkia toistumisen esiintymiä. Tämä on aika, jolloin viennin pitäisi alkaa päivittyä.

1. Ota muutokset käyttöön ja aktivoi ne valitsemalla **Tallenna**.

Kun muokkaat useiden vientien aikataulua, valitse **Säilytä tai korvaa aikataulut** -kohdassa:
- **Säilytä yksittäiset aikataulut**: Jatka valitun viennin aiemmin määritettyä aikataulua ja poista ne vain käytöstä tai ota ne käyttöön.
- **Määritä uusi aikataulu kaikille valituille viennille**: ohita valittujen vientien aiemmin luodut aikataulut.

### <a name="run-exports-on-demand"></a>Suorita vientejä tarvittaessa

Jos haluat viedä tietoja odottamatta ajoitettua päivitystä, siirry kohtaan **Tiedot** > **Viennit**.

- Jos haluat suorittaa kaikki viennit, valitse komentopalkissa **Suorita kaikki**. Tämä toiminto suorittaa vain viennit, jotka ovat aktiivisia aikatauluja.
- Jos haluat suorittaa yksittäisen viennin, valitse se luettelosta ja valitse komentopalkissa **Suorita**. Näin viennit suoritetaan ilman aktiivista aikataulua. 

## <a name="remove-an-export"></a>Viennin poistaminen

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse poistettava vienti.

1. Valitse komentopalkissa **Poista**.

1. Vahvista poisto valitsemalla **Poista** vahvistusnäytössä.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
