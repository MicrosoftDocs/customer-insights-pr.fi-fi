---
title: Käyttäytymistietojen (kuratoitujen dimensioiden) jakaminen demografisten dimensioiden avulla
description: Käytä yhtenäisiä profiilin kuratoituja ulottuvuuksia ottaaksesi käyttäjäryhmätilastoja käyttöön asiakasprofiilin ominaisuuksissa.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 95395e09bc0ba5ba93138957c62105f31c709e91
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8233043"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Käyttäytymistietojen jakaminen demografisten dimensioiden avulla

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Käyttämällä yhtenäisiä profiilin demografisia dimensioita käyttäjät voivat käyttää käyttäjäryhmätietoja profiilin ominaisuuksista. Voit sitten käyttää näitä ominaisuuksia vuorovaikutteisissa käyttäytymistietojen analyyseissä, mukaan lukien verkkosivustosi tai mobiilisovelluksesi sitoutumistietojen keräämät tiedot.

>[!NOTE]
> Tapahtumanäkemykset sisältävät tapahtuman ominaisuuksien kattavat dimensiot. Lisätietoja: [Dimensioiden tarkasteleminen ja luominen](dimensions.md)

## <a name="prerequisite"></a>Edellytykset

- Sitoutumistilastoympäristö, jossa sinulla on asiakasprofiilitiedot linkitettyinä yleisötilastoympäristöön, jossa asiakasprofiilit luodaan. Lisätietoja: [Linkin luominen kohdeyleisön ja sitoutumistietojen välille](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Kun olet luonut linkin kohdeyleisön ja sitoutumistietoympäristöjen välille, haluat ehkä vain asiakasprofiilin ominaisuuksiin liittyvät tiedot, jotka voivat olla hyödyllisiä sitoutumistietojen dimensioiksi. Lisätietoja on kohdassa [Ota käyttöön käyttäjäryhmän yhdistetyt profiilit -määritteet ja -segmentit](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Uuden mukautetun raportin luominen

1. Valitse vasemmanpuoleisesta ruudusta **Mukautettu** > **Uusi raportti** ja valitse sitten haluamasi mittausarvo. (Tässä esimerkissä valitsimme **Sivunäkymät tunnin mukaan**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Valitse mittari.":::

2. Valitse Visualisointi-editorissa **Dimensiot** ja valitse sitten **Demografiatiedot** avattavasta **Dimension tyyppi** -valikosta.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Valitse demografiatiedot.":::

3. Valitse **Signal.Customer.*xxx***-dimensio. (Tässä esimerkissä näkyy Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Valitse dimensio.":::
  
## <a name="limitations"></a>Rajoitukset

Tällä hetkellä voit käyttää demografisia dimensioita vain käyttäytymistietojen jakamiseen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
