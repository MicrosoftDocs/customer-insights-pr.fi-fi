---
title: Dynamics 365 Customer Insightsin käytön aloittaminen
description: Yleiskuvaus Customer Insightsista auttaa resursseja pääsemään nopeasti alkuun.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1a19d83930d667bdca5301dcc5a3ffa5db6a7bdc
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741129"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insightsin käytön aloittaminen

Customer Insights auttaa ymmärtämään asiakkaita entistä syvällisemmin. Luo kokonaisvaltainen asiakasnäkymä yhdistämällä tietoja eri tapahtuma-, toiminto- ja havaintolähteistä. Voit muodostaa näiden merkityksellisten tietojen avulla asiakaskeskeisiä kokemuksia ja prosesseja. Asiakastietojen yhtenäistäminen ja ymmärtäminen sekä älykkäiden merkityksellisten tietojen ja toimintojen saaminen niiden avulla.

## <a name="step-1-create-an-environment"></a>Vaihe 1: Ympäristön luominen

Aluksi on luotava työympäristö. Jos organisaatiosi on jo ostanut käyttöoikeuden, katso kohta [Ympäristön luominen](create-environment.md). Lisätietoja Customer Insights -kokeiluversion käynnistämisestä on ohjeaiheessa [Kokeiluympäristön määrittäminen](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Vaihe 2: Tutustu Customer Insightsiin

Kun kirjaudut Customer Insights -tiliin ensimmäisen kerran, voit määrittää asetuksia ja tutkia tuotetta.

1. [Kirjaudu Customer Insightsiin](https://home.ci.ai.dynamics.com) käyttämällä Microsoft Azure Active Directory (AAD) -käyttäjätililläsi.

1. [Muuta ympäristöä](manage-environments.md#switch-environments) niin, että näet esittelytiedot ja [tutustut Customer Insightsiin](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Vaihe 3: Tietojen suhteiden syöttäminen, yhdenmukaistaminen ja määrittäminen

Yhtenäiset profiilit ovat perusteita tietojen tarkastelemiseen ja käyttöön. Tuo tietoja eri lähteistä ja suorita tietojen yhdistäminen luodaksesi yhtenäiset profiilit. Määritä suhteet entiteettien välillä tietojen lisäämiseksi profiileihin täydennysominaisuuksien avulla.

1. Voit käyttää tietoja luomalla tietolähteitä useista vaihtoehdoista. Valitse [Power Query -yhdistimet](connect-power-query.md), [Common Data Model -kansio](connect-common-data-model.md) tai [Microsoft Dataverse](connect-dataverse-managed-lake.md). 

1. Suorita tietojen [yhdistämisprosessi](data-unification.md) etsimällä [lähdekentät](map-entities.md), poistamalla [kaksoiskappaleet](remove-duplicates.md), [yhdistämällä ehdot](match-entities.md) ja [yhdistämällä kentät](merge-entities.md).

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

1. Tarkista integrointivaihtoehdot esimerkiksi muihin Dynamics 365 -sovelluksiin, joissa on [asiakaskorttiapuohjelma](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
