---
title: Mittareiden tarkasteleminen ja luominen
description: Mittausarvojen luominen, muokkaaminen ja poistaminen.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 97189168e0f5586aad8be8089a1f9e27893c2115c7e805ddaab1efc00e11b860
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034265"
---
# <a name="view-and-create-metrics"></a>Mittareiden tarkasteleminen ja luominen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Mittausarvot auttavat ymmärtämään vierailijoiden käyttäytymisen. Ne kokoavat yhteen tapahtuman ominaisuudet ja mittaavat verkko-ominaisuuksien tilastotietoja ja suorituskykyä.  

Oletetaan, että käytät markkinointikampanjaa sivustossasi. Mittareilla voit seurata kampanjan aikana sivustoosi tulleiden yksilöllisten vierailijoiden tai käyttäjien määrää. Mittaustietojen analysoiminen auttaa ymmärtämään paremmin sivustosi kohdeyleisöä. Yhdistämällä mittausarvot [mukautetun raportin](custom-reports.md) [dimensioihin](dimensions.md) voit mitata käyttäjien käyttäytymistä. Voit esimerkiksi erotella vierailijat uusiin ja palaaviin luokkiin ja määrittää ryhmien kiinnostuksen ja tarkoituksen väliset erot.

## <a name="view-metrics"></a>Mittaustietojen tarkasteleminen

Tapahtumanäkemykset sisältävät yleisesti käytettyjä tapahtuman ominaisuuksien yhdistelmiä järjestelmän mittareina: 

- Kävijät
- Käynnit
- Sivujen katselukerrat
- Napsautukset

Nämä järjestelmäarvot perustuvat perustapahtumien olemassa oleviin tapahtuman ominaisuuksiin.

1. Valitse vasemmassa siirtymisruudussa **Tiedot**. 
1. Valitse **Mittaustiedot**-välilehti, jos haluat nähdä luettelon työtilan kaikista mittaustiedoista. 
   > [!NOTE]
   > Järjestelmän luomat mittaustiedot ovat vain luku -muodossa. Niitä ei voi muuttaa tai poistaa. Voit luoda ja muokata vain mukautettuja mittaustietoja.

## <a name="create-a-metric"></a>Luo mittari

Ympäristön ja työtilan järjestelmänvalvojat voivat luoda mittareita. Tapahtuman ominaisuudet on lähetettävä työtilaan ennen mittausarvon luontia. Voit luoda perustapahtumien lähettämään tapahtuman ominaisuuksiin perustuvia mittareita tai [lähettää mukautettuja tapahtuman ominaisuuksia](advanced-SDK-implementation.md) verkko-SDK:n avulla.

1. Siirry kohtaan **Tieto** > **Mittarit**.
1. Valitse **Uusi mittari**.

   :::image type="content" source="media/new-metric.png" alt-text="Mittarin lisääminen tapahtumaan.":::

1. Valitse muodoksi **Kokonaisluku** tai **Kaksinkertainen** tietotyyppi. Kokonaisluku on kokonainen numero. Kaksoiserotinta varten voi valita yhden ja kolmen desimaalin väliltä.
1. Etsi **Resurssikirjasto**-ruudussa tapahtuman ominaisuus, johon mittausarvo perustuu.
1. Valitse ominaisuuden vierestä **plusmerkki (+)**, jos haluat käyttää sitä kaavassa. Voit luoda vain yhden ominaisuuden perusteella kaavan. 
1. Valitse jokin seuraavista koostetuista funktioista. 

   - Summa: kaikkien arvojen aritmeettinen kokonaissumma 
   - Keskiarvo: kaikkien arvojen keskiarvo
   - Määrä: arvojen kokonaismäärä
   - Erillisten määrä: erillisten arvojen kokonaismäärä

   Mittarin määrityksen jälkeen näet muuttujan viimeisen tunnin toiminnan esikatselun.

1. Valitse **Tallenna**. 
1. Kirjoita mittarin nimi ja valitse **Tallenna**.

Voi kestää enintään minuutin, ennen kuin mittausarvoa voi käyttää [mukautettujen raporttien luomiseen](custom-reports.md).

## <a name="edit-a-metric"></a>Muokkaa mittaria

1. Siirry kohtaan **Tieto** > **Mittarit**.
1. Valitse mittari luettelosta.
1. Mittausarvon määrityksen muuttaminen
1. Valitse **Tallenna**.

## <a name="change-the-name-of-a-metric"></a>Muuta mittarin nimeä

1. Siirry kohtaan **Tieto** > **Mittarit**.
1. Valitse mittausarvolle **Lisää [...]** ja valitse sitten **Muokkaa nimeä**.
1. Nimen muuttaminen. 
1. Valitse **Nimeä uudelleen**.

## <a name="delete-a-metric"></a>Poistetaanko mittari

1. Siirry kohtaan **Tieto** > **Mittarit**.
1. Valitse mittausarvolle **Lisää [...]** ja valitse sitten **Poista**.

   :::image type="content" source="media/delete-metric.png" alt-text="Mittarin poistaminen tapahtumaan.":::

1. Vahvista poisto valitsemalla **Poista**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
