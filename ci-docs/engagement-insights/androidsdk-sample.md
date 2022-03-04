---
title: Android SDK:n esimerkki
description: Esimerkkiprojekti, joka sisältää lisätietoja Android SDK:sta
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229914"
---
# <a name="run-the-android-sdk-sample"></a>Android SDK:n esimerkin suorittaminen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tässä esimerkissä Android-projekti auttaa ymmärtämään, miten SDK toimii sovelluksessa. Sinun ei tarvitse kirjoittaa koodia. Sinun tarvitsee vain lisätä käsittelyavain, ja näet heti työtilan tapahtumat.

## <a name="prerequisites"></a>Edellytykset

- [Android Studio](https://developer.android.com/studio)
- [Käsittelyavain](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Android SDK:n esimerkin lataaminen

1. [Vuorovaikutuksen merkityksellisten tietojen Android SDK:n esimerkin lataaminen](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Pura pakattu tiedosto `ei-android-sample.zip`.
1. Avaa purettu kansio Android Studiossa.
1. Korvaa tiedostossa `AndroidManifest.xml` merkkijono `"Your-Ingestion-Key"` työtilan käsittelyavaimella, joka saadaan vuorovaikutuksen merkityksellisistä tiedoista kohdassa **Järjestelmänvalvoja** > **Työtila** > **Asennusopas**. 

   > [!NOTE]
   > Osaa `${applicationId}` ei tarvitse korvata. Se täytetään automaattisesti.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Voit käynnistää esimerkkiprojektin valitsemalla **Suorita**.
1. Tarkastele työtilan tapahtumia.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
