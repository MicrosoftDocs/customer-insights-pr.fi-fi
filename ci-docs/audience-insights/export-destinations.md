---
title: Tietojen vieminen Customer Insightsista
description: Jaa tietoja hallitsemalla vientejä.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253036"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="2abe4-103">Viennit (esiversio) – yleiskatsaus</span><span class="sxs-lookup"><span data-stu-id="2abe4-103">Exports (preview) overview</span></span>

<span data-ttu-id="2abe4-104">**Viennit**-sivulla näkyvät kaikki määritetyt viennit.</span><span class="sxs-lookup"><span data-stu-id="2abe4-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="2abe4-105">Viennit jakavat tiettyjä tietoja eri sovellusten kanssa.</span><span class="sxs-lookup"><span data-stu-id="2abe4-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="2abe4-106">Ne voivat sisältää asiakasprofiileja tai entiteettejä, rakenteita ja yhdistämistietoja.</span><span class="sxs-lookup"><span data-stu-id="2abe4-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="2abe4-107">Kukin vienti edellyttää [yhteyttä, jonka määrittää järjestelmänvalvoja todennuksen ja käytön hallitsemiseksi](connections.md).</span><span class="sxs-lookup"><span data-stu-id="2abe4-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="2abe4-108">Siirry kohtaan **Tiedot** > **Viennit**, kun haluat tarkastella vientisivua.</span><span class="sxs-lookup"><span data-stu-id="2abe4-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="2abe4-109">Kaikilla käyttäjärooleilla on määritettyjen vientien tarkastelemisen oikeus.</span><span class="sxs-lookup"><span data-stu-id="2abe4-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="2abe4-110">Käyttämällä komentopalkin hakukenttää voit etsiä viennit nimen, yhteyden nimen tai yhteystyypin mukaan.</span><span class="sxs-lookup"><span data-stu-id="2abe4-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="2abe4-111">Määritä uusi vienti</span><span class="sxs-lookup"><span data-stu-id="2abe4-111">Set up a new export</span></span>

<span data-ttu-id="2abe4-112">Jotta voit määrittää tai muokata vientiä, sinulla on oltava käytettävissä yhteydet.</span><span class="sxs-lookup"><span data-stu-id="2abe4-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="2abe4-113">Yhteydet määräytyvät [käyttäjäroolisi](permissions.md) mukaan:</span><span class="sxs-lookup"><span data-stu-id="2abe4-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="2abe4-114">Järjestelmänvalvojat voivat käyttää kaikkia yhteyksiä.</span><span class="sxs-lookup"><span data-stu-id="2abe4-114">Administrators have access to all connections.</span></span> <span data-ttu-id="2abe4-115">He voivat myös luoda uusia yhteyksiä viennin määrittämisen jälkeen.</span><span class="sxs-lookup"><span data-stu-id="2abe4-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="2abe4-116">Osallistujat voivat käyttää tiettyjä yhteyksiä.</span><span class="sxs-lookup"><span data-stu-id="2abe4-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="2abe4-117">Järjestelmänvalvojat voivat määrittää ja jakaa osallistujille yhteyksiä.</span><span class="sxs-lookup"><span data-stu-id="2abe4-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="2abe4-118">Vientiluettelossa näkyvät osallistujat, voivatko he muokata tai vain tarkastella vientiä **Oikeutesi**-sarakkeessa.</span><span class="sxs-lookup"><span data-stu-id="2abe4-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="2abe4-119">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2abe4-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="2abe4-120">Katsojat voivat tarkastella vain aiemmin luotuja vientejä, mutta eivät luoda niitä.</span><span class="sxs-lookup"><span data-stu-id="2abe4-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="2abe4-121">Määritä uusi vienti</span><span class="sxs-lookup"><span data-stu-id="2abe4-121">Define a new export</span></span>

1. <span data-ttu-id="2abe4-122">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="2abe4-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2abe4-123">Valitse **Lisää vienti** luodaksesi uuden viennin.</span><span class="sxs-lookup"><span data-stu-id="2abe4-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="2abe4-124">Valitse **Määritä vienti** -ruudussa käytettävä yhteys.</span><span class="sxs-lookup"><span data-stu-id="2abe4-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="2abe4-125">[Yhteydet](connections.md) ovat järjestelmänvalvojien hallitsemia.</span><span class="sxs-lookup"><span data-stu-id="2abe4-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="2abe4-126">Anna tarvittavat tiedot ja luo vienti valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="2abe4-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="2abe4-127">Uuden viennin määritteleminen aiemmin luodun viennin perusteella</span><span class="sxs-lookup"><span data-stu-id="2abe4-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="2abe4-128">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="2abe4-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2abe4-129">Valitse vientiluettelosta vienti, jonka haluat kopioida.</span><span class="sxs-lookup"><span data-stu-id="2abe4-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="2abe4-130">Valitse komentopalkissa **Luo kaksoiskappale**, jos haluat avata **Määritä vienti** -ruudun, jossa on valitun viennin tiedot.</span><span class="sxs-lookup"><span data-stu-id="2abe4-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="2abe4-131">Tarkista ja mukauta vienti ja valitse **Tallenna**, jos haluat luoda uuden viennin.</span><span class="sxs-lookup"><span data-stu-id="2abe4-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="2abe4-132">Muokkaa vientiä</span><span class="sxs-lookup"><span data-stu-id="2abe4-132">Edit an export</span></span>

1. <span data-ttu-id="2abe4-133">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="2abe4-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2abe4-134">Valitse vientiluettelosta vienti, jonka haluat muokata.</span><span class="sxs-lookup"><span data-stu-id="2abe4-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="2abe4-135">Valitse komentopalkissa **Muokkaa**.</span><span class="sxs-lookup"><span data-stu-id="2abe4-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="2abe4-136">Muuta päivitettävät arvot ja valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="2abe4-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="2abe4-137">Viennin ja viennin tietojen tarkasteleminen</span><span class="sxs-lookup"><span data-stu-id="2abe4-137">View exports and export details</span></span>

<span data-ttu-id="2abe4-138">Kun olet luonut vientikohteet, ne näkyvät kohdassa **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="2abe4-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="2abe4-139">Kaikki käyttäjät näkevät jaetut tiedot ja niiden uusimman tilan.</span><span class="sxs-lookup"><span data-stu-id="2abe4-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="2abe4-140">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="2abe4-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2abe4-141">Käyttäjät, joilla ei ole muokkausoikeutta, valitsevat **Näytä** (ei **Muokkaa**) nähdäkseen viennin tiedot.</span><span class="sxs-lookup"><span data-stu-id="2abe4-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="2abe4-142">Sivuruudussa näkyy viennin määritys.</span><span class="sxs-lookup"><span data-stu-id="2abe4-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="2abe4-143">Arvoja ei voi muuttaa ilman muokkausoikeutta.</span><span class="sxs-lookup"><span data-stu-id="2abe4-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="2abe4-144">Palaa vientisivulle valitsemalla **Sulje**.</span><span class="sxs-lookup"><span data-stu-id="2abe4-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="2abe4-145">Aikatauluta ja suorita useita vientejä</span><span class="sxs-lookup"><span data-stu-id="2abe4-145">Schedule and run exports</span></span>

<span data-ttu-id="2abe4-146">Jokaisella määritetyllä viennillä on päivitysaikataulu.</span><span class="sxs-lookup"><span data-stu-id="2abe4-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="2abe4-147">Päivityksen aikana järjestelmä etsii uusia tai päivitettyjä tietoja, jotka sisällytetään vientiin.</span><span class="sxs-lookup"><span data-stu-id="2abe4-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="2abe4-148">Vieminen suoritetaan oletusarvoisesti jokaisen [ajoitetun järjestelmän päivityksen](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="2abe4-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2abe4-149">Voit mukauttaa päivitysaikataulua tai poistaa sen käytöstä, jos haluat suorittaa viennit manuaalisesti.</span><span class="sxs-lookup"><span data-stu-id="2abe4-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="2abe4-150">Vientiaikataulut määräytyvät ympäristön tilan mukaan.</span><span class="sxs-lookup"><span data-stu-id="2abe4-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="2abe4-151">Jos aikataulutetun viennin käynnistyessä on käynnissä [riippuvuuksien](system.md#refresh-policies) päivityksiä, järjestelmä suorittaa ensin riippuvuudet ja suorittaa sitten viennin.</span><span class="sxs-lookup"><span data-stu-id="2abe4-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="2abe4-152">Voit nähdä, milloin vienti on viimeksi päivitetty sarakkeessa **Päivitetty**.</span><span class="sxs-lookup"><span data-stu-id="2abe4-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="2abe4-153">Aikataulun viennit</span><span class="sxs-lookup"><span data-stu-id="2abe4-153">Schedule exports</span></span>

<span data-ttu-id="2abe4-154">Voit määrittää mukautettuja päivitysaikatauluja yksittäiselle viennille tai usealle viennille samalla kertaa.</span><span class="sxs-lookup"><span data-stu-id="2abe4-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="2abe4-155">Tällä hetkellä määritetty aikataulu näkyy vientiluettelon **Aikataulu**-sarakkeessa.</span><span class="sxs-lookup"><span data-stu-id="2abe4-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="2abe4-156">Aikataulun muutosoikeus on sama kuin [viennin muokkaamiseen ja määrittämiseen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2abe4-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="2abe4-157">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="2abe4-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2abe4-158">Valitse vienti, jonka haluat aikatauluttaa.</span><span class="sxs-lookup"><span data-stu-id="2abe4-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="2abe4-159">Valitse komentopalkista **Aikatauluta**.</span><span class="sxs-lookup"><span data-stu-id="2abe4-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="2abe4-160">Määritä **Aikatauluta vienti** -ruudussa **Suoritettava aikataulu** -arvoksi **Käytössä**, jotta vienti voidaan suorittaa automaattisesti.</span><span class="sxs-lookup"><span data-stu-id="2abe4-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="2abe4-161">Valitse **Ei käytössä**, jos haluat päivittää sen manuaalisesti.</span><span class="sxs-lookup"><span data-stu-id="2abe4-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="2abe4-162">Jos haluat päivittää viennit automaattisesti, valitse **Toistumisarvo** ja määritä sen tiedot.</span><span class="sxs-lookup"><span data-stu-id="2abe4-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="2abe4-163">Määritetty aika koskee kaikkia toistumisen esiintymiä.</span><span class="sxs-lookup"><span data-stu-id="2abe4-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="2abe4-164">Tämä on aika, jolloin viennin pitäisi alkaa päivittyä.</span><span class="sxs-lookup"><span data-stu-id="2abe4-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="2abe4-165">Ota muutokset käyttöön ja aktivoi ne valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="2abe4-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="2abe4-166">Kun muokkaat useiden vientien aikataulua, valitse **Säilytä tai korvaa aikataulut** -kohdassa:</span><span class="sxs-lookup"><span data-stu-id="2abe4-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="2abe4-167">**Säilytä yksittäiset aikataulut**: Jatka valitun viennin aiemmin määritettyä aikataulua ja poista ne vain käytöstä tai ota ne käyttöön.</span><span class="sxs-lookup"><span data-stu-id="2abe4-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="2abe4-168">**Määritä uusi aikataulu kaikille valituille viennille**: ohita valittujen vientien aiemmin luodut aikataulut.</span><span class="sxs-lookup"><span data-stu-id="2abe4-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="2abe4-169">Suorita vientejä tarvittaessa</span><span class="sxs-lookup"><span data-stu-id="2abe4-169">Run exports on demand</span></span>

<span data-ttu-id="2abe4-170">Jos haluat viedä tietoja odottamatta ajoitettua päivitystä, siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="2abe4-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="2abe4-171">Jos haluat suorittaa kaikki viennit, valitse komentopalkissa **Suorita kaikki**.</span><span class="sxs-lookup"><span data-stu-id="2abe4-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="2abe4-172">Tämä toiminto suorittaa vain viennit, jotka ovat aktiivisia aikatauluja.</span><span class="sxs-lookup"><span data-stu-id="2abe4-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="2abe4-173">Jos haluat suorittaa yksittäisen viennin, valitse se luettelosta ja valitse komentopalkissa **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="2abe4-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="2abe4-174">Näin viennit suoritetaan ilman aktiivista aikataulua.</span><span class="sxs-lookup"><span data-stu-id="2abe4-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="2abe4-175">Viennin poistaminen</span><span class="sxs-lookup"><span data-stu-id="2abe4-175">Remove an Export</span></span>

1. <span data-ttu-id="2abe4-176">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="2abe4-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2abe4-177">Valitse poistettava vienti.</span><span class="sxs-lookup"><span data-stu-id="2abe4-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="2abe4-178">Valitse komentopalkissa **Poista**.</span><span class="sxs-lookup"><span data-stu-id="2abe4-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="2abe4-179">Vahvista poisto valitsemalla **Poista** vahvistusnäytössä.</span><span class="sxs-lookup"><span data-stu-id="2abe4-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
