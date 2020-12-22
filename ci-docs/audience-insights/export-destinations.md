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
# <a name="export-destinations-preview"></a><span data-ttu-id="44a07-103">Vientikohteet (esiversio)</span><span class="sxs-lookup"><span data-stu-id="44a07-103">Export destinations (preview)</span></span>

<span data-ttu-id="44a07-104">**Vientikohteet**-sivulla näkyvät kaikki sijainnit, joihin olet määrittänyt tietojen viemisen.</span><span class="sxs-lookup"><span data-stu-id="44a07-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="44a07-105">Voit myös lisätä uusia kohteita vientiä varten.</span><span class="sxs-lookup"><span data-stu-id="44a07-105">You can also add new destinations for export.</span></span> <span data-ttu-id="44a07-106">Lisäksi se näyttää viennissä valittavissa olevat vaihtoehdot.</span><span class="sxs-lookup"><span data-stu-id="44a07-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="44a07-107">Saat nopeasti yleiskuvan, kuvauksen ja tietoja siitä, mitä kullakin laajennettavuusvaihtoehdolla voi tehdä.</span><span class="sxs-lookup"><span data-stu-id="44a07-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="44a07-108">Vie yhtenäiset profiilit, mitat ja segmentit yrityksen kannalta merkityksellisiin sovelluksiin.</span><span class="sxs-lookup"><span data-stu-id="44a07-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="44a07-109">Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet** ja etsi seuraavat laajennettavuusvaihtoehdot:</span><span class="sxs-lookup"><span data-stu-id="44a07-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="44a07-110">Dynamics 365 -asiakaskortti -laajennus</span><span class="sxs-lookup"><span data-stu-id="44a07-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="44a07-111">Facebookin mainosten hallinta -yhdistin</span><span class="sxs-lookup"><span data-stu-id="44a07-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="44a07-112">Power Automateyhdistin</span><span class="sxs-lookup"><span data-stu-id="44a07-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="44a07-113">Power Appsyhdistin</span><span class="sxs-lookup"><span data-stu-id="44a07-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="44a07-114">Power BIyhdistin</span><span class="sxs-lookup"><span data-stu-id="44a07-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="44a07-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="44a07-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="44a07-116">Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="44a07-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="44a07-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="44a07-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="44a07-118">Azure Blob -säilö</span><span class="sxs-lookup"><span data-stu-id="44a07-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="44a07-119">LiveRamp&reg;-yhdistin</span><span class="sxs-lookup"><span data-stu-id="44a07-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="44a07-120">Microsoft Teams -botti</span><span class="sxs-lookup"><span data-stu-id="44a07-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="44a07-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="44a07-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="44a07-122">Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="44a07-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="44a07-123">Uuden vientikohteen lisääminen</span><span class="sxs-lookup"><span data-stu-id="44a07-123">Add a new export destination</span></span>

<span data-ttu-id="44a07-124">Vientikohteiden lisäämistä varten on [järjestelmänvalvojan käyttöoikeudet](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="44a07-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="44a07-125">Jos viet tietoja Microsoft-palveluihin, oletamme, että molemmat palvelut ovat samassa organisaatiossa.</span><span class="sxs-lookup"><span data-stu-id="44a07-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="44a07-126">Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="44a07-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="44a07-127">Siirry **Omat vientikohteet** -välilehteen.</span><span class="sxs-lookup"><span data-stu-id="44a07-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="44a07-128">Luo uusi vientikohde valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="44a07-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="44a07-129">Valitse **Lisää kohde** -ruudun avattavasta luettelosta vientikohteen **Tyyppi**.</span><span class="sxs-lookup"><span data-stu-id="44a07-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="44a07-130">Luo vientikohde antamalla tarvittavat tiedot ja valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="44a07-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="44a07-131">Voit myös valita **Määritä** **Tutustu**-välilehden ruudussa.</span><span class="sxs-lookup"><span data-stu-id="44a07-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="44a07-132">Vientikohteiden näyttäminen</span><span class="sxs-lookup"><span data-stu-id="44a07-132">View Export destinations</span></span>

<span data-ttu-id="44a07-133">Kun olet luonut vientikohteita, ne löytyvät taulukosta **Omat vientikohteet** -välilehdessä. Tässä taulukossa on kolme saraketta:</span><span class="sxs-lookup"><span data-stu-id="44a07-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="44a07-134">**Näyttönimi**: kohdetta luotaessa annettu nimi.</span><span class="sxs-lookup"><span data-stu-id="44a07-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="44a07-135">**Tyyppi**: Kohdetta luotaessa määritetty vientikohteen tyyppi.</span><span class="sxs-lookup"><span data-stu-id="44a07-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="44a07-136">**Luotu**: päivämäärä, jolloin kohde luotiin.</span><span class="sxs-lookup"><span data-stu-id="44a07-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="44a07-137">Vientikohteen lisääminen</span><span class="sxs-lookup"><span data-stu-id="44a07-137">Edit an export destination</span></span>

1. <span data-ttu-id="44a07-138">Valitse muokattavan vientikohteen kohdalla kolme allekkaista pistettä.</span><span class="sxs-lookup"><span data-stu-id="44a07-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="44a07-139">![Kolme pistettä allekkain](media/export-destinations-page-ellipsis.png "Kolme pistettä allekkain")</span><span class="sxs-lookup"><span data-stu-id="44a07-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="44a07-140">Valitse avattavassa valikossa **Muokkaa**.</span><span class="sxs-lookup"><span data-stu-id="44a07-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="44a07-141">Muuta päivitettävät arvot ja valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="44a07-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="44a07-142">Tietojen vienti tarvittaessa</span><span class="sxs-lookup"><span data-stu-id="44a07-142">Export data on demand</span></span>

<span data-ttu-id="44a07-143">Kun vientikohteelle on määritetty yhdistin, vientejä suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="44a07-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="44a07-144">Jos haluat viedä tietoja odottamatta ajoitettua päivitystä, siirry **Omat vientikohteet** -välilehteen kohdassa **Järjestelmänvalvoja** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="44a07-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="44a07-145">![Kolme pistettä allekkain](media/export-destinations-page-ellipsis.png "Kolme pistettä allekkain")</span><span class="sxs-lookup"><span data-stu-id="44a07-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="44a07-146">Voit suorittaa viennin kaikkiin vientikohteisiin samanaikaisesti valitsemalla luettelon yläpuolella **Vie**.</span><span class="sxs-lookup"><span data-stu-id="44a07-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="44a07-147">Valitse kolmen pisteen painike (...) luettelokohdan perästä ja suorita vienti yksittäiseen vientikohteeseen valitsemalla **Vie**.</span><span class="sxs-lookup"><span data-stu-id="44a07-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="44a07-148">Vientikohteen poistaminen</span><span class="sxs-lookup"><span data-stu-id="44a07-148">Remove an Export destination</span></span>

<span data-ttu-id="44a07-149">Vientikohteen poistaminen aloitetaan **Vientikohde**-pääsivulta.</span><span class="sxs-lookup"><span data-stu-id="44a07-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="44a07-150">Valitse poistettavan vientikohteen kohdalla kolme allekkaista pistettä.</span><span class="sxs-lookup"><span data-stu-id="44a07-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="44a07-151">![Kolme pistettä allekkain](media/export-destinations-page-ellipsis.png "Kolme pistettä allekkain")</span><span class="sxs-lookup"><span data-stu-id="44a07-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="44a07-152">Valitse avattavassa valikossa **Poista**.</span><span class="sxs-lookup"><span data-stu-id="44a07-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="44a07-153">Vahvista poisto valitsemalla **Poista** vahvistusnäytössä.</span><span class="sxs-lookup"><span data-stu-id="44a07-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
