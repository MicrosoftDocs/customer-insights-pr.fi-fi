---
title: Tapahtumien luominen ja muokkaaminen
description: Tapahtumien luominen ja muokkaaminen.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: dbafa2231daa82c34ee2ec8292111575e95af675
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228199"
---
# <a name="create-and-modify-events"></a>Tapahtumien luominen ja muokkaaminen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tapahtuma on käyttäjän käyttäytymistä edustavaa tietoa, kuten aktiviteetti verkkosivustolla.

- *Perustason* tapahtuma kirjaa ylös, milloin käyttäjä tarkastelee sivua (katselutapahtuma) tai on vuorovaikutuksessa sen sisällön kanssa (toimintotapahtuma).
- *Tarkennettu* tapahtuma on perustapahtuman virtuaalinen näkymä. Voit määrittää tarkennettuja tapahtumia poistamalla ja lisäämällä ominaisuuksia tai suodattamalla tapahtumia ominaisuusarvojen perusteella.

## <a name="prerequisites"></a>edellytykset

Jos haluat nähdä tapahtumia, yhdistä verkkosivustosi data seurannan merkityksellisiin tietoihin yksinkertaisella koodikatkelmalla. Lisätietoja on kohdassa [Verkko-SDK:n asentaminen sivustolle](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Yhdistä ensin tiedot.":::

## <a name="create-refined-events"></a>Luo tarkennettuja tapahtumia

Tarkennetuilla tapahtumilla voit pienentää perustapahtuman laajuutta  [vientiä](export-events.md) varten tai poistaa ominaisuuksia, joita ei tarvitse näyttää.

> [!NOTE]
> Kun lisäät www-SDK:n verkkosivustoosi, voit tarkastella perustapahtumia ja luoda tarkennettuja tapahtumia. 

Voit tarkastella perustapahtumiasi seuraavasti:

1. Valitse vasemmassa siirtymisruudussa **Tiedot**.

1. Valitse **Tapahtumat**, niin näet luettelon työtilan tapahtumista.

    :::image type="content" source="media/data-events.png" alt-text="Näytä tapahtumat.":::

Voit luoda tarkennetun tapahtuman perustapahtumasta näin: 

1. Siirry kohtaan **Tiedot** > **Tapahtumat** ja valitse **+ Uudet tapahtumat** näytön yläosassa.

1. Valitse **Uudet tapahtumat** -dialogissa **Luo tarkennettuja tapahtumia** ja valitse sitten **Seuraava**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Uusien tapahtumien ohjattu toiminto.":::
     
1. Syötä **Uudet tapahtumat** -dialogissa seuraavat tiedot:

   - Valitse tapahtumat avattavasta **Perustapahtumat**-valikosta.
   - Kirjoita nimi **Tarkennetun tapahtuman näyttönimi** -ruutuun.
   - Voit myös päivittää ehdotetun **Todellinen nimi** -ruudun käyttämättä välilyöntejä.

1. Ota asetuksesi käyttöön valitsemalla **Luo**.

Tarkennettu tapahtuma näkyy nyt **Tapahtumat**-luettelossa.

### <a name="edit-event-name"></a>Tapahtuman nimen muokkaaminen

Voit muuttaa perustapahtuman tai tarkennetun tapahtuman nimeä ja ominaisuuksia.

1. Siirry kohtaan **Tiedot** > **Tapahtumat**. 

1. Valitse tapahtuman kohdalla **Lisää [...]** ja valitse sitten **Muokkaa nimeä**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Tarkennettujen tapahtumien luonnin asetukset.":::

3. Päivitä tapahtuman nimi ja valitse **Nimeä uudelleen**.

### <a name="view-the-details-of-a-refined-event"></a>Tarkastele tarkennetun tapahtuman tietoja:

1. Valitse **Tapahtuma**-luettelossa perustapahtuma tai tarkennettu tapahtuma. 

1. Valitse **Ominaisuuksien lisääminen ja poistaminen** näytön yläosassa avataksesi **Muokkaa ominaisuuksia** -ruudun. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Lisää ja poista ominaisuuksia.":::

1. Valitse näytettävät ja piilotettavat ominaisuudet valintaruutujen avulla. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Tarkennettujen tapahtumien ominaisuuksien muokkaaminen.":::

1. Valitse **Vahvista** käyttääksesi valintaasi ja valitse sitten **Tallenna**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Muokkaa valittuja ominaisuuksia tarkennetussa tapahtumassa

1. Avaa yksityiskohtainen näkymä siirtymällä kohtaan **Tiedot** > **Tapahtumat** ja valitse tarkennetut tapahtumat.
1. Valitse **Lisää ja poista ominaisuuksia**. 
1. Muokkaa valintaruutujen valintoja.
1. Ota muutokset käyttöön valitsemalla **Vahvista** ja sitten **Tallenna**.

Tietoja tapahtumien viemisestä: [Tapahtumien vieminen](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
