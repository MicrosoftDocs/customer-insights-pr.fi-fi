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
ms.openlocfilehash: eeabd889f7b694f8d809894169a3cdc068acc340
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529397"
---
# <a name="use-a-template-to-build-a-measure"></a>Mittarin luominen mallin avulla

Voit luoda niitä käyttämällä ennalta määritettyjä malleja, joissa on usein käytettyjä [mittareita](measures.md). Mallien yksityiskohtaiset kuvaukset ja ohjattu kokemus auttavat mittarien tehokkaassa luomisessa. Mallit perustuvat *Yhdistetty aktiviteetti* -entiteetin yhdistettyihin tietoihin. Varmista siis, että olet määrittänyt [asiakasaktiviteetit](activities.md), ennen kuin luot mittarin mallista.

Jos haluat luoda mukautettuja mittareita, katso [Mittareiden luominen tyhjästä mittarien luontitoiminnon avulla](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Yksittäiset kuluttajat (kuluttajakauppa)](#tab/b2c)

Käytettävissä olevat mittarimallit: 
- Keskimääräinen tapahtuman arvo (ATV)
- Tapahtuman kokonaisarvo
- Keskimääräinen päivätuotto
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

1. Määritä **Määritä ajanjakso** -osassa aikaväli käytettäville tiedoille. Jos haluat uuden mittarin kattavan koko tietojoukon, valitse **Koko ajan**. Valitse **Tietty ajanjakso**, jos haluat mittarin keskittyvän tiettyyn ajanjaksoon.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Näyttökuva, jossa näkyy ajanjakso-osa, kun mittaria määritetään mallista.":::

1. Valitse seuraavassa osassa **Lisää tiedot**, jos haluat valita aktiviteetit ja yhdistää vastaavat *Yhdistetty aktiviteetti* -kohteen tiedot.

    1. Vaihe 1/2: Valitse **Aktiviteettityyppi**-kohdassa haluamasi entiteetin tyyppi. Valitse **Aktiviteetit**-kohdassa entiteetit, jotka haluat yhdistää.
    1. Vaihe 2/2: Valitse määrite *Yhdistetty aktiviteetti* -entiteetistä komponentille, jota kaava edellyttää. Esimerkiksi Keskimääräinen tapahtuman arvo on määrite, joka vastaa tapahtuman arvoa. Valitse **Aktiviteetin aikaleima** -kohdassa Yhdistetty aktiviteetti -kohteen määrite, joka kuvaa aktiviteetin päivämäärää ja aikaa.
   
1. Kun tietojen yhdistäminen on onnistunut, voit nähdä tilan **Valmis** ja yhdistettyjen aktiviteettien ja määritteiden nimen.

1. Nyt voit laskea mittarin tulokset valitsemalla **Suorita**. Jos haluat tarkentaa sitä myöhemmin, valitse **Tallenna luonnos**.

# <a name="business-accounts-b-to-b"></a>[Yritystilit (yritysten väliset)](#tab/b2b)

Tämä ominaisuus on käytettävissä vain niissä ympäristöissä luoduille yksiköille, joissa yksittäiset asiakkaat ovat ensisijainen kohdeyleisö.

---
