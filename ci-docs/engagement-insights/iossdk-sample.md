---
title: iOS SDK:n esimerkin suorittaminen
description: Esimerkkiprojekti, joka sisältää lisätietoja iOS SDK:sta
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bbe4ba648952a8081af4c8f2610276809fa5efeb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232838"
---
# <a name="run-the-ios-sdk-sample"></a>iOS SDK:n esimerkin suorittaminen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tässä esimerkissä iOS-projekti auttaa ymmärtämään, miten SDK toimii sovelluksessa. Sinun ei tarvitse kirjoittaa koodia. Sinun tarvitsee vain lisätä käsittelyavain, ja näet heti työtilan tapahtumat.

## <a name="prerequisites"></a>Edellytykset

- [Xcoden versio 9+](https://developer.apple.com/xcode/downloads/)
- [Käsittelyavain](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>iOS SDK -sovelluksen lataaminen

1. [Lataa vuorovaikutuksen merkityksellisten tietojen iOS SDK:n esimerkki](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Pura pakattu tiedosto `ei-ios-sample.zip`.
1. Avaa esimerkkisovellusprojekti Xcodessa.
1. Korvaa tiedostossa `EIConfig.plist` merkkijono `“YOUR-INGESTION-KEY”` kentässä `ingestionKey` työtilan käsittelyavaimella, joka saadaan vuorovaikutuksen merkityksellisistä tiedoista kohdassa **Järjestelmänvalvoja** > **Työtila** > **Asennusopas**.
1. Voit käynnistää esimerkkiprojektin valitsemalla **Suorita**.
1. Tarkastele työtilan tapahtumia.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
