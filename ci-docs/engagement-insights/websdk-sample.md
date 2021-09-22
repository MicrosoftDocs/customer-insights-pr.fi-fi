---
title: SDK:n verkkosovelluksen näytteen suorittaminen
description: Tutustu SDK:n verkkosovelluksen näytteen mukauttamiseen ja suorittamiseen.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036599"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Suorita SDK:n verkkosovelluksen näyte Dynamics 365 Customer Insightsin vuorovaikutuksen merkitykselliset tiedot -ominaisuutta varten.

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Vuorovaikutuksen merkitykselliset tiedot -ominaisuuden SDK:n verkkosovelluksen kirjasto on JavaScript-kirjasto, joka sisältää näytekoodia, jota voit käyttää verkkosivustollasi.

## <a name="prerequisites"></a>Edellytykset

- Asenna [Visual Studio Code](https://code.visualstudio.com/).
- [Asenna Live Server -laajennus](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) Visual Studio Codessa ja tutustu Live Serverin suorittamiseen.
- Sinulla on oltava [käsittelyavain](instrument-website.md).

## <a name="run-sample"></a>Suorita näyte

1. [Lataa SDK:n verkkosovelluksen näyte](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Pura pakattu tiedosto `ei_websdk_sample.zip`.

1. Avaa purettu kansio Visual Studio Codessa.

1. Korvaa `ei_websdk_sample.html`-tiedostossa merkkijono "INGESTION KEY" käyttöavaimellasi vuorovaikutuksen merkitykselliset tiedot-ominaisuuden portaalista ja merkkijono "NAME" yleisellä nimellä, jota haluat käyttää SDK-esiintymille. Varmista, että korvaat kaikki esiintymät.

1. Avaa `ei_websdk_sample.html`-tiedosto käyttäen Live Serveriä Visual Studio Codessa valitsemalla tilapalkista **Julkaise**.

1. Kun avaat sivun, katselutapahtuman pitäisi lähteä automaattisesti. Sivun painikkeiden napsauttaminen lähettää toimintotapahtumia. Lisäksi **Seuraa tapahtumia** -painike lähettää mukautettuja tapahtumia. **Siirry Bingiin** -painikkeen valitseminen lähettää toimintotapahtuman, ennen kuin siirryt Bingin verkkosivustolle.

1. Katso tapahtumien virtaavan, kun siirryt työtilaasi. Tämä työtila on yhdistetty vaiheessa 4 syötettyyn käsittelyavaimeen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]