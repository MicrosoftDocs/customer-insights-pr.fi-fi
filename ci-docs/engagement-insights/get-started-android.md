---
title: Android SDK:n käytön aloittaminen
description: Lisätietoja Android SDK:n mukauttamisesta ja suorittamisesta
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a060ac60db71a7b0fb8c0d7a3b0e266004fbee6a
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494271"
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

## <a name="integrate-the-sdk-into-your-application"></a>Integroiminen SDK sovellukseen
Aloita prosessi valitsemalla työtila. Valitse sitten Android-mobiiliympäristö ja lataa Android SDK.

- Valitse työtila vasemmanpuoleisessa siirtymisruudussa olevan työtilan valitsimen avulla.

- Jos sinulla ei ole vielä työtilaa, valitse **Uusi työtila** ja luo [uusi työtila](create-workspace.md) ohjeiden mukaan.

- Kun työtila on luotu, siirry kohtaan **Hallinta** > **Työtila** ja valitse **Asennusopas**. 

## <a name="configure-the-sdk"></a>SDK:n määrittäminen

Kun olet ladannut SDK:n, voit käyttää sitä Android Studion avulla tapahtumien käyttöönotossa ja määrittämisessä. Tapoja tehdä on kaksi:
### <a name="option-1-using-jitpack-recommended"></a>Vaihtoehto 1: JitPackin käyttäminen (suositellaan)
1. Lisää JitPack-säilö `build.gradle`-juureen:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Lisää riippuvuus:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-using-download-link"></a>Vaihtoehto 2: Latauslinkin käyttäminen
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

1. Lisää `manifests`-kansion alla sijaitsevaan `AndroidManifest.xml`-tiedostoon verkon ja Internetin käyttöoikeudet. 
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```
    
1. Määritä vuorovaikutuksen merkityksellisten tietojen SDK:n määritys `AndroidManifest.xml`-tiedoston kautta. 

## <a name="enable-auto-instrumentation"></a>Automaattisen instrumentoinnin käyttöönotto
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

1. Ota käyttöön tapahtumien `View` automaattinen sieppaus tai poista se käytöstä määrittämällä yllä olevan kentän `autoCapture` arvoksi `true` tai `false`. `Action`-tapahtumat on nyt lisättävä manuaalisesti.

1. (Valinnainen) Muita määrityksiä ovat muun muassa päätepisteen keruutyökalun URL-osoite. Ne voidaan lisätä käsittelyavaimen metatietoihin tiedostossa `AndroidManifest.xml` seuraavasti:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="implement-custom-events"></a>Mukautettujen tapahtumien toteuttaminen

Kun SDK on alustettu, voit käsitellä tapahtumia ja niiden ominaisuuksia `MainActivity`-ympäristössä.

    
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

## <a name="set-user-details-for-your-event-optional"></a>Käyttäjän tietojen määrittäminen tapahtumaa varten (valinnainen)

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
