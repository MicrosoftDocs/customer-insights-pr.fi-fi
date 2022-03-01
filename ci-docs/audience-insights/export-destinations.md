---
title: Vientikohteet
description: Tietojen vienti ja vientikohteiden hallinta.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643859"
---
# <a name="export-destinations-preview"></a>Vientikohteet (esiversio)

**Vientikohteet**-sivulla näkyvät kaikki sijainnit, joihin olet määrittänyt tietojen viemisen. Voit myös lisätä uusia kohteita vientiä varten. Lisäksi se näyttää viennissä valittavissa olevat vaihtoehdot. Saat nopeasti yleiskuvan, kuvauksen ja tietoja siitä, mitä kullakin laajennettavuusvaihtoehdolla voi tehdä. Vie yhtenäiset profiilit, mitat ja segmentit yrityksen kannalta merkityksellisiin sovelluksiin.

Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet** ja etsi seuraavat laajennettavuusvaihtoehdot:

- [Dynamics 365 -asiakaskortti -laajennus](customer-card-add-in.md)
- [Facebookin mainosten hallinta -yhdistin](export-facebook.md)
- [Power Automateyhdistin](export-power-automate.md)
- [Power Appsyhdistin](export-power-apps.md)
- [Power BIyhdistin](export-power-bi.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Azure Blob -säilö](export-azure-blob-storage.md)
- [LiveRamp&reg;-yhdistin](export-liveramp.md)
- [Microsoft Teams -botti](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [Customer Insights API](apis.md)

## <a name="add-a-new-export-destination"></a>Uuden vientikohteen lisääminen

Vientikohteiden lisäämistä varten on [järjestelmänvalvojan käyttöoikeudet](permissions.md). Jos viet tietoja Microsoft-palveluihin, oletamme, että molemmat palvelut ovat samassa organisaatiossa.

1. Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.

1. Siirry **Omat vientikohteet** -välilehteen.

1. Luo uusi vientikohde valitsemalla **Lisää kohde**.

1. Valitse **Lisää kohde** -ruudun avattavasta luettelosta vientikohteen **Tyyppi**.

1. Luo vientikohde antamalla tarvittavat tiedot ja valitsemalla **Seuraava**.

Voit myös valita **Määritä** **Tutustu**-välilehden ruudussa.

## <a name="view-export-destinations"></a>Vientikohteiden näyttäminen

Kun olet luonut vientikohteita, ne löytyvät taulukosta **Omat vientikohteet** -välilehdessä. Tässä taulukossa on kolme saraketta:

- **Näyttönimi**: kohdetta luotaessa annettu nimi.
- **Tyyppi**: Kohdetta luotaessa määritetty vientikohteen tyyppi.
- **Luotu**: päivämäärä, jolloin kohde luotiin.

## <a name="edit-an-export-destination"></a>Vientikohteen lisääminen

1. Valitse muokattavan vientikohteen kohdalla kolme allekkaista pistettä.

   > [!div class="mx-imgBorder"]
   > ![Kolme pistettä allekkain](media/export-destinations-page-ellipsis.png "Kolme pistettä allekkain")

1. Valitse avattavassa valikossa **Muokkaa**.

1. Muuta päivitettävät arvot ja valitse **Tallenna**.

## <a name="export-data-on-demand"></a>Tietojen vienti tarvittaessa

Kun vientikohteelle on määritetty yhdistin, vientejä suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) yhteydessä.

Jos haluat viedä tietoja odottamatta ajoitettua päivitystä, siirry **Omat vientikohteet** -välilehteen kohdassa **Järjestelmänvalvoja** > **Vientikohteet**.

> [!div class="mx-imgBorder"]
> ![Kolme pistettä allekkain](media/export-destinations-page-ellipsis.png "Kolme pistettä allekkain")

- Voit suorittaa viennin kaikkiin vientikohteisiin samanaikaisesti valitsemalla luettelon yläpuolella **Vie**.
- Valitse kolmen pisteen painike (...) luettelokohdan perästä ja suorita vienti yksittäiseen vientikohteeseen valitsemalla **Vie**.

## <a name="remove-an-export-destination"></a>Vientikohteen poistaminen

Vientikohteen poistaminen aloitetaan **Vientikohde**-pääsivulta.

1. Valitse poistettavan vientikohteen kohdalla kolme allekkaista pistettä.

   > [!div class="mx-imgBorder"]
   > ![Kolme pistettä allekkain](media/export-destinations-page-ellipsis.png "Kolme pistettä allekkain")

2. Valitse avattavassa valikossa **Poista**.

3. Vahvista poisto valitsemalla **Poista** vahvistusnäytössä.
