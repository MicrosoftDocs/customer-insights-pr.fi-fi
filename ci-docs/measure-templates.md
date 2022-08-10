---
title: Luo mittareita malleista
description: Määritä mittareita käyttämällä malleja yleisiin käyttötapauksiin.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170769"
---
# <a name="create-measures-from-templates"></a>Luo mittareita malleista

Voit luoda niitä käyttämällä ennalta määritettyjä malleja, joissa on usein käytettyjä [mittareita](measures.md). Mallit perustuvat *Yhdistetty aktiviteetti* -entiteetin yhdistettyihin tietoihin. Varmista siis, että olet määrittänyt [asiakasaktiviteetit](activities.md), ennen kuin luot mittarin mallista.

Mittarimalleja tuetaan vain **yksittäisten asiakkaiden** ympäristöissä. Jos haluat luoda mukautettuja tai yritystenvälisiä mittareita, katso [Mittareiden luontitoiminnon käyttö](measure-builder.md).

Käytettävissä olevat mittarimallit:
- Keskimääräinen tapahtuman arvo (ATV)
- Tapahtuman kokonaisarvo
- Keskimääräinen päivätuotto
- Keskimääräinen kuukausituotto
- Keskimääräinen vuosituotto
- Tapahtumien määrä
- Ansaitut kanta-asiakaspisteet
- Lunastetut kanta-asiakaspisteet
- Kanta-asiakaspisteiden saldo
- Aktiivisen asiakkaan elinkaari
- Kanta-asiakkuuden kesto
- Aika viime ostosta

## <a name="build-a-new-measure-using-a-template"></a>Uuden mittarin luominen mallin avulla

1. Siirry **Mittarit**-kohtaan.

1. Valitse ensin **Uusi** ja sitten **Valitse malli**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Näyttökuva avattavasta valikosta luotaessa uutta mittaria, jonka korostus on mallissa.":::

1. Etsi tarpeisiisi sopiva malli ja valitse **Valitse malli**.

1. Tarkista tarvittavat tiedot ja valitse **Aloitus**, jos kaikki tiedot ovat paikoillaan.

1. Valitse mittarin nimen vieressä oleva **Muokkaa tietoja** -kohta. Anna mittarin nimi. Vaihtoehtoisesti voit lisätä mittariin [tunnisteita](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Muokkaa tietoja -valintaikkuna.":::

1. Valitse **Valmis**.

1. Määritä **Määritä ajanjakso** -osassa aikaväli tiedoille. Jos haluat uuden mittarin kattavan koko tietojoukon, valitse **Koko ajan**. Valitse **Tietty ajanjakso**, jos haluat mittarin keskittyvän tiettyyn ajanjaksoon.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Näyttökuva, jossa näkyy ajanjakso-osa, kun mittaria määritetään mallista.":::

1. Valitse seuraavassa osassa **Lisää tiedot**, jos haluat valita aktiviteetit ja yhdistää vastaavat *Yhdistetty aktiviteetti* -kohteen tiedot.

    1. Vaihe 1/2: Valitse **Aktiviteettityyppi**-kohdassa haluamasi entiteetin tyyppi. Valitse **Aktiviteetit**-kohdassa entiteetit, jotka haluat yhdistää ja sitten **Seuraava**.
    1. Vaihe 2/2: Valitse määrite *Yhdistetty aktiviteetti* -entiteetistä komponentille, jota kaava edellyttää. Esimerkiksi Keskimääräinen tapahtuman arvo on määrite, joka vastaa tapahtuman arvoa. Valitse **Aktiviteetin aikaleima** -kohdassa *Yhdistetty aktiviteetti* -kohteen määrite, joka kuvaa aktiviteetin päivämäärää ja aikaa.
    1. Valitse **Tallenna**.

    Kun tietojen yhdistäminen on onnistunut, voit nähdä tilan **Valmis** ja yhdistettyjen aktiviteettien ja määritteiden nimen.

1. Voit laskea mittarin tulokset valitsemalla **Suorita**. Valitse **Tallenna luonnos**, jos haluat pitää nykyisen määrityksen ja suorittaa mittarin myöhemmin. **Mittarit**-sivu avautuu.

## <a name="next-step"></a>Seuraava vaihe

Voit luoda [asiakassegmentin](segments.md) olemassa olevien mittareiden avulla.

[!INCLUDE [footer-include](includes/footer-banner.md)]
