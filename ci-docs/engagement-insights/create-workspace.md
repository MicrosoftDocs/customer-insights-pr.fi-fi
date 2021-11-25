---
title: Luo uusi työtila
description: Työtilan tarkoitus ja uuden työtilan luominen.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1f8922703af506974c8b5b24086b61f05a83609d
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673439"
---
# <a name="create-a-new-workspace-and-add-members"></a>Uuden työtilan luominen ja jäsenten lisääminen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Työtilassa voit tarkastella käyttäjäaktiviteetteja reaaliaikaisesti, jotta saat paremman kuvan kohderyhmästäsi. Siellä voit tallentaa ja hallita tapahtumia ja raportteja.

Kun luot työtilan, voit valita, millaisiin tietoihin haluat keskittyä. Voit milloin tahansa lisätä muita käyttäjiä tai jäseniä olemassa olevaan työtilaan. 

## <a name="create-a-new-workspace"></a>Luo uusi työtila

Työtilan luontiprosessiin kuuluu *ympäristön* määrittäminen järjestelemään työtilasi. Ympäristö on tila, joka voi sisältää yhden tai useamman työtilan. Ympäristön avulla voit hallita työtilojasi ja yhteyksiäsi kohdeyleisötietojen ominaisuuteen.

1. Valitse työtilanvaihtajasta **+Uusi**.

   :::image type="content" source="media/new-workspace.png" alt-text="Customer Insights -sivu, jolla on kuvaselite siirtymisruudun ja kuvauksen päällä.":::

1. Syötä **Työtila**-ruudussa **Työtilan nimi**.

   :::image type="content" source="media/workspace-name.png" alt-text="Kirjoita työtilan nimi.":::

1. Valitse ympäristön tyyppi (verkko tai mobiili), jota haluat mitata.

1. Valitse **Näytä lisäasetukset**, jotta voit ottaa käyttöön ja tai poistaa käytöstä nämä valinnaiset asetukset:

   - Vaihda **Tuntemattomasta tunnettuun** arvoon "käytössä", jotta voit liittää verkkotaphtumia aiemmin todennettuihin käyttäjiin. Lisätietoja on kohdassa [Todennettujen vierailijoiden verkkotapahtumien tunnistaminen](unknown-to-known.md)
   - Vaihda **Suodata bottiliikenne** arvoon "käytössä", jotta voit poistaa tämän työtilan bottiverkkoliikenteen. 

1. Valitse **Valmis**, kun olet valmis. 

1. Asenna koodikatkelma, jotta voit alkaa vastaanottaa tietoja ja valitse sitten **Valmis** luodaksesi työtilan. Lisätietoja on kohdassa [Kehittäjän resurssien yleiskatsaus](developer-resources.md).

> [!NOTE]
> Voit nyt lisätä jäseniä ja delegoida heille käyttöoikeustasoja **Rooli**-luettelosta. Lisätietoja: [Roolit ja oikeudet](user-roles.md). 

Lisätietoja: [Ympäristöjen ja työtilojen hallinta](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
