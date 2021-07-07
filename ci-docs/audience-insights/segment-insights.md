---
title: Aiemmin luotujen segmenttien segmentin merkitykselliset tiedot
description: Aiemmin luotujen segmenttien merkityksellisten tietojen erot ja yhteneväisyydet ovat nähtävissä.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2856888d6ac64d5daabcc5a234f13bc6f88bb3df
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306070"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="3c4d7-103">Segmentin merkitykselliset tiedot (esiversio)</span><span class="sxs-lookup"><span data-stu-id="3c4d7-103">Segment insights (preview)</span></span>

<span data-ttu-id="3c4d7-104">Tutustu olemassa olevien segmenttien tärkeisiin ja merkityksellisiin tietoihin.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="3c4d7-105">Selvitä, mikä erottaa toisistaan kaksi segmenttiä tai mitä yhteistä niillä on.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="3c4d7-106">Segmenttien päällekkäisyys</span><span class="sxs-lookup"><span data-stu-id="3c4d7-106">Segment overlap</span></span>

<span data-ttu-id="3c4d7-107">Segmenttien päällekkäisyysanalyysi osoittaa, kuinka monta ja mitkä asiakkaat ovat yhteisiä kahdelle tai useammalle segmentille.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="3c4d7-108">Esimerkiksi se, miten säännöllisesti ostavat asiakkaat ovat päällekkäisiä sellaisen segmentin kanssa, joka sisältää palvelua tai tuotetta koskevia tyytyväisiä asiakkaita.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="3c4d7-109">Voit myös analysoida, miten päällekkäisyys muuttuu tietyillä määritteillä.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="3c4d7-110">Päällekkäisyys analyysin suorittaminen</span><span class="sxs-lookup"><span data-stu-id="3c4d7-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="3c4d7-111">Siirry kohtaan **Segmentit** ja valitse **Merkitykselliset havainnot (esiversio)** -välilehti.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="3c4d7-112">Valitse **Uusi** ja valitse sitten **Päällekkäisyys**-asetus **Valitse merkityksellisten havaintojen tyyppi** -ruudussa.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="3c4d7-113">Valitse kiinnostavat segmentit ja valitse sitten **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="3c4d7-114">Valitse vaihtoehtoisesti yksi tai useampi kiinnostava kenttä, jos haluat analysoida jokaisen mahdollisen kentän arvon päällekkäisyydet ja valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="3c4d7-115">Anna nimi päällekkäisyysanalyysille, valinnainen näyttönimi ja kuvaus.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="3c4d7-116">Aloita analyysi valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="3c4d7-117">Päällekkäisyysanalyysi on valmis, kun tila muuttuu tilasta Päivittää tilaan Onnistui.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="3c4d7-118">Päällekkäisyysanalyysin tarkasteleminen ja optimointi</span><span class="sxs-lookup"><span data-stu-id="3c4d7-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="3c4d7-119">Kun analyysi on valmis, etsi tietoja segmenttejä koskevista merkityksellisistä havainnoista kohdassa **Segmentit** > **Merkitykselliset tiedot (esiversio)**.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Segmentin päällekkäisyysoivallusten tiedot":::

<span data-ttu-id="3c4d7-121">Valitse merkityksellinen tieto, kun haluat nähdä analyysin tulokset:</span><span class="sxs-lookup"><span data-stu-id="3c4d7-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="3c4d7-122">Niiden jäsenten määrä, jotka ovat päällekkäisiä analysoitavaksi valittujen segmenttien kanssa.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="3c4d7-123">Niiden jäsenien määrä, jotka sisältyvät yhteen segmentteihin mutta eivät muihin segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="3c4d7-124">Jos valitsit kenttiä päällekkäisyyden määrityksen määrittämisen aikana, ne löytyvät vastaavista välilehdistä.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="3c4d7-125">Voit valita minkä tahansa määritteen kiinnostuksen tason suodattimen avattavan valikon avulla. Alla olevassa taulukossa näkyvät vastaavat tiedot.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-125">You can use the filter dropdown to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="3c4d7-126">Segmentin erottimet</span><span class="sxs-lookup"><span data-stu-id="3c4d7-126">Segment differentiators</span></span>

<span data-ttu-id="3c4d7-127">Segmentin erot auttaa sinua saamaan selville, mikä erottaa segmentin muista asiakkaista tai toisesta segmentistä.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="3c4d7-128">Sinun täytyy vain valita segmentti, niin järjestelmä tunnistaa profiilimääritteet ja mittarit, jotka erottavat valitun segmentin.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="3c4d7-129">Erilaisuussanalyysin suorittaminen</span><span class="sxs-lookup"><span data-stu-id="3c4d7-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="3c4d7-130">Siirry kohtaan **Segmentit** ja valitse **Merkitykselliset havainnot (esiversio)** -välilehti.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="3c4d7-131">Valitse **Uusi** ja valitse sitten **Päällekkäisyys**-asetus **Valitse merkityksellisten havaintojen tyyppi** -ruudussa.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="3c4d7-132">Valitse segmentti, jonka haluat analysoida **ensisijaiseksi segmentiksi**, ja valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="3c4d7-133">Voit verrata ensisijaista segmenttiäsi valitsemalla **Kaikki asiakkaat** tai **Toissijainen segmentti** ja valitsemalla sitten **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="3c4d7-134">Voit vaihtoehtoisesti valita yhden tai useita kiinnostavia kenttiä, jos haluat tarkentaa analyysin tiettyihin määritteisiin ja valita **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="3c4d7-135">Anna nimi päällekkäisyysanalyysille, valinnainen näyttönimi ja kuvaus.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="3c4d7-136">Aloita analyysi valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="3c4d7-137">Päällekkäisyysanalyysi on valmis, kun tila muuttuu tilasta Päivittää tilaan Onnistui.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="3c4d7-138">Erilaisuusanalyysin tarkasteleminen ja optimointi</span><span class="sxs-lookup"><span data-stu-id="3c4d7-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="3c4d7-139">Kun analyysi on valmis, etsi tietoja segmenttejä koskevista merkityksellisistä havainnoista kohdassa **Segmentit** > **Merkitykselliset tiedot (esiversio)**.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Segmentin erilaisuusoivallusten tiedot":::

<span data-ttu-id="3c4d7-141">Valitse merkityksellinen tieto, kun haluat nähdä analyysin tulokset.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="3c4d7-142">Erilaisuusanalyysi sisältää kaksi välilehteä.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="3c4d7-143">**Määritteet**-välilehdessä on luettelo profiilimääritteistä, joita pidetään erottavinä tekijöinä.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="3c4d7-144">**Mittarit**-välilehdessä on lueteltu erottavat tekijät.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="3c4d7-145">Jokaisessa välilehdessä on seuraavat tiedot:</span><span class="sxs-lookup"><span data-stu-id="3c4d7-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="3c4d7-146">Paremmuusjärjestykseen jaoteltu luettelo erottavista tekijöistä eropisteiden järjestyksessä.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="3c4d7-147">Kun erottavan tekijän **erilaisuuspisteet**.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="3c4d7-148">Erilaisuuspisteet edustavat kahden segmentin välisen määritteen eron astetta.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="3c4d7-149">Mitä suurempi ero on, sitä enemmän määritteet eroavat toisistaan segmenttien välillä.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="3c4d7-150">Valitsemalla pistemäärän voit avata **Erilaisuuspisteet**-ruudun, jossa on kyseisen määritteen arvojen jakaumat.</span><span class="sxs-lookup"><span data-stu-id="3c4d7-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="3c4d7-151">Segmentin merkityksellisten tietojen hallinta</span><span class="sxs-lookup"><span data-stu-id="3c4d7-151">Manage segment insights</span></span>

<span data-ttu-id="3c4d7-152">Voit käyttää seuraavia vaihtoehtoja komentopalkissa oivallusten käsittelyyn:</span><span class="sxs-lookup"><span data-stu-id="3c4d7-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="3c4d7-153">**Palaa**, kun haluat palauta mekrkityksellisten tietojen luetteloon</span><span class="sxs-lookup"><span data-stu-id="3c4d7-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="3c4d7-154">**Päivitä**, jos haluat suorittaa analyysin uudelleen</span><span class="sxs-lookup"><span data-stu-id="3c4d7-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="3c4d7-155">**Poista**, jos haluat poistaa tämän merkityksellisen tiedon</span><span class="sxs-lookup"><span data-stu-id="3c4d7-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]