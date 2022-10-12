---
title: Aikatauluta järjestelmän päivitys
description: Määritä aika, jolloin järjestelmä päivitetään
ms.date: 09/27/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 4aac02b570357d2086f7a9d7340b0e4837157a0b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610324"
---
# <a name="schedule-system-refresh"></a>Aikatauluta järjestelmän päivitys

Ajoittaa kaikkien [käsiteltyjen tietolähteiden](data-sources.md) automaattiset päivitykset. Automaattisten päivitysten avulla voit varmistaa, että tietolähteiden päivitykset näkyvät yhtenäisessä asiakasprofiilissa.

> [!NOTE]
> Hallitsemasi Power Query -tietolähteet päivittyvät omien aikataulujensa mukaan. Voit ajoittaa hallitsemiesi Power Query -tietolähteiden päivitykset määrittämällä päivitysasetukset kyseiselle tietolähteelle **Tietolähteet**-sivulla. Ajoitus kohdistetaan ylävirran tietojen päivitysaikataulun kanssa siten, että päivitykset eivät kaikki tapahdu samanaikaisesti.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform – tietovuon päivitysasetukset.":::

## <a name="set-system-refresh-schedule"></a>Määritä järjestelmän päivitysaikataulu

1. Siirry kohtaan **Järjestelmänvalvoja** > **Järjestelmä** ja valitse **Aikataulu**-välilehti.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Aikatauluta päivitys -välilehti Järjestelmä-sivulla.":::

1. Ajoitetun päivityksen oletustila on **Ei käytössä**. Jos haluat ottaa ajoitetut päivitykset käyttöön, vaihda näytön yläreunassa olevan kohdan arvoksi **Käytössä**.

1. Valitse päivitysväliksi **Viikoittain** (oletusarvo) tai **Päivittäin**. Jos aiot aikatauluttaa viikoittaiset päivitykset, valitse vähintään yksi päivä, jolloin haluat suorittaa päivityksen.

1. Määritä **Aikavyöhyke** ja määritä sitten avattava **Aika**-luettelo, jos haluat määrittää päivityksen ajoituksen. Jos haluat aikatauluttaa useita päivityksiä yhdelle päivälle, valitse **Lisää toinen aika**. Voit lisätä enintään neljä päivitystä.

1. Ota muutokset käyttöön valitsemalla **Tallenna**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
