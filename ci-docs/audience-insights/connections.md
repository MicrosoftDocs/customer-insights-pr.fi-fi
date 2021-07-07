---
title: Yhteydet muihin palveluihin Customer Insightsista.
description: Tietojen jakaminen muille palveluille.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304968"
---
# <a name="connections-preview-overview"></a>Yhteydet (esiversio) – yleiskuvaus

Yhteydet ovat avain, joka mahdollistaa tietojen jakamisen Customer Insightsiin ja ulos sieltä. Kukin yhteys muodostaa tietojen jakamisen tietyn palvelun kanssa. Yhteydet ovat perusta [kolmansien osapuolten rikastusten määrittämiselle](enrichment-hub.md) ja [viennin määrittämiselle](export-destinations.md). Samaa yhteyttä voidaan käyttää useita kertoja. Esimerkiksi yksi yhteys Dynamics 365 Marketingiin toimii useaa vientiä varten ja yhtä Leadspace-yhteyttä voi käyttää useisiin rikastuksiin.

Luo ja tarkastele yhteyksiä kohdassa **Järjestelmänvalvoja** > **Yhteydet**.

**Yhteydet**-välilehdessä näkyvät kaikki aktiiviset yhteydet. Luettelossa näkyy rivi kutakin yhteyttä varten. 

Saat **Tutustu**-välilehdessä nopean yleiskatsauksen, kuvauksen ja tietoja siitä, mitä kullakin laajennettavuusvaihtoehdolla voi tehdä.

### <a name="exports"></a>Viennit

Vain järjestelmänvalvojat voivat määrittää uusia yhteyksiä, mutta he voivat myöntää osallistujille käyttöoikeudet aiemmin luotujen yhteyksien käyttöön. Järjestelmänvalvojat määrittävät tietojen lähtemisen, osallistujat määrittävät tiedot ja tiheyden, joka vastaa heidän tarpeitaan. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Rikastukset

Vain järjestelmänvalvojat voivat määrittää uusia yhteyksiä, mutta luodut yhteydet ovat aina sekä järjestelmänvalvojien että osallistujien käytettävissä. Järjestelmänvalvojat hallinnoivat tunnistetietoja ja antavat hyväksyntänsä tietojen siirroille. Tämän jälkeen sekä järjestelmänvalvojat että osallistujat voivat käyttää yhteyksiä rikastuksiin.

## <a name="add-a-new-connection"></a>Lisää uusi yhteys

Jotta voit lisätä yhteyksiä, tarvitset [järjestelmänvalvojan käyttöoikeudet](permissions.md). Jos muodostat yhteyden muihin Microsoftin palveluihin, oletamme, että molemmat palvelut ovat samassa organisaatiossa.

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet (esiversio)**.

1. Siirry **Yhteydet**-välilehteen.

1. Luo uusi yhteys valitsemalla **Lisää yhteys**. Valitse avattavasta valikosta luotavan yhteyden tyyppi.

1. Anna **Määritä yhteys** -ruudussa tarvittavat tiedot. 
   1. Yhteyden **Näyttönimi** ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.
   1. Täsmälliset kentät määräytyvät sen mukaan, mihin palveluun muodostat yhteyden. Saat tietoja liittyvästä yhteystyypistä kohdepalvelun artikkelista.

1. luo yhteys valitsemalla **Tallenna**.

Voit myös valita **Määritä** **Tutustu**-välilehden ruudussa.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Salli osallistujien käyttää yhteyttä vientiin

Kun määrität tai muokkaat vientiyhteyttä, valitse käyttäjät, joilla on oikeus käyttää tätä yhteyttä [vientien](export-destinations.md) määrittämiseen. Yhteys on oletusarvoisesti niiden käyttäjien käytettävissä, joilla on järjestelmänvalvojan rooli. Voit muuttaa tätä asetusta kohdassa **Valitse, kuka voi käyttää tätä yhteyttä** ja sallia osallistujaroolin käyttäjien käyttää tätä yhteyttä.

- Osallistujat eivät voi tarkastella tai muokata yhteyttä. He näkevät vain näyttönimen tyypin ja tyypin vientiä luodessaan.
- Kun jaat yhteyden, osallistujat voivat käyttää yhteyttä. Osallistujat näkevät jaetut yhteydet vientiä määrittäessään. He voivat hallita jokaista tätä yhteyttä käyttävää vientiä.
- Voit muuttaa tätä asetusta niin, että säilytetään osallistujien jo määrittämät viennit.

## <a name="edit-a-connection"></a>Yhteyden muokkaaminen

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet (esiversio)**.

1. Siirry **Yhteydet**-välilehteen.

1. Valitse muokattavan yhteyden kohdalla kolme allekkaista pistettä.

1. Valitse **muokkaa**.

1. Muuta päivitettävät arvot ja valitse **Tallenna**.

## <a name="remove-a-connection"></a>Yhteyden poistaminen

Jos poistettavaa yhteyttä käyttävät rikastukset tai viennit, ne on ensin irrotettava tai poistettava. Poistoikkuna opastaa sinut liittyviin rikastuksiin tai vienteihin. 

irrotetut rikastukset ja viennit muuttuvat passiivisiksi. Voit aktivoida ne uudelleen lisäämällä niihin toisen yhteyden [Rikastus](enrichment-hub.md)- tai [Viennit](export-destinations.md)-sivulla.

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet (esiversio)**.

1. Siirry **Yhteydet**-välilehteen.

1. Valitse poistettavan yhteyden kohdalla kolme allekkaista pistettä.

1. Valitse avattavassa valikossa **Poista**. Vahvistusvalintaikkuna avautuu.

   1. Jos tätä yhteyttä käyttää jokin rikastus tai vienti, valitse painike, kun haluat nähdä, mikä käyttää yhteyttä.
      - **Viennit:** Voit joko poistaa viennin tai katkaista yhteyden, jos haluat poistaa yhteyden. Järjestelmänvalvojat voivat katkaista viennin yhteyden **Katkaise yhteys** -toiminnon avulla. Tämä toiminto on käytettävissä yksittäisille ja useille valituille viennille. Kun katkaiset yhteyden, säilytät vientimäärityksen, mutta se suoritetaan vasta, kun siihen on lisätty toinen yhteys.
      - **Rikastukset:** Voit joko poistaa rikastuksen tai passivoida sen, jos haluat poistaa yhteyden. 
   1. Kun yhteydellä ei ole enää riippuvuuksia, palaa kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja yritä poistaa yhteys uudelleen.

1. Vahvista poisto valitsemalla **Poista**.
