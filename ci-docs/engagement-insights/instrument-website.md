---
title: Koodin lisääminen verkkosivustolle
description: Tapahtumia tallentavan koodikatkelman lisääminen verkkosivustollesi.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035090"
---
# <a name="install-the-code-snippet-on-a-website"></a>Koodikatkelman asentaminen verkkosivustolle

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tässä artikkelissa kuvataan, miten järjestelmänvalvoja asentaa koodikatkelman verkkosivustolle. Pian sen jälkeen, kun olet lisännyt komentosarjan verkkosivustollesi, alat nähdä työtilassasi tapahtumia. Lisätietoja: [Työtilojen ja ympäristön hallinta](manage-environments-workspaces.md). Jos haluat siepata tapahtumia mobiilisovelluksessa, katso lisätietoja [kehittäjän resurssien yleiskatsauksesta](developer-resources.md).


### <a name="prerequisites"></a>Edellytykset

* Tietojen tallentaminen edellyttää järjestelmänvalvojan käyttöoikeuksia työtilaan.
* Verkkosivustoasi tai projektiasi on isännöitävä verkossa, jotta se voi lähettää aktiviteettitietoja. Palvelin ei hyväksy paikallisesta tiedostosta lähetettyjä tietoja.


## <a name="add-code-to-your-website"></a>Koodin lisääminen verkkosivustolle
1.  Siirry kohtaan **Järjestelmänvalvoja** > **Työtila** ja valitse sitten **Asennusopas**.
1. Kopioi koodikatkelma valitsemalla **Kopioi koodi**. Oletusarvoisesti työtilasi käsittelyavain on upotettu koodikatkelmaan.
:::image type="content" source="media/copy-code.png" alt-text="Koodikatkelmasivun näyttökuva.":::
3. Lisää kopioitu koodikatkelma verkkosivustollesi lähelle <head> tunnistetta ja ennen muita skriptejä tai CSS-tunnisteita.
4.  Julkaise päivitetty verkkosivusto ja odota saapuvan verkkoliikenteen kirjaamista jokunen minuutti.
5.  Voit tarkastella tietojasi valitsemalla työtilan siirtymisruudun työtilanvaihtajasta. Valitse sitten jokin **Löydä**-osan raporteista.

## <a name="configuration-options"></a>Määritysvaihtoehdot

Voit muuttaa koodikatkelman seuraavia määritysvalintoja:

- **ingestionKey**: Käsittelyavain, jota käytetään tapahtumien lähettämiseen työtilaasi. Voit lähettää tapahtumia toiseen työtilaan vaihtamalla käyttöavainta. Käyttöavain on yksilöllinen jokaisessa työtilassa. 
- **autoCapture**: Määrittää, tallennetaanko sivunkatselukerrat ja vuorovaikutukset verkkosivuston kanssa. Siinä on kaksi vaihtoehtoa:
    - **view**: Aseta arvoksi *true*, jos haluat, että sivunkatselukerrat tallennetaan. Sivunkatselukerrat tallennetaan *Katselu*[-tapahtumina](glossary.md#event) eli [perustapahtuman](glossary.md#base-event) muotoina.
    - **click**: Aseta arvoksi *true*, jos haluat, että vierailijoiden vuorovaikutukset verkkosivustolla tallennetaan. Vuorovaikutukset tallennetaan *Toiminto*[-tapahtumina](glossary.md#event) eli [perustapahtuman](glossary.md#base-event) muotoina.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
