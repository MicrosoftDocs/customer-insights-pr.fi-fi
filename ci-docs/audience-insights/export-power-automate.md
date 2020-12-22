---
title: Power Automate -yhdistin | Microsoft Docs
description: Luo työnkulkuja Microsoft Power Automatessa Dynamics 365 Customer Insightsista.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405579"
---
# <a name="power-automate-connector-preview"></a>Power Automate -yhdistin (esiversio)

Käynnistä tietyt tapahtumat automaattisesti, kun tiedot muuttuvat ja hallitse monimutkaisempia työnkulkuja suoraan [Power Automatessa](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automaten käynnistimet

Voit käyttää erilaisia käynnistimiä, joiden avulla voit luoda työnkulkuja toistuvien tehtävien, kuten ilmoitusten tai edistyneiden toimintojen, automatisoimiseksi. 

- Käynnistin, kun tietolähteen päivitys epäonnistuu. 
- Käynnistin, kun tietolähteen päivitys onnistuu.
- Käynnistin, kun segmentin raja ylitetään. Käynnistin rajoittuu rajan yläpuolen ylittämiseen.
- Käynnistin, kun segmentin raja ylitetään liiketoiminnan mittarilla. Käynnistin rajoittuu rajan yläpuolen ylittämiseen.
- Käynnistä, kun (tietolähteiden, segmenttien, mittojen,...) täysi päivitys on valmis.
- Käynnistä, kun yhdistämisprosessi (eri yhdistämisvaihtoehdot) on valmis.

[Käynnistimien määrittäminen Power Automatessa](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate -toiminnot
Power Automate -yhdistin määrittää muut toiminnot kuin käytettävissä olevat käynnistimet. Lisätietoja on julkaisussa [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Power Automaten työnkulun luominen käyttäjäryhmän merkityksellisissä tiedoissa

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Järjestelmä**.

1. Valitse **Järjestelmä**-sivulla **Tila**-välilehti.

1. Valitse **Tietolähteet**-kohdassa **Työnkulut** ja valitse sitten avattavasta luettelosta **Luo työnkulku**.
   > [!div class="mx-imgBorder"]
   > ![Power Automate -yhdistin, jossa näkyy Luo työnkulku -toiminto](media/power-automate-connector-create-flow.png "Power Automate -yhdistin, jossa näkyy Luo työnkulku -toiminto")

1. Luo haluamasi työnkulku Power Automatessa valitsemalla jokin käytettävissä olevista käynnistimistä. Jos olet luomassa ensimmäistä työnkulkua, Power Automate -yhdistin on ensin todennettava.
