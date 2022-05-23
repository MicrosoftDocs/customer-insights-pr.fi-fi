---
title: Tietojen yhdistämisen tarkistaminen
description: Tarkista tietojen yhdistämisvaiheet, luo unified customer profiles -profiilit ja tarkista tulokset
ms.date: 05/04/2022
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
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741658"
---
# <a name="review-data-unification"></a>Tietojen yhdistämisen tarkistaminen

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Tässä yhdistämisprosessin viimeisessä vaiheessa näkyy yhteenveto prosessin osavaiheista ja mahdollisuus tehdä muutoksia, ennen kuin luot yhtenäisen profiilin.

:::image type="content" source="media/m3_review.png" alt-text="Kuvakaappaus kohdasta Tarkista ja luo asiakasprofiileja.":::

## <a name="review-the-data-unification-steps"></a>Tietojen yhdistämisvaiheiden tarkasteleminen

1. Tarkista ja tee tarvittavat muutokset valitsemalla tietojen yhdistämisvaiheissa **Muokkaa**.

1. Jos valintasi ovat haluamasi, valitse **Luo asiakasprofiilit**. **Yhtenäistä**-sivu tulee näkyviin, kun unified customer profile luodaan. Yhdistäminen-algoritmin valmistuminen kestää jonkin aikaa, eikä määritystä voi muuttaa, ennen kuin se on valmis.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

Kun yhdistäminen on valmis, unified customer profile -entiteetti, jonka nimi on *Asiakas*, näkyy **Entiteetit**-sivulla **Profiilit**-osassa. Ensimmäinen onnistunut yhdistäminen luo yhtenäisen *Asiakas*-entiteetin. Kaikki seuraavat suoritukset laajentavat kyseistä entiteettiä.

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
