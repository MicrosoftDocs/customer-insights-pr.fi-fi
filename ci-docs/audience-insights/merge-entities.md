---
title: Entiteettien yhdistäminen tietoja yhtenäistettäessä
description: Yhtenäisten asiakasprofiilien luominen yhdistämällä entiteettejä.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4ad06a0baf57e612fc0e0214dfd23d28e7d2b6be
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896507"
---
# <a name="merge-entities"></a><span data-ttu-id="42b0c-103">Entiteettien yhdistäminen</span><span class="sxs-lookup"><span data-stu-id="42b0c-103">Merge entities</span></span>

<span data-ttu-id="42b0c-104">Yhdistämisvaihe on tietojen yhdistämisprosessin viimeinen vaihe.</span><span class="sxs-lookup"><span data-stu-id="42b0c-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="42b0c-105">Sen tarkoitus on täsmäyttää ristiriitaiset tiedot.</span><span class="sxs-lookup"><span data-stu-id="42b0c-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="42b0c-106">Esimerkkejä ristiriitaisista tiedoista ovat esimerkiksi asiakkaan nimi, joka on kahdessa tietojoukossa hieman eri tavalla (esimerkiksi Grant Marshall ja Grant Marshal) ja puhelinnumero, jonka muodot ovat erilaiset (esimerkiksi 617-803-091X ja 617803091X).</span><span class="sxs-lookup"><span data-stu-id="42b0c-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="42b0c-107">Näiden ristiriitaisten arvopisteiden yhdistäminen tapahtuu määrite kerrallaan.</span><span class="sxs-lookup"><span data-stu-id="42b0c-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="42b0c-108">Kun [täsmäytysvaihe](match-entities.md) on suoritettu, voit aloittaa yhdistämisvaiheen valitsemalla **Yhdistä**-ruudun **Yhdistäminen**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="42b0c-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="42b0c-109">Tarkista järjestelmän suositukset</span><span class="sxs-lookup"><span data-stu-id="42b0c-109">Review system recommendations</span></span>

<span data-ttu-id="42b0c-110">**Yhdistäminen**-sivulla voit valita määritteitä yhdistettäväksi yhdistettyä asiakasprofiilientiteettiä (määritysprosessin tulos) varten tai poistaa määritteitä yhdistämisprosessista.</span><span class="sxs-lookup"><span data-stu-id="42b0c-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="42b0c-111">Järjestelmä yhdistää jotkin määritteet automaattisesti.</span><span class="sxs-lookup"><span data-stu-id="42b0c-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="42b0c-112">Tarkastele yhdistettyjä määritteitä</span><span class="sxs-lookup"><span data-stu-id="42b0c-112">View merged attributes</span></span>

<span data-ttu-id="42b0c-113">Voit tarkastella määritteitä, jotka sisältyvät yhteen automaattisesti yhdistettyyn määritteeseen valitsemalla kyseisen yhdistetyn määritteen.</span><span class="sxs-lookup"><span data-stu-id="42b0c-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="42b0c-114">Kaksi määritettä, jotka muodostavat yhdistetyn määritteen, näkyvät yhdistetyn määritteen alapuolella kahdella uudelle rivillä.</span><span class="sxs-lookup"><span data-stu-id="42b0c-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="42b0c-115">![Valitse yhdistetty määrite](media/configure-data-merge-profile-attributes.png "Valitse yhdistetty määrite")</span><span class="sxs-lookup"><span data-stu-id="42b0c-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="42b0c-116">Erottele yhdistetyt määritteet</span><span class="sxs-lookup"><span data-stu-id="42b0c-116">Separate merged attributes</span></span>

<span data-ttu-id="42b0c-117">Jos haluat erotella automaattisesti yhdistettyjä määritteitä tai poistaa niiden yhdistämisen, etsi määrite **Profiilimääritteet**-taulukosta.</span><span class="sxs-lookup"><span data-stu-id="42b0c-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="42b0c-118">Valitse kolme pistettä (...) -painike.</span><span class="sxs-lookup"><span data-stu-id="42b0c-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="42b0c-119">Valitse avattavasta luettelosta **Erottele kentät**.</span><span class="sxs-lookup"><span data-stu-id="42b0c-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="42b0c-120">Poista yhdistetyt määritteet</span><span class="sxs-lookup"><span data-stu-id="42b0c-120">Remove merged attributes</span></span>

<span data-ttu-id="42b0c-121">Jos haluat poistaa määritteen lopullisesta asiakasprofiilientiteetistä, etsi se **Profiilimääritteet**-taulukosta.</span><span class="sxs-lookup"><span data-stu-id="42b0c-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="42b0c-122">Valitse kolme pistettä (...) -painike.</span><span class="sxs-lookup"><span data-stu-id="42b0c-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="42b0c-123">Valitse avattavasta luettelosta **Älä yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="42b0c-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="42b0c-124">Määrite siirretään **Poistettu asiakastietueesta** -osaan.</span><span class="sxs-lookup"><span data-stu-id="42b0c-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="42b0c-125">Lisää yhdistetty määrite manuaalisesti</span><span class="sxs-lookup"><span data-stu-id="42b0c-125">Manually add a merged attribute</span></span>

<span data-ttu-id="42b0c-126">Jos haluat lisätä yhdistetyn määritteen, siirry **Yhdistäminen**-sivulle.</span><span class="sxs-lookup"><span data-stu-id="42b0c-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="42b0c-127">Valitse **Lisää yhdistetty määrite**.</span><span class="sxs-lookup"><span data-stu-id="42b0c-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="42b0c-128">Anna **nimi**, joka määrittää määritteen **Yhdistäminen**-sivulla myöhemmin.</span><span class="sxs-lookup"><span data-stu-id="42b0c-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="42b0c-129">Vaihtoehtoisesti voit myös antaa **näyttönimen**, joka näkyy yhdistetyssä asiakasprofiilientiteetissä.</span><span class="sxs-lookup"><span data-stu-id="42b0c-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="42b0c-130">Määritä **Valitse määritteiden kaksoiskappaleet**, jos haluat valita määritteet, jotka haluat yhdistää täsmäytetyistä entiteeteistä.</span><span class="sxs-lookup"><span data-stu-id="42b0c-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="42b0c-131">Voit myös hakea määritteitä.</span><span class="sxs-lookup"><span data-stu-id="42b0c-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="42b0c-132">Määritä **Arvioi tärkeyden mukaan**, jos haluat määrittää jonkin määritteen tärkeämmäksi kuin toiset.</span><span class="sxs-lookup"><span data-stu-id="42b0c-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="42b0c-133">Jos esimerkiksi *WebAccountCSV*-entiteetti sisältää tarkat tiedot *Täydelliset nimet* -määritteestä, voit määrittää tämän entiteetin tärkeämmäksi kuin *ContactCSV* valitsemalla *WebAccountCSV*-entiteetin.</span><span class="sxs-lookup"><span data-stu-id="42b0c-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="42b0c-134">Tuloksena *WebAccountCSV* siirtyy ensimmäiseksi prioriteetin mukaan, kun taas *ContactCSV* siirretään toiseksi prioriteetin mukaan, kun haetaan ovat *Täydellinen nimi* -määritteen arvot.</span><span class="sxs-lookup"><span data-stu-id="42b0c-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="42b0c-135">Suorita yhdistäminen</span><span class="sxs-lookup"><span data-stu-id="42b0c-135">Run your merge</span></span>

<span data-ttu-id="42b0c-136">Jos yhdistät määritteet manuaalisesti tai annat järjestelmän yhdistää ne, voit aina suorittaa yhdistämisen.</span><span class="sxs-lookup"><span data-stu-id="42b0c-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="42b0c-137">Valitse **Suorita** **Yhdistäminen**-sivulla, jos haluat aloittaa prosessin.</span><span class="sxs-lookup"><span data-stu-id="42b0c-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="42b0c-138">![Tietojen yhdistämisen tallennus- ja suoritustoiminto](media/configure-data-merge-save-run.png "Tietojen yhdistämisen tallennus- ja suoritustoiminto")</span><span class="sxs-lookup"><span data-stu-id="42b0c-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="42b0c-139">Jos haluat tehdä lisää muutoksia ja suorittaa vaiheen uudelleen, voit peruuttaa meneillään olevan yhdistämisen.</span><span class="sxs-lookup"><span data-stu-id="42b0c-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="42b0c-140">Valitse **Pävitetään...**-teksti ja valitse sitten **Peruuta työ** näkyviin tulevassa reunaruudussa.</span><span class="sxs-lookup"><span data-stu-id="42b0c-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="42b0c-141">Kun **Päivitetään...** -teksti muuttuu tekstiksi **Onnistui**, yhdistäminen on suorittanut ja ratkaissut ristiriidat tiedoissa määritettyjen käytäntöjen mukaisesti.</span><span class="sxs-lookup"><span data-stu-id="42b0c-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="42b0c-142">Yhdistetyt ja yhdistämättömät määritteet sisällytetään yhdistettyyn profiilientiteettiin.</span><span class="sxs-lookup"><span data-stu-id="42b0c-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="42b0c-143">Pois jätettyjä määritteitä ei sisällytetä yhdistettyyn profiilientiteettiin.</span><span class="sxs-lookup"><span data-stu-id="42b0c-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="42b0c-144">Jos yhdistäminen oli suoritettu onnistunessti jo aiemmin, kaikki loppupään prosessit, kuten rikastus, segmentointi ja mittaaminen, suoritetaan automaattisesti uudelleen.</span><span class="sxs-lookup"><span data-stu-id="42b0c-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="42b0c-145">Kun kaikki loppupään prosessit on suoritettu uudelleen, asiakasprofiilit vastaavat tekemiäsi muutoksia.</span><span class="sxs-lookup"><span data-stu-id="42b0c-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="42b0c-146">Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="42b0c-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="42b0c-147">Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="42b0c-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="42b0c-148">Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja.</span><span class="sxs-lookup"><span data-stu-id="42b0c-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="42b0c-149">Kun työn jossakin tehtävissä on valittu **Näytä tiedot**, saat lisätietoja: käsittelyajan, viimeisimmän käsittelypäivämäärän sekä kaikki tehtävään liitetyt virheet ja varoitukset.</span><span class="sxs-lookup"><span data-stu-id="42b0c-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="42b0c-150">Seuraava vaihe</span><span class="sxs-lookup"><span data-stu-id="42b0c-150">Next Step</span></span>

<span data-ttu-id="42b0c-151">Määritä [aktiviteetit](activities.md), [rikastaminen](enrichment-hub.md) tai [suhteet](relationships.md), jos haluat lisää merkityksellisiä tietoja asiakkaista.</span><span class="sxs-lookup"><span data-stu-id="42b0c-151">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="42b0c-152">Jos aktiviteetit, rikastaminen tai suhteet on jo määritetty tai jos segmentit on määritetty, ne käsitellään automaattisesti käyttämään uusia asiakastietoja.</span><span class="sxs-lookup"><span data-stu-id="42b0c-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]