---
title: Mittareiden luominen ja hallinta
description: Määritä yrityksen suorituskyvyn analysoimiseen ja kuvaamiseen liittyvät mittarit.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 402e5ef3515bce0e6f56788781b7bd909738aaa6
ms.sourcegitcommit: b833e333745d321edeaf96d3ed14458cbce02ff1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049246"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="4be17-103">Mittojen määrittäminen ja hallinta</span><span class="sxs-lookup"><span data-stu-id="4be17-103">Define and manage measures</span></span>

<span data-ttu-id="4be17-104">Mittarien avulla ymmärrät paremmin asiakkaiden käyttäytymistä ja liiketoiminnan suorituskykyä.</span><span class="sxs-lookup"><span data-stu-id="4be17-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="4be17-105">Ne näyttävät olennaiset arvot [yhtenäisistä profiileista](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="4be17-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="4be17-106">Yritys haluaa esimerkiksi nähdä *kokonaissumman asiakasta kohden*, kun halutaan ymmärtää yksittäisen asiakkaan ostohistoria tai mitata *yrityksen kokonaismyyntiä* koko liiketoiminnan kokonaistuottoa varten.</span><span class="sxs-lookup"><span data-stu-id="4be17-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="4be17-107">Mittarit luodaan käyttämällä mittareiden luontiohjelmaa. Se on tietojen kysely-ympäristö, jossa on useita operaattoreita ja yksinkertaiset yhdistämisvalinnat.</span><span class="sxs-lookup"><span data-stu-id="4be17-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="4be17-108">Sen avulla voi suodattaa tietoja, ryhmitellä tuloksia, havaita [entiteettisuhteiden polkuja](relationships.md) ja esikatsella tulosta.</span><span class="sxs-lookup"><span data-stu-id="4be17-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="4be17-109">Käytä mittarin luontiohjelmaa liiketoiminta-aktiviteettien suunnittelemisessa tekemällä kyselyjä asiakastiedoista ja poimimalla tietoja.</span><span class="sxs-lookup"><span data-stu-id="4be17-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="4be17-110">Esimerkiksi *asiakaskohtainen kokonaiskulutus*- ja *asiakaskohtainen kokonaispalautus* -mittarin luominen auttaa tunnistamaan asiakkaat, jotka ostavat paljon, mutta tekevät myös paljon palautuksia.</span><span class="sxs-lookup"><span data-stu-id="4be17-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="4be17-111">Voit [luoda segmentin](segments.md) seuraavien parhaiden toimintojen suorittamiseksi.</span><span class="sxs-lookup"><span data-stu-id="4be17-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="4be17-112">Rakenna oma mittari tyhjästä</span><span class="sxs-lookup"><span data-stu-id="4be17-112">Build your own measure from scratch</span></span>

<span data-ttu-id="4be17-113">Tässä osassa kerrotaan uuden mittarin luomisesta alusta alkaen.</span><span class="sxs-lookup"><span data-stu-id="4be17-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="4be17-114">Voit luoda mittarin ja tietomääritteet tietoentiteeteistä, joille on määritetty suhde yhteyden muodostamiseksi asiakasentiteettiin.</span><span class="sxs-lookup"><span data-stu-id="4be17-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="4be17-115">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Mittarit**.</span><span class="sxs-lookup"><span data-stu-id="4be17-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="4be17-116">Valitse **Uusi** ja valitse **Luo oma**.</span><span class="sxs-lookup"><span data-stu-id="4be17-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="4be17-117">Valitse **Muokkaa nimeä** ja anna mittarille **nimi**.</span><span class="sxs-lookup"><span data-stu-id="4be17-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="4be17-118">Jos uuden mittarin määrityksellä on vain kaksi kenttää, esimerkiksi asiakastunnus ja yksi laskenta, tulos lisätään uudena sarakkeena järjestelmän luomaan entiteettiin, jota jonka nimi on mukautettu mittari.</span><span class="sxs-lookup"><span data-stu-id="4be17-118">If your new measure configuration has only two fields, for example, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="4be17-119">Voit myös nähdä mittarin arvon yhdistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="4be17-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="4be17-120">Muut mittarit luovat omat entiteetit.</span><span class="sxs-lookup"><span data-stu-id="4be17-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="4be17-121">Valitse määritysalueessa koostetoiminto avattavasta **Valitse toiminto** -valikosta.</span><span class="sxs-lookup"><span data-stu-id="4be17-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="4be17-122">Koostetoimintoja ovat seuraavat:</span><span class="sxs-lookup"><span data-stu-id="4be17-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="4be17-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="4be17-123">**Sum**</span></span>
   - <span data-ttu-id="4be17-124">**Keskiarvo**</span><span class="sxs-lookup"><span data-stu-id="4be17-124">**Average**</span></span>
   - <span data-ttu-id="4be17-125">**Määrä**</span><span class="sxs-lookup"><span data-stu-id="4be17-125">**Count**</span></span>
   - <span data-ttu-id="4be17-126">**Yksilöllinen määrä**</span><span class="sxs-lookup"><span data-stu-id="4be17-126">**Count Unique**</span></span>
   - <span data-ttu-id="4be17-127">**Enintään**</span><span class="sxs-lookup"><span data-stu-id="4be17-127">**Max**</span></span>
   - <span data-ttu-id="4be17-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="4be17-128">**Min**</span></span>
   - <span data-ttu-id="4be17-129">**Ensimmäinen**: ottaa tietueen ensimmäisen arvon</span><span class="sxs-lookup"><span data-stu-id="4be17-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="4be17-130">**Viimeinen**: ottaa tietueeseen lisätyn viimeisen arvon</span><span class="sxs-lookup"><span data-stu-id="4be17-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Mittarin laskelmien operaattorit.":::

1. <span data-ttu-id="4be17-132">Valitse **Lisää määrite**, jos haluat valita tälle mittarille luotavat tiedot.</span><span class="sxs-lookup"><span data-stu-id="4be17-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="4be17-133">Valitse **Määritteet**-välilehti.</span><span class="sxs-lookup"><span data-stu-id="4be17-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="4be17-134">Tietoentiteetti: valitse entiteetti, joka sisältää mitattavan määritteen.</span><span class="sxs-lookup"><span data-stu-id="4be17-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="4be17-135">Tietomäärite: valitse määrite, jota haluat käyttää koostetoiminnossa mittarin laskemiseksi.</span><span class="sxs-lookup"><span data-stu-id="4be17-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="4be17-136">Voit valita vain yhden määritteen kerrallaan.</span><span class="sxs-lookup"><span data-stu-id="4be17-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="4be17-137">Voit valita myös tietomääritteen olemassa olevasta mittarista valitsemalla **Mittarit**-välilehden. Vaihtoehtoisesti voit hakea mitä tahansa entiteetin tai mittarin nimeä.</span><span class="sxs-lookup"><span data-stu-id="4be17-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="4be17-138">Valitse **Lisää**, jos haluat lisätä valitun määritteen mittariin.</span><span class="sxs-lookup"><span data-stu-id="4be17-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Valitse laskelmissa käytettävä määrite.":::

1. <span data-ttu-id="4be17-140">Jos haluat luoda monimutkaisia mittareita, voit lisätä määritteiden määrää tai käyttää mittarin toiminnossa matemaattisia operaattoreita.</span><span class="sxs-lookup"><span data-stu-id="4be17-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Luo monimutkainen mittari, jossa on matemaattisia operaattoreita.":::

1. <span data-ttu-id="4be17-142">Jos haluat lisätä suodattimia, valitse määritysalueen **Suodatin**-kohta.</span><span class="sxs-lookup"><span data-stu-id="4be17-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="4be17-143">Valitse **Suodattimet**-ruudun **Lisää määrite** -osassa määrite, jota haluat käyttää suodattimien luomisessa.</span><span class="sxs-lookup"><span data-stu-id="4be17-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="4be17-144">Aseta suodatinoperaattorit, jos haluat määrittää jokaiselle valitulle määritteelle suodattimen.</span><span class="sxs-lookup"><span data-stu-id="4be17-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="4be17-145">Valitse **Käytä**, jos haluat lisätä suodattimet mittariin.</span><span class="sxs-lookup"><span data-stu-id="4be17-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="4be17-146">Jos haluat lisätä dimensioita, valitse määritysalueen **Dimensio**-kohta.</span><span class="sxs-lookup"><span data-stu-id="4be17-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="4be17-147">Dimensiot näkyvät mittarin tulosentiteetin sarakkeina.</span><span class="sxs-lookup"><span data-stu-id="4be17-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="4be17-148">Valitse **Muokkaa dimensioita**, jos haluat lisätä tietomääritteitä, joiden mukaan mittarin arvot ryhmitellään.</span><span class="sxs-lookup"><span data-stu-id="4be17-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="4be17-149">Tämä voi olla esimerkiksi kaupunki tai sukupuoli.</span><span class="sxs-lookup"><span data-stu-id="4be17-149">For example, city or gender.</span></span> <span data-ttu-id="4be17-150">Oletusarvoisesti valitaan *CustomerID*-dimensio *asiakastason mittareiden* luomiseksi.</span><span class="sxs-lookup"><span data-stu-id="4be17-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="4be17-151">Voit poistaa oletusdimension, jos haluat luoda *yritystason mittareita*.</span><span class="sxs-lookup"><span data-stu-id="4be17-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="4be17-152">Valitse **Valmis**, jos haluat lisätä dimensiot mittariin.</span><span class="sxs-lookup"><span data-stu-id="4be17-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="4be17-153">Jos tiedoissa on arvoja, jotka on korvattava kokonaisluvulla, korvaa esimerkiksi *tyhjäarvo* arvolla *0*, valitse **Säännöt**.</span><span class="sxs-lookup"><span data-stu-id="4be17-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="4be17-154">Määritä sääntö ja varmista, että valitset korvaavaksi arvoksi vain kokonaislukuja.</span><span class="sxs-lookup"><span data-stu-id="4be17-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="4be17-155">Jos yhdistetyn tietoentiteetin ja *asiakas*-entiteetin välillä on useita polkuja, tulee valita jokin määritetyistä [entiteettisuhteen poluista](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="4be17-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="4be17-156">Mittarin tulokset voivat vaihdella valitun polun mukaan.</span><span class="sxs-lookup"><span data-stu-id="4be17-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="4be17-157">Valitse **Tietomääritteet** ja valitse sitten entiteettipolku, jota käytetään mittarin tunnistamisessa.</span><span class="sxs-lookup"><span data-stu-id="4be17-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="4be17-158">Jos *Asiakas*-entiteetissä on vain yksi polku, ohjausobjektia ei näy.</span><span class="sxs-lookup"><span data-stu-id="4be17-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="4be17-159">Ota valinta käyttöön valitsemalla **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="4be17-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Valitse mittarin entiteettipolku.":::

1. <span data-ttu-id="4be17-161">Jos haluat lisätä mittarille lisää laskelmia, valitse **Uusi laskelma**.</span><span class="sxs-lookup"><span data-stu-id="4be17-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="4be17-162">Uusissa laskelmissa voi käyttää vain saman entiteettipolun entiteettejä.</span><span class="sxs-lookup"><span data-stu-id="4be17-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="4be17-163">Lisälaskelmat näkyvät uusina sarakkeina mittarin tulosentiteetissä.</span><span class="sxs-lookup"><span data-stu-id="4be17-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="4be17-164">Valitse laskelman **...**-kohta, jos haluat **monistaa**, **uudelleennimetä** tai **poistaa** laskelman mittarista.</span><span class="sxs-lookup"><span data-stu-id="4be17-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="4be17-165">**Esiversio**-alueessa on näkyvissä mittarin tulosentiteetin tietorakenne, myös suodattimet ja dimensiot.</span><span class="sxs-lookup"><span data-stu-id="4be17-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="4be17-166">Esiversio readoi dynaamisesti määrityksen muutoksiin.</span><span class="sxs-lookup"><span data-stu-id="4be17-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="4be17-167">Laske määritetyn mittarin tulokset valitsemalla **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="4be17-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="4be17-168">Valitse **Tallenna ja sulje**, jos haluat pitää nykyisen määrityksen ja suorittaa mittarin myöhemmin.</span><span class="sxs-lookup"><span data-stu-id="4be17-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="4be17-169">Siirry **Mittarit**-kohtaan, jos haluat nähdä juuri luodun mittarin luettelossa.</span><span class="sxs-lookup"><span data-stu-id="4be17-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="4be17-170">Mittarin luominen mallin avulla</span><span class="sxs-lookup"><span data-stu-id="4be17-170">Use a template to build a measure</span></span>

<span data-ttu-id="4be17-171">Voit luoda niitä käyttämällä ennalta määritettyjä malleja, joissa on usein käytettyjä mittoja.</span><span class="sxs-lookup"><span data-stu-id="4be17-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="4be17-172">Mallien yksityiskohtaiset kuvaukset ja ohjattu kokemus auttavat mittarien tehokkaassa luomisessa.</span><span class="sxs-lookup"><span data-stu-id="4be17-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="4be17-173">Mallit perustuvat *Yhdistetty aktiviteetti* -entiteetin yhdistettyihin tietoihin.</span><span class="sxs-lookup"><span data-stu-id="4be17-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="4be17-174">Varmista siis, että olet määrittänyt [asiakasaktiviteetit](activities.md), ennen kuin luot mittarin mallista.</span><span class="sxs-lookup"><span data-stu-id="4be17-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="4be17-175">Käytettävissä olevat mittarimallit:</span><span class="sxs-lookup"><span data-stu-id="4be17-175">Available measure templates:</span></span> 
- <span data-ttu-id="4be17-176">Keskimääräinen tapahtuman arvo (ATV)</span><span class="sxs-lookup"><span data-stu-id="4be17-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="4be17-177">Tapahtuman kokonaisarvo</span><span class="sxs-lookup"><span data-stu-id="4be17-177">Total transaction value</span></span>
- <span data-ttu-id="4be17-178">Keskimääräinen päivätuotto</span><span class="sxs-lookup"><span data-stu-id="4be17-178">Average daily revenue</span></span>
- <span data-ttu-id="4be17-179">Keskimääräinen vuosituotto</span><span class="sxs-lookup"><span data-stu-id="4be17-179">Average yearly revenue</span></span>
- <span data-ttu-id="4be17-180">Tapahtumien määrä</span><span class="sxs-lookup"><span data-stu-id="4be17-180">Transaction count</span></span>
- <span data-ttu-id="4be17-181">Ansaitut kanta-asiakaspisteet</span><span class="sxs-lookup"><span data-stu-id="4be17-181">Loyalty points earned</span></span>
- <span data-ttu-id="4be17-182">Lunastetut kanta-asiakaspisteet</span><span class="sxs-lookup"><span data-stu-id="4be17-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="4be17-183">Kanta-asiakaspisteiden saldo</span><span class="sxs-lookup"><span data-stu-id="4be17-183">Loyalty points balance</span></span>
- <span data-ttu-id="4be17-184">Aktiivisen asiakkaan elinkaari</span><span class="sxs-lookup"><span data-stu-id="4be17-184">Active customer lifespan</span></span>
- <span data-ttu-id="4be17-185">Kanta-asiakkuuden kesto</span><span class="sxs-lookup"><span data-stu-id="4be17-185">Loyalty membership duration</span></span>
- <span data-ttu-id="4be17-186">Aika viime ostosta</span><span class="sxs-lookup"><span data-stu-id="4be17-186">Time since last purchase</span></span>

<span data-ttu-id="4be17-187">Seuraavassa ohjeessa on kuvattu, miten uusi mittari voidaan luoda mallin avulla.</span><span class="sxs-lookup"><span data-stu-id="4be17-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="4be17-188">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Mittarit**.</span><span class="sxs-lookup"><span data-stu-id="4be17-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="4be17-189">Valitse ensin **Uusi** ja sitten **Valitse malli**.</span><span class="sxs-lookup"><span data-stu-id="4be17-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Näyttökuva avattavasta valikosta luotaessa uutta mittaria, jossa on korostettuna malli.":::

1. <span data-ttu-id="4be17-191">Etsi tarpeisiisi sopiva malli ja valitse **Valitse malli**.</span><span class="sxs-lookup"><span data-stu-id="4be17-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="4be17-192">Tarkista tarvittavat tiedot ja valitse **Aloitus**, jos kaikki tiedot ovat paikoillaan.</span><span class="sxs-lookup"><span data-stu-id="4be17-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="4be17-193">Määritä **Muokkaa nimeä** -ruudussa mittarin ja tulosentiteetin nimi.</span><span class="sxs-lookup"><span data-stu-id="4be17-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="4be17-194">Valitse **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="4be17-194">Select **Done**.</span></span>

1. <span data-ttu-id="4be17-195">Määritä **Määritä ajanjakso** -osassa aikaväli käytettäville tiedoille.</span><span class="sxs-lookup"><span data-stu-id="4be17-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="4be17-196">Valitse, kattaako uusi mittari koko tietojoukon, valitsemalla **Kaikki aikavälit**.</span><span class="sxs-lookup"><span data-stu-id="4be17-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="4be17-197">Jos haluat, että mittari keskittyy **tiettyyn ajanjaksoon**.</span><span class="sxs-lookup"><span data-stu-id="4be17-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Näyttökuva, jossa näkyy ajanjakso-osa, kun mittaria määritetään mallista.":::

1. <span data-ttu-id="4be17-199">Valitse seuraavassa osassa **Lisää tiedot**, jos haluat valita aktiviteetit ja yhdistää vastaavat *Yhdistetty aktiviteetti* -kohteen tiedot.</span><span class="sxs-lookup"><span data-stu-id="4be17-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="4be17-200">Vaihe 1/2: Valitse **Aktiviteettityyppi**-kohdassa haluamasi entiteetin tyyppi.</span><span class="sxs-lookup"><span data-stu-id="4be17-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="4be17-201">Valitse **Aktiviteetit**-kohdassa entiteetit, jotka haluat yhdistää.</span><span class="sxs-lookup"><span data-stu-id="4be17-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="4be17-202">Vaihe 2/2: Valitse määrite *Yhdistetty aktiviteetti* -entiteetistä komponentille, jota kaava edellyttää.</span><span class="sxs-lookup"><span data-stu-id="4be17-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="4be17-203">Esimerkiksi Keskimääräinen tapahtuman arvo on määrite, joka vastaa tapahtuman arvoa.</span><span class="sxs-lookup"><span data-stu-id="4be17-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="4be17-204">Valitse **Aktiviteetin aikaleima** -kohdassa Yhdistetty aktiviteetti -kohteen määrite, joka kuvaa aktiviteetin päivämäärää ja aikaa.</span><span class="sxs-lookup"><span data-stu-id="4be17-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="4be17-205">Kun tietojen yhdistäminen on onnistunut, voit nähdä tilan **Valmis** ja yhdistettyjen aktiviteettien ja määritteiden nimen.</span><span class="sxs-lookup"><span data-stu-id="4be17-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Näyttökuva valmiin mittarimallin määrityksestä.":::

1. <span data-ttu-id="4be17-207">Nyt voit laskea mittarin tulokset valitsemalla **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="4be17-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="4be17-208">Jos haluat tarkentaa sitä myöhemmin, valitse **Tallenna luonnos**.</span><span class="sxs-lookup"><span data-stu-id="4be17-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="4be17-209">Hallitse mittoja</span><span class="sxs-lookup"><span data-stu-id="4be17-209">Manage your measures</span></span>

<span data-ttu-id="4be17-210">**Mittarit**-sivulla on mittarien luettelo.</span><span class="sxs-lookup"><span data-stu-id="4be17-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="4be17-211">Saat tietoja mittarityypistä, tekijästä, luontipäivästä ja tilasta.</span><span class="sxs-lookup"><span data-stu-id="4be17-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="4be17-212">Jos valitset mittarin luettelosta, voit esikatsella tulostetta ja ladata .CSV-tiedoston.</span><span class="sxs-lookup"><span data-stu-id="4be17-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="4be17-213">Jos haluat päivittää kaikki mitat samalla kertaa, valitse **Päivitä kaikki** valitsematta tiettyä mittaa.</span><span class="sxs-lookup"><span data-stu-id="4be17-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4be17-214">![Yksittäisten mittojen hallintatoiminnot](media/measure-actions.png "Yksittäisten mittojen hallintatoiminnot")</span><span class="sxs-lookup"><span data-stu-id="4be17-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="4be17-215">Valitse seuraaville vaihtoehdoille mittari luettelosta:</span><span class="sxs-lookup"><span data-stu-id="4be17-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="4be17-216">Voit tarkastella tietoja valitsemalla mitan nimen.</span><span class="sxs-lookup"><span data-stu-id="4be17-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="4be17-217">**Muokkaa** mitan määritystä.</span><span class="sxs-lookup"><span data-stu-id="4be17-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="4be17-218">**Päivitä** mittari uusimpien tietojen perusteella.</span><span class="sxs-lookup"><span data-stu-id="4be17-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="4be17-219">**Nimeä uudelleen** mitta.</span><span class="sxs-lookup"><span data-stu-id="4be17-219">**Rename** the measure.</span></span>
- <span data-ttu-id="4be17-220">**Poista** mitta.</span><span class="sxs-lookup"><span data-stu-id="4be17-220">**Delete** the measure.</span></span>
- <span data-ttu-id="4be17-221">**Aktivoi** tai **poista aktivointi**.</span><span class="sxs-lookup"><span data-stu-id="4be17-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="4be17-222">Passiivisia mittareita ei päivitetä [aikataulutetun päivityksen](system.md#schedule-tab) aikana.</span><span class="sxs-lookup"><span data-stu-id="4be17-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="4be17-223">Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="4be17-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="4be17-224">Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="4be17-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="4be17-225">Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja.</span><span class="sxs-lookup"><span data-stu-id="4be17-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="4be17-226">Kun työn jossakin tehtävissä on valittu **Näytä tiedot**, saat lisätietoja: käsittelyajan, viimeisimmän käsittelypäivämäärän sekä kaikki tehtävään liitetyt virheet ja varoitukset.</span><span class="sxs-lookup"><span data-stu-id="4be17-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="4be17-227">Seuraava vaihe</span><span class="sxs-lookup"><span data-stu-id="4be17-227">Next step</span></span>

<span data-ttu-id="4be17-228">Voit luoda [asiakassegmentin](segments.md) olemassa olevien mittareiden avulla.</span><span class="sxs-lookup"><span data-stu-id="4be17-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
