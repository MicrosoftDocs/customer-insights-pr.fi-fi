---
title: Vientikohteet
description: Tietojen vienti ja vientikohteiden hallinta.
ms.date: 07/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5557442983f8c48cd46387009e0060beb6e764bb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596081"
---
# <a name="export-destinations-preview-overview"></a>Vientikohteiden (esiversio) yleiskuvaus

**Vientikohteet**-sivulla näkyvät kaikki sijainnit, joihin olet määrittänyt tietojen viemisen. Voit myös lisätä uusia kohteita vientiä varten. Lisäksi se näyttää viennissä valittavissa olevat vaihtoehdot. Saat nopeasti yleiskuvan, kuvauksen ja tietoja siitä, mitä kullakin laajennettavuusvaihtoehdolla voi tehdä. Vie yhtenäiset profiilit, mitat ja segmentit yrityksen kannalta merkityksellisiin sovelluksiin.

Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet** ja etsi seuraavat laajennettavuusvaihtoehdot:

- [Adobe Campaign Standard](export-adobe-campaign-standard.md)
- [Adobe Experience Platform](export-adobe-experience-platform.md)
- [AdRoll](export-adroll.md)
- [Autopilot](export-autopilot.md)
- [Azure Blob -säilö](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [Microsoft Teams -botti](export-teams-bot.md)
- [Customer Insights API](apis.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Customer Service (Asiakaskortin apuohjelma)](customer-card-add-in.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 -myyntikeskus (Asiakaskortin apuohjelma)](customer-card-add-in.md)
- [Facebook-mainosten hallinta](export-facebook.md)
- [Google Ads](export-google-ads.md)
- [LiveRamp&reg;](export-liveramp.md)
- [Mailchimp](export-mailchimp.md)
- [Marketo](export-marketo.md)
- [Power Automate](export-power-automate.md)
- [Power Apps](export-power-apps.md)
- [Power BI](export-power-bi.md)
- [SendGrid](export-sendgrid.md)
- [SFTP](export-sftp.md)

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]