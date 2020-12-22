---
title: Segmenttien luonti ja hallinta
description: Luo asiakassegmenttejä ja ryhmittele ne eri määritteiden perusteella.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405631"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="bcdca-103">Segmenttien luonti ja hallinta</span><span class="sxs-lookup"><span data-stu-id="bcdca-103">Create and manage segments</span></span>

<span data-ttu-id="bcdca-104">Segmenttien avulla asiakkaita ryhmitellä demografia-, tapahtuma- tai toimintamääritteiden perusteella.</span><span class="sxs-lookup"><span data-stu-id="bcdca-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="bcdca-105">Segmenttejä käyttämällä voit kohdistaa markkinointikampanjoita, myyntiaktiviteetteja ja asiakastukitoimintoja liiketoiminnan tavoitteiden saavuttamiseksi.</span><span class="sxs-lookup"><span data-stu-id="bcdca-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="bcdca-106">Voit määrittää asiakasprofiilientiteetin ja sen liittyvien entiteettien ympärille monimutkaisia suodattimia.</span><span class="sxs-lookup"><span data-stu-id="bcdca-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="bcdca-107">Kukin segmentti luo käsittelyn jälkeen joukon asiakastietueita, joita voit viedä ja joihin voit tehdä toimintoja.</span><span class="sxs-lookup"><span data-stu-id="bcdca-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="bcdca-108">Käytössä on jotakin [palvelurajoituksia](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="bcdca-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="bcdca-109">Ellei toisin mainita, kaikki segmentit ovat **dynaamisia segmenttejä**, jotka päivitetään toistuvan aikataulun mukaisesti.</span><span class="sxs-lookup"><span data-stu-id="bcdca-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="bcdca-110">Seuraava esimerkki kuvaa segmentointiominaisuutta.</span><span class="sxs-lookup"><span data-stu-id="bcdca-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="bcdca-111">Olemme määritelleet segmentin asiakkaille, jotka tilasivat vähintään 500 dollarilla tavaraa viimeisen 90 päivän aikana *ja* jotka olivat mukana eskaloidussa asiakaspalvelupuhelussa.</span><span class="sxs-lookup"><span data-stu-id="bcdca-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bcdca-112">![Useita ryhmiä](media/segmentation-group1-2.png "Useita ryhmiä")</span><span class="sxs-lookup"><span data-stu-id="bcdca-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="bcdca-113">Luo uusi segmentti</span><span class="sxs-lookup"><span data-stu-id="bcdca-113">Create a new segment</span></span>

<span data-ttu-id="bcdca-114">Segmenttejä hallitaan **Segmentit**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="bcdca-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="bcdca-115">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Segmentit**-sivu.</span><span class="sxs-lookup"><span data-stu-id="bcdca-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="bcdca-116">Valitse **Uusi** > **Tyhjä segmentti**.</span><span class="sxs-lookup"><span data-stu-id="bcdca-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="bcdca-117">Valitse **Uusi segmentti** -ruudussa segmentin tyyppi ja anna **nimi**.</span><span class="sxs-lookup"><span data-stu-id="bcdca-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="bcdca-118">Vaihtoehtoisesti voit antaa näyttönimen ja kuvauksen, joiden avulla segmentin voi tunnistaa.</span><span class="sxs-lookup"><span data-stu-id="bcdca-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="bcdca-119">Kun valitset **Seuraava**, näyttöön avautuu **Segmentin muodostin** -sivu, jolla voit määrittää ryhmän.</span><span class="sxs-lookup"><span data-stu-id="bcdca-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="bcdca-120">Ryhmä on joukko asiakkaita.</span><span class="sxs-lookup"><span data-stu-id="bcdca-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="bcdca-121">Valitse sen määritteen sisältävä entiteetti, jonka mukaan segmentointi tehdään.</span><span class="sxs-lookup"><span data-stu-id="bcdca-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="bcdca-122">Valitse segmentointiperusteen määrite.</span><span class="sxs-lookup"><span data-stu-id="bcdca-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="bcdca-123">Tällä määritteellä voi olla jokin neljästä arvotyypistä: numeerinen, merkkijono, päivämäärä tai totuusarvo.</span><span class="sxs-lookup"><span data-stu-id="bcdca-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="bcdca-124">Valitse operaattori ja arvo valitulle määritteelle.</span><span class="sxs-lookup"><span data-stu-id="bcdca-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bcdca-125">![Mukautettu ryhmäsuodatin](media/customer-group-numbers.png "Asiakkaan ryhmäsuodatin")</span><span class="sxs-lookup"><span data-stu-id="bcdca-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="bcdca-126">Luku</span><span class="sxs-lookup"><span data-stu-id="bcdca-126">Number</span></span> |<span data-ttu-id="bcdca-127">Määritelmä</span><span class="sxs-lookup"><span data-stu-id="bcdca-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="bcdca-128">1</span><span class="sxs-lookup"><span data-stu-id="bcdca-128">1</span></span>     |<span data-ttu-id="bcdca-129">Entity</span><span class="sxs-lookup"><span data-stu-id="bcdca-129">Entity</span></span>          |
   |<span data-ttu-id="bcdca-130">2</span><span class="sxs-lookup"><span data-stu-id="bcdca-130">2</span></span>     |<span data-ttu-id="bcdca-131">Määrite</span><span class="sxs-lookup"><span data-stu-id="bcdca-131">Attribute</span></span>          |
   |<span data-ttu-id="bcdca-132">3</span><span class="sxs-lookup"><span data-stu-id="bcdca-132">3</span></span>    |<span data-ttu-id="bcdca-133">Operaattori</span><span class="sxs-lookup"><span data-stu-id="bcdca-133">Operator</span></span>         |
   |<span data-ttu-id="bcdca-134">4</span><span class="sxs-lookup"><span data-stu-id="bcdca-134">4</span></span>    |<span data-ttu-id="bcdca-135">Arvo</span><span class="sxs-lookup"><span data-stu-id="bcdca-135">Value</span></span>         |

8. <span data-ttu-id="bcdca-136">Jos entiteetti on yhdistetty yhdistettyyn asiakaskohteeseen [suhteen](relationships.md) kautta , sinun täytyy määrittää suhdepolku, jotta voit luoda kelvollisen segmentin.</span><span class="sxs-lookup"><span data-stu-id="bcdca-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="bcdca-137">Lisää entiteetit suhdepolusta, kunnes voit valita **Asiakas : CustomerInsights** -entiteetin avattavasta luettelosta.</span><span class="sxs-lookup"><span data-stu-id="bcdca-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="bcdca-138">Valitse sitten jokaisessa ehdossa **Kaikki tietueet**.</span><span class="sxs-lookup"><span data-stu-id="bcdca-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bcdca-139">![Suhdepolku segmentin luonnin aikana](media/segments-multiple-relationships.png "Suhdepolku segmentin luonnin aikana")</span><span class="sxs-lookup"><span data-stu-id="bcdca-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="bcdca-140">Tallenna segmentti valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="bcdca-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="bcdca-141">Segmentti tallennetaan ja käsitellään, jos kaikki vaatimukset on vahvistettu.</span><span class="sxs-lookup"><span data-stu-id="bcdca-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="bcdca-142">Muussa tapauksessa se tallennetaan luonnoksena.</span><span class="sxs-lookup"><span data-stu-id="bcdca-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="bcdca-143">Valitse **Palaa segmentteihin**, jos haluat siirtyä takaisin **Segmentit**-sivulle.</span><span class="sxs-lookup"><span data-stu-id="bcdca-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="bcdca-144">Aiemmin luotujen segmenttien hallinta</span><span class="sxs-lookup"><span data-stu-id="bcdca-144">Manage existing segments</span></span>

<span data-ttu-id="bcdca-145">**Segmentit**-sivulla voit tarkastella kaikkia tallennettuja segmenttejä ja hallita niitä.</span><span class="sxs-lookup"><span data-stu-id="bcdca-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="bcdca-146">Jokaista segmenttiä edustaa rivi, joka sisältää segmentin lisätietoja.</span><span class="sxs-lookup"><span data-stu-id="bcdca-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="bcdca-147">Voit lajitella sarakkeen segmentit valitsemalla sarakeotsikon.</span><span class="sxs-lookup"><span data-stu-id="bcdca-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="bcdca-148">Voit suodattaa segmenttejä oikeassa yläkulmassa olevan **Haku**-ruudun avulla.</span><span class="sxs-lookup"><span data-stu-id="bcdca-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bcdca-149">![Aiemmin luodun segmentin hallintavaihtoehdot](media/segments-selected-segment.png "Aiemmin luodun segmentin hallintavaihtoehdot")</span><span class="sxs-lookup"><span data-stu-id="bcdca-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="bcdca-150">Seuraava toiminto on käytettävissä, kun valitse segmentin:</span><span class="sxs-lookup"><span data-stu-id="bcdca-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="bcdca-151">**Näytä** segmentin tietoja, mukaan lukien jäsenmäärän trendi, segmentin jäsenten esikatselu.</span><span class="sxs-lookup"><span data-stu-id="bcdca-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="bcdca-152">**Muokkaa** segmenttiä, jos haluat muuttaa sen ominaisuuksia.</span><span class="sxs-lookup"><span data-stu-id="bcdca-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="bcdca-153">**Päivitä** segmentti siten, että se sisältää uusimmat tiedot.</span><span class="sxs-lookup"><span data-stu-id="bcdca-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="bcdca-154">**Aktivoi** segmentti tai **Poista aktivointi**.</span><span class="sxs-lookup"><span data-stu-id="bcdca-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="bcdca-155">Segmenteillä on kaksi mahdollista tilaa: aktiivinen ja passiivinen.</span><span class="sxs-lookup"><span data-stu-id="bcdca-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="bcdca-156">Näistä tiloista on hyötyä segmenttiä muokattaessa.</span><span class="sxs-lookup"><span data-stu-id="bcdca-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="bcdca-157">Passiivisissa segmenteissä on segmentin määritelmä, mutta se ei sisällä vielä asiakkaita.</span><span class="sxs-lookup"><span data-stu-id="bcdca-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="bcdca-158">Kun segmentti aktivoidaan, tila muuttuu passiivisesta aktiivisesti ja se aloittaa segmentin määritelmää vastaavien asiakkaiden etsimisen.</span><span class="sxs-lookup"><span data-stu-id="bcdca-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="bcdca-159">Jos [aikataulutettu päivitys](system.md#schedule-tab) on määritetty, passiivisten segmenttien **Tila**-arvon on **Ohitettu**, mikä osoittaa, että päivitystä ei edes yritetty.</span><span class="sxs-lookup"><span data-stu-id="bcdca-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="bcdca-160">Kun passiivinen segmentti aktivoidaan, se päivittyy ja se sisällytetään aikataulutettuihin päivityksiin.</span><span class="sxs-lookup"><span data-stu-id="bcdca-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="bcdca-161">Voit vaihtoehtoisesti määrittää tulevan päivämäärän ja kellonajan tietyn segmentin aktivointiin ja aktivoinnin poistamiseen avattavan **Aktivoi / Poista aktivointi** -valikon **Ajoita myöhemmin** -toiminnolla.</span><span class="sxs-lookup"><span data-stu-id="bcdca-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="bcdca-162">**Nimeä uudelleen** segmentti.</span><span class="sxs-lookup"><span data-stu-id="bcdca-162">**Rename** the segment.</span></span>
- <span data-ttu-id="bcdca-163">**Lataa** jäsenten luettelo CSV-tiedostona.</span><span class="sxs-lookup"><span data-stu-id="bcdca-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="bcdca-164">**Lisää kohteeseen** -vaihtoehto lähettää segmentin asiakastunnusten luettelon toiseen sovelluksen käsiteltäväksi.</span><span class="sxs-lookup"><span data-stu-id="bcdca-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="bcdca-165">**Poista** segmentti.</span><span class="sxs-lookup"><span data-stu-id="bcdca-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="bcdca-166">Päivitä segmentit</span><span class="sxs-lookup"><span data-stu-id="bcdca-166">Refresh segments</span></span>

<span data-ttu-id="bcdca-167">Voit päivittää kaikki segmentit kerralla valitsemalla **Päivitä kaikki** **Segmentit**-sivulla. Halutessasi voit päivittää yhden tai useita segmenttejä, kun valitset ne ja valitse sitten **Päivitä** asetuksista.</span><span class="sxs-lookup"><span data-stu-id="bcdca-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="bcdca-168">Voit myös määrittää toistuvan päivityksen kohdassa **Järjestelmänvalvoja** > **Järjestelmä** > **Ajoita**.</span><span class="sxs-lookup"><span data-stu-id="bcdca-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="bcdca-169">Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="bcdca-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="bcdca-170">Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="bcdca-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="bcdca-171">Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja.</span><span class="sxs-lookup"><span data-stu-id="bcdca-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="bcdca-172">Kun työn jossakin tehtävissä on valittu **Näytä tiedot**, saat lisätietoja: käsittelyajan, viimeisimmän käsittelypäivämäärän sekä kaikki tehtävään liitetyt virheet ja varoitukset.</span><span class="sxs-lookup"><span data-stu-id="bcdca-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="bcdca-173">Segmenttien lataaminen ja vieminen</span><span class="sxs-lookup"><span data-stu-id="bcdca-173">Download and export segments</span></span>

<span data-ttu-id="bcdca-174">Voit ladata segmenttejäsi CSV-tiedostoon tai viedä ne Dynamics 365 Salesiin.</span><span class="sxs-lookup"><span data-stu-id="bcdca-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="bcdca-175">Segmenttien lataaminen CSV-tiedostoon</span><span class="sxs-lookup"><span data-stu-id="bcdca-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="bcdca-176">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Segmentit**-sivu.</span><span class="sxs-lookup"><span data-stu-id="bcdca-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="bcdca-177">Valitse tietyn segmentin ruudussa kolme pistettä.</span><span class="sxs-lookup"><span data-stu-id="bcdca-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="bcdca-178">Valitse **Lataa CSV-tiedostona** toimintojen avattavasta luettelosta.</span><span class="sxs-lookup"><span data-stu-id="bcdca-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="bcdca-179">Segmenttien vieminen Dynamics 365 Salesiin</span><span class="sxs-lookup"><span data-stu-id="bcdca-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="bcdca-180">Ennen segmenttien viemistä Dynamics 365 Salesiin järjestelmänvalvojan on [luotava vientikohde](export-destinations.md) Dynamics 365 Salesille.</span><span class="sxs-lookup"><span data-stu-id="bcdca-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="bcdca-181">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Segmentit**-sivu.</span><span class="sxs-lookup"><span data-stu-id="bcdca-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="bcdca-182">Valitse tietyn segmentin ruudussa kolme pistettä.</span><span class="sxs-lookup"><span data-stu-id="bcdca-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="bcdca-183">Valitse **Lisää kohteeseen** avattavasta toimintoluettelosta ja valitse sitten vientikohde, johon haluat lähettää tiedot.</span><span class="sxs-lookup"><span data-stu-id="bcdca-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="bcdca-184">Segmenttien luonnostila</span><span class="sxs-lookup"><span data-stu-id="bcdca-184">Draft mode for segments</span></span>

<span data-ttu-id="bcdca-185">Jos kaikkia segmentin käsittelyssä tarvittavat vaatimukset eivät täyty, voit tallentaa segmentin luonnoksena ja käyttää sitä **Segmentit**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="bcdca-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="bcdca-186">Se tallennetaan passiivisena segmenttinä, eikä sitä voi aktivoida, ennen kuin se on kelvollinen.</span><span class="sxs-lookup"><span data-stu-id="bcdca-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="bcdca-187">Lisää ryhmään ehtoja</span><span class="sxs-lookup"><span data-stu-id="bcdca-187">Add more conditions to a group</span></span>

<span data-ttu-id="bcdca-188">Jos haluat lisätä ryhmään ehtoja, voit käyttää seuraavaa kahta loogista operaattoria:</span><span class="sxs-lookup"><span data-stu-id="bcdca-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="bcdca-189">**JA**-operaattori: Molempien ehtojen on täytyttävä segmentointiprosessin aikana.</span><span class="sxs-lookup"><span data-stu-id="bcdca-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="bcdca-190">Tämä vaihtoehto on hyödyllinen, kun määrität ehtoja eri entiteeteille.</span><span class="sxs-lookup"><span data-stu-id="bcdca-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="bcdca-191">**TAI**-operaattori: Jommankumman ehdoista on täytyttävä segmentointiprosessin aikana.</span><span class="sxs-lookup"><span data-stu-id="bcdca-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="bcdca-192">Tämä vaihtoehto on hyödyllinen, kun määrität useita ehtoja samalle entiteetille.</span><span class="sxs-lookup"><span data-stu-id="bcdca-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bcdca-193">![TAI-operaattori, jossa jommankumman ehdoista on täytyttävä](media/segmentation-either-condition.png "TAI-operaattori, jossa jommankumman ehdoista on täytyttävä")</span><span class="sxs-lookup"><span data-stu-id="bcdca-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="bcdca-194">Tällä hetkellä on mahdollista upottaa **TAI**-operaattoria **JA**-operaattorin sisään, mutta ei toisin päin.</span><span class="sxs-lookup"><span data-stu-id="bcdca-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="bcdca-195">Yhdistä useita ryhmiä</span><span class="sxs-lookup"><span data-stu-id="bcdca-195">Combine multiple groups</span></span>

<span data-ttu-id="bcdca-196">Kukin ryhmä tuottaa tietyn asiakasjoukon.</span><span class="sxs-lookup"><span data-stu-id="bcdca-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="bcdca-197">Voit yhdistää nämä ryhmät niin, että ne sisältävät liiketoimintatapaukseesi tarvittavat asiakkaat.</span><span class="sxs-lookup"><span data-stu-id="bcdca-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="bcdca-198">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Segmentit**-sivu ja valitse sitten segmentti.</span><span class="sxs-lookup"><span data-stu-id="bcdca-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="bcdca-199">Valitse **Lisää ryhmä**.</span><span class="sxs-lookup"><span data-stu-id="bcdca-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bcdca-200">![Asiakasryhmä - lisää ryhmä](media/customer-group-add-group.png "Asiakasryhmä - lisää ryhmä")</span><span class="sxs-lookup"><span data-stu-id="bcdca-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="bcdca-201">Valitse jokin seuraavista operaattoreista: **Unioni**, **Leikkaus** tai **Lukuun ottamatta**.</span><span class="sxs-lookup"><span data-stu-id="bcdca-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bcdca-202">![Asiakasryhmä - lisää liitos](media/customer-group-union.png "Asiakasryhmä - lisää liitos")</span><span class="sxs-lookup"><span data-stu-id="bcdca-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="bcdca-203">Määritä uusi ryhmä valitsemalla joukko-operaattori.</span><span class="sxs-lookup"><span data-stu-id="bcdca-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="bcdca-204">Eri ryhmien tallentaminen määrittää säilytettävät tiedot:</span><span class="sxs-lookup"><span data-stu-id="bcdca-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="bcdca-205">**Liitos** yhdistää kaksi ryhmää.</span><span class="sxs-lookup"><span data-stu-id="bcdca-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="bcdca-206">**Leikkaa** asettaa kaksi ryhmää päällekkäin.</span><span class="sxs-lookup"><span data-stu-id="bcdca-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="bcdca-207">Vain molemmille ryhmille *yhteiset* tiedot säilytetään yhdistetyssä ryhmässä.</span><span class="sxs-lookup"><span data-stu-id="bcdca-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="bcdca-208">**Lukuun ottamatta** yhdistää kaksi ryhmää.</span><span class="sxs-lookup"><span data-stu-id="bcdca-208">**Except** combines the two groups.</span></span> <span data-ttu-id="bcdca-209">Vain ryhmän A tiedot, jotka *eivät ole yhteisiä* ryhmän B tietojen kanssa, säilytetään.</span><span class="sxs-lookup"><span data-stu-id="bcdca-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="bcdca-210">Tarkastele käsittelyhistoriaa ja segmentin jäseniä</span><span class="sxs-lookup"><span data-stu-id="bcdca-210">View processing history and segment members</span></span>

<span data-ttu-id="bcdca-211">Voit tarkastella segmentin yhdistettyjä tietoja tarkastelemalla sen tietoja.</span><span class="sxs-lookup"><span data-stu-id="bcdca-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="bcdca-212">Valitse **Segmentit**-sivulla segmentti, jota haluat tarkastella.</span><span class="sxs-lookup"><span data-stu-id="bcdca-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="bcdca-213">Sivun yläosassa on trendikaavio, joka visualisoi jäsenmäärän muutokset.</span><span class="sxs-lookup"><span data-stu-id="bcdca-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="bcdca-214">Vie kohdistin arvopisteiden päälle, jos haluat nähdä tietyn päivämäärän jäsenmäärän.</span><span class="sxs-lookup"><span data-stu-id="bcdca-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="bcdca-215">Voit päivittää visualisoinnin aikavälin.</span><span class="sxs-lookup"><span data-stu-id="bcdca-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bcdca-216">![Segmentin aikaväli](media/segment-time-range.png "Segmentin aikaväli")</span><span class="sxs-lookup"><span data-stu-id="bcdca-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="bcdca-217">Alaosassa on luettelo segmentin jäsenistä.</span><span class="sxs-lookup"><span data-stu-id="bcdca-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="bcdca-218">Tässä luettelossa näkyvät kentät perustuvat segmentin entiteettien määritteisiin.</span><span class="sxs-lookup"><span data-stu-id="bcdca-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="bcdca-219">Luettelo on täsmäävien segmentin jäsenten esikatselu. Siinä näkyvät segmentin ensimmäiset 100 tietuetta, joten voit nopeasti arvioida segmentin ja tarkistaa sen määritykset tarpeen mukaan.</span><span class="sxs-lookup"><span data-stu-id="bcdca-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="bcdca-220">Jos haluat nähdä kaikki täsmäävät tietueet, sinun on [vietävä segmentti](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="bcdca-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="bcdca-221">Pikasegmentit</span><span class="sxs-lookup"><span data-stu-id="bcdca-221">Quick segments</span></span>

<span data-ttu-id="bcdca-222">Segmentin muodostimen lisäksi segmenttejä voi luoda myös toisella tavalla.</span><span class="sxs-lookup"><span data-stu-id="bcdca-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="bcdca-223">Pikasegmenttien avulla voit luoda yksinkertaisia segmenttejä yhdellä operaattorilla nopeasti ja saat analyysit heti käyttöösi.</span><span class="sxs-lookup"><span data-stu-id="bcdca-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="bcdca-224">Valitse **Segmentit**-sivulla **Uusi** > **Pikaluontilomake**.</span><span class="sxs-lookup"><span data-stu-id="bcdca-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="bcdca-225">Valitse **Profiilit**-vaihtoehto, jos haluat muodostaa segmentin, joka perustuu yhdistettyyn asiakasentiteettiin.</span><span class="sxs-lookup"><span data-stu-id="bcdca-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="bcdca-226">Valitse **Mittarit**-vaihtoehto, jos haluat muodostaa segmentin kunkin aiemmin **Mittarit**-sivulla luotujen asiakasmääritetyyppisten mittareiden ympärille.</span><span class="sxs-lookup"><span data-stu-id="bcdca-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="bcdca-227">Valitse **Analytiikka**-asetus, jos haluat luoda segmentin, joka on luotu käyttämällä joko **Ennusteet**-tai **Mukautetut mallit** -ominaisuuden avulla luotuja tuloskohteita.</span><span class="sxs-lookup"><span data-stu-id="bcdca-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="bcdca-228">Valitse **Uusi pikasegmentti** -valintaikkunasta määrite avattavasta **Kenttä**-valikosta.</span><span class="sxs-lookup"><span data-stu-id="bcdca-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="bcdca-229">Järjestelmä tarjoaa lisätietoja, joiden avulla voit aiempaa helpommin luoda asiakkaille segmenttejä.</span><span class="sxs-lookup"><span data-stu-id="bcdca-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="bcdca-230">Luokkakentille näytetään 10 parasta asiakasmäärää.</span><span class="sxs-lookup"><span data-stu-id="bcdca-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="bcdca-231">Valitse **Arvo** ja valitse sitten **Tarkista**.</span><span class="sxs-lookup"><span data-stu-id="bcdca-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="bcdca-232">Jos määrite on numeerinen, järjestelmä näyttää, mikä määrite kuuluu mihinkin asiakasprosenttipisteeseen.</span><span class="sxs-lookup"><span data-stu-id="bcdca-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="bcdca-233">Valitse **Operaattori** ja **Arvo** ja valitse sitten **Tarkista**.</span><span class="sxs-lookup"><span data-stu-id="bcdca-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="bcdca-234">Järjestelmä näyttää **arvioidun segmentin koon**.</span><span class="sxs-lookup"><span data-stu-id="bcdca-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="bcdca-235">Voit määrittää, luodaanko määritetty segmentti vai avataanko sen ensin, jolloin voit määrittää toisen segmentin koon.</span><span class="sxs-lookup"><span data-stu-id="bcdca-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bcdca-236">![Nopean segmentin nimi ja arvioi](media/quick-segment-name.png "Nopean segmentin nimi ja arvioi")</span><span class="sxs-lookup"><span data-stu-id="bcdca-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="bcdca-237">Anna segmentille **nimi**.</span><span class="sxs-lookup"><span data-stu-id="bcdca-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="bcdca-238">Vaihtoehtoisesti voit antaa **näyttönimen**.</span><span class="sxs-lookup"><span data-stu-id="bcdca-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="bcdca-239">Luo segmentti valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="bcdca-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="bcdca-240">Kun segmentin käsittely on valmis, voit tarkistaa sen kuten minkä tahansa luodun segmentin.</span><span class="sxs-lookup"><span data-stu-id="bcdca-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="bcdca-241">Seuraavissa skenaarioissa suosittelemme käyttämään segmentin muodostinta suositeltujen segmentin ominaisuuksien sijaan seuraavalla tavalla:</span><span class="sxs-lookup"><span data-stu-id="bcdca-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="bcdca-242">Luodaan segmenttejä suodattimien avulla kategorisissa kentissä, joissa operaattori on eri kuin **On**-operaattori</span><span class="sxs-lookup"><span data-stu-id="bcdca-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="bcdca-243">Luodaan segmenttejä suodattimien avulla numeerisissa kentissä, joissa operaattori on eri kuin **Välissä**, **Suurempi kuin**- ja **Pienempi kuin** -operaattorit</span><span class="sxs-lookup"><span data-stu-id="bcdca-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="bcdca-244">Sellaisten segmenttien luominen, joissa on suodattimia päivämäärätyyppikentissä</span><span class="sxs-lookup"><span data-stu-id="bcdca-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="bcdca-245">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="bcdca-245">Next steps</span></span>

<span data-ttu-id="bcdca-246">[Vie segmentti](export-destinations.md) ja tutustu [asiakaskorttiin](customer-card-add-in.md) ja [yhdistimiin](export-power-bi.md), jotta saat asiakastason tietoja.</span><span class="sxs-lookup"><span data-stu-id="bcdca-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
