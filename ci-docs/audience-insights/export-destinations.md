---
title: Tietojen vieminen Customer Insightsista
description: Jaa tietoja hallitsemalla vientejä.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896139"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="7c7f8-103">Viennit (esiversio) – yleiskatsaus</span><span class="sxs-lookup"><span data-stu-id="7c7f8-103">Exports (preview) overview</span></span>

<span data-ttu-id="7c7f8-104">**Viennit**-sivulla näkyvät kaikki määritetyt viennit.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="7c7f8-105">Viennit jakavat tiettyjä tietoja eri sovellusten kanssa.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="7c7f8-106">Ne voivat sisältää asiakasprofiileja tai entiteettejä, rakenteita ja yhdistämistietoja.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="7c7f8-107">Kukin vienti edellyttää [yhteyttä, jonka määrittää järjestelmänvalvoja todennuksen ja käytön hallitsemiseksi](connections.md).</span><span class="sxs-lookup"><span data-stu-id="7c7f8-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7c7f8-108">Maaliskuuhun 2021 asti vienti loi automaattisesti yhteyden vastaavaan palveluun.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="7c7f8-109">Vienti edellyttää nyt [yhteyttä, joka on luotu ja jaettu järjestelmänvalvojan toimesta](connections.md) ennen viennin luomista.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="7c7f8-110">Siirry kohtaan **Tiedot** > **Viennit**, kun haluat tarkastella vientisivua.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="7c7f8-111">Kaikilla käyttäjärooleilla on määritettyjen vientien tarkastelemisen oikeus.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="7c7f8-112">Käyttämällä komentopalkin hakukenttää voit etsiä viennit nimen, yhteyden nimen tai yhteystyypin mukaan.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="7c7f8-113">Määritä uusi vienti</span><span class="sxs-lookup"><span data-stu-id="7c7f8-113">Set up a new export</span></span>

<span data-ttu-id="7c7f8-114">Jotta voit määrittää tai muokata vientiä, sinulla on oltava käytettävissä yhteydet.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="7c7f8-115">Yhteydet määräytyvät [käyttäjäroolisi](permissions.md) mukaan:</span><span class="sxs-lookup"><span data-stu-id="7c7f8-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="7c7f8-116">Järjestelmänvalvojat voivat käyttää kaikkia yhteyksiä.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-116">Administrators have access to all connections.</span></span> <span data-ttu-id="7c7f8-117">He voivat myös luoda uusia yhteyksiä viennin määrittämisen jälkeen.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="7c7f8-118">Osallistujat voivat käyttää tiettyjä yhteyksiä.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="7c7f8-119">Järjestelmänvalvojat voivat määrittää ja jakaa osallistujille yhteyksiä.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="7c7f8-120">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7c7f8-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="7c7f8-121">Katsojat voivat tarkastella vain aiemmin luotuja vientejä, mutta eivät luoda niitä.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="7c7f8-122">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7c7f8-123">Luo uusi vientikohde valitsemalla **Lisää vienti**.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="7c7f8-124">Valitse **Määritä vienti** -ruudussa käytettävä yhteys.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="7c7f8-125">[Yhteydet](connections.md) ovat järjestelmänvalvojien hallitsemia.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="7c7f8-126">Anna tarvittavat tiedot ja luo vienti valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="7c7f8-127">Muokkaa vientiä</span><span class="sxs-lookup"><span data-stu-id="7c7f8-127">Edit an export</span></span>

1. <span data-ttu-id="7c7f8-128">Valitse muokattavan vientikohteen kohdalla kolme allekkaista pistettä.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="7c7f8-129">Valitse avattavasta valikosta **Muokkaa**.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="7c7f8-130">Muuta päivitettävät arvot ja valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="7c7f8-131">Viennin ja viennin tietojen tarkasteleminen</span><span class="sxs-lookup"><span data-stu-id="7c7f8-131">View Exports and export details</span></span>

<span data-ttu-id="7c7f8-132">Kun olet luonut vientikohteet, ne näkyvät kohdassa **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="7c7f8-133">Kaikki käyttäjät näkevät jaetut tiedot ja niiden uusimman tilan.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="7c7f8-134">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7c7f8-135">Käyttäjät, joilla ei ole muokkausoikeutta, valitsevat **Näytä** (ei **Muokkaa**) nähdäkseen viennin tiedot.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="7c7f8-136">Tämä sivuruutu näyttää tämän viennin määrityksen.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="7c7f8-137">Arvoja ei voi muuttaa ilman muokkausoikeutta.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="7c7f8-138">Palaa vientisivulle valitsemalla **Sulje**.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="7c7f8-139">Suorita vientejä tarvittaessa</span><span class="sxs-lookup"><span data-stu-id="7c7f8-139">Run exports on demand</span></span>

<span data-ttu-id="7c7f8-140">Kun olet määrittänyt viennin, se suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) yhteydessä niin kauan kuin sillä on toimiva yhteys.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="7c7f8-141">Jos haluat viedä tietoja odottamatta ajoitettua päivitystä, siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="7c7f8-142">Sinulla on kaksi vaihtoehtoa:</span><span class="sxs-lookup"><span data-stu-id="7c7f8-142">You have two options:</span></span>

- <span data-ttu-id="7c7f8-143">Jos haluat suorittaa kaikki viennit, valitse komentopalkissa **Suorita kaikki**.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="7c7f8-144">Jos haluat suorittaa yksittäisen viennin, valitse luettelokohteesta kolme pistettä (...) ja valitse sitten **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="7c7f8-145">Viennin poistaminen</span><span class="sxs-lookup"><span data-stu-id="7c7f8-145">Remove an Export</span></span>

1. <span data-ttu-id="7c7f8-146">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7c7f8-147">Valitse poistettavan viennin kohdalla kolme allekkaista pistettä.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="7c7f8-148">Valitse avattavassa valikossa **Poista**.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="7c7f8-149">Vahvista poisto valitsemalla **Poista** vahvistusnäytössä.</span><span class="sxs-lookup"><span data-stu-id="7c7f8-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
