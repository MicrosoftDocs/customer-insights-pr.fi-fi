---
title: Tietoraporttien tarkastelu
description: Käytettävissä olevien raporttien avulla voit tarkastella verkkosivustosi aktiviteetteja reaaliaikaisesti.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 06/18/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: cb6d9ab75b95a5f677d2267f5412a55327930987b2fc3a1a21958633a8116bd2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036644"
---
# <a name="view-reports"></a>Näytä raportit

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Raportti on kokoelma tietojen visualisointeja. Niissä käytetään SDK:n avulla kerättyjä tietoja, jotka auttavat käyttäjän toiminnan mittaamisessa ja ymmärtämisessä. Dynamics 365 Customer Insightsin vuorovaikutuksen merkitykselliset tiedot sisältävät valmiita raportteja (OOB-raportteja) verkko- ja mobiiliprojekteja varten.  

## <a name="web-reports"></a>Verkkoraportit

Verkkoraportteja voi käyttää vasemmanpuoleisen siirtymisruudun **Etsi**-kohdassa.

:::image type="content" source="media/report-menu.png" alt-text="Siirtymisruutu, jossa näkyy käytettävissä olevien raporttien luettelo.":::

### <a name="real-time-usage-report"></a>Reaaliaikainen käyttöraportti

**Reaaliaikainen käyttöraportti** tarjoaa yhteenvedon kulloisistakin aktiviteeteista verkkosivustollasi ja päivittyy automaattisesti minuutin välein. Reaaliaikaisen käytön avulla voit seurata markkinointikampanjoiden, lehdistötapahtumien ja muiden skenaarioiden vaikutuksia sivustosi liikenteeseen.

### <a name="key-metrics-reports"></a>Tärkeimpien mittareiden raportti

- **Sivunäkymät** luetteloi yksittäisten sivujen sivunäkymät sekä valitun ajanjakson sivunäkymien kokonaismäärän.

- **Käynnit**-kohdassa on tietoja käyntien määrästä ja kestosta.

- **Kävijät**-kohdassa on tietoja sivuston uusista ja sivustolle palaavista yksittäisistä kävijöistä.

### <a name="content-reports"></a>Sisältöraportit

- **Linkit**-kohdassa kerrotaan napsautusten määrä ja tyypit.

- **Lopetussivut**-kohdassa kerrotaan linkit, jotka kävijät valitsivat poistuessaan sivustosta.

### <a name="traffic-sources-reports"></a>Liikennelähderaportit

- **Viittaajat**-kohdassa ovat toimialueet ja URL-osoitteet, jotka viittaavat sivuston kävijöihin.

- **Seurantakoodit**-kohdassa on tietoja niiden linkkien seurantakoodeista, joiden avulla kävijät tulivat sivustoon.

### <a name="visitor-profiles-reports"></a>Vierailijaprofiiliraportit

- **Laitteet**-kohdassa on luettelo fyysisistä laitteista, joiden avulla käytetään sivustoa.

- **Käyttöjärjestelmä ja selaimet** antaa tietoja käyttöjärjestelmistä ja selaimista, jotka olivat käytössä, kun sivustosi avattiin.

- **Sijainnit**-kohdassa on tietoja kävijöistä maan, alueen ja kaupungin mukaan.

- **Kielet**-kohdassa on sivunäkymät kävijän ensisijaisten kielten mukaan.

## <a name="mobile-reports"></a>Mobiiliraportit

Mobiiliraportit on ryhmitelty reaaliaikaisen käytön, sovelluksen ja käyttäjän luokkien mukaan. Mobiiliraportteja voi käyttää vasemmanpuoleisen siirtymisruudun **Etsi**-kohdassa.   

:::image type="content" source="media/mobile-reports.png" alt-text="Vuorovaikutuksen merkityksellisten tietojen käyttöliittymä, jossa on tiedot kaavioina ja luetteloina näyttävä reaaliaikainen käyttöraportti.":::   

### <a name="real-time-usage"></a>Reaaliaikainen käyttö

**Reaaliaikainen käyttö** -kohdassa on yleiskatsaus minuutin välein päivittyvän mobiilisovelluksen nykyisestä aktiviteetista. Reaaliaikaisen käytön avulla voit valvoa aktiivisten käyttäjien ja istuntojen määrää sovelluksessa ja näyttönäkymien päällä.

### <a name="app-reports"></a>Sovellusraportit

- **Näyttönäkymät**-kohdassa ovat yksittäisten näyttöjen näyttönäkymät sovelluksessa tiettyjä aikavälinä. Voit tarkastella näyttönäkymiä näytön nimen tai näytön otsikon mukaan.

- **Istunnot**-kohdassa on tietoja istuntojen määrästä ja kestosta.

- **Palautustiheys** ryhmittelee istuntojen määrät edellisestä istunnosta kuluneiden päivien määrän.

- **Käyttäjät**-kohdassa ovat uudet ja palanneet käyttäjät mobiilisovelluksessa.

- **Tapahtumat**-kohdassa ovat kaikki sovelluksesta kerätyt tapahtumat sekä kunkin tapahtuman kokonaismäärä.

### <a name="user-reports"></a>Käyttäjäraportit

- **Sovellusversioissa** ovat käytössä olevat mobiilisovelluksen versiot käyttäjäkannan perusteella.

- **Laitteet ja käyttöjärjestelmäversiot** -kohdassa on tietoja siitä, mitä laitteita ja käyttöjärjestelmiä mobiilisovelluksessa käytetään.

- **Sijainnit**-kohdassa on tietoja sovelluksen käyttäjistä maan, alueen ja kaupungin mukaan.

## <a name="filter-by-time-or-value"></a>Suodatus ajan tai arvon mukaan

Voit valita aikavälin tai arvon verkko- tai mobiiliraportissa, jos haluat tarkastella arvoa tai ajanjaksoa. 

- Voit valita aikavälin valitsemalla raportin avattavasta luettelosta **Lisää [...]** -kohdan. Aikavälin valinta ei ole käytössä reaaliaikaisissa käyttöraporteissa – niiden aikavälinä on "nyt".

- Useimmissa raporteissa voit suodattaa raporttia arvon perusteella valitsemalla sellaisen kaaviosta tai luettelosta.

[!INCLUDE[footer-include](../includes/footer-banner.md)]