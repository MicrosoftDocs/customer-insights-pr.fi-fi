---
title: SDK:n verkkosovelluksen näytteen suorittaminen
description: Tutustu SDK:n verkkosovelluksen näytteen mukauttamiseen ja suorittamiseen.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606204"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Suorita SDK:n verkkosovelluksen näyte Dynamics 365 Customer Insightsin vuorovaikutuksen merkitykselliset tiedot -ominaisuutta varten.

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Vuorovaikutuksen merkitykselliset tiedot -ominaisuuden SDK:n verkkosovelluksen kirjasto on JavaScript-kirjasto, joka sisältää näytekoodia, jota voit käyttää verkkosivustollasi.

## <a name="prerequisites"></a>Edellytykset

- Asenna [Visual Studio Code](https://code.visualstudio.com/).
- [Asenna Live Server -laajennus](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) Visual Studio Codessa ja tutustu Live Serverin suorittamiseen.
- Sinulla on oltava [vuorovaikutuksen merkityksellisten tietojen työtila](create-workspace.md).

## <a name="run-sample"></a>Suorita näyte

1. [Lataa SDK:n verkkosovelluksen näyte](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Pura pakattu tiedosto `ei_websdk_sample.zip`.

1. Avaa purettu kansio Visual Studio Codessa.

1. Siirry työtilasi vuorovaikutuksen merkityksellisten tietojen portaaliin. Valitse **Järjestelmänvalvoja** > **Työtila**  ja sitten **Asennusopas**. Seuraa ensimmäistä vaihtoehtoa ja valitse **Kopioi koodi** kopioidaksesi JavaScript-koodikatkelman.

1. Liitä `ei_websdk_sample.html`-tiedostossa juuri kopioimasi koodikatkelma tämän rivin alle:

   - <-- LIITÄ JAVASCRIPT-KOODIKATKELMA VUOROVAIKUTUKSEN MERKITYKSELLISTEN TIETOJEN PORTAALISTA TÄHÄN TÄMÄN RIVIN ALLE -->

1. Avaa `ei_websdk_sample.html`-tiedosto käyttäen Live Serveriä Visual Studio Codessa valitsemalla tilapalkista **Julkaise**.

1. Kun avaat sivun, katselutapahtuman pitäisi lähteä automaattisesti. Sivun painikkeiden napsauttaminen lähettää toimintotapahtumia. Lisäksi **Seuraa tapahtumia** -painike lähettää mukautettuja tapahtumia. **Siirry Bingiin** -painikkeen valitseminen lähettää toimintotapahtuman, ennen kuin siirryt Bingin verkkosivustolle.

1. Katso tapahtumien virtaavan, kun siirryt työtilaasi. Tämä työtila on yhdistetty vaiheessa 4 syötettyyn käsittelyavaimeen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
