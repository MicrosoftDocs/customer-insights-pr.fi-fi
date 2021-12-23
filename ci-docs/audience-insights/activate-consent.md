---
title: Suostumussääntöjen aktivoiminen segmenteille
description: Noudata näitä vaiheita, jotka linkittävät suostumustiedot ja aktivoivat suostumuksen tarkistukset käyttäjäryhmän merkityksellisissä tiedoissa. Järjestelmänvalvoja voi myös poistaa suostumuksen tarkistukset käytöstä.
ms.date: 11/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 552cb0739c4d17266dd028638df067f3384b738a
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884070"
---
# <a name="activate-consent-rules"></a>Aktivoi hyväksyntäsäännöt

[Suostumuskeskus (esiversio)](../consent-management/overview.md) auttaa harmonisoimaan suostumustietoja eri lähteistä. Käytä yhdistettyä *Suostumus*-entiteettiä, kun haluat käyttää oletussuostumustarkistuksia. Kun olet tuonut suostumustiedot Suostumuskeskukseen ja määrittänyt tietojen säännöt, *Suostumus*-entiteetti synkronoidaan automaattisesti käyttäjäryhmän merkityksellisiin tietoihin.

## <a name="enable-consent-checks"></a>Ota suostumuksen tarkistukset käyttöön

Suostumuskeskukseen (esiversio) tuotujen suostumustietojen ja määritettyjen sääntöjen avulla voit ottaa suostumuksen tarkistukset käyttöön. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Hyväksyntä-välilehti kohdeyleisötietojen asetuksissa, joissa on aktivoituja hyväksyntätietoja.":::

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Järjestelmä**.

1. Valitse **Suostumus (esiversio)** -välilehti.

1. Määritä **Ota suostumuksen tarkistukset käyttöön** -osan kaikkien käyttöönotettavien alueiden valitsimen arvoksi **Käytössä**.

1. Valitse **Salli hyväksynnän oletussääntöjen ohittaminen** -valintaruutu, jos haluat poistaa tietyn segmentin pakotetut oletussuostumustarkistukset. 

1. Valitse avattavasta valikosta missä haluat sallia ohitukset.     

1. Valitse **Linkitä suostumus asiakasprofiileihin** -osassa määrite, jota käytetään tunnisteena suostumustietojen linkittämiseen asiakastietoihin. Se on todennäköisesti puhelinnumero tai sähköpostiosoite. 

1. Ota asetukset käyttöön valitsemalla **Tallenna**.

## <a name="disable-consent-checks"></a>Ota suostumustarkistukset pois käytöstä

Jos haluat lopettaa hyväksyntätietojen käytön kohdeyleisötiedoissa, järjestelmänvalvojan on päivitettävä järjestelmäasetukset sen mukaan.

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Järjestelmä**.

1. Valitse **Suostumus (esiversio)** -välilehti.

1. Valitse **Ota suostumuksen tarkistukset käyttöön** -osassa valitsimen arvoksi **Ei käytössä**.

> [!TIP]
> Jos haluat lopettaa hyväksynnän hallintaominaisuuden käytön, katso [Hyväksyntäkeskuksen järjestelmäasetukset (esiversio)](../consent-management/system-settings.md).
