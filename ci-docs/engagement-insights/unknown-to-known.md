---
title: Tunnista aiemmin todennettujen kävijöiden verkkotapahtumat tuntemattomista tunnetuiksi
description: Tuntemattomasta tunnetuksi -ominaisuuden avulla voit liittää sivuston tapahtumia aiemmin todennettuihin kävijöihin.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: 75ce776fd5be1c426508ae6f5c239c86bdd3ec39
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230676"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Tunnista aiemmin todennettujen kävijöiden verkkotapahtumat

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

**Tuntemattomasta tunnetuksi** -sitouttamistietojen ominaisuus mahdollistaa verkkosivuston tapahtumien yhdistämisen aiemmin todennettuihin vierailijoihin. Jos ominaisuus on poistettu käytöstä, kävijöitä, jotka on todennettu aikaisemman vierailun aikana ja sitten poistuneet, ei tunnisteta, jos heitä ei todenneta uudelleen palatessaan. 

Henkilö esimerkiksi vieraili verkkosivustolla viime viikolla, kirjautui käyttäjätililleen sivustolla ja selasi tuoteluetteloa. Henkilö palaa seuraavalla viikolla selaamaan lisää tuotteita kirjautumatta tililleen. Sivuston omistaja, joka käyttää **tuntemattomasta tunnetuksi** -ominaisuutta, tietäisi, että sama henkilö on palannut ja mitä hän on tehnyt sivustolla. Tämä mahdollistaa verkkosivustojen toiminnan tarkemman raportoinnin ja analysoinnin.

## <a name="enable-unknown-to-known"></a>Ota käyttöön tuntemattomasta tunnetuksi

Tämän toiminnon käyttöönottamiseen tarvitaan [työtilan järjestelmänvalvojan](user-roles.md) oikeudet. 

1. Siirry sitoutumisen kävijätietoihin **järjestelmänvalvojan** > **työtilassa**. 
2. Valitse **Asetukset**-välilehti.
3. Määritä **Tuntemattomasta tunnetuksi** -osassa tilaksi **Käytössä**.

![Ota käyttöön tuntemattomasta tunnetuksi](media/U2Ktoggle.png "Ota käyttöön tuntemattomasta tunnetuksi")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>JavaScript-koodin lisääminen sivustosi seurantakatkelmaan

Sivusto voi siepata **käyttäjän authId-tunnuksen** seuraavalla JavaScript-esimerkillä käyttämällä [sitoutumisen kävijätietoja verkko-SDK:ssa](advanced-SDK-implementation.md). Jotta **tuntemattomasta tunnetuksi** ominaisuus toimisi, sinun on siepattava authId *ja* otettava userMapping:True käyttöön JavaScript-katkelmassa alla olevan esimerkin mukaan.

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
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
