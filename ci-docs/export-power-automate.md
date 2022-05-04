---
title: Power Automate -yhdistin | Microsoft Docs
description: Työnkulkujen luominen Microsoft Power Automatessa Dynamics 365 Customer Insightsista.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 409792bc3f12fca451ef038e3300758bdf9ecf3b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646339"
---
# <a name="power-automate-connector-preview"></a>Power Automate -yhdistin (esiversio)

Käynnistä tietyt tapahtumat automaattisesti, kun tiedot muuttuvat ja hallitse monimutkaisempia työnkulkuja suoraan [Power Automatessa](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Voit tehdä enintään 100 kutsua 60 sekunnissa. Voit kutsua ohjelmointirajapinnan päätepistettä useita kertoja käyttämällä $skip-parametria. [Lisätietoja $skip-parametristä](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Power Automaten käynnistimet

Käynnistimien avulla voit luoda pilven työnkulkuja ja automatisoida toistuvia tehtäviä, kuten ilmoituksia tai lisätoimintoja. 

- Käynnistin, kun tietolähteen päivitys epäonnistuu. 
- Käynnistin, kun tietolähteen päivitys onnistuu.
- Käynnistin, kun segmentin raja ylitetään. Käynnistin rajoittuu rajan yläpuolen ylittämiseen.
- Käynnistin, kun segmentin raja ylitetään liiketoiminnan mittarilla. Vain liiketoimintamittareita, joilla ei ole dimensiota, tuetaan. Käynnistin rajoittuu rajan yläpuolen ylittämiseen.
- Käynnistä, kun kohteen (esimerkiksi tietolähteet, segmentit tai mittarit) täysi päivitys on valmis.
- Käynnistä, kun yhdistämisprosessi (eri yhdistämisvaihtoehdot) on valmis.

[Määritä käynnistimet Power Automatessa.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate -toiminnot

Power Automate -yhdistin määrittää muut toiminnot kuin käytettävissä olevat käynnistimet. Lisätietoja on julkaisussa [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Power Automaten työnkulun luominen

1. Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.

1. Valitse **Power Automate** -ruudussa **Määritä**.

1. Näyttöön avautuu Customer Insightsin yhdistin (esimatselu) Power Automatessa. **Kirjaudu** Power Automateiin.

1. Valitse jokin käytettävissä olevista käynnistimistä ja lisää vaiheita uuteen työnkulkuun. Lisätietoja on kohdassa [Pilven työnkulun luominen Power Automatessa](/power-automate/get-started-logic-flow).

Seuraavassa on esimerkkejä työnkulkujen käytöstä: 
- Julkaise viesti Microsoft Teams -kanavassa, jos tietolähteen päivitys epäonnistuu. 
- Lähetä sähköpostia tietojen omistajille, kun segmentin raja-arvo ylittyy.



[!INCLUDE [footer-include](includes/footer-banner.md)]
