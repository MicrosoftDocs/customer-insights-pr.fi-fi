---
title: Tietojen yhdistämisen tarkistaminen
description: Tarkista tietojen yhdistämisvaiheet, luo unified customer profiles -profiilit ja tarkista tulokset
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 0f7b2e9af65796c4d304dbd9893a21617e847620
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844082"
---
# <a name="review-data-unification"></a>Tietojen yhdistämisen tarkistaminen

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Tässä yhdistämisprosessin viimeisessä vaiheessa näkyy yhteenveto prosessin osavaiheista ja mahdollisuus tehdä muutoksia, ennen kuin luot yhtenäisen profiilin.

:::image type="content" source="media/m3_review.png" alt-text="Kuvakaappaus kohdasta Tarkista ja luo asiakasprofiileja.":::

## <a name="review-the-data-unification-steps"></a>Tietojen yhdistämisvaiheiden tarkasteleminen

1. Tarkista ja tee tarvittavat muutokset valitsemalla tietojen yhdistämisvaiheissa **Muokkaa**.

1. Jos valintasi ovat haluamasi, valitse **Luo asiakasprofiilit**. **Yhtenäistä**-sivu tulee näkyviin, kun unified customer profile luodaan. Kaikissa muissa ruuduissa paitsi **Lähdekentät** tilana on **Jonossa** tai **Päivittää**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Näyttökuva yhtenäistämissivulla, jossa ruutujen tilana on Jonossa tai päivittää":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Yhdistäminen-algoritmin valmistuminen kestää jonkin aikaa, eikä määritystä voi muuttaa, ennen kuin se on valmis. Kun yhdistäminen on valmis, unified customer profile -entiteetti, jonka nimi on *Asiakas*, näkyy **Entiteetit**-sivulla **Profiilit**-osassa. Ensimmäinen onnistunut yhdistäminen luo yhtenäisen *Asiakas*-entiteetin. Kaikki seuraavat suoritukset laajentavat kyseistä entiteettiä.

## <a name="review-the-results-of-data-unification"></a>Tietojen yhdistämisen tulosten tarkasteleminen

Yhdistämisen jälkeen **Tiedot** > **Yhdistä** -sivu näyttää unified customer profiles -profiilien määrän. Jokaisen yhdistäminenprosessin vaiheen tulokset näkyvät kussakin ruudussa. Esimerkiksi **Lähdekentät** näyttää yhdistettyjen määritteiden (kenttien) määrän ja **Tietueiden kaksoiskappaleet** näyttää löydettyjen tietueiden kaksoiskappaleiden määrän.

:::image type="content" source="media/m3_unified.png" alt-text="Näyttökuva Tietojen yhtenäistäminen -sivusta, kun tiedot on yhdistetty.":::

> [!TIP]
> **Vastaavat ehdot** -ruutu näkyy vain, jos valittuna on useita entiteettejä.

Suosittelemme, että tarkistat tulokset, erityisesti vastaavuussääntöjen [laadun ja muokkaat](data-unification-update.md#manage-match-rules) niitä tarvittaessa.

Tee tarvittaessa [muutoksia yhdistämisasetuksiin](data-unification-update.md) ja suorita yhtenäinen profiili uudelleen.

## <a name="next-step"></a>Seuraava vaihe

Määrittämällä [aktiviteetteja](activities.md), [rikastuksia](enrichment-hub.md), [suhteita](relationships.md) tai [mittareita](measures.md) saat enemmän tietoja asiakkaistasi.

[!INCLUDE[footer-include](includes/footer-banner.md)]
