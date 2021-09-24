---
title: iOS SDK:n käytön aloittaminen
description: Lisätietoja iOS SDK:n mukauttamisesta ja suorittamisesta
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: f05929435eeee9cf3f891ab18842c5861e39d5ba
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494226"
---
# <a name="get-started-with-the-ios-sdk"></a>iOS SDK:n käytön aloittaminen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tämä opasohjelma opastaa iOS-sovelluksen instrumentoinnissa Dynamics 365 Customer Insightsin vuorovaikutuksen merkityksellisten tietojen SDK:n avulla. Tapahtumat näkyvät portaalissa viiden minuutin kuluessa.

## <a name="configuration-options"></a>Määritysvaihtoehdot

Seuraavat määritysvalinnat voidaan välittää SDK:lle annetun tiedoston `EIConfig.plist` kautta:

- **ingestionKey**: Käsittelyavain, jonka avulla tapahtumat lähetetään projektiin.
- **autocollectAction**: Totuusarvo, joka ottaa käyttöön toimintotapahtuman automaattisen instrumentoinnin tai poistaa sen käytöstä.
- **autocollectView**: Totuusarvo, joka ottaa käyttöön näyttötapahtuman automaattisen instrumentoinnin tai poistaa sen käytöstä.
- **endpointUrl**: Päätepisteen URL-osoite, johon tapahtumat ohjataan.

## <a name="prerequisites"></a>Edellytykset

- Xcoden versio 9+
- iOS:n versio 8.2+
- Käsittelyavain (katso alla olevat ohjeet sen hankkimiseksi)

## <a name="integrate-the-sdk-into-your-application"></a>Integroiminen SDK sovellukseen

Aloita prosessi valitsemalla käsiteltävä työtila. Valitse sitten iOS-mobiiliympäristö ja lataa SDK.

- Valitse työtila vasemmanpuoleisessa siirtymisruudussa olevan työtilan valitsimen avulla.

- Jos sinulla ei ole vielä työtilaa, valitse **Uusi työtila** ja luo [uusi työtila](create-workspace.md) ohjeiden mukaan.

- Kun työtila on luotu, siirry kohtaan **Hallinta** > **Työtila** ja valitse **Asennusopas**.

## <a name="configure-the-sdk"></a>SDK:n määrittäminen

Kun olet ladannut SDK:n, voit käyttää sitä Xcoden avulla tapahtumien käyttöönotossa ja määrittämisessä. Tapoja tehdä on kaksi

### <a name="option-1-using-cocoapods-recommended"></a>Vaihtoehto 1: CocoaPodsin käyttäminen (suositellaan)
CocoaPods on Swift- ja Objective-C Cocoa -projektien riippuvuuksienhallintaohjelma. Sen käyttö helpottaa sitoutumistietojen SDK:n integrointia iOS:lle. CocoaPodsissa voit myös päivittää sitoutumistiedot SDK:n uusimpaan versioon. Tämän avulla voit käyttää CocoaPodsia integroidaksesi sitoutumistietojen SDK:n Xcode-projektiisi. 

1. Asenna CocoaPods. 

1. Luo projektisi päähakemistoon uusi tiedosto nimeltä Podfile, ja lisää siihen seuraavat lauseet. Korvaa YOUR_TARGET_PROJECT_NAME Xcode-projektin nimellä. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
Edellä olevassa määrityksessä on sekä SDK:n debug- että julkaisuversiot. Valitse, kumpi on paras projektillesi.

1. Asenna tiedosto suorittamalla seuraava komento: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>Vaihtoehto 2: Latauslinkin käyttäminen

1. Lataa [vuorovaikutuksen merkityksellisten tietojen iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) ja aseta tiedosto `EIObjC.xcframework` kansioon `Frameworks`.

1. Jos kansiota `Frameworks` ei ole olemassa, luo kansio projektin kansioon.

## <a name="enable-auto-instrumentation"></a>Automaattisen instrumentoinnin käyttöönotto
 
Voit ottaa automaattisen instrumentoinnin käyttöön helposti, ilman koodausta. Kun projekti suoritetaan, se seuraa automaattisesti tapahtumia `view` ja `action` määritetyn käsittelyavaimen avulla. 

1. Päivitä ja sisällytä annettu tiedosto `EIConfig.plist` projektin hakemistokansioon seuraavia kenttiä varten:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = YES
    - autocollectAction = YES

2. Lisää sitten tiedosto `EIConfig.plist` projektiin Xcoden avulla. 



Jos haluat poistaa käytöstä automaattisen instrumentoinnin, päivitä seuraavat tiedostossa `EIConfig.plist` olevat kentät projektin hakemistokansiossa. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Mukautettujen tapahtumien toteuttaminen

1. Avaa projekti Xcodessa ja siirry **yleisiin** asetuksiin. 
1. Lisää `EIObjC.xcframework` projektiin Ympäristöt, kirjastot ja upotettu sisältö -osassa.

1. Tuo kehyksen otsikkotiedosto AppDelegate.m-sovelluksessa seuraavalla koodikatkelmalla:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Ota käyttöön vuorovaikutuksen merkityksellisten tietojen SDK sovelluksesta didFinishLaunchingWithOptions.
1. Kopioi XML-katkelma **asennusohjeesta**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Seuraa tapahtumaa seuraavasti:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Käyttäjän tietojen määrittäminen tapahtumaa varten

SDK:n avulla voit määrittää käyttäjätiedot, jotka voidaan lähettää jokaisen tapahtuman yhteydessä. Voit määrittää käyttäjän kutsumalla ohjelmointirajapintaa `setUser:(nonnull EIUser *)user` SDK:ssa.

Kun käyttäjän tiedot määritetään tasolla `Analytics`, kaikissa telemetriatiedoissa on nämä tiedot. Jos kuitenkin määrität tapahtuman tason kutsumalla EIEvent-objektin ohjelmointirajapintaa `setUser:(nonnull EIUser *)user`, vain tämä tietty tapahtuma sisältää nämä tiedot.

Tietoluokka `EIUser` sisältää seuraavat NSString-ominaisuudet:

- **localId**: Käyttäjän paikallinen tunnus.
- **authId**: Todennettu käyttäjätunnus.
- **authType**: Käyttäjätunnuksen todennuksessa käytetyn todennuksen tyyppi.
- **name**: Käyttäjän nimi.
- **email**: Käyttäjän sähköpostiosoite.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
