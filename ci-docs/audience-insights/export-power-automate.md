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
ms.openlocfilehash: dc9bbe22b7f10cf92f06cae18fbece9808b87dce
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226710"
---
# <a name="power-automate-connector-preview"></a>Power Automate -yhdistin (esiversio)

Käynnistä tietyt tapahtumat automaattisesti, kun tiedot muuttuvat ja hallitse monimutkaisempia työnkulkuja suoraan [Power Automatessa](https://flow.microsoft.com/).

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

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.

1. Valitse **Power Automate** -ruudussa **Määritä**.

1. Näyttöön avautuu Customer Insightsin yhdistin (esimatselu) Power Automatessa. **Kirjaudu** Power Automateiin.

1. Valitse jokin käytettävissä olevista käynnistimistä ja lisää vaiheita uuteen työnkulkuun. Lisätietoja on kohdassa [Pilven työnkulun luominen Power Automatessa](/power-automate/get-started-logic-flow).

Seuraavassa on esimerkkejä työnkulkujen käytöstä: 
- Julkaise viesti Microsoft Teams -kanavassa, jos tietolähteen päivitys epäonnistuu. 
- Lähetä sähköpostia tietojen omistajille, kun segmentin raja-arvo ylittyy.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
