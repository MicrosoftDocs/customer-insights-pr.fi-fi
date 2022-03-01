---
title: Kehittyneet SDK:n verkkosovelluksen skenaariot
description: Edistyneitä skenaarioita, jotka kannattaa ottaa huomioon, kun verkkosivustoon lisätään SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036324"
---
# <a name="advanced-web-sdk-instrumentation"></a>Edistynyt SDK:n verkkosovelluksen käyttö

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tässä artikkelissa esitellään edistyneitä skenaarioita, jotka kannattaa ottaa huomioon, kun [lisäät verkkosivustollesi](instrument-website.md) Dynamics 365 Customer Insightsin vuorovaikutuksen merkityksellisten tietojen ominaisuuden SDK:n.

## <a name="setting-user-details-for-your-event"></a>Tapahtuman käyttäjätietojen määritys

SDK:n avulla voit määrittää käyttäjätiedot, jotka voidaan lähettää jokaisen tapahtuman yhteydessä. Voit määrittää käyttäjätiedot `user`-ominaisuudessa (tältä ominaisuudelta odotettu tieto on `IUser`-objekti), joka on samankaltainen kuin ominaisuudet `src`, `name` ja `cfg` koodikatkelman määrityksessä.

`IUser`-objekti sisältää seuraavat merkkijono-ominaisuudet:

- **localId**: Käyttäjän paikallinen tunnus.
- **authId**: Todennettu käyttäjätunnus.
- **authType**: Käyttäjätunnuksen todennuksessa käytetyn todennuksen tyyppi.
- **name**: Käyttäjän nimi.
- **email**: Käyttäjän sähköpostiosoite.
    
Seuraavassa esimerkissä on käyttäjätietoja lähettävä koodikatkelma. Jos funktiossa on *-merkintä, korvaa se omalla toteutuksellasi kyseisten arvojen kutsumisesta:  

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Voit määrittää käyttäjätietoja myös kutsumalla ohjelmointirajapintaa `setUser(user: IUser)` SDK:ssa. Ohjelmointirajapinnan `setUser API` kutsumisen jälkeen lähetetyt telemetriatiedot sisältävät käyttäjätiedot.

## <a name="adding-custom-properties-for-each-event"></a>Mukautettujen ominaisuuksien lisääminen kuhunkin tapahtumaan

SDK:n avulla voit määrittää mukautettuja ominaisuuksia, jotka voidaan lähettää jokaisen tapahtuman yhteydessä. Voit määrittää mukautetut ominaisuudet avain-arvo-pareja sisältäviksi objekteiksi (arvo voi olla tyyppiä `string | number | boolean`). Objektin voi lisätä ominaisuuteen `props`, joka on samankaltainen kuin ominaisuudet `src`, `name` ja `cfg` koodikatkelman määrityksessä. 

Seuraavassa esimerkissä on mukautettuja ominaisuuksia lähettävä koodikatkelma.

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Voit määrittää mukautettuja ominaisuuksia myös yksitellen kutsumalla ohjelmointirajapintaa `setProperty(name: string, value: string | number | boolean)` SDK:ssa.

## <a name="sending-custom-events"></a>Mukautettujen tapahtumien lähettäminen

SDK:n avulla voit lähettää mukautettuja tapahtumia. Tapahtuman mukana lähetettävälle tapahtumalle ja sen ominaisuuksille on määritettävä nimi.

Seuraavassa esimerkissä on mukautettua tapahtumaa seuraava koodikatkelma. "NAME" on koodikatkelman määrityksen `name`-avaimen arvo. Se on myös muuttujan nimi ikkunaobjektissa, johon SDK ladataan.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]