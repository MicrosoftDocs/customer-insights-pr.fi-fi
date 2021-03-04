---
title: Power Automate -yhdistin | Microsoft Docs
description: Luo työnkulkuja Microsoft Power Automatessa Dynamics 365 Customer Insightsista.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268820"
---
# <a name="power-automate-connector-preview"></a>Power Automate -yhdistin (esiversio)

Käynnistä tietyt tapahtumat automaattisesti, kun tiedot muuttuvat ja hallitse monimutkaisempia työnkulkuja suoraan [Power Automatessa](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automaten käynnistimet

Käynnistimien avulla voit luoda pilven työnkulkuja ja automatisoida toistuvia tehtäviä, kuten ilmoituksia tai lisätoimintoja. 

- Käynnistin, kun tietolähteen päivitys epäonnistuu. 
- Käynnistin, kun tietolähteen päivitys onnistuu.
- Käynnistin, kun segmentin raja ylitetään. Käynnistin rajoittuu rajan yläpuolen ylittämiseen.
- Käynnistin, kun segmentin raja ylitetään liiketoiminnan mittarilla. Käynnistin rajoittuu rajan yläpuolen ylittämiseen.
- Käynnistä, kun (tietolähteiden, segmenttien, mittojen,...) täysi päivitys on valmis.
- Käynnistä, kun yhdistämisprosessi (eri yhdistämisvaihtoehdot) on valmis.

[Käynnistimien määrittäminen Power Automatessa](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate -toiminnot
Power Automate -yhdistin määrittää muut toiminnot kuin käytettävissä olevat käynnistimet. Lisätietoja on julkaisussa [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Power Automaten työnkulun luominen

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.

1. Valitse **Power Automate** -ruudussa **Määritä**.

1. Näyttöön avautuu Customer Insightsin yhdistin (esimatselu) Power Automatessa. **Kirjaudu** Power Automateiin.

1. Valitse jokin käytettävissä olevista käynnistimistä ja lisää vaiheita uuteen työnkulkuun. Lisätietoja on kohdassa [Pilven työnkulun luominen Power Automatessa](https://docs.microsoft.com/power-automate/get-started-logic-flow).

Seuraavassa on esimerkkejä työnkulkujen käytöstä: 
- Julkaise viesti Microsoft Teams -kanavassa, jos tietolähteen päivitys epäonnistuu. 
- Lähetä sähköpostia tietojen omistajille, kun segmentin raja-arvo ylittyy.



[!INCLUDE[footer-include](../includes/footer-banner.md)]