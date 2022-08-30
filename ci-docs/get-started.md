---
title: Dynamics 365 Customer Insightsin käytön aloittaminen
description: Yleiskuvaus Customer Insightsista auttaa resursseja pääsemään nopeasti alkuun.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: audience-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: ce0336c4bf853bc81ec01c45410169a63b69eb03
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304607"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insightsin käytön aloittaminen

Customer Insights auttaa ymmärtämään asiakkaita entistä syvällisemmin. Luo kokonaisvaltainen asiakasnäkymä yhdistämällä tietoja eri tapahtuma-, toiminto- ja havaintolähteistä. Voit muodostaa näiden merkityksellisten tietojen avulla asiakaskeskeisiä kokemuksia ja prosesseja. Asiakastietojen yhtenäistäminen ja ymmärtäminen sekä älykkäiden merkityksellisten tietojen ja toimintojen saaminen niiden avulla.

## <a name="step-1-create-an-environment"></a>Vaihe 1: Ympäristön luominen

Lue ensin työskentely-ympäristö. Jos organisaatiosi on jo ostanut käyttöoikeuden, katso kohta [Ympäristön luominen](create-environment.md). Lisätietoja Customer Insights -kokeiluversion käynnistämisestä on ohjeaiheessa [Kokeiluympäristön määrittäminen](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Vaihe 2: Tutustu Customer Insightsiin

Kun kirjaudut Customer Insights -tiliin ensimmäisen kerran, määritä asetukset ja tutki tuotetta.

1. [Kirjaudu Customer Insightsiin](https://home.ci.ai.dynamics.com) käyttämällä Microsoft Azure Active Directory (AAD) -käyttäjätililläsi.

1. Muuta ympäristöä niin, että näet esittelytiedot ja [tutustut Customer Insightsiin](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Vaihe 3: Tietojen suhteiden syöttäminen, yhdenmukaistaminen ja määrittäminen

Yhtenäiset profiilit ovat perusteita tietojen tarkastelemiseen ja käyttöön. Tuo tietoja eri lähteistä ja suorita tietojen yhdistäminen luodaksesi yhtenäiset profiilit. Määritä suhteet käsiteltyjen entiteettien välillä ja lisää tiedot profiileihin rikastusominaisuuksien avulla.

1. Voit käyttää tietoja luomalla tietolähteitä useista vaihtoehdoista. Valitse joko [Azure Data Lake Storage, mukaan lukien Common Data Model](connect-common-data-model.md), [Azure Synapse Analytics](connect-synapse.md), [Microsoft Dataverse](connect-dataverse-managed-lake.md) tai [Power Query -yhdistimet](connect-power-query.md).

1. Suorita tietojen [yhdistämisprosessi](data-unification.md) etsimällä [lähdekentät](map-entities.md), poistamalla [kaksoiskappaleet](remove-duplicates.md), [yhdistämällä ehdot](match-entities.md) ja [yhdistämällä kentät](merge-entities.md).

1. Tutustu [entiteetteihin, jotka järjestelmä luo](entities.md) ja luo [suhteet syötettyjen entiteettien välille](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Vaihe 4: Yhtenäisten profiilien tehostaminen ennusteiden, aktiviteettien ja toimenpiteiden avulla

Yhtenäisten profiilien avulla voit tehostaa tietojen keräämistä ja parantaa niiden tietoja entisestään.

1. Voit [rikastaa asiakastietojasi](enrichment-hub.md) valitsemalla laajenevasta rikastamisen tarjoajien kirjastosta.

1. [Valmiiden mallien](predictions-overview.md) avulla voit ennustaa vaihtuvuuden todennäköisyyttä tai odotettuja tuottoja.

1. [Määritä aktiviteetit](activities.md) lisättyjen tietojen perusteella ja visualisoi vuorovaikutus asiakkaiden kanssa aikajärjestyksessä.

1. [Luo mittareita](measures.md) liiketoiminnan tavoitteiden ja suorituskykyilmaisimien mittaamiseksi.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Vaihe 5: Luo segmenttejä ja aktivoi tietoja erilaisten vientivaihtoehtojen avulla

Kun tiedot ovat nyt täydellisiä ja sisältävät monenlaisia tietoja asiakkaistasi, etsi tapoja, joilla voit toimia tietojen perusteella.

1. [Luo segmenttejä](segments.md) ja asiakaspohjan alijoukkoja, jotta voit varmistaa, että toiminnot ovat olennaisia kohdeasiakkaille.

1. Selaa laajennettavissa olevaa [vientivaihtoehtojen](export-destinations.md) luetteloa, jossa voit käyttää asiakastietoja. Voit esimerkiksi käyttää tietoja kampanjoiden hallintaan ja digitaalisen markkinoinnin tavoittamiseen.

1. Tarkista integrointivaihtoehdot esimerkiksi muihin Dynamics 365 -sovelluksiin, joissa on [asiakaskorttiapuohjelma](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
