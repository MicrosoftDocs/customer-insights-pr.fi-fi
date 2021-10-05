---
title: Koodin lisääminen verkkosivustolle
description: Dynamics 365 Customer Insights -tapahtumia tallentavan koodikatkelman lisääminen verkkosivustollesi.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ad835f762226d62fdb0f544627f2a76ff09a1ffd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558845"
---
# <a name="install-the-web-sdk-on-a-website"></a>Www-SDK:n asentaminen verkkosivustoon

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tässä artikkelissa kuvataan, miten järjestelmänvalvoja asentaa ohjelmistokehitystyökalut (SDK) verkkosivustoon. Työtilassasi näet tapahtumia pian verkkosivustosi instrumentoinnin jälkeen. Lisätietoja: [Työtilojen ja ympäristön hallinta](manage-environments-workspaces.md). Jos haluat siepata tapahtumia mobiilisovelluksessa, katso lisätietoja [kehittäjän resurssien yleiskatsauksesta](developer-resources.md).


### <a name="prerequisites"></a>Edellytykset

* Tietojen tallentaminen edellyttää järjestelmänvalvojan käyttöoikeuksia työtilaan.
* Verkkosivustoasi tai projektiasi on isännöitävä verkossa, jotta se voi lähettää aktiviteettitietoja. Palvelin ei hyväksy paikallisesta tiedostosta lähetettyjä tietoja.


## <a name="add-web-sdk-to-your-website"></a>Lisää www-SDK sivustollesi

Siirry kohtaan **Järjestelmänvalvoja** > **Työtila** ja valitse sitten **Asennusopas**. Www-SDK voidaan asentaa kahdella tavalla. Ensimmäinen on latauslinkin käyttäminen, ja toinen on solmun paketinhallinnan (NPM) paketin asentaminen.

### <a name="option-1-using-the-download-link"></a>Vaihtoehto 1: Latauslinkin käyttäminen

1. Kopioi koodikatkelma valitsemalla **Kopioi koodi**. Oletusarvoisesti työtilasi käsittelyavain on upotettu koodikatkelmaan.
  :::image type="content" source="media/copy-code.png" alt-text="Koodikatkelmasivun näyttökuva.":::

1. Lisää kopioitu koodi verkkosivustoosi lähellä <head> tunnistetta ja ennen muita skriptejä tai CSS-tunnisteita.
1. Julkaise päivitetty verkkosivusto ja odota saapuvan verkkoliikenteen kirjaamista jokunen minuutti.
1. Voit tarkastella tietojasi valitsemalla työtilan siirtymisruudun työtilanvaihtajasta. Valitse sitten jokin **Löydä**-osan raporteista.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Vaihtoehto 2: NPM-paketin käyttäminen (suositellaan JavaScript-pohjaisiin verkkosovelluksiin)

1. Siirry [NPM-verkkosivullemme](https://www.npmjs.com/package/engagementinsights-web) ja asenna ja määritä WWW-SDK NPM-paketti ohjeiden mukaan.
1. Julkaise päivitetty verkkosivusto ja odota saapuvan verkkoliikenteen kirjaamista jokunen minuutti.
1. Voit tarkastella tietojasi valitsemalla työtilan siirtymisruudun työtilanvaihtajasta. Valitse sitten jokin **Löydä**-osan raporteista.

## <a name="configuration-options"></a>Määritysvaihtoehdot

Voit muuttaa koodikatkelman seuraavia määritysvalintoja:

- **ingestionKey**: Käsittelyavain, jota käytetään tapahtumien lähettämiseen työtilaasi. Voit lähettää tapahtumia toiseen työtilaan vaihtamalla käyttöavainta. Käyttöavain on yksilöllinen jokaisessa työtilassa.
- **autoCapture**: Määrittää, tallennetaanko sivunkatselukerrat ja vuorovaikutukset verkkosivuston kanssa. Siinä on kaksi vaihtoehtoa:
    - **view**: Aseta arvoksi *true*, jos haluat, että sivunkatselukerrat tallennetaan. Sivunkatselukerrat tallennetaan *Katselu*[-tapahtumina](glossary.md#event) eli [perustapahtuman](glossary.md#base-event) muotoina.
    - **click**: Aseta arvoksi *true*, jos haluat, että vierailijoiden vuorovaikutukset verkkosivustolla tallennetaan. Vuorovaikutukset tallennetaan *Toiminto*[-tapahtumina](glossary.md#event) eli [perustapahtuman](glossary.md#base-event) muotoina.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
