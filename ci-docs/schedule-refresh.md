---
title: Aikatauluta järjestelmän päivitys
description: Määritä aika, jolloin järjestelmä päivitetään
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 949ea071ca41127b0c45488d5d7af3f6aa4e1c35
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/02/2022
ms.locfileid: "9395952"
---
# <a name="schedule-system-refresh"></a>Aikatauluta järjestelmän päivitys

Ajoittaa kaikkien [käsiteltyjen tietolähteiden](data-sources.md) automaattiset päivitykset. Automaattisten päivitysten avulla voit varmistaa, että tietolähteiden päivitykset näkyvät yhtenäisessä asiakasprofiilissa.

> [!NOTE]
> Hallitsemasi Power Query -tietolähteet päivittyvät omien aikataulujensa mukaan. Voit ajoittaa hallitsemiesi Power Query -tietolähteiden päivitykset määrittämällä päivitysasetukset kyseiselle tietolähteelle **Tietolähteet**-sivulla.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform – tietovuon päivitysasetukset.":::

## <a name="set-system-refresh-schedule"></a>Määritä järjestelmän päivitysaikataulu

1. Siirry kohtaan **Järjestelmänvalvoja** > **Järjestelmä** ja valitse **Aikataulu**-välilehti.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Aikatauluta päivitys -välilehti Järjestelmä-sivulla.":::

1. Ajoitetun päivityksen oletustila on **Ei käytössä**. Jos haluat ottaa ajoitetut päivitykset käyttöön, vaihda näytön yläreunassa olevan kohdan arvoksi **Käytössä**.

1. Valitse päivitysväliksi **Viikoittain** (oletusarvo) tai **Päivittäin**. Jos aiot aikatauluttaa viikoittaiset päivitykset, valitse vähintään yksi päivä, jolloin haluat suorittaa päivityksen.

1. Määritä **Aikavyöhyke** ja määritä sitten avattava **Aika**-luettelo, jos haluat määrittää päivityksen ajoituksen. Jos haluat aikatauluttaa useita päivityksiä yhdelle päivälle, valitse **Lisää toinen aika**. Voit lisätä enintään neljä päivitystä.

1. Ota muutokset käyttöön valitsemalla **Tallenna**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
