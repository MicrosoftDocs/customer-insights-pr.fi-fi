---
title: Luo ja muokkaa rakennettuja tapahtumia
description: Tarkennettujen tapahtumien luominen ja muokkaaminen.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034770"
---
# <a name="create-and-modify-refined-events"></a>Luo ja muokkaa rakennettuja tapahtumia

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Tapahtuma on käyttäjän käyttäytymistä edustavaa tietoa, kuten aktiviteetti verkkosivustolla.

- *Perustason* tapahtuma kirjaa ylös, milloin käyttäjä tarkastelee sivua (katselutapahtuma) tai on vuorovaikutuksessa sen sisällön kanssa (toimintotapahtuma).
- *Tarkennettu* tapahtuma on perustapahtuman virtuaalinen näkymä. Voit määrittää tarkennettuja tapahtumia poistamalla ja lisäämällä ominaisuuksia tai suodattamalla tapahtumia ominaisuusarvojen perusteella.

Tarkennetuilla tapahtumilla voit pienentää perustapahtuman laajuutta  [vientiä](export-events.md) varten tai poistaa ominaisuuksia, joita ei tarvitse näyttää.

## <a name="create-refined-events"></a>Tarkennettujen tapahtumien luominen

Tarkennettu tapahtuma voidaan luoda perustapahtumasta kolmella tavalla. 

1. Siirry kohtaan **Tiedot**> **Tapahtumat** ja valitse jokin seuraavista vaihtoehdoista:
    - Valitse **Uudet tapahtumat** ja valitse sitten **Luo tarkennettuja tapahtumia**.
    - Avaa yksityiskohtainen näkymä valitsemalla perustapahtuma ja valitse sitten ylimmästä valikosta **Luo tarkennettuja tapahtumia**.
    - Avaa perustapahtuman pikakuvakevalikko valitsemalla **Lisää [...]**. Valitse sitten **Luo tarkennettuja tapahtumia**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Tarkennettujen tapahtumien luonnin asetukset.":::

1. Kirjoita **Luo tarkennettuja tapahtumia** -valintaikkunaan seuraavat tiedot:

- Valitse tapahtuma avattavasta **Perustapahtumat**-luettelosta, jos olet luomassa uutta tapahtumaa.
- Kirjoita nimi **Tarkennetun tapahtuman näyttönimi** -ruutuun.
- Voit myös päivittää ehdotetun **Todellinen nimi** -ruudun käyttämättä välilyöntejä.

3. Ota asetuksesi käyttöön valitsemalla **Luo**.

1. Avaa **Muokkaa ominaisuuksia** -ruutu valitsemalla tarkennetun tapahtuman tietonäkymässä **Lisää ja poista ominaisuuksia**. 

1. Valitse näytettävät ja piilotettavat ominaisuudet valintaruutujen avulla. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Tarkennettujen tapahtumien ominaisuuksien muokkaaminen.":::

1. Ota valinta käyttöön valitsemalla **Vahvista**.

1. Tallenna määritys valitsemalla **Tallenna**.

## <a name="edit-refined-events"></a>Tarkennettujen tapahtumien muokkaaminen

Voit muuttaa tarkennetun tapahtuman nimeä ja ominaisuuksia.

### <a name="edit-event-name"></a>Tapahtuman nimen muokkaaminen

1. Siirry kohtaan **Tiedot** > **Tapahtumat**. 
1. Valitse tapahtuman kohdalla **Lisää [...]** ja valitse sitten **Muokkaa nimeä**.
1. Päivitä tapahtuman nimi ja valitse **Nimeä uudelleen**.

### <a name="edit-selected-properties"></a>Valittujen ominaisuuksien muokkaaminen

1. Avaa yksityiskohtainen näkymä siirtymällä kohtaan **Tiedot** > **Tapahtumat** ja valitse tarkennetut tapahtumat.
1. Valitse **Lisää ja poista ominaisuuksia**. 
1. Muokkaa valintaruutujen valintoja.
1. Ota muutokset käyttöön valitsemalla **Vahvista** ja sitten **Tallenna**.

Tietoja tapahtumien viemisestä: [Tapahtumien vieminen](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
