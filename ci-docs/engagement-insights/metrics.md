---
title: Mittareiden tarkasteleminen ja luominen
description: Mittausarvojen luominen, muokkaaminen ja poistaminen.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 79600a14bc7e98dfd066270f19c353fd007e1341
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623718"
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
   > Järjestelmän luomat mittaustiedot ovat vain luku -muodossa. Et voi muokata tai poistaa niitä. Voit luoda ja muokata vain mukautettuja mittaustietoja.

## <a name="create-a-metric"></a>Luo mittari

Ympäristön ja työtilan järjestelmänvalvojat voivat luoda mittareita. Tapahtuman ominaisuudet on lähetettävä työtilaan ennen mittausarvon luontia. Voit luoda perustapahtumien lähettämään tapahtuman ominaisuuksiin perustuvia mittareita tai [lähettää mukautettuja tapahtuman ominaisuuksia](advanced-SDK-implementation.md) verkko-SDK:n avulla.

1. Siirry kohtaan **Tieto** > **Mittarit**.
1. Valitse **Uusi arvo** avataksesi **Resurssikirjaston** ja **Uusi nimetön arvo** -dialogin.

   :::image type="content" source="media/new-metric.png" alt-text="Mittarin lisääminen tapahtumaan.":::

1. Valitse **Uusi nimetön arvo** -dialogissa avattava **Muoto**-luettelo ja valitse **Kokonaisluku**- tai **Kaksinkertainen**-tietotyyppi. Kokonaisluku on kokonainen numero. Kaksinkertaisen osalta voit valita yhden desimaalipaikan tai kolme desimaalipaikkaa.

   :::image type="content" source="media/create-new-metric.png" alt-text="Luo uusi arvo":::
   
5. Etsi **Resurssikirjasto**-ruudussa tapahtuman ominaisuus, johon mittausarvo perustuu.
6. Valitse ominaisuuden vierestä **plusmerkki (+)**, jos haluat käyttää sitä kaavassa. Voit luoda vain yhden ominaisuuden perusteella kaavan. 
7. Valitse jokin seuraavista koostetuista funktioista. 

   - Summa: kaikkien arvojen aritmeettinen kokonaissumma 
   - Keskiarvo: kaikkien arvojen keskiarvo
   - Määrä: arvojen kokonaismäärä
   - Erillisten määrä: erillisten arvojen kokonaismäärä

   Mittarin määrityksen jälkeen näet muuttujan viimeisen tunnin toiminnan esikatselun.

1. Valitse **Tallenna**. 
1. Kirjoita mittarin nimi ja valitse **Tallenna**.

Voi kestää enintään minuutin, ennen kuin mittausarvoa voi käyttää [mukautettujen raporttien luomiseen](custom-reports.md).

## <a name="edit-a-metric"></a>Muokkaa mittaria

Voit muokata vain mukautettuja arvoja.

1. Siirry kohtaan **Tieto** > **Mittarit**.
1. Valitse mittari luettelosta.
1. Mittausarvon määrityksen muuttaminen
1. Valitse **Tallenna**.

## <a name="change-the-name-of-a-metric"></a>Muuta mittarin nimeä

Voit muuttaa vain mukautettujen arvojen nimiä.

1. Siirry kohtaan **Tieto** > **Mittarit**.
1. Valitse mittausarvolle **Lisää [...]** ja valitse sitten **Muokkaa nimeä**.
1. Nimen muuttaminen. 
1. Valitse **Nimeä uudelleen**.

## <a name="delete-a-metric"></a>Poistetaanko mittari

Voit poistaa vain mukautettuja arvoja.

1. Siirry kohtaan **Tieto** > **Mittarit**.
1. Valitse mittausarvolle **Lisää [...]** ja valitse sitten **Poista**.

   :::image type="content" source="media/delete-metric.png" alt-text="Mittarin poistaminen tapahtumaan.":::

1. Vahvista poisto valitsemalla **Poista**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
