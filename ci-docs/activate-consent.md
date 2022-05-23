---
title: Suostumussääntöjen aktivoiminen segmenteille
description: Noudata näitä vaiheita, jotka linkittävät suostumustiedot ja aktivoivat suostumuksen tarkistukset Dynamics 365 Customer Insightsissa. Järjestelmänvalvoja voi myös poistaa suostumuksen tarkistukset käytöstä.
ms.date: 04/27/2022
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f82e3a4031fee8bcaa88575cbd68b37385a7fffb
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755166"
---
# <a name="activate-consent-rules"></a>Aktivoi hyväksyntäsäännöt

[Suostumuskeskus (esiversio)](consent-management/overview.md) auttaa harmonisoimaan suostumustietoja eri lähteistä. Käytä yhdistettyä *Suostumus*-entiteettiä, kun haluat käyttää oletussuostumustarkistuksia. Kun olet tuonut suostumustiedot ja määrittänyt yhdistämissäännöt, *Suostumus*-entiteetti synkronoidaan automaattisesti Dynamics 365 Customer Insightsiin.

## <a name="enable-consent-checks"></a>Ota suostumuksen tarkistukset käyttöön

Suostumuskeskukseen (esiversio) tuotujen suostumustietojen ja määritettyjen sääntöjen avulla voit ottaa suostumuksen tarkistukset käyttöön. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Hyväksyntä-välilehti Customer Insightsin asetuksissa, joissa on aktivoituja hyväksyntätietoja.":::

1. Siirry Customer Insightsissa kohtaan **Hallinta** > **Järjestelmä**.

1. Valitse **Suostumus (esiversio)** -välilehti.

1. Määritä **Ota suostumuksen tarkistukset käyttöön** -osan kaikkien käyttöönotettavien alueiden valitsimen arvoksi **Käytössä**.

1. Valitse **Salli hyväksynnän oletussääntöjen ohittaminen** -valintaruutu, jos haluat poistaa tietyn segmentin pakotetut oletussuostumustarkistukset. 

1. Valitse avattavasta valikosta missä haluat sallia ohitukset.     

1. Valitse **Linkitä suostumus asiakasprofiileihin** -osassa määrite, jota käytetään tunnisteena suostumustietojen linkittämiseen asiakastietoihin. Se on todennäköisesti puhelinnumero tai sähköpostiosoite. 

1. Ota asetukset käyttöön valitsemalla **Tallenna**.

## <a name="disable-consent-checks"></a>Ota suostumustarkistukset pois käytöstä

Jos haluat lopettaa hyväksyntätietojen käytön Customer Insightsissa, järjestelmänvalvojan on päivitettävä järjestelmäasetukset sen mukaan.

1. Siirry Customer Insightsissa kohtaan **Hallinta** > **Järjestelmä**.

1. Valitse **Suostumus (esiversio)** -välilehti.

1. Valitse **Ota suostumuksen tarkistukset käyttöön** -osassa valitsimen arvoksi **Ei käytössä**.

> [!TIP]
> Jos haluat lopettaa hyväksynnän hallintaominaisuuden käytön, katso [Hyväksyntäkeskuksen järjestelmäasetukset (esiversio)](consent-management/system-settings.md).
