---
title: Mittareiden luominen ja hallinta
description: Määritä yrityksen suorituskyvyn analysoimiseen ja kuvaamiseen liittyvät mittarit.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269924"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="a90c7-103">Mittojen määrittäminen ja hallinta</span><span class="sxs-lookup"><span data-stu-id="a90c7-103">Define and manage measures</span></span>

<span data-ttu-id="a90c7-104">Mittareiden avulla saat lisätietoja asiakkaan toiminnasta ja liiketoiminnan suorituskyvystä noutamalla olennaisia arvoja [yhdistetyistä profiileista](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="a90c7-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="a90c7-105">Esimerkissä yritys haluaa lisätietoja yksittäisen asiakkaan ostohistoriasta *asiakaskohtaisen kokonaiskulutuksen* avulla.</span><span class="sxs-lookup"><span data-stu-id="a90c7-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="a90c7-106">Vaihtoehtoisesti halutaan tietoja koko yrityksen koostetusta myyntituotosta *yrityksen kokonaismyyntiä* kuvaavan mittarin avulla.</span><span class="sxs-lookup"><span data-stu-id="a90c7-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="a90c7-107">Mittarit luodaan käyttämällä mittareiden luontiohjelmaa. Se on tietojen kysely-ympäristö, jossa on useita operaattoreita ja yksinkertaiset yhdistämisvalinnat.</span><span class="sxs-lookup"><span data-stu-id="a90c7-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="a90c7-108">Sen avulla voi suodattaa tietoja, ryhmitellä tuloksia, havaita [entiteettisuhteiden polkuja](relationships.md) ja esikatsella tulosta.</span><span class="sxs-lookup"><span data-stu-id="a90c7-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="a90c7-109">Käytä mittarin luontiohjelmaa liiketoiminta-aktiviteettien suunnittelemisessa tekemällä kyselyjä asiakastiedoista ja poimimalla tietoja.</span><span class="sxs-lookup"><span data-stu-id="a90c7-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="a90c7-110">Esimerkiksi *asiakaskohtainen kokonaiskulutus*- ja *asiakaskohtainen kokonaispalautus* -mittarin luominen auttaa tunnistamaan asiakkaat, jotka ostavat paljon, mutta tekevät myös paljon palautuksia.</span><span class="sxs-lookup"><span data-stu-id="a90c7-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="a90c7-111">Voit [luoda segmentin](segments.md) seuraavien parhaiden toimintojen suorittamiseksi.</span><span class="sxs-lookup"><span data-stu-id="a90c7-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="a90c7-112">Luo mittari</span><span class="sxs-lookup"><span data-stu-id="a90c7-112">Create a measure</span></span>

<span data-ttu-id="a90c7-113">Tässä osassa kerrotaan uuden mittarin luomisesta alusta alkaen.</span><span class="sxs-lookup"><span data-stu-id="a90c7-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="a90c7-114">Voit luoda mittarin ja tietomääritteet tietoentiteeteistä, joille on määritetty suhde yhteyden muodostamiseksi asiakasentiteettiin.</span><span class="sxs-lookup"><span data-stu-id="a90c7-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="a90c7-115">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Mittarit**.</span><span class="sxs-lookup"><span data-stu-id="a90c7-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="a90c7-116">Valitse **Uusi**.</span><span class="sxs-lookup"><span data-stu-id="a90c7-116">Select **New**.</span></span>

1. <span data-ttu-id="a90c7-117">Valitse **Muokkaa nimeä** ja anna mittarille **nimi**.</span><span class="sxs-lookup"><span data-stu-id="a90c7-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="a90c7-118">Jos uudella mittarin määrityksellä on vain kaksi kenttää, esimerkiksi CustomerID ja yksi laskelma, tulos lisätään uudeksi sarakkeeksi järjestelmän luomaan entiteettiin nimeltä Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="a90c7-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="a90c7-119">Voit myös nähdä mittarin arvon yhdistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="a90c7-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="a90c7-120">Muut mittarit luovat omat entiteetit.</span><span class="sxs-lookup"><span data-stu-id="a90c7-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="a90c7-121">Valitse määritysalueessa koostetoiminto avattavasta **Valitse toiminto** -valikosta.</span><span class="sxs-lookup"><span data-stu-id="a90c7-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="a90c7-122">Koostetoimintoja ovat seuraavat:</span><span class="sxs-lookup"><span data-stu-id="a90c7-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="a90c7-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="a90c7-123">**Sum**</span></span>
   - <span data-ttu-id="a90c7-124">**Keskiarvo**</span><span class="sxs-lookup"><span data-stu-id="a90c7-124">**Average**</span></span>
   - <span data-ttu-id="a90c7-125">**Määrä**</span><span class="sxs-lookup"><span data-stu-id="a90c7-125">**Count**</span></span>
   - <span data-ttu-id="a90c7-126">**Yksilöllinen määrä**</span><span class="sxs-lookup"><span data-stu-id="a90c7-126">**Count Unique**</span></span>
   - <span data-ttu-id="a90c7-127">**Enintään**</span><span class="sxs-lookup"><span data-stu-id="a90c7-127">**Max**</span></span>
   - <span data-ttu-id="a90c7-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="a90c7-128">**Min**</span></span>
   - <span data-ttu-id="a90c7-129">**Ensimmäinen**: ottaa tietueen ensimmäisen arvon</span><span class="sxs-lookup"><span data-stu-id="a90c7-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="a90c7-130">**Viimeinen**: ottaa tietueeseen lisätyn viimeisen arvon</span><span class="sxs-lookup"><span data-stu-id="a90c7-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Mittarin laskelmien operaattorit.":::

1. <span data-ttu-id="a90c7-132">Valitse **Lisää määrite**, jos haluat valita tälle mittarille luotavat tiedot.</span><span class="sxs-lookup"><span data-stu-id="a90c7-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="a90c7-133">Valitse **Määritteet**-välilehti.</span><span class="sxs-lookup"><span data-stu-id="a90c7-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="a90c7-134">Tietoentiteetti: valitse entiteetti, joka sisältää mitattavan määritteen.</span><span class="sxs-lookup"><span data-stu-id="a90c7-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="a90c7-135">Tietomäärite: valitse määrite, jota haluat käyttää koostetoiminnossa mittarin laskemiseksi.</span><span class="sxs-lookup"><span data-stu-id="a90c7-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="a90c7-136">Voit valita vain yhden määritteen kerrallaan.</span><span class="sxs-lookup"><span data-stu-id="a90c7-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="a90c7-137">Voit valita myös tietomääritteen olemassa olevasta mittarista valitsemalla **Mittarit**-välilehden. Vaihtoehtoisesti voit hakea mitä tahansa entiteetin tai mittarin nimeä.</span><span class="sxs-lookup"><span data-stu-id="a90c7-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="a90c7-138">Valitse **Lisää**, jos haluat lisätä valitun määritteen mittariin.</span><span class="sxs-lookup"><span data-stu-id="a90c7-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Valitse laskelmissa käytettävä määrite.":::

1. <span data-ttu-id="a90c7-140">Jos haluat luoda monimutkaisia mittareita, voit lisätä määritteiden määrää tai käyttää mittarin toiminnossa matemaattisia operaattoreita.</span><span class="sxs-lookup"><span data-stu-id="a90c7-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Luo monimutkainen mittari, jossa on matemaattisia operaattoreita.":::

1. <span data-ttu-id="a90c7-142">Jos haluat lisätä suodattimia, valitse määritysalueen **Suodatin**-kohta.</span><span class="sxs-lookup"><span data-stu-id="a90c7-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="a90c7-143">Valitse **Suodattimet**-ruudun **Lisää määrite** -osassa määrite, jota haluat käyttää suodattimien luomisessa.</span><span class="sxs-lookup"><span data-stu-id="a90c7-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="a90c7-144">Aseta suodatinoperaattorit, jos haluat määrittää jokaiselle valitulle määritteelle suodattimen.</span><span class="sxs-lookup"><span data-stu-id="a90c7-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="a90c7-145">Valitse **Käytä**, jos haluat lisätä suodattimet mittariin.</span><span class="sxs-lookup"><span data-stu-id="a90c7-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="a90c7-146">Jos haluat lisätä dimensioita, valitse määritysalueen **Dimensio**-kohta.</span><span class="sxs-lookup"><span data-stu-id="a90c7-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="a90c7-147">Dimensiot näkyvät mittarin tulosentiteetin sarakkeina.</span><span class="sxs-lookup"><span data-stu-id="a90c7-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="a90c7-148">Valitse **Muokkaa dimensioita**, jos haluat lisätä tietomääritteitä, joiden mukaan mittarin arvot ryhmitellään.</span><span class="sxs-lookup"><span data-stu-id="a90c7-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="a90c7-149">Tämä voi olla esimerkiksi kaupunki tai sukupuoli.</span><span class="sxs-lookup"><span data-stu-id="a90c7-149">For example, city or gender.</span></span> <span data-ttu-id="a90c7-150">Oletusarvoisesti valitaan *CustomerID*-dimensio *asiakastason mittareiden* luomiseksi.</span><span class="sxs-lookup"><span data-stu-id="a90c7-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="a90c7-151">Voit poistaa oletusdimension, jos haluat luoda *yritystason mittareita*.</span><span class="sxs-lookup"><span data-stu-id="a90c7-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="a90c7-152">Valitse **Valmis**, jos haluat lisätä dimensiot mittariin.</span><span class="sxs-lookup"><span data-stu-id="a90c7-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="a90c7-153">Jos yhdistetyn tietoentiteetin ja asiakasentiteetin välillä on useita polkuja, tulee valita jokin määritetyistä [entiteettisuhteen poluista](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="a90c7-153">If there are multiple paths between the data entity you mapped and the Customer entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="a90c7-154">Mittarin tulokset voivat vaihdella valitun polun mukaan.</span><span class="sxs-lookup"><span data-stu-id="a90c7-154">Measure results can vary depending on the selected path.</span></span>
   1. <span data-ttu-id="a90c7-155">Valitse **Tietomääritteet** ja valitse sitten entiteettipolku, jota käytetään mittarin tunnistamisessa.</span><span class="sxs-lookup"><span data-stu-id="a90c7-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span>
   1. <span data-ttu-id="a90c7-156">Ota valinta käyttöön valitsemalla **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="a90c7-156">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Valitse mittarin entiteettipolku.":::

1. <span data-ttu-id="a90c7-158">Jos haluat lisätä mittarille lisää laskelmia, valitse **Uusi laskelma**.</span><span class="sxs-lookup"><span data-stu-id="a90c7-158">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="a90c7-159">Uusissa laskelmissa voi käyttää vain saman entiteettipolun entiteettejä.</span><span class="sxs-lookup"><span data-stu-id="a90c7-159">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="a90c7-160">Lisälaskelmat näkyvät uusina sarakkeina mittarin tulosentiteetissä.</span><span class="sxs-lookup"><span data-stu-id="a90c7-160">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="a90c7-161">Valitse laskelman **...**-kohta, jos haluat **monistaa**, **uudelleennimetä** tai **poistaa** laskelman mittarista.</span><span class="sxs-lookup"><span data-stu-id="a90c7-161">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="a90c7-162">**Esiversio**-alueessa on näkyvissä mittarin tulosentiteetin tietorakenne, myös suodattimet ja dimensiot.</span><span class="sxs-lookup"><span data-stu-id="a90c7-162">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="a90c7-163">Esiversio readoi dynaamisesti määrityksen muutoksiin.</span><span class="sxs-lookup"><span data-stu-id="a90c7-163">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="a90c7-164">Laske määritetyn mittarin tulokset valitsemalla **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="a90c7-164">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="a90c7-165">Valitse **Tallenna ja sulje**, jos haluat pitää nykyisen määrityksen ja suorittaa mittarin myöhemmin.</span><span class="sxs-lookup"><span data-stu-id="a90c7-165">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="a90c7-166">Siirry **Mittarit**-kohtaan, jos haluat nähdä juuri luodun mittarin luettelossa.</span><span class="sxs-lookup"><span data-stu-id="a90c7-166">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="a90c7-167">Hallitse mittoja</span><span class="sxs-lookup"><span data-stu-id="a90c7-167">Manage your measures</span></span>

<span data-ttu-id="a90c7-168">Kun [mittari on luotu](#create-a-measure), **Mittarit**-sivulla näkyy mittariluettelo.</span><span class="sxs-lookup"><span data-stu-id="a90c7-168">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="a90c7-169">Saat tietoja mittarityypistä, tekijästä, luontipäivästä ja tilasta.</span><span class="sxs-lookup"><span data-stu-id="a90c7-169">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="a90c7-170">Jos valitset mittarin luettelosta, voit esikatsella tulostetta ja ladata .CSV-tiedoston.</span><span class="sxs-lookup"><span data-stu-id="a90c7-170">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="a90c7-171">Jos haluat päivittää kaikki mitat samalla kertaa, valitse **Päivitä kaikki** valitsematta tiettyä mittaa.</span><span class="sxs-lookup"><span data-stu-id="a90c7-171">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a90c7-172">![Yksittäisten mittojen hallintatoiminnot](media/measure-actions.png "Yksittäisten mittojen hallintatoiminnot")</span><span class="sxs-lookup"><span data-stu-id="a90c7-172">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="a90c7-173">Valitse seuraaville vaihtoehdoille mittari luettelosta:</span><span class="sxs-lookup"><span data-stu-id="a90c7-173">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="a90c7-174">Voit tarkastella tietoja valitsemalla mitan nimen.</span><span class="sxs-lookup"><span data-stu-id="a90c7-174">Select the measure name to see its details.</span></span>
- <span data-ttu-id="a90c7-175">**Muokkaa** mitan määritystä.</span><span class="sxs-lookup"><span data-stu-id="a90c7-175">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="a90c7-176">**Päivitä** mittari uusimpien tietojen perusteella.</span><span class="sxs-lookup"><span data-stu-id="a90c7-176">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="a90c7-177">**Nimeä uudelleen** mitta.</span><span class="sxs-lookup"><span data-stu-id="a90c7-177">**Rename** the measure.</span></span>
- <span data-ttu-id="a90c7-178">**Poista** mitta.</span><span class="sxs-lookup"><span data-stu-id="a90c7-178">**Delete** the measure.</span></span>
- <span data-ttu-id="a90c7-179">**Aktivoi** tai **poista aktivointi**.</span><span class="sxs-lookup"><span data-stu-id="a90c7-179">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="a90c7-180">Passiivisia mittareita ei päivitetä [aikataulutetun päivityksen](system.md#schedule-tab) aikana.</span><span class="sxs-lookup"><span data-stu-id="a90c7-180">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="a90c7-181">Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="a90c7-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a90c7-182">Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="a90c7-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a90c7-183">Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja.</span><span class="sxs-lookup"><span data-stu-id="a90c7-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a90c7-184">Kun työn jossakin tehtävissä on valittu **Näytä tiedot**, saat lisätietoja: käsittelyajan, viimeisimmän käsittelypäivämäärän sekä kaikki tehtävään liitetyt virheet ja varoitukset.</span><span class="sxs-lookup"><span data-stu-id="a90c7-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="a90c7-185">Seuraava vaihe</span><span class="sxs-lookup"><span data-stu-id="a90c7-185">Next step</span></span>

<span data-ttu-id="a90c7-186">Voit luoda [asiakassegmentin](segments.md) olemassa olevien mittareiden avulla.</span><span class="sxs-lookup"><span data-stu-id="a90c7-186">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]