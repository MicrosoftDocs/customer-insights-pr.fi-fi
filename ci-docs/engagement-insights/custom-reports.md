---
title: Tietoja mukautetuista raporteista
description: Tutustu raporttien luomiseen ja mukauttamiseen.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: e8cdfc07b67b78febc1d50b3b1fd44ab94448e64
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232144"
---
# <a name="create-and-edit-custom-reports"></a>Mukautettujen raporttien luominen ja muokkaaminen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Voit valmiiden (out-of-box, OOB) raporttien lisäksi luoda mukautetun raportin, jossa on kaavio- ja taulukkotyyppisiä visualisointeja ymmärtääksesi paremmin asiakkaiden käyttäytymistä. Tässä artikkelissa selitetään, miten luodaan raportti tarvitsemillasi tiedoilla käyttäen taulukko- ja kaaviovisualisointeja. Lisätietoja OOB-raporteista on kohdassa [Raporttien tarkasteleminen](view-reports.md).

## <a name="create-a-custom-report"></a>Mukautetun raportin luominen

1. Mukautettujen raporttien luettelo on kohdassa **Analysoi** > **Mukautettu**.

1. Aloita mukautetun raportin luominen valitsemalla **Uusi raportti**.

   :::image type="content" source="media/new-custom-report.png" alt-text="Uudet mukautetut raportit.":::

1. Päätä, minkätyyppisen raportin haluat koota:

    - Valitsemalla komentopalkista **Lisää visualisointi** voit luoda oletusmuotoisen taulukkovisualisoinnin.
    - Voit myös valita pylväs-, palkki-, viiva-, alue-, ympyrä-, rengas- tai taulukkovisualisoinnin **Raporttieditori**-ruudusta.

1. Valitse **Tiedot**-osassa **Visualisointieditori**-ruudussa yksi käytössä olevista vaihtoehdoista (esimerkiksi sivunäytöt) avattavasta **Mittaukset** -valikosta. Voit myös lisätä **dimensioita** (esimerkiksi maan), jotka näkyvät visualisoinnissa. Lisätietoja löytyy kohdista [Tarkastele ja luo mittauksia](metrics.md) ja [Tarkastele ja luo dimensioita](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Valitse raportille arvo.":::

1. Valitse **Rakenne**-osa **Visualisointieditori**-ruudusta lisätäksesi **Otsikkotekstin** ja vaihtaaksesi **Otsikon** käyttöön ja pois käytöstä.  Voit myös vaihtaa visualisoinnin tyypin valitsemalla toisen kaavion, esimerkiksi **ympyräkaavion**.

1. Muuta visualisoinnin kokoa ja sijaintia seuraavasti:
   - Valitse visualisointi ja muuta sen kokoa vetämällä sen kulmaa tai reunaa.
   - Valitse visualisointi ja siirrä se uuteen sijaintiin. Voit muuttaa sijaintia myös nuolinäppäimillä.
1. Voit lisätä visualisoinnin valitsemalla komentopalkista **Lisää visualisointi**.
1. Kun olet lisännyt raporttiin haluamasi visualisoinnit, valitse komentopalkissa **Tallenna**.

1. Anna mukautetulle raportille nimi ja luo se valitsemalla **Tallenna**.
 
## <a name="filter-a-custom-report"></a>Suodata mukautettu raportti

Voit valita aikavälin tai päivämääräalueen mukautetussa raportissa keskittyäksesi arvoon tai ajanjaksoon.

Jos haluat valita aikavälin, valitse raporttinäkymän oikeasta yläkulmasta arvo. Arvot löytyvät raportin avattavasta luettelosta. Voit valita myös vaihtoehdon *Kiinteä päivämääräalue*.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Suodattaminen ajan tai päivämääräalueen mukaan.":::

Useimmissa raporteissa voit valita kohdan **+ Lisää ehto** valitaksesi dimension tai segmentin suodattamaan raportin. Saat lisätietoja kohdasta [Segmenttien tarkasteleminen ja luominen](segments.md).

## <a name="edit-a-custom-report"></a>Mukautetun raportin muokkaaminen

1. Mukautettujen raporttien luettelo on kohdassa **Analysoi** > **Mukautettu**.

1. Valitse mukautettujen raporttien luettelosta **Lisää [...]** 

1. Valitse **Muokkaa nimeä** vaihtaaksesi raportin nimeä.

1. Voit lisätä, poistaa tai siirtää visualisointeja tai muuttaa niiden kokoa valitsemalla raportin nimen ja käyttämällä valintoja **+ Lisää visualisointi** ja **Muokkaa**.

1. Muuta visualisoinnin ominaisuuksia valitsemalla visualisointi, valitsemalla **...** ja sitten **Muokkaa visualisointia**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Mukautettujen raporttien kaavio-ominaisuuksien muokkaaminen.":::

1. Kun raportin muokkaus on valmis, ota muutokset käyttöön valitsemalla **Tallenna**. 

## <a name="delete-a-custom-report"></a>Mukautetun raportin poistaminen

1. Mukautettujen raporttien luettelo on kohdassa **Analysoi** > **Mukautettu**.

1. Valitse mukautettujen raporttien luettelosta **...**

1. Poista raportti valitsemalla **Poista**.

1. Vahvista poisto, jotta raportti poistetaan pysyvästi.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
