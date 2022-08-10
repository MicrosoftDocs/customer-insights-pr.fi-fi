---
title: Luo yksinkertaisia segmenttejä pikasegmenteillä
description: Luo yksinkertaisia segmenttejä ja ryhmittele ne eri määritteiden perusteella.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171131"
---
# <a name="create-simple-segments-with-quick-segments"></a>Luo yksinkertaisia segmenttejä pikasegmenteillä

Pikasegmenttien avulla voidaan nopeasti luoda yksinkertaisia segmenttejä yhdellä operaattorilla, jotta merkitykselliset tiedot saadaan nopeammin. Pikasegmenttejä tuetaan vain **yksittäisten asiakkaiden** ympäristöissä.

## <a name="create-a-new-segment-with-quick-segments"></a>Luo uusi segmentti pikasegmenteillä

1. Valitse **Segmentit**.

1. Valitse **Uusi** > **Luo**.
   - Valitse **Profiilit**-vaihtoehto, jos haluat muodostaa segmentin, joka perustuu *yhdistettyyn asiakas* entiteettiin.
   - Valitse **Mittarit**-vaihtoehto rakentaaksesi segmentin aiemmin luotujen mittareiden perusteella.
   - Valitse **Analytiikka**-asetus, jos haluat luoda segmentin, joka on luotu käyttämällä joko **Ennusteet**-tai **Mukautetut mallit** -ominaisuuden avulla luotuja tuloskohteita.

1. Valitse **Uusi pikasegmentti** -valintaikkunasta määrite avattavasta **Kenttä**-valikosta. Järjestelmä antaa valinnan mukaan erilaisia arvoja.
   - Luokkakentille näytetään 10 parasta asiakasmäärää. Valitse **Arvo** ja valitse sitten **Tarkista**.
   - Jos määrite on numeerinen, järjestelmä näyttää, mikä määrite kuuluu mihinkin asiakasprosenttipisteeseen. Valitse **Operaattori** ja **Arvo** ja valitse sitten **Tarkista**.

1. Järjestelmä näyttää **arvioidun segmentin koon**. Voit määrittää, luodaanko määritetty segmentti, tai palata valitsemaan toisen kentän.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nopean segmentin nimi ja arvioi.":::

1. Anna segmentille **nimi** ja **tulosentiteetin nimi**. Vaihtoehtoisesti voit lisätä [tunnisteita](work-with-tags-columns.md#manage-tags).

1. Luo segmentti valitsemalla **Tallenna**. **Segmentit**-sivu avautuu.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Seuraavat vaiheet

[Vie segmentti](export-destinations.md) ja tutustu [asiakaskorttien integrointiin](customer-card-add-in.md), jotta voit käyttää segmenttejä muissa sovelluksissa.

[!INCLUDE [footer-include](includes/footer-banner.md)]
