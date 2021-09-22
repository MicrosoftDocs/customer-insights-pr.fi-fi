---
title: Vuorovaikutuksen merkitykselliset tiedot -ominaisuuden käytön aloittaminen
description: Yhteenveto ohjeresursseista, joiden avulla pääsee nopeasti alkuun.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405354"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Dynamics 365 Customer Insightsin vuorovaikutuksen merkitykselliset tiedot -ominaisuuden käytön aloittaminen (julkinen esiversio)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Vuorovaikutuksen merkitykselliset tiedot -ominaisuuden avulla voit kerätä ja mitata asiakkaiden käyttäytymistä verkkosivustollasi. Se integroituu kohderyhmän merkityksellisten tietojen ominaisuuden, jotta voit tarkastella monipuolista reaaliaikaista käyttäytymisanalytiikkaa asiakasprofiiliraporttien rinnalla. Tämän artikkelin linkit auttavat sinua määrittämään ympäristösi nopeasti.

## <a name="step-1-review-prerequisites"></a>Vaihe 1: Tarkista edellytykset

Ensin sinulla on oltava voimassa oleva Microsoft Azure Active Directory -käyttäjätili. Lue sitten seuraavat artikkelit, ennen kuin määrität vuorovaikutusten merkityksellisten tietojen työtilan.

- Tarkasta ja hyväksy Microsoftin [palvelun käyttöehdot](terms-of-service.md).  
- Lue artikkeli [Evästeiden ja käyttäjien suostumusten hallinta](user-consent-storage.md). Kun olet tutustunut tähän artikkeliin, arvioi, täytyykö sinun päivittää käyttäjän suostumusta koskeva ilmoituksesi. Jos sinulla ei ole aiemmin ollut muita kuin olennaisia evästeitä, sinun on todennäköisesti päivitettävä sivustokäytäntösi.
- [Sanasto](glossary.md) sisältää pikaoppaan keskeisistä käsitteistä ja konsepteista.

## <a name="step-2-explore-engagement-insights"></a>Vaihe 2: Tutustu vuorovaikutuksen merkityksellisiin tietoihin

Kun käyt ensimmäisen kerran vuorovaikutusten merkityksellisissä tiedoissa, voit määrittää asetuksia, tarkastella käytäntöjä ja tutustua tuotteeseen.

1. Kirjaudu [vuorovaikutusten merkitykselliset tiedot -ominaisuuden portaaliin](https://pi.dynamics.com) Microsoft Azure Active Directory käyttäjätilisi avulla. (Se voi olla koulu- tai työtilisi.)

1. Valitse alueesi ja määritä valintaruudun avulla, haluatko vastaanottaa päivityksiä ja tarjouksia sähköpostitse.

1. Tutustu **vuorovaikutuksen merkityksellisten tietojen (esiversio) käyttöehtoihin** ja **tietosuojalausekkeeseen** ja hyväksy ne valitsemalla **Tutustu esittelyyn**.

1. Tutustu tuotteeseen esimerkkitietojoukon avulla.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Vaihe 3: Määritä työtila ja lisää koodia verkkosivustollesi

Työtilassa voit tarkastella käyttäjäaktiviteetteja reaaliajassa sekä tallentaa ja hallita raportteja. Lisää verkkosivustollesi koodia alkaaksesi kerätä *tapahtumia* eli käyttäjiltä tulevia aktiviteettitietoja.

1. [Luo työtila](create-workspace.md) ja lisää jäseniä.

1. [Lisää koodi sivustoon](instrument-website.md) tai [mobiilisovellukseen](developer-resources.md#capture-events-from-mobile-apps), jos haluat nähdä työtilaan saapuvan käyttäjän aktiviteetin.

1. Tarkastele [reaaliaikaista raporttia](view-reports.md), josta näet aktiiviset käyttäjät selaimen, laitteen, käyttöjärjestelmän, sijainnin ja kielen perusteella. Voit myös luoda omia visualisointejasi [mukautettujen raporttien](custom-reports.md) avulla.
    
## <a name="step-4-export-data-to-other-channels"></a>Vaihe 4: Vie tietoja muihin kanaviin

Voit luoda *tarkennettuja tapahtumia* (virtuaalisia näkymiä) verkkoanalytiikkatiedoistasi. Suodata sitten tiedot ja vie ne Azure Data Lake Storageen. Voit lisätä viedyt tiedot tietolähteenä. Lue lisätietoja kohdasta [Linkin luominen kohdeyleisön ja sitoutumistietojen välille](integrate-audience-insights-engagement-insights.md).

1. [Luo tarkennettuja tapahtumia](refined-events.md) vietäväksi.

1. [Vie tiedot](export-events.md) Data Lake Storageen.

1. Tutustu [henkilötietoja sisältävien tapahtumatietojen poistamiseen ja viemiseen](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Vaihe 5: Pysy yhteydessä

Arvostamme aktiivista osallistumistasi ja suunnittelemme ottavamme kaiken merkityksellisen palautteen huomioon tulevien julkaisujen kehittämisessä. Anna palautteesi ja ilmoita ongelmista jollakin seuraavista kanavista:
- [Yhteisö](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Anna palautetta](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Tuen pyytäminen](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
