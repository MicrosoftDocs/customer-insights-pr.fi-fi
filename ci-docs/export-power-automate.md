---
title: Power Automate -yhdistin (esiversio) | Microsoft Docs
description: Työnkulkujen luominen Microsoft Power Automatessa Dynamics 365 Customer Insightsista.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196114"
---
# <a name="power-automate-connector-preview"></a>Power Automate -yhdistin (esiversio)

Käynnistä tietyt tapahtumat automaattisesti, kun tiedot muuttuvat ja hallitse monimutkaisempia työnkulkuja suoraan [Microsoft Power Automatessa](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään 100 kutsua 60 sekunnissa. Voit kutsua ohjelmointirajapinnan päätepistettä useita kertoja käyttämällä [$skip-parametria](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Power Automaten käynnistimet

Käynnistimien avulla voit luoda pilven työnkulkuja ja automatisoida toistuvia tehtäviä, kuten ilmoituksia tai lisätoimintoja. Käytä käynnistintä, kun

- Tietolähteen päivittäminen ei onnistu.
- Tietolähteen päivittäminen onnistuu.
- Kun segmentin raja ylitetään. Käynnistin rajoittuu rajan yläpuolen ylittämiseen.
- Kun segmentin raja ylitetään liiketoiminnan mittarilla. Vain liiketoimintamittareita, joilla ei ole dimensiota, tuetaan. Käynnistin rajoittuu rajan yläpuolen ylittämiseen.
- Täydellinen ajoitettu päivitys on valmis. Tämä käynnistin ei toimi manuaalisesti aloitettujen päivitysten yhteydessä.
- Yhdistämisprosessin päivittäminen on päättynyt.

[Määritä käynnistimet Power Automatessa.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate -toiminnot

Power Automate -yhdistin määrittää muut toiminnot kuin käytettävissä olevat käynnistimet. Lisätietoja on julkaisussa [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Power Automaten työnkulun luominen

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Power Automate** -ruudussa **Määritä**.

1. Näyttöön avautuu Customer Insightsin yhdistin (esikatselu) Power Automatessa. **Kirjaudu** Power Automateiin.

1. Valitse jokin käytettävissä olevista käynnistimistä ja lisää vaiheita uuteen työnkulkuun. Lisätietoja on kohdassa [Pilven työnkulun luominen Power Automatessa](/power-automate/get-started-logic-flow).

Seuraavassa on esimerkkejä työnkulkujen käytöstä: 
- Julkaise viesti Microsoft Teams -kanavassa, jos tietolähteen päivitys epäonnistuu. 
- Lähetä sähköpostia tietojen omistajille, kun segmentin raja-arvo ylittyy.

[!INCLUDE [footer-include](includes/footer-banner.md)]
