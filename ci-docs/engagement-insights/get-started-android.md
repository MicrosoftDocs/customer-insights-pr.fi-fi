---
title: Android SDK:n käytön aloittaminen
description: Lisätietoja Android SDK:n mukauttamisesta ja suorittamisesta
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036914"
---
# <a name="get-started-with-the-android-sdk"></a>Android SDK:n käytön aloittaminen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tämä opasohjelma opastaa sinua Android-sovelluksen instrumentoinnissa Dynamics 365 Customer Insightsin vuorovaikutuksen merkityksellisten tietojen SDK:n kanssa. Tapahtumat näkyvät portaalissa viiden minuutin kuluessa.

## <a name="configuration-options"></a>Määritysvaihtoehdot
Seuraavat määritysvalinnat voidaan välittää SDK:lle:

- **ingestionKey**: Käsittelyavain, jonka avulla tapahtumat lähetetään työtilaan.

## <a name="prerequisites"></a>Edellytykset

- Android Studio

- Androidin ohjelmointirajapinnan taso: 16 (Jelly Bean)

- Käsittelyavain (katso alla olevat ohjeet sen hankkimiseksi)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>Vaihe 1: Integroiminen SDK sovellukseen
Aloita prosessi valitsemalla työtila. Valitse sitten Android-mobiiliympäristö ja lataa Android SDK.

- Valitse työtila vasemmanpuoleisessa siirtymisruudussa olevan työtilan valitsimen avulla.

- Jos sinulla ei ole vielä työtilaa, valitse **Uusi työtila** ja luo [uusi työtila](create-workspace.md) ohjeiden mukaan.

## <a name="step-2-configure-the-sdk"></a>Vaihe 2: SDK:n määrittäminen

1. Kun työtila on luotu, siirry kohtaan **Hallinta** > **Työtila** ja valitse **Asennusopas**. 

1. Lataa [vuorovaikutuksen merkityksellisten tietojen Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) ja aseta tiedosto `eiandroidsdk-debug.aar` kansioon `libs`.

1. Avaa projektin tason tiedosto `build.gradle` ja lisää seuraavat koodikatkelmat:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Määritä vuorovaikutuksen merkityksellisten tietojen SDK:n määritys tiedoston `AndroidManifest.xml` kautta. Tiedosto sijaitsee kansiossa `manifests`. 
1. Kopioi XML-katkelma **asennusohjeesta**. `Your-Ingestion-Key` täytetään automaattisesti.

   > [!NOTE]
   > Osaa `${applicationId}` ei tarvitse korvata. Se täytetään automaattisesti.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Ota käyttöön tapahtumien `View` automaattinen sieppaus tai poista se käytöstä määrittämällä yllä olevan kentän `autoCapture` arvoksi `true` tai `false`.

1. (Valinnainen) Muita määrityksiä ovat muun muassa päätepisteen keruutyökalun URL-osoite. Ne voidaan lisätä käsittelyavaimen metatietoihin tiedostossa `AndroidManifest.xml` seuraavasti:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>Vaihe 3: Alusta SDK kohteesta MainActivity 

Kun SDK on alustettu, voit käsitellä tapahtumia ja niiden ominaisuuksia MainActivity-ympäristössä.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Kaikkien tapahtumien ominaisuuden määrittäminen (valinnainen)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Kontekstitapahtuman ominaisuudet tukevat seuraavia tyyppejä:
- String
- Päivämäärä
- Kaksinkertainen
- Long
- Boolean
- UUID

### <a name="track-an-event"></a>Seuraa tapahtumaa

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>Käyttäjän tietojen määrittäminen tapahtumaa varten (valinnainen)

SDK:n avulla voit määrittää käyttäjätiedot, jotka voidaan lähettää jokaisen tapahtuman yhteydessä. Voit määrittää käyttäjän kutsumalla ohjelmointirajapintaa `setUser(user: User)` tasolla `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Tietoluokka `User` sisältää seuraavat merkkijonon ominaisuudet:

- **localId**: Käyttäjän paikallinen tunnus.
- **authId**: Todennettu käyttäjätunnus.
- **authType**: Todennustyyppiä käytetään todennetun käyttäjätunnuksen hakemisessa.
- **name**: Käyttäjän nimi.
- **email**: Käyttäjän sähköpostiosoite.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
