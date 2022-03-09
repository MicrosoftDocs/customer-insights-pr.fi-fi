---
title: Kehittyneet SDK:n verkkosovelluksen skenaariot
description: Edistyneitä skenaarioita, jotka kannattaa ottaa huomioon, kun verkkosivustoon lisätään SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a083d8215f295af0884257a016b62b8c7e4ab2c7
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227194"
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

Seuraavassa esimerkissä on käyttäjätietoja lähettävä koodikatkelma. Jos toimintoa edeltää tähtisymboli *, korvaa toiminto mukautetulla toteutuksella:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
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

Voit määrittää käyttäjätiedot myös kutsumalla `setUser(user: IUser)`-ohjelmointirajapintaa. Ohjelmointirajapinnan `setUser` kutsumisen jälkeen lähetetyt telemetriatiedot sisältävät käyttäjätiedot.

## <a name="adding-custom-properties-for-each-event"></a>Mukautettujen ominaisuuksien lisääminen kuhunkin tapahtumaan

SDK:n avulla voit määrittää mukautettuja ominaisuuksia, jotka voidaan lähettää jokaisen tapahtuman yhteydessä. Voit määrittää mukautetut ominaisuudet avain-arvo-pareja sisältäviksi objekteiksi (arvo voi olla tyyppiä `string | number | boolean`). Voit lisätä objektin ominaisuuteen, jonka nimi on `props`, ja joka on samanlainen kuin `src`, `name` ja `cfg` koodikatkelmamäärityksessä.

Seuraavassa esimerkissä on mukautettuja ominaisuuksia lähettävä koodikatkelma.

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
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

Voit määrittää mukautetut ominaisuudet myös kutsumalla `setProperty(name: string, value: string | number | boolean)`-ohjelmointirajapintaa.

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
