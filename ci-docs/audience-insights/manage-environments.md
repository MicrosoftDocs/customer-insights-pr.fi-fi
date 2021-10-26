---
title: Luo ja hallitse ympäristöjä
description: Tietoja palveluun rekisteröitymisestä ja ympäristöjen hallinnasta.
ms.date: 10/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: ce2fdd435a81bb04148057554c5958e3ab59f125
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645122"
---
# <a name="manage-environments"></a>Ympäristöjen hallinta

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Ympäristöjen vaihtaminen

Voit vaihtaa ympäristöä valitsemalla sivun oikeassa yläkulmassa **Ympäristöt**.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Näyttökuva ohjausobjektista, jonka avulla voit vaihtaa ympäristöä.":::

Järjestelmänvalvojat voivat [Luoda](create-environment.md) ja hallita ympäristöjä.

## <a name="edit-an-existing-environment"></a>Aiemmin luodun ympäristön muokkaaminen

Voit muokata joitakin aiemmin luotujen ympäristöjen tietoja.

1.  Valitse sovelluksen otsikossa **Ympäristö**-valitsin.

2.  Valitse **Muokkaa**-kuvake.

3. Voit päivittää ympäristön asetuksia **Muokkaa ympäristöä** -ruudussa.

Lisätietoja ympäristön asetuksista on kohdassa [Uuden ympäristön luominen](create-environment.md).

## <a name="copy-the-environment-configuration"></a>Kopioi ympäristön määritys

Kun luot uuden ympäristön, voit kopioida määrityksen aiemmin luodusta ympäristöstä. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Näyttökuva ympäristöasetusten asetusvaihtoehdoista.":::

Näkyviin tulee luettelo kaikista organisaation käytettävissä olevista ympäristöistä, joista voit kopioida tietoja.

Seuraavat määritysasetukset kopioidaan:

- Käsitellyt/tuodut tietolähteet
- Tietojen yhtenäistämisen (yhdistäminen, vastaavuus) määritys
- Segmentit
- Mittarit
- Suhteet
- Aktiviteetit
- Haku- ja suodatusindeksi
- Vientikohteet
- Ajoitettu päivitys
- Rikastukset
- Mallien hallinta
- Roolimääritykset

Seuraavia tietoja *ei* kopioida:

- Asiakasprofiilit.
- Tietolähteen tunnistetiedot. Sinun on annettava kunkin tietolähteen tunnistetiedot ja päivitettävä tietolähteet manuaalisesti.
- Common Data Model -kansion ja Dataversen hallitun Data Laken tietolähteet. Nämä tietolähteet on luotava manuaalisesti samalla nimellä kuin lähdeympäristössä.

Kun kopioit ympäristön, näkyviin tulee vahvistussanoma siitä, että uusi ympäristö on luotu. Valitse **Siirry tietolähteisiin**, kun haluat nähdä tietolähteiden luettelon.

Kaikkien tietolähteiden tilana näkyy **Vaatii tunnistetietoja**. Muokkaa tietolähteitä ja päivitä ne syöttämällä tunnistetiedot.

:::image type="content" source="media/data-sources-copied.png" alt-text="Luettelo kopioiduista tietolähteistä, jotka vaativat todennusta.":::

Kun olet päivittänyt tietolähteet, siirry kohtaan **Tiedot** > **Yhtenäistäminen**. Siellä ovat lähdeympäristön asetukset. Voit muokata niitä tarpeen mukaan tai valita **Suorita**, jolloin tietojen yhtenäistämisprosessi alkaa ja yhtenäistetty asiakasentiteetti luodaan.

Kun tietojen yhtenäistäminen on valmis, päivitä myös kohdat **Mittarit** ja **Segmentit** siirtymällä niihin.

## <a name="reset-an-existing-environment"></a>Aiemmin luodun ympäristön palauttaminen

Järjestelmänvalvoja voi palauttaa ympäristön tyhjään tilaan, jos haluat poistaa kaikki määritykset ja käsitellyt tiedot.

1.  Valitse sovelluksen otsikossa **Ympäristö**-valitsin. 

2.  Valitse ympäristö, jonka haluat palauttaa, ja valitse sitten kolme pistettä (**...**). 

3. Valitse **Palauta**-vaihtoehto. 

4.  Vahvista poisto antamalla ympäristön nimi ja valitsemalla **Palauta**.

## <a name="delete-an-existing-environment"></a>Olemassa olevan ympäristön poistaminen

Järjestelmänvalvoja voi poistaa myös hallitsemasi ympäristön.

1.  Valitse sovelluksen otsikossa **Ympäristö**-valitsin.

2.  Valitse ympäristö, jonka haluat palauttaa, ja valitse sitten kolme pistettä (**...**). 

3. Valitse **Poista**-vaihtoehto. 

4.  Vahvista poisto antamalla ympäristön nimi ja valitsemalla **Poista**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
