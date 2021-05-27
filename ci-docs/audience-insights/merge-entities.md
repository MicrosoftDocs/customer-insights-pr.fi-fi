---
title: Entiteettien yhdistäminen tietoja yhtenäistettäessä
description: Yhtenäisten asiakasprofiilien luominen yhdistämällä entiteettejä.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085572"
---
# <a name="merge-entities"></a><span data-ttu-id="19379-103">Entiteettien yhdistäminen</span><span class="sxs-lookup"><span data-stu-id="19379-103">Merge entities</span></span>

<span data-ttu-id="19379-104">Yhdistämisvaihe on tietojen yhdistämisprosessin viimeinen vaihe.</span><span class="sxs-lookup"><span data-stu-id="19379-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="19379-105">Sen tarkoitus on täsmäyttää ristiriitaiset tiedot.</span><span class="sxs-lookup"><span data-stu-id="19379-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="19379-106">Esimerkkejä ristiriitaisista tiedoista ovat esimerkiksi asiakkaan nimi, joka on kahdessa tietojoukossa hieman eri tavalla (esimerkiksi Grant Marshall ja Grant Marshal) ja puhelinnumero, jonka muodot ovat erilaiset (esimerkiksi 617-803-091X ja 617803091X).</span><span class="sxs-lookup"><span data-stu-id="19379-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="19379-107">Näiden ristiriitaisten arvopisteiden yhdistäminen tapahtuu määrite kerrallaan.</span><span class="sxs-lookup"><span data-stu-id="19379-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Tietojen yhdistämisprosessin yhdistämissivu, jossa on taulukossa yhdistettyjä kenttiä, jotka määrittävät yhtenäisen asiakasprofiilin.":::

<span data-ttu-id="19379-109">Kun [täsmäytysvaihe](match-entities.md) on suoritettu, voit aloittaa yhdistämisvaiheen valitsemalla **Yhdistä**-ruudun **Yhdistäminen**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="19379-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="19379-110">Tarkista järjestelmän suositukset</span><span class="sxs-lookup"><span data-stu-id="19379-110">Review system recommendations</span></span>

<span data-ttu-id="19379-111">Voit valita ja poistaa käytöstä määritteitä, jotka yhdistetään yhdistetyn asiakasprofiilin entiteettiin kohdassa **Tiedot** > **Yhdistäminen** > **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="19379-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="19379-112">Yhtenäinen asiakasprofiili on tietojen yhdistämisprosessin tulos.</span><span class="sxs-lookup"><span data-stu-id="19379-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="19379-113">Järjestelmä yhdistää jotkin määritteet automaattisesti.</span><span class="sxs-lookup"><span data-stu-id="19379-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="19379-114">Jos haluat tarkastella määritteitä, jotka sisältyvät automaattisesti yhdistettyyn määritteeseen, valitse kyseinen yhdistetty määrite taulukon **Asiakaskentät**-välilehdessä.</span><span class="sxs-lookup"><span data-stu-id="19379-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="19379-115">Määritteet, jotka muodostavat yhdistetyn määritteen, näkyvät yhdistetyn määritteen alapuolella kahdella uudelle rivillä.</span><span class="sxs-lookup"><span data-stu-id="19379-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="19379-116">Erota, nimeä uudelleen, poista käytöstä ja muokkaa yhdistettyjä kenttiä</span><span class="sxs-lookup"><span data-stu-id="19379-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="19379-117">Voit muuttaa sitä, miten järjestelmä käsittelee yhdistettyjä määritteitä muodostaakseen yhtenäisen asiakasprofiilin.</span><span class="sxs-lookup"><span data-stu-id="19379-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="19379-118">Valitse **Näytä lisää** ja valitse, mitä haluat muuttaa.</span><span class="sxs-lookup"><span data-stu-id="19379-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Valinnat Näytä lisää -pudotusvalikossa yhdistettyjen määritteiden hallintaa varten.":::

<span data-ttu-id="19379-120">Lisätietoja on seuraavissa osissa.</span><span class="sxs-lookup"><span data-stu-id="19379-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="19379-121">Erota yhdistetyt kentät</span><span class="sxs-lookup"><span data-stu-id="19379-121">Separate merged fields</span></span>

<span data-ttu-id="19379-122">Jos haluat erottaa yhdistetyt kentät, etsi määrite taulukosta.</span><span class="sxs-lookup"><span data-stu-id="19379-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="19379-123">Erotetut kentät näkyvät erillisinä arvopisteinä yhdistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="19379-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="19379-124">Valitse yhdistetty kenttä.</span><span class="sxs-lookup"><span data-stu-id="19379-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="19379-125">Valitse **Näytä lisää** ja valitse sitten **Erota kentät**.</span><span class="sxs-lookup"><span data-stu-id="19379-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="19379-126">Vahvista erottelu.</span><span class="sxs-lookup"><span data-stu-id="19379-126">Confirm the separation.</span></span>

1. <span data-ttu-id="19379-127">Valitse **Tallenna** ja **Suorita** muutosten käsittelemiseksi.</span><span class="sxs-lookup"><span data-stu-id="19379-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="19379-128">Yhdistettyjen kenttien nimeäminen uudelleen</span><span class="sxs-lookup"><span data-stu-id="19379-128">Rename merged fields</span></span>

<span data-ttu-id="19379-129">Yhdistettyjen määritteiden näyttönimen muuttaminen.</span><span class="sxs-lookup"><span data-stu-id="19379-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="19379-130">Tuloste-entiteetin nimeä ei voi muuttaa.</span><span class="sxs-lookup"><span data-stu-id="19379-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="19379-131">Valitse yhdistetty kenttä.</span><span class="sxs-lookup"><span data-stu-id="19379-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="19379-132">Valitse **Näytä lisää** ja valitse sitten **Nimeä uudelleen**.</span><span class="sxs-lookup"><span data-stu-id="19379-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="19379-133">Vahvista muutettu näyttönimi.</span><span class="sxs-lookup"><span data-stu-id="19379-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="19379-134">Valitse **Tallenna** ja **Suorita** muutosten käsittelemiseksi.</span><span class="sxs-lookup"><span data-stu-id="19379-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="19379-135">Poista yhdistettyjä kenttiä käytöstä</span><span class="sxs-lookup"><span data-stu-id="19379-135">Exclude merged fields</span></span>

<span data-ttu-id="19379-136">Poista määrite käytöstä yhdistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="19379-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="19379-137">Jos kenttää käytetään muissa prosesseissa, esimerkiksi segmentissä, poista se näistä prosesseista, ennen kuin poistat kentän asiakasprofiilista.</span><span class="sxs-lookup"><span data-stu-id="19379-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="19379-138">Valitse yhdistetty kenttä.</span><span class="sxs-lookup"><span data-stu-id="19379-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="19379-139">Valitse **Näytä lisää** ja valitse **Poista käytöstä**.</span><span class="sxs-lookup"><span data-stu-id="19379-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="19379-140">Vahvista käytöstä poisto.</span><span class="sxs-lookup"><span data-stu-id="19379-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="19379-141">Valitse **Tallenna** ja **Suorita** muutosten käsittelemiseksi.</span><span class="sxs-lookup"><span data-stu-id="19379-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="19379-142">Valitse **Yhdistä**-sivulla **Käytöstä poistetut kentät** nähdäksesi luettelon kaikista käytöstä poistetuista kentistä.</span><span class="sxs-lookup"><span data-stu-id="19379-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="19379-143">Tämän ruudun avulla käytöstä poistettuja kenttiä voidaan lisätä takaisin.</span><span class="sxs-lookup"><span data-stu-id="19379-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="19379-144">Yhdistä kentät manuaalisesti</span><span class="sxs-lookup"><span data-stu-id="19379-144">Manually combine fields</span></span>

<span data-ttu-id="19379-145">Määritä yhdistetty määrite manuaalisesti.</span><span class="sxs-lookup"><span data-stu-id="19379-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="19379-146">Valitse **Yhdistä**-sivulla **Yhdistä kentät**.</span><span class="sxs-lookup"><span data-stu-id="19379-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="19379-147">Anna **Nimi** ja **Tulostekentän nimi**.</span><span class="sxs-lookup"><span data-stu-id="19379-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="19379-148">Valitse lisättävä kenttä.</span><span class="sxs-lookup"><span data-stu-id="19379-148">Choose a field to add.</span></span> <span data-ttu-id="19379-149">Valitse **Lisää kenttiä** yhdistääksesi useampia kenttiä.</span><span class="sxs-lookup"><span data-stu-id="19379-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="19379-150">Vahvista käytöstä poisto.</span><span class="sxs-lookup"><span data-stu-id="19379-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="19379-151">Valitse **Tallenna** ja **Suorita** muutosten käsittelemiseksi.</span><span class="sxs-lookup"><span data-stu-id="19379-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="19379-152">Kenttien järjestyksen muuttaminen</span><span class="sxs-lookup"><span data-stu-id="19379-152">Change the order of fields</span></span>

<span data-ttu-id="19379-153">Jotkin entiteetit sisältävät enemmän tietoja kuin toiset.</span><span class="sxs-lookup"><span data-stu-id="19379-153">Some entities contain more details than others.</span></span> <span data-ttu-id="19379-154">Jos entiteetti sisältää kentän uusimmat tiedot, voit priorisoida sen muita entiteettejä korkeammalle arvojen yhdistämisessä.</span><span class="sxs-lookup"><span data-stu-id="19379-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="19379-155">Valitse yhdistetty kenttä.</span><span class="sxs-lookup"><span data-stu-id="19379-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="19379-156">Valitse **Näytä lisää** ja valitse sitten **Muokkaa**.</span><span class="sxs-lookup"><span data-stu-id="19379-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="19379-157">Valitse **Yhdistä kentät** -ruudussa **Siirrä ylös/alas** järjestyksen määrittämiseksi, tai vedä ja pudota niitä haluttuun sijaintiin.</span><span class="sxs-lookup"><span data-stu-id="19379-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="19379-158">Vahvista muutos.</span><span class="sxs-lookup"><span data-stu-id="19379-158">Confirm the change.</span></span>

1. <span data-ttu-id="19379-159">Valitse **Tallenna** ja **Suorita** muutosten käsittelemiseksi.</span><span class="sxs-lookup"><span data-stu-id="19379-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="19379-160">Suorita yhdistäminen</span><span class="sxs-lookup"><span data-stu-id="19379-160">Run your merge</span></span>

<span data-ttu-id="19379-161">Jos yhdistät määritteet manuaalisesti tai annat järjestelmän yhdistää ne, voit aina suorittaa yhdistämisen.</span><span class="sxs-lookup"><span data-stu-id="19379-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="19379-162">Valitse **Suorita** **Yhdistäminen**-sivulla, jos haluat aloittaa prosessin.</span><span class="sxs-lookup"><span data-stu-id="19379-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="19379-163">![Tietojen yhdistämisen tallennus- ja suoritustoiminto](media/configure-data-merge-save-run.png "Tietojen yhdistämisen tallennus- ja suoritustoiminto")</span><span class="sxs-lookup"><span data-stu-id="19379-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="19379-164">Valitse **Suorita vain yhdistämistoiminto**, jos haluat, että tulos näkyy vain yhdistetyssä asiakasentiteetissä.</span><span class="sxs-lookup"><span data-stu-id="19379-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="19379-165">Jatkoprosessit päivittyvät [päivitysaikataulun mukaan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="19379-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="19379-166">Valitse **Suorita yhdistäminen ja jatkoprosessit**, kun haluat päivittää muutokset järjestelmään.</span><span class="sxs-lookup"><span data-stu-id="19379-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="19379-167">Kaikki prosessit, kuten rikastus, segmentit ja mittarit, käynnistyvät uudelleen automaattisesti.</span><span class="sxs-lookup"><span data-stu-id="19379-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="19379-168">Kun kaikki jatkoprosessit on suoritettu loppuun, asiakasprofiilit vastaavat tehtyjä muutoksia.</span><span class="sxs-lookup"><span data-stu-id="19379-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="19379-169">Jos haluat tehdä lisää muutoksia ja suorittaa vaiheen uudelleen, voit peruuttaa käynnissä olevan yhdistämisen.</span><span class="sxs-lookup"><span data-stu-id="19379-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="19379-170">Valitse **Pävitetään...**-teksti ja valitse sitten **Peruuta työ** näkyviin tulevassa reunaruudussa.</span><span class="sxs-lookup"><span data-stu-id="19379-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="19379-171">Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="19379-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="19379-172">Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="19379-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="19379-173">Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja.</span><span class="sxs-lookup"><span data-stu-id="19379-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="19379-174">Kun työn jossakin tehtävissä on valittu **Näytä tiedot**, saat lisätietoja: käsittelyajan, viimeisimmän käsittelypäivämäärän sekä kaikki tehtävään liitetyt virheet ja varoitukset.</span><span class="sxs-lookup"><span data-stu-id="19379-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="19379-175">Seuraava vaihe</span><span class="sxs-lookup"><span data-stu-id="19379-175">Next Step</span></span>

<span data-ttu-id="19379-176">Määritä [aktiviteetit](activities.md), [rikastaminen](enrichment-hub.md) tai [suhteet](relationships.md), jos haluat lisää merkityksellisiä tietoja asiakkaista.</span><span class="sxs-lookup"><span data-stu-id="19379-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="19379-177">Jos olet jo määrittänyt aktiviteetteja, rikastuksia tai segmenttejä, ne käsitellään automaattisesti uusimpien asiakastietojen perusteella.</span><span class="sxs-lookup"><span data-stu-id="19379-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
