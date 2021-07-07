---
title: Tuotesuositusten ennusteen näyteopas
description: Tämän näyteoppaan avulla voi kokeilla valmista tuotesuosituksen ennustemallia.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: a85ee598ec747d0594755314e83a127ce0f2af95
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306162"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="a4bdc-103">Tuotesuositusten ennusteen (esiversio) näyteopas</span><span class="sxs-lookup"><span data-stu-id="a4bdc-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="a4bdc-104">Aiheessa käsitellään kattavasti tuotesuosituksen ennusteen esimerkkiä käyttämällä alla olevia näytetietoja.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="a4bdc-105">Skenaario</span><span class="sxs-lookup"><span data-stu-id="a4bdc-105">Scenario</span></span>

<span data-ttu-id="a4bdc-106">Contoso on yritys, joka tuottaa laadukkaat kahvi- ja kahvikoneet, joita he myyvät Contoso Coffee -verkkosivustonsa kautta.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="a4bdc-107">Tavoitteena on ymmärtää, mitä tuotteita tulisi suositella toistuville asiakkaille.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="a4bdc-108">Jos tiedetään, mitä asiakkaat **todennäköisesti ostavat**, markkinointiponnisteluissa voidaan keskittyä näihin tiettyihin nimikkeisiin.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a4bdc-109">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="a4bdc-109">Prerequisites</span></span>

- <span data-ttu-id="a4bdc-110">Vähintään [osallistujan oikeudet](permissions.md) Customer Insightsissa.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="a4bdc-111">Seuraavat vaiheet on suositeltavaa toteuttaa [uudessa ympäristössä](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="a4bdc-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="a4bdc-112">Tehtävä 1 – Tietojen käsitteleminen</span><span class="sxs-lookup"><span data-stu-id="a4bdc-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="a4bdc-113">Tutustu etenkin artikkeleihin, joissa on [tietoja tietojen käsittelystä](data-sources.md) ja [tietolähteiden tuomisestä Power Query -yhdistimiä](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a4bdc-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="a4bdc-114">Seuraavissa tiedoissa oletetaan, että tietojen käsittely on yleisesti ottaen tuttua.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="a4bdc-115">Asiakas tietojen käsitteleminen sähköisen kaupankäynnin ympäristössä</span><span class="sxs-lookup"><span data-stu-id="a4bdc-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="a4bdc-116">Luo **eCommerce**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a4bdc-117">Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="a4bdc-118">Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a4bdc-119">Päivitä seuraavien sarakkeiden tietotyyppi:</span><span class="sxs-lookup"><span data-stu-id="a4bdc-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="a4bdc-120">**DateOfBirth**: päivämäärä</span><span class="sxs-lookup"><span data-stu-id="a4bdc-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="a4bdc-121">**CreatedOn**: päivämäärä, aika ja aikavyöhyke</span><span class="sxs-lookup"><span data-stu-id="a4bdc-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Syntymäpäivän muuntaminen päivämääräksi.":::

5. <span data-ttu-id="a4bdc-123">Vaihda oikean ruudun Nimi-kentän tietolähteen nimi. Vanha nimi on **Query** ja uusi on **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="a4bdc-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="a4bdc-124">**Tallenna** tietolähde.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="a4bdc-125">Verkko-ostostietojen käsitteleminen</span><span class="sxs-lookup"><span data-stu-id="a4bdc-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="a4bdc-126">Lisää toinen tietojoukko samaan **eCommerce**-tietolähteeseen.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="a4bdc-127">Valitse **Text/CSV**-yhdistin uudelleen.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="a4bdc-128">Anna **Verkko-ostokset**-tietojen URL-osoite https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="a4bdc-129">Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a4bdc-130">Päivitä seuraavien sarakkeiden tietotyyppi:</span><span class="sxs-lookup"><span data-stu-id="a4bdc-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="a4bdc-131">**PurchasedOn**: päivämäärä ja aika</span><span class="sxs-lookup"><span data-stu-id="a4bdc-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="a4bdc-132">**TotalPrice**: valuutta</span><span class="sxs-lookup"><span data-stu-id="a4bdc-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="a4bdc-133">Vaihda sivuruudun **Nimi**-kentän tietolähteen nimi. Vanha nimi on **Query** ja uusi on **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="a4bdc-134">**Tallenna** tietolähde.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-134">**Save** the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="a4bdc-135">Asiakastietojen käyttäminen kanta-asiakasrakenteesta</span><span class="sxs-lookup"><span data-stu-id="a4bdc-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="a4bdc-136">Luo **LoyaltyScheme**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a4bdc-137">Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="a4bdc-138">Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a4bdc-139">Päivitä seuraavien sarakkeiden tietotyyppi:</span><span class="sxs-lookup"><span data-stu-id="a4bdc-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="a4bdc-140">**DateOfBirth**: päivämäärä</span><span class="sxs-lookup"><span data-stu-id="a4bdc-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="a4bdc-141">**RewardsPoints**: kokonaisluku</span><span class="sxs-lookup"><span data-stu-id="a4bdc-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="a4bdc-142">**CreatedOn**: päivämäärä, aika</span><span class="sxs-lookup"><span data-stu-id="a4bdc-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="a4bdc-143">Vaihda oikeanpuoleisen ruudun **Nimi**-kentässä tietolähteen nimi **Query** nimeksi **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="a4bdc-144">**Tallenna** tietolähde.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-144">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="a4bdc-145">Tehtävä 2 – tietojen yhtenäistäminen</span><span class="sxs-lookup"><span data-stu-id="a4bdc-145">Task 2 - Data unification</span></span>

<span data-ttu-id="a4bdc-146">Tietojen purkamisen jälkeen aloitetaan nyt tietojen yhdistäminen ja luodaan yhtenäinen asiakasprofiili.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-146">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="a4bdc-147">Lisätietoja on kohdassa [Tietojen yhtenäistäminen](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="a4bdc-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="a4bdc-148">Liitä</span><span class="sxs-lookup"><span data-stu-id="a4bdc-148">Map</span></span>

1. <span data-ttu-id="a4bdc-149">Kun tiedot on käsitelty, tee eCommerce- ja Loyalty-tietojen yhdistämismääritys yleisiin tietotyyppeihin.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="a4bdc-150">Valitse **Tiedot** > **Yhtenäistä** > **Määritä vastaavuus**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="a4bdc-151">Valitse asiakasprofiilin ilmaisevat entiteetit: **eCommerceContacts** ja **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![ecommerce- ja loyalty-tietolähteiden yhtenäistäminen](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="a4bdc-153">Valitse **ContactId** **eCommerceContacts**-perusavaimeksi ja **LoyaltyID** **loyCustomers**-perusavaimeksi.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Yhtenäistäminen LoyaltyId-perusavaimena](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="a4bdc-155">Täsmäytä</span><span class="sxs-lookup"><span data-stu-id="a4bdc-155">Match</span></span>

1. <span data-ttu-id="a4bdc-156">Valitse **Täsmäytä**-välilehdessä **Määritä järjestys**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="a4bdc-157">Valitse avattavasta **Ensisijainen**-luettelosta ensisijaiseksi lähteeksi **eCommerceContacts: eCommerce** ja sisällytä kaikki tietueet.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-157">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="a4bdc-158">Valitse avattavasta **Entiteetti 2** -luettelosta **loyCustomers: LoyaltyScheme** ja sisällytä kaikki tietueet.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-158">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![eCommerce- ja Loyalty-täsmäytyksen yhtenäistäminen](media/unify-match-order.png)

4. <span data-ttu-id="a4bdc-160">Valitse **Luo uusi sääntö**</span><span class="sxs-lookup"><span data-stu-id="a4bdc-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="a4bdc-161">Lisää ensimmäinen ehto FullName-kentässä.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="a4bdc-162">Valitse eCommerceContacts-kohdassa avattavasta valikosta **FullName**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-162">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="a4bdc-163">Valitse loyCustomers-kohdassa avattavasta valikosta **FullName**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-163">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="a4bdc-164">Valitse avattava **Normalisoi**-luettelo ja valitse sitten **Tyyppi (puhelin, nimi, osoite...)**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="a4bdc-165">Määritä **Tarkkuustaso**: **Perustaso** ja **Arvo**: **Suuri**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="a4bdc-166">Anna uuden säännön **FullName, Email**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="a4bdc-167">Lisää sähköpostiosoitteen toinen ehto valitsemalla **Lisää ehto**</span><span class="sxs-lookup"><span data-stu-id="a4bdc-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="a4bdc-168">Valitse entity eCommerceContacts-kohdassa avattavasta valikosta **Sähköposti**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-168">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="a4bdc-169">Valitse entity loyCustomers-kohdassa avattavasta valikosta **Sähköposti**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-169">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="a4bdc-170">Jätä Normalisoi-kohta tyhjäksi.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="a4bdc-171">Määritä **Tarkkuustaso**: **Perustaso** ja **Arvo**: **Suuri**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Nimen ja sähköpostin vastaavuussäännön yhtenäistäminen](media/unify-match-rule.png)

7. <span data-ttu-id="a4bdc-173">Valitse **Tallenna** ja **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="a4bdc-174">Yhdistä</span><span class="sxs-lookup"><span data-stu-id="a4bdc-174">Merge</span></span>

1. <span data-ttu-id="a4bdc-175">Siirry **Yhdistä**-välilehteen.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="a4bdc-176">Vaihda **loyCustomers**-entiteetin **ContactId**-kohdassa näyttönimeksi **ContactIdLOYALTY** erottamaan se muista käsitellyistä tunnuksista.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![kanta-asiakastunnuksen contactid-nimen vaihtaminen](media/unify-merge-contactid.png)

1. <span data-ttu-id="a4bdc-178">Aloita yhdistämisprosessi valitsemalla **Tallenna** ja **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="a4bdc-179">Tehtävä 3 – tuotesuositusennusteen määrittäminen</span><span class="sxs-lookup"><span data-stu-id="a4bdc-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="a4bdc-180">Kun asiakasprofiilit on yhtenäistetty, tilauksen vaihtuvuusennusteet voidaan nyt suorittaa.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="a4bdc-181">Siirry kohtaan **Analytiikka** > **Ennuste** ja valitse sitten **Tuotesuositus**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="a4bdc-182">Valitse **Aloita**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-182">Select **Get started**.</span></span>

1. <span data-ttu-id="a4bdc-183">Anna mallille nimi **OOB - tuotesuositusmallin ennuste** ja tulosentiteetille nimi **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="a4bdc-184">Määritä mallille kolme ehtoa seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="a4bdc-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="a4bdc-185">**Tuotteiden määrä**: Määritä arvoksi **5**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="a4bdc-186">Tämä asetus määrittää, miten montaa tuotetta haluat suositella asiakkaillesi.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="a4bdc-187">**Toista odotetut ostot**: Valitse **Kyllä**, jos haluat sisällyttää tuotteet asiakkaiden aiemmin ostamaan suositukseen.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-187">**Repeat purchases expected**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="a4bdc-188">**Katso taaksepäin -ikkuna:** Valitse vähintään **365 päivää**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="a4bdc-189">Tämä asetus määrittää, miten pitkälle menneisyyteen asiakkaan aktiviteetteja tarkastellaan, kun sitä käytetään suositusten syötteenä.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Tuotesuositusmallin mallin määritykset.":::

1. <span data-ttu-id="a4bdc-191">Valitse **Pakolliset tiedot** ja valitse ostohistorian **Lisää tiedot** -kohta.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="a4bdc-192">Lisää **eCommercePurchases : eCommerce** -entiteetti ja yhdistä eCommercen kentät vastaaviin mallin edellyttämiin kenttiin.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="a4bdc-193">Liitä **eCommercePurchases : eCommerce** -entiteetti **eCommerceContacts : eCommerce** -entiteettiin.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![eCommerce-entiteetit.](media/model-purchase-join.png)

1. <span data-ttu-id="a4bdc-195">Määritä mallin aikataulu valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="a4bdc-196">Mallia on koulutettava säännöllisesti, jotta se oppii uusia malleja, kun uusia tietoja käsitellään.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="a4bdc-197">Valitse tässä esimerkissä **Kuukausittain**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="a4bdc-198">Kun tiedot on tarkistettu, valitse **Tallenna ja suorita**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="a4bdc-199">Tehtävä 4 – mallin tulosten ja selitysten tarkistaminen</span><span class="sxs-lookup"><span data-stu-id="a4bdc-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="a4bdc-200">Anna mallin suorittaa tietojen kouluttaminen ja pisteyttäminen.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="a4bdc-201">Voit nyt tarkastella tuotesuositusmallin selityksiä.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="a4bdc-202">Lisätietoja on kohdassa [Ennusteen tilan ja tulosten tarkasteleminen](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="a4bdc-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="a4bdc-203">Tehtävä 5 – eniten ostettujen tuotteiden segmentin luominen</span><span class="sxs-lookup"><span data-stu-id="a4bdc-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="a4bdc-204">Tuotantomallin suorittaminen luo uuden entiteetin, jonka saa näkyviin valitsemalla **Tiedot** > **Entiteetit**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="a4bdc-205">Voit luoda uuden segmentin mallin luoman entiteetin perusteella.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="a4bdc-206">Valitse **Segmentit**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-206">Go to **Segments**.</span></span> <span data-ttu-id="a4bdc-207">Valitse ensin **Uusi** ja sitten **Luominen kohteesta** > **Analytiikka**.</span><span class="sxs-lookup"><span data-stu-id="a4bdc-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Segmentin luominen mallin tulosteen avulla](media/segment-intelligence.png)

1. <span data-ttu-id="a4bdc-209">Valitse **OOBProductRecommendationModelPrediction**-päätepiste ja määritä segmentti:</span><span class="sxs-lookup"><span data-stu-id="a4bdc-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="a4bdc-210">Kenttä: ProductID</span><span class="sxs-lookup"><span data-stu-id="a4bdc-210">Field: ProductID</span></span>
   - <span data-ttu-id="a4bdc-211">Operaattori: Arvo</span><span class="sxs-lookup"><span data-stu-id="a4bdc-211">Operator: Value</span></span>
   - <span data-ttu-id="a4bdc-212">Arvo: Valitse kolme suosituinta tuotetunnusta</span><span class="sxs-lookup"><span data-stu-id="a4bdc-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Luo segmentti mallin tuloksista.":::

<span data-ttu-id="a4bdc-214">Nyt sinulla on dynaamisesti päivitetty segmentti, joka määrittää asiakkaat, jotka ovat valmiita ostamaan kolme suositeltua tuotetta</span><span class="sxs-lookup"><span data-stu-id="a4bdc-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="a4bdc-215">Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a4bdc-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
