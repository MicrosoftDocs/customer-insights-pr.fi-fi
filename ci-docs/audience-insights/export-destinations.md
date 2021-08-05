---
title: Tietojen vieminen Customer Insightsista
description: Jaa tietoja hallitsemalla vientejä.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 47bdcc5bb38587063e4414377568943f868107a3
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539339"
---
# <a name="exports-preview-overview"></a>Viennit (esiversio) – yleiskatsaus

**Viennit**-sivulla näkyvät kaikki määritetyt viennit. Viennit jakavat tiettyjä tietoja eri sovellusten kanssa. Ne voivat sisältää asiakasprofiileja tai entiteettejä, rakenteita ja yhdistämistietoja. Kukin vienti edellyttää [yhteyttä, jonka määrittää järjestelmänvalvoja todennuksen ja käytön hallitsemiseksi](connections.md).

Siirry kohtaan **Tiedot** > **Viennit**, kun haluat tarkastella vientisivua. Kaikki käyttäjäroolit voivat tarkastella määritettyjä raportteja. Etsi komentopalkin hakukentän avulla vientejä nimen, yhteyden nimen tai yhteystyypin mukaan.

## <a name="set-up-a-new-export"></a>Määritä uusi vienti

Jotta voit määrittää tai muokata vientiä, sinulla on oltava käytettävissä yhteydet. Yhteydet määräytyvät [käyttäjäroolisi](permissions.md) mukaan:
- Järjestelmänvalvojat voivat käyttää kaikkia yhteyksiä. He voivat myös luoda uusia yhteyksiä viennin määrittämisen jälkeen.
- Osallistujat voivat käyttää tiettyjä yhteyksiä. Järjestelmänvalvojat voivat määrittää ja jakaa osallistujille yhteyksiä. Vientiluettelossa näkyvät osallistujat, voivatko he muokata tai vain tarkastella vientiä **Oikeutesi**-sarakkeessa. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Katsojat voivat tarkastella vain aiemmin luotuja vientejä, mutta eivät luoda niitä.

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
