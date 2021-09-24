---
title: Aloita Dynamics 365 Customer Insightsin käyttäjäryhmien merkityksellisten tietojen ominaisuuden avulla
description: Yleiskatsaus yleisistä käyttäjäryhmän merkityksellisistä tiedoista auttaa resursseja pääsemään nopeasti alkuun.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: aaaf1848df175469d8af07754ac153b777781ffb
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466573"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Aloita Dynamics 365 Customer Insightsin käyttäjäryhmien merkityksellisten tietojen ominaisuuden avulla

Käyttäjäryhmätiedot voivat auttaa sinua rakentamaan syvemmän ymmärryksen asiakkaistasi. Luo kokonaisvaltainen asiakasnäkymä yhdistämällä tietoja eri tapahtuma-, toiminto- ja havaintolähteistä. Voit muodostaa näiden merkityksellisten tietojen avulla asiakaskeskeisiä kokemuksia ja prosesseja. Asiakastietojen yhtenäistäminen ja ymmärtäminen sekä älykkäiden merkityksellisten tietojen ja toimintojen saaminen niiden avulla.

## <a name="step-1-create-an-environment"></a>Vaihe 1: Ympäristön luominen

Aluksi on luotava työympäristö. Jos organisaatiosi on jo ostanut käyttöoikeuden, katso kohta [Maksetun tilauksen käytön aloittaminen](get-started-paid.md). Lisätietoja kokeilun käyttäjäryhmän merkityksellisistä tiedoista on ohjeaiheessa [Kokeiluympäristön määrittäminen](get-started-trial.md). 

## <a name="step-2-explore-audience-insights"></a>Vaihe 2: Tutustu käyttäjäryhmän merkityksellisiin tietoihin

Kun kirjaudut ensimmäisen kerran käyttäjäryhmien merkityksellisiin tietoihin, voit määrittää asetuksia, tarkastella tuotetta.

1. [Kirjaudu sisään käyttäjäryhmän merkityksellisiin tietoihin](https://home.ci.ai.dynamics.com) käyttämällä Microsoft Azure Active Directory (AAD) -käyttäjätiliäsi.

1. [Muuta ympäristöä](manage-environments.md#switch-environments) niin, että näet esittelytiedot ja [käyttäjäryhmän merkityksellisisä tietoja](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Vaihe 3: Tietojen suhteiden syöttäminen, yhdenmukaistaminen ja määrittäminen

Yhtenäiset profiilit ovat perusteita tietojen tarkastelemiseen ja käyttöön. Tuo tietoja eri lähteistä ja suorita tietojen yhdistäminen luodaksesi yhtenäiset profiilit. Määritä suhteet entiteettien välillä tietojen lisäämiseksi profiileihin täydennysominaisuuksien avulla. 

1. Voit käyttää tietoja luomalla tietolähteitä useista vaihtoehdoista. Valitse [Power Query -yhdistimien](connect-power-query.md), [Common Data Model -kansion](connect-common-data-model.md) tai [Microsoft Dataversen](connect-common-data-service-lake.md) väliltä. 

1. Suorita [tietojen yhdistämisprosessi](data-unification.md) käymällä läpi [liittämis](map-entities.md)-, [vastaavuus](match-entities.md)- ja [yhdistämis](merge-entities.md)-vaiheet.

1. Tutustu [entiteetteihin, jotka järjestelmä luo](entities.md) ja luo [suhteet syötettyjen entiteettien välille](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Vaihe 4: Yhtenäisten profiilien tehostaminen ennusteiden, aktiviteettien ja toimenpiteiden avulla

Yhtenäisten profiilien avulla voit tehostaa tietojen keräämistä ja parantaa niiden antamia tietoja.

1. Voit [rikastaa asiakastietojasi](enrichment-hub.md) valitsemalla laajenevasta rikastamisen tarjoajien kirjastosta.

1. [Valmiiden mallien](predictions-overview.md) avulla voit ennustaa vaihtuvuuden todennäköisyyttä tai odotettuja tuottoja.

1. [Määritä aktiviteetit](activities.md) lisättyjen tietojen perusteella ja visualisoi vuorovaikutus asiakkaiden kanssa aikajärjestyksessä. 

1. [Luo mittareita](measures.md) liiketoiminnan tavoitteiden ja suorituskykyilmaisimien mittaamiseksi.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Vaihe 5: Luo segmenttejä ja aktivoi tietoja erilaisten vientivaihtoehtojen avulla

Nyt kun tietosi ovat täydelliset ja sisältävät laajan valikoiman tietoja asiakkaistasi, on aika etsiä tapoja toimia näiden tietojen suhteen. 

1. [Luo segmenttejä](segments.md) ja asiakaspohjan alijoukkoja, jotta voit varmistaa, että toiminnot ovat olennaisia kohdeasiakkaille.

1. Selaa laajennettavissa olevaa [vientivaihtoehtojen](export-destinations.md) luetteloa, jossa voit käyttää asiakastietoja. Voit esimerkiksi käyttää tietoja kampanjoiden hallintaan ja digitaalisen markkinoinnin tavoittamiseen.

1. Tarkastele integrointivaihtoehtoja, esimerkiksi [yhdistämällä suoraan sitouttamistietoihin](../engagement-insights/integrate-audience-insights-engagement-insights.md) tai muihin Dynamics 365 -sovelluksiin [asiakaskortti-apuohjelman](customer-card-add-in.md) avulla.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
