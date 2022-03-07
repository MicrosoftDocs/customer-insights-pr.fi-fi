---
title: Dimensioiden tarkasteleminen ja luominen
description: Dimensioiden luominen, muokkaaminen ja poistaminen.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b575c5e84197d76f53a722bac60c5af928c917f9671720ede1de38c4a7478be4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033993"
---
# <a name="view-and-create-dimensions"></a>Dimensioiden tarkasteleminen ja luominen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dimensio on tapahtuman määrite, joka voi kuvailla, suodattaa tai ryhmitellä tietoja. Jos käytät verkkosivustossasi markkinointikampanjaa, voit lajitella vierailijat dimensioiden avulla uusien ja palaavien käyttäjien mukaan.  

Tapahtumanäkemykset sisältävät tapahtuman ominaisuuksien kattavat dimensiot. Esimerkkejä:

- Selaimen nimi
- Sivun nimi
- Laitteen malli
- Käyttöjärjestelmä
- Maa tai alue

## <a name="view-dimensions"></a>Näytä dimensiot

Dimensiot perustuvat olemassa oleviin tapahtuman ominaisuuksiin. Kun käytät seurantakoodia hankenäkemyksissä, järjestelmä luo automaattisesti järjestelmän dimensiot.

1. Valitse vasemmassa siirtymisruudussa **Tiedot**. 
1. Valitse **Dimensiot**, jos haluat nähdä luettelon työtilan kaikista dimensioista. 
   > [!NOTE]
   > Järjestelmän luomat dimensiot ovat vain luku -muodossa. Niitä ei voi muokata. Voit luoda ja muokata vain mukautettuja dimensioita.

## <a name="create-a-dimension"></a>Luo dimensio

Järjestelmän luoman dimension lisäksi ympäristön ja työtilan järjestelmänvalvojat voivat luoda mukautettuja dimensioita. Mukautetut dimensiot perustuvat perustapahtumien oletusominaisuuksiin tai voivat käyttää [tapahtuman mukautettuja ominaisuuksia](advanced-SDK-implementation.md).

1. Siirry kohtaan **Tieto** > **Dimensiot**.
1. Valitse **Lisää dimensio**.

   :::image type="content" source="media/add-dimension.png" alt-text="Dimension lisääminen tapahtumaan.":::

1. Valitse **Luo dimensio** -ruudussa ominaisuus, johon dimensio perustuu. Ominaisuusluettelossa näkyvät kaikki työtilan ominaisuudet, joita ei ole liitetty dimensioon.
1. Anna nimi **Näyttönimi**-ruudussa. Voit vaihtoehtoisesti lisätä kuvauksen.
1. Tallenna dimensio valitsemalla **Luo**. Dimension käyttö [mukautetussa raportissa](custom-reports.md) tai [segmentissä](segments.md) voi kestää enintään minuutin. 

## <a name="edit-a-dimension"></a>Muokkaa dimensiota

Voit muuttaa dimension nimeä ja kuvausta.

1. Siirry kohtaan **Tieto** > **Dimensiot**.
1. Valitse poistettava dimensio.
1. Päivitä dimensio **Muokkaa dimensiota** -ruudussa.
1. Valitse **Käytä** tallentaaksesi muutoksesi.

## <a name="delete-a-dimension"></a>Poista dimensio

Voit poistaa vain käyttäjän luomia dimensioita, mutta et voi poistaa järjestelmän dimensioita.

Dimension poistaminen on pysyvää. Poistettua dimensiota käyttävät raportit ja segmentit eivät enää toimi. 

1. Siirry kohtaan **Tieto** > **Dimensiot**.
1. Valitse poistettava dimensio.
1. Valitse **Poista dimensio** **Muokkaa dimensiota** -ruudussa.

   :::image type="content" source="media/delete-dimension.png" alt-text="Dimension poistaminen tapahtumasta.":::

1. Vahvista poisto kirjoittamalla **VAHVISTA POISTO** (kirjoitettuna isolla). 
1. Valitse **Poista**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
