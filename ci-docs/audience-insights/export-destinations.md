---
title: Tietojen vieminen Customer Insightsista
description: Jaa tietoja hallitsemalla vientejä.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016610"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="bf86e-103">Viennit (esiversio) – yleiskatsaus</span><span class="sxs-lookup"><span data-stu-id="bf86e-103">Exports (preview) overview</span></span>

<span data-ttu-id="bf86e-104">**Viennit**-sivulla näkyvät kaikki määritetyt viennit.</span><span class="sxs-lookup"><span data-stu-id="bf86e-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="bf86e-105">Viennit jakavat tiettyjä tietoja eri sovellusten kanssa.</span><span class="sxs-lookup"><span data-stu-id="bf86e-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="bf86e-106">Ne voivat sisältää asiakasprofiileja tai entiteettejä, rakenteita ja yhdistämistietoja.</span><span class="sxs-lookup"><span data-stu-id="bf86e-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="bf86e-107">Kukin vienti edellyttää [yhteyttä, jonka määrittää järjestelmänvalvoja todennuksen ja käytön hallitsemiseksi](connections.md).</span><span class="sxs-lookup"><span data-stu-id="bf86e-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="bf86e-108">Siirry kohtaan **Tiedot** > **Viennit**, kun haluat tarkastella vientisivua.</span><span class="sxs-lookup"><span data-stu-id="bf86e-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="bf86e-109">Kaikilla käyttäjärooleilla on määritettyjen vientien tarkastelemisen oikeus.</span><span class="sxs-lookup"><span data-stu-id="bf86e-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="bf86e-110">Käyttämällä komentopalkin hakukenttää voit etsiä viennit nimen, yhteyden nimen tai yhteystyypin mukaan.</span><span class="sxs-lookup"><span data-stu-id="bf86e-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="bf86e-111">Määritä uusi vienti</span><span class="sxs-lookup"><span data-stu-id="bf86e-111">Set up a new export</span></span>

<span data-ttu-id="bf86e-112">Jotta voit määrittää tai muokata vientiä, sinulla on oltava käytettävissä yhteydet.</span><span class="sxs-lookup"><span data-stu-id="bf86e-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="bf86e-113">Yhteydet määräytyvät [käyttäjäroolisi](permissions.md) mukaan:</span><span class="sxs-lookup"><span data-stu-id="bf86e-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="bf86e-114">Järjestelmänvalvojat voivat käyttää kaikkia yhteyksiä.</span><span class="sxs-lookup"><span data-stu-id="bf86e-114">Administrators have access to all connections.</span></span> <span data-ttu-id="bf86e-115">He voivat myös luoda uusia yhteyksiä viennin määrittämisen jälkeen.</span><span class="sxs-lookup"><span data-stu-id="bf86e-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="bf86e-116">Osallistujat voivat käyttää tiettyjä yhteyksiä.</span><span class="sxs-lookup"><span data-stu-id="bf86e-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="bf86e-117">Järjestelmänvalvojat voivat määrittää ja jakaa osallistujille yhteyksiä.</span><span class="sxs-lookup"><span data-stu-id="bf86e-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="bf86e-118">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bf86e-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="bf86e-119">Katsojat voivat tarkastella vain aiemmin luotuja vientejä, mutta eivät luoda niitä.</span><span class="sxs-lookup"><span data-stu-id="bf86e-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="bf86e-120">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="bf86e-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bf86e-121">Luo uusi vientikohde valitsemalla **Lisää vienti**.</span><span class="sxs-lookup"><span data-stu-id="bf86e-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="bf86e-122">Valitse **Määritä vienti** -ruudussa käytettävä yhteys.</span><span class="sxs-lookup"><span data-stu-id="bf86e-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="bf86e-123">[Yhteydet](connections.md) ovat järjestelmänvalvojien hallitsemia.</span><span class="sxs-lookup"><span data-stu-id="bf86e-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="bf86e-124">Anna tarvittavat tiedot ja luo vienti valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="bf86e-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="bf86e-125">Muokkaa vientiä</span><span class="sxs-lookup"><span data-stu-id="bf86e-125">Edit an export</span></span>

1. <span data-ttu-id="bf86e-126">Valitse muokattavan vientikohteen kohdalla kolme allekkaista pistettä.</span><span class="sxs-lookup"><span data-stu-id="bf86e-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="bf86e-127">Valitse avattavasta valikosta **Muokkaa**.</span><span class="sxs-lookup"><span data-stu-id="bf86e-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="bf86e-128">Muuta päivitettävät arvot ja valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="bf86e-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="bf86e-129">Viennin ja viennin tietojen tarkasteleminen</span><span class="sxs-lookup"><span data-stu-id="bf86e-129">View Exports and export details</span></span>

<span data-ttu-id="bf86e-130">Kun olet luonut vientikohteet, ne näkyvät kohdassa **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="bf86e-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="bf86e-131">Kaikki käyttäjät näkevät jaetut tiedot ja niiden uusimman tilan.</span><span class="sxs-lookup"><span data-stu-id="bf86e-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="bf86e-132">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="bf86e-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bf86e-133">Käyttäjät, joilla ei ole muokkausoikeutta, valitsevat **Näytä** (ei **Muokkaa**) nähdäkseen viennin tiedot.</span><span class="sxs-lookup"><span data-stu-id="bf86e-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="bf86e-134">Tämä sivuruutu näyttää tämän viennin määrityksen.</span><span class="sxs-lookup"><span data-stu-id="bf86e-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="bf86e-135">Arvoja ei voi muuttaa ilman muokkausoikeutta.</span><span class="sxs-lookup"><span data-stu-id="bf86e-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="bf86e-136">Palaa vientisivulle valitsemalla **Sulje**.</span><span class="sxs-lookup"><span data-stu-id="bf86e-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="bf86e-137">Suorita vientejä tarvittaessa</span><span class="sxs-lookup"><span data-stu-id="bf86e-137">Run exports on demand</span></span>

<span data-ttu-id="bf86e-138">Kun olet määrittänyt viennin, se suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) yhteydessä niin kauan kuin sillä on toimiva yhteys.</span><span class="sxs-lookup"><span data-stu-id="bf86e-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="bf86e-139">Jos haluat viedä tietoja odottamatta ajoitettua päivitystä, siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="bf86e-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="bf86e-140">Sinulla on kaksi vaihtoehtoa:</span><span class="sxs-lookup"><span data-stu-id="bf86e-140">You have two options:</span></span>

- <span data-ttu-id="bf86e-141">Jos haluat suorittaa kaikki viennit, valitse komentopalkissa **Suorita kaikki**.</span><span class="sxs-lookup"><span data-stu-id="bf86e-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="bf86e-142">Jos haluat suorittaa yksittäisen viennin, valitse luettelokohteesta kolme pistettä (...) ja valitse sitten **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="bf86e-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="bf86e-143">Viennin poistaminen</span><span class="sxs-lookup"><span data-stu-id="bf86e-143">Remove an Export</span></span>

1. <span data-ttu-id="bf86e-144">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="bf86e-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bf86e-145">Valitse poistettavan viennin kohdalla kolme allekkaista pistettä.</span><span class="sxs-lookup"><span data-stu-id="bf86e-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="bf86e-146">Valitse avattavassa valikossa **Poista**.</span><span class="sxs-lookup"><span data-stu-id="bf86e-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="bf86e-147">Vahvista poisto valitsemalla **Poista** vahvistusnäytössä.</span><span class="sxs-lookup"><span data-stu-id="bf86e-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
