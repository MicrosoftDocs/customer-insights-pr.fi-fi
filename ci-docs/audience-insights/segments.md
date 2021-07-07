---
title: Käyttäjäryhmien merkityksellisten tietojen segmentit
description: Yleiskatsaus segmenteistä ja niiden luomisesta ja hallinnasta.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306253"
---
# <a name="segments-overview"></a><span data-ttu-id="2786e-103">Segmenttien yleiskatsaus</span><span class="sxs-lookup"><span data-stu-id="2786e-103">Segments overview</span></span>

<span data-ttu-id="2786e-104">Segmenttien avulla asiakkaita ryhmitellä demografia-, tapahtuma- tai toimintamääritteiden perusteella.</span><span class="sxs-lookup"><span data-stu-id="2786e-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="2786e-105">Segmenttejä käyttämällä voit kohdistaa markkinointikampanjoita, myyntiaktiviteetteja ja asiakastukitoimintoja liiketoiminnan tavoitteiden saavuttamiseksi.</span><span class="sxs-lookup"><span data-stu-id="2786e-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="2786e-106">Segmenttimäärityksen suodattimia vastaavia asiakasprofiileita kutsutaan segmentin *jäseniksi*.</span><span class="sxs-lookup"><span data-stu-id="2786e-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="2786e-107">Käytössä on jotakin [palvelurajoituksia](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="2786e-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="2786e-108">Luo uusi segmentti</span><span class="sxs-lookup"><span data-stu-id="2786e-108">Create a new segment</span></span>

<span data-ttu-id="2786e-109">Uuden segmentin voi luoda useilla tavoilla:</span><span class="sxs-lookup"><span data-stu-id="2786e-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="2786e-110">Monimutkainen segmentti segmentin muodostimella: [Tyhjä segmentti](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="2786e-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="2786e-111">Yksinkertaiset segmentit yhdellä operaattorilla: [Pikasegmentti](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="2786e-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="2786e-112">Tekoälyä käyttävä tapa löytää samanlaisia asiakkaita: [Samanlaiset asiakkaat](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="2786e-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="2786e-113">Tekoälypohjaiset ehdotukset, jotka perustuvat mittareihin tai määritteisiin: [Ehdotetut segmentit mittareiden parantamiseksi](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="2786e-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="2786e-114">Aktiviteetteihin perustuvat ehdotukset: [Asiakasaktiviteettien perusteella ehdotetut segmentit](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="2786e-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="2786e-115">Aiemmin luotujen segmenttien hallinta</span><span class="sxs-lookup"><span data-stu-id="2786e-115">Manage existing segments</span></span>

<span data-ttu-id="2786e-116">Siirry **Segmentit**-sivulle nähdäksesi kaikki tallennetut segmentit ja hallitaksesi niitä.</span><span class="sxs-lookup"><span data-stu-id="2786e-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="2786e-117">Jokaista segmenttiä edustaa rivi, joka sisältää segmentin lisätietoja.</span><span class="sxs-lookup"><span data-stu-id="2786e-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Valittu segmentti sekä vaihtoehtojen avattava luettelo ja käytettävissä olevat vaihtoehdot.":::

<span data-ttu-id="2786e-119">Seuraava toiminto on käytettävissä, kun valitse segmentin:</span><span class="sxs-lookup"><span data-stu-id="2786e-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="2786e-120">**Näytä** segmentin tietoja, mukaan lukien jäsenmäärän trendi, segmentin jäsenten esikatselu.</span><span class="sxs-lookup"><span data-stu-id="2786e-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="2786e-121">**Muokkaa** segmenttiä, jos haluat muuttaa sen ominaisuuksia.</span><span class="sxs-lookup"><span data-stu-id="2786e-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="2786e-122">Luo segmentin **kaksoiskappale**.</span><span class="sxs-lookup"><span data-stu-id="2786e-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="2786e-123">Voit muokata sen ominaisuuksia heti tai tallentaa kaksoiskappaleen.</span><span class="sxs-lookup"><span data-stu-id="2786e-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="2786e-124">**Päivitä** segmentti siten, että se sisältää uusimmat tiedot.</span><span class="sxs-lookup"><span data-stu-id="2786e-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="2786e-125">**Aktivoi** segmentti tai **Poista aktivointi**.</span><span class="sxs-lookup"><span data-stu-id="2786e-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="2786e-126">Segmenteillä on kaksi mahdollista tilaa: aktiivinen ja passiivinen.</span><span class="sxs-lookup"><span data-stu-id="2786e-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="2786e-127">Näistä tiloista on hyötyä segmenttiä muokattaessa.</span><span class="sxs-lookup"><span data-stu-id="2786e-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="2786e-128">Passiivisissa segmenteissä on segmentin määritelmä, mutta se ei sisällä vielä asiakkaita.</span><span class="sxs-lookup"><span data-stu-id="2786e-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="2786e-129">Kun segmentti aktivoidaan, tila muuttuu passiivisesta aktiivisesti ja se aloittaa segmentin määritelmää vastaavien asiakkaiden etsimisen.</span><span class="sxs-lookup"><span data-stu-id="2786e-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="2786e-130">Jos [aikataulutettu päivitys](system.md#schedule-tab) on määritetty, passiivisten segmenttien **Tila**-arvon on **Ohitettu**, mikä osoittaa, että päivitystä ei edes yritetty.</span><span class="sxs-lookup"><span data-stu-id="2786e-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="2786e-131">Kun passiivinen segmentti aktivoidaan, se päivittyy ja se sisällytetään aikataulutettuihin päivityksiin.</span><span class="sxs-lookup"><span data-stu-id="2786e-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="2786e-132">Voit vaihtoehtoisesti määrittää tulevan päivämäärän ja kellonajan tietyn segmentin aktivointiin ja aktivoinnin poistamiseen avattavan **Aktivoi / Poista aktivointi** -valikon **Ajoita myöhemmin** -toiminnolla.</span><span class="sxs-lookup"><span data-stu-id="2786e-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="2786e-133">**Nimeä uudelleen** segmentti.</span><span class="sxs-lookup"><span data-stu-id="2786e-133">**Rename** the segment.</span></span>
- <span data-ttu-id="2786e-134">**Lataa** jäsenten luettelo CSV-tiedostona.</span><span class="sxs-lookup"><span data-stu-id="2786e-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="2786e-135">**Hallitse vientiä** tarkastellaksesi vientiin liittyviä segmenttejä ja hallita niitä.</span><span class="sxs-lookup"><span data-stu-id="2786e-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="2786e-136">Lisätietoja vienneistä.</span><span class="sxs-lookup"><span data-stu-id="2786e-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="2786e-137">**Poista** segmentti.</span><span class="sxs-lookup"><span data-stu-id="2786e-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="2786e-138">Päivitä segmentit</span><span class="sxs-lookup"><span data-stu-id="2786e-138">Refresh segments</span></span>

<span data-ttu-id="2786e-139">Voit päivittää kaikki segmentit kerralla valitsemalla **Päivitä kaikki** **Segmentit**-sivulla. Halutessasi voit päivittää yhden tai useita segmenttejä, kun valitset ne ja valitse sitten **Päivitä** asetuksista.</span><span class="sxs-lookup"><span data-stu-id="2786e-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="2786e-140">Voit myös määrittää toistuvan päivityksen kohdassa **Järjestelmänvalvoja** > **Järjestelmä** > **Ajoita**.</span><span class="sxs-lookup"><span data-stu-id="2786e-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="2786e-141">Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="2786e-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="2786e-142">Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="2786e-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="2786e-143">Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja.</span><span class="sxs-lookup"><span data-stu-id="2786e-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="2786e-144">Kun työn jossakin tehtävissä on valittu **Näytä tiedot**, saat lisätietoja: käsittelyajan, viimeisimmän käsittelypäivämäärän sekä kaikki tehtävään liitetyt virheet ja varoitukset.</span><span class="sxs-lookup"><span data-stu-id="2786e-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="2786e-145">Segmenttien vienti</span><span class="sxs-lookup"><span data-stu-id="2786e-145">Export segments</span></span>

<span data-ttu-id="2786e-146">Voit viedä segmentin segmenttisivulta tai [vientisivulta](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2786e-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="2786e-147">Siirry **Segmentit**-sivulle.</span><span class="sxs-lookup"><span data-stu-id="2786e-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="2786e-148">Valitse **Näytä lisää [...]** segmentistä, jonka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="2786e-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="2786e-149">Valitse **Hallitse vientejä** toimintojen avattavasta luettelosta.</span><span class="sxs-lookup"><span data-stu-id="2786e-149">Select **Manage exports** from the actions dropdown list.</span></span>

1. <span data-ttu-id="2786e-150">**Segmentin vienti (esikatselu)** -sivu avautuu.</span><span class="sxs-lookup"><span data-stu-id="2786e-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="2786e-151">Voit nähdä kaikki määritetyt viennit ryhmiteltyinä viennin mukaan, joka sisältää nykyisen segmentin tai ei sisällä sitä.</span><span class="sxs-lookup"><span data-stu-id="2786e-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="2786e-152">Jos haluat lisätä valitun segmentin vientiin, valitse vienti luettelosta ja valitse **Lisää segmentti**.</span><span class="sxs-lookup"><span data-stu-id="2786e-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="2786e-153">Jos haluat luoda uuden viennin valitulla segmentillä, valitse **Lisää vienti**.</span><span class="sxs-lookup"><span data-stu-id="2786e-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="2786e-154">Lisätietoja viennin luomisesta on ohjeaiheessa [Uuden viennin luominen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2786e-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2786e-155">Palaa segmenttien pääsivulle valitsemalla **Takaisin**.</span><span class="sxs-lookup"><span data-stu-id="2786e-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="2786e-156">Tarkastele käsittelyhistoriaa ja segmentin jäseniä</span><span class="sxs-lookup"><span data-stu-id="2786e-156">View processing history and segment members</span></span>

<span data-ttu-id="2786e-157">Voit tarkastella segmentin yhdistettyjä tietoja tarkastelemalla sen tietoja.</span><span class="sxs-lookup"><span data-stu-id="2786e-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="2786e-158">Valitse **Segmentit**-sivulla segmentti, jota haluat tarkastella.</span><span class="sxs-lookup"><span data-stu-id="2786e-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="2786e-159">Sivun yläosassa on trendikaavio, joka visualisoi jäsenmäärän muutokset.</span><span class="sxs-lookup"><span data-stu-id="2786e-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="2786e-160">Vie kohdistin arvopisteiden päälle, jos haluat nähdä tietyn päivämäärän jäsenmäärän.</span><span class="sxs-lookup"><span data-stu-id="2786e-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="2786e-161">Voit päivittää visualisoinnin aikavälin.</span><span class="sxs-lookup"><span data-stu-id="2786e-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2786e-162">![Segmentin aikaväli](media/segment-time-range.png "Segmentin aikaväli")</span><span class="sxs-lookup"><span data-stu-id="2786e-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="2786e-163">Alaosassa on luettelo segmentin jäsenistä.</span><span class="sxs-lookup"><span data-stu-id="2786e-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="2786e-164">Tässä luettelossa näkyvät kentät perustuvat segmentin entiteettien määritteisiin.</span><span class="sxs-lookup"><span data-stu-id="2786e-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="2786e-165">Luettelo on täsmäävien segmentin jäsenten esikatselu. Siinä näkyvät segmentin ensimmäiset 100 tietuetta, joten voit nopeasti arvioida segmentin ja tarkistaa sen määritykset tarpeen mukaan.</span><span class="sxs-lookup"><span data-stu-id="2786e-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="2786e-166">Jos haluat nähdä kaikki täsmäävät tietueet, sinun on [vietävä segmentti](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2786e-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
