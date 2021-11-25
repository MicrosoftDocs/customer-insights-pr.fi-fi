---
title: Hyväksynnän sääntöjen aktivoiminen segmenteille kohdeyleisön merkityksellisissä tiedoissa
description: Vaiheet, jotka linkittävät hyväksyntätiedot ja aktivoivat hyväksyntätarkistukset kohdeyleisötiedoissa.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 33ec3a684c2ca47badb4e5461f069d1b2e4a4f3d
ms.sourcegitcommit: 2a0947cffb52eaf885aa2e50c95b3693f7e4c589
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753057"
---
# <a name="activate-consent-rules"></a>Aktivoi hyväksyntäsäännöt

[Suostumuskeskus (esiversio)](../consent-management/overview.md) auttaa harmonisoimaan suostumustietoja eri lähteistä. Käytä yhdistettyä *Suostumus*-entiteettiä, kun haluat käyttää oletussuostumustarkistuksia. Kun olet tuonut hyväksyntätiedot Suostumuskeskukseen ja määrittänyt tuotujen hyväksyntätietojen säännöt, *Suostumus*-kohde synkronoidaan automaattisesti kohdeyleisötietoihin.

## <a name="enable-consent-checks"></a>Ota suostumuksen tarkistukset käyttöön

Suostumuskeskukseen (esiversio) tuotujen hyväksyntätietojen ja määritettyjen sääntöjen avulla voit ottaa hyväksyntätarkistukset käyttöön kohdeyleisötiedoissa. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Hyväksyntä-välilehti kohdeyleisötietojen asetuksissa, joissa on aktivoituja hyväksyntätietoja.":::

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Järjestelmä**.

1. Valitse **Suostumus (esiversio)** -välilehti.

1. Määritä **Ota hyväksynnän tarkistukset käyttöön** -osassa sen alueen valitsin, jonka haluat **ottaa käyttöön**.

1. Valitse **Salli hyväksynnän oletussääntöjen ohittaminen** -valintaruutu, jos haluat poistaa tietyn segmentin pakotetut oletussuostumustarkistukset. 

1. Valitse avattavasta valikosta missä haluat sallia ohitukset.     

1. Valitse **Linkitä hyväksyntä asiakasprofiileihin** -osassa määrite, jota käytetään tunnisteena hyväksyntätietojen linkittämiseen asiakastietoihin. Se on todennäköisesti puhelinnumero tai sähköpostiosoite. 

1. Ota asetukset käyttöön valitsemalla **Tallenna**.

## <a name="disable-consent-checks"></a>Ota suostumustarkistukset pois käytöstä

Jos haluat lopettaa hyväksyntätietojen käytön kohdeyleisötiedoissa, järjestelmänvalvojan on päivitettävä järjestelmäasetukset sen mukaan.

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Järjestelmä**.

1. Valitse **Suostumus (esiversio)** -välilehti.

1. Valitse **Ota hyväksyntätarkistukset käyttöön** -osassa valitsimen arvoksi **Ei käytössä**.
