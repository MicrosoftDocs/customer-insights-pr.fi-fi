---
title: Vuorovaikutuksen merkitykselliset tiedot -ominaisuuden käytön aloittaminen
description: Yhteenveto ohjeresursseista, joiden avulla pääsee nopeasti alkuun.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: c435810e712bbbf69f8f1cfb582fc0a971566de6
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225594"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Dynamics 365 Customer Insightsin vuorovaikutuksen merkitykselliset tiedot -ominaisuuden käytön aloittaminen (julkinen esiversio)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Vuorovaikutuksen merkitykselliset tiedot -ominaisuuden avulla voit kerätä ja mitata asiakkaiden käyttäytymistä verkkosivustollasi. Se integroituu kohderyhmän merkityksellisten tietojen ominaisuuden, jotta voit tarkastella monipuolista reaaliaikaista käyttäytymisanalytiikkaa asiakasprofiiliraporttien rinnalla. Tämän artikkelin linkit auttavat sinua määrittämään ympäristösi nopeasti.

## <a name="step-1-review-prerequisites"></a>Vaihe 1: Tarkista edellytykset

Ensin sinulla on oltava voimassa oleva Microsoft Azure Active Directory (AAD) -käyttäjätili. Lue sitten seuraavat artikkelit, ennen kuin määrität vuorovaikutusten merkityksellisten tietojen työtilan.

- Tarkasta ja hyväksy Microsoftin [palvelun käyttöehdot](terms-of-service.md).  
- Lue artikkeli [Evästeiden ja käyttäjien suostumusten hallinta](user-consent-storage.md). Tämän jälkeen voit arvioida, onko käyttäjän hyväksyntäilmoitus päivitettävä. Jos sinulla ei ole aiemmin ollut muita kuin olennaisia evästeitä, sinun on todennäköisesti päivitettävä sivustokäytäntösi.
- [Sanasto](glossary.md) sisältää pikaoppaan keskeisistä käsitteistä ja konsepteista.

## <a name="step-2-explore-engagement-insights"></a>Vaihe 2: Tutustu vuorovaikutuksen merkityksellisiin tietoihin

Kun käyt ensimmäisen kerran seurantatietojen oivalluksissa, voit määrittää asetuksia, tarkastella käytäntöjä ja tutkia sitä.

1. Kirjaudu [sitoutumistiedot-ominaisuusportaaliin](https://home.ci.ai.dynamics.com/app/engagement-insights) Microsoft AAD -käyttäjätilin (koulun tai työ) avulla.

1. Valitse alue ja valitse sitten valintaruutu, jos haluat ottaa sähköpostipäivitykset ja tarjoukset käyttöön.

1. Voit tarkastella **osallistumisen tietojen (esiversio) käyttöehtoja** ja **tietosuojatietoja** ja hyväksyä nämä asetukset valitsemalla **Tutustu esittelyyn**.

1. Tutustu tuotteeseen esimerkkitietojoukon avulla.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>Vaihe 3: Työtilan määrittäminen ja raporttien luominen

Työtilassa voit tarkastella käyttäjäaktiviteetteja reaaliajassa sekä tallentaa ja hallita raportteja. Lisää verkkosivustollesi koodia alkaaksesi kerätä *tapahtumia* eli käyttäjiltä tulevia aktiviteettitietoja.

1. [Luo työtila](create-workspace.md) ja lisää jäseniä.

1. [Lisää koodi sivustoon](instrument-website.md) tai [mobiilisovellukseen](developer-resources.md#capture-events-from-mobile-apps), jos haluat nähdä työtilaan saapuvan käyttäjän aktiviteetin.

1. Tarkastele [reaaliaikaista raporttia](view-reports.md), jossa näkyvät aktiiviset käyttäjät selaimen, laitteen, käyttöjärjestelmän, sijainnin ja kielen mukaan. Voit myös luoda omia visualisointejasi [mukautettujen raporttien](custom-reports.md) avulla.

1. Luo [dimensioita](dimensions.md), jotta voit lajitella kävijöitä uusien ja palaavien mukaan, [mittareita](metrics.md), jotka auttavat ymmärtämään käyttäjien käyttäytymistä ja [segmenttejä](segments.md), joiden avulla voit tunnistaa käyttäjien alijoukkoja perustuen ominaisuuksiin tai sivustovuorovaikutukseen.
    
## <a name="step-4-export-data-to-other-channels"></a>Vaihe 4: Vie tietoja muihin kanaviin

Voit luoda *tarkennettuja tapahtumia* (virtuaalisia näkymiä) verkkoanalytiikkatiedoistasi. Suodata sitten tiedot ja vie ne Azure Data Lake Storageen. Voit lisätä viedyt tiedot tietolähteenä.

1. [Luo tarkennettuja tapahtumia](refined-events.md) vietäväksi.

1. [Tietojen vieminen](export-events.md) Azure Data Lake Storageen.

1. [Luo linkki käyttäjäryhmän ja sitoutumisen merkityksellisiin tietoihin](integrate-audience-insights-engagement-insights.md) jakaaksesi tietoja näiden kahden ominaisuuksiin.

1. [Tunnista aiemmin todennettujen käyttäjien verkkotapahtumia](unknown-to-known.md) **tuntemattomasta tunnettuun** -ominaisuuden avulla.

1. Tutustu [henkilötietoja sisältävien tapahtumatietojen poistamiseen ja viemiseen](delete-export-personal-data.md).

## <a name="step-5-create-and-manage-funnel-reports"></a>Vaihe 5: Suppiloraporttien luominen ja hallinta

Suppiloraporttiin kerätään sivuston tai mobiilisovelluksen asiakassiirtymän tietojen vaiheet. Sen lisäksi, että luot valmiita profiiliraportteja ja mukautettuja raportteja, voit luoda suppiloraportin, joka tunnistaa polun, jonka asiakkaat kulkevat ennen ostoa. 

1. [Luo suppiloraportti](funnel-reports.md) päätöksenteon tueksi ja tunnistaaksesi alueet, joissa on optimoinnin ja prosessien parantamisen varaa.

1. Luo kanavien välisiä suppiloraportteja, kun olet varustanut mobiilisovelluksen käyttäjäryhmän merkityksellisillä tiedoilla [Android SDK](get-started-android.md) tai [iOS SDK](get-started-ios.md).

1. Käytä [suppilon merkityksellisiä tietoja](funnel-reports.md#funnel-insights) saadaksesi lisätietoja asiakaskäyttäytymisestä suppiloraportin vaiheissa.
 
## <a name="step-6-stay-connected"></a>Vaihe 6: Pysy yhteydessä

Arvostamme aktiivista osallistumistasi ja harkitsemme kaikkia tärkeitä palautteita uusien julkaisujen kehittämisessä. Anna palautteesi ja ilmoita ongelmista jollakin seuraavista kanavista:
- [Yhteisö](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Anna palautetta](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Tuen pyytäminen](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
