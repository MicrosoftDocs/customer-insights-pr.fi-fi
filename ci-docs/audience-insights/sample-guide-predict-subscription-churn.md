---
title: Tilauksen vaihtuvuusennusteen näyteopas
description: Tämän näyteoppaan avulla voi kokeilla valmista tilauksen vaihtuvuusennustemallia.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653976"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="5eed5-103">Tilauksen vaihtuvuusennusteen (esiversio) näyteopas</span><span class="sxs-lookup"><span data-stu-id="5eed5-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="5eed5-104">Aiheessa käsitellään kattavasti tilauksen vaihtuvuusennuste-esimerkki käyttämällä alla olevia näytetietoja.</span><span class="sxs-lookup"><span data-stu-id="5eed5-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="5eed5-105">Skenaario</span><span class="sxs-lookup"><span data-stu-id="5eed5-105">Scenario</span></span>

<span data-ttu-id="5eed5-106">Contoso on yritys, joka tuottaa laadukasta kahvia ja laadukkaita kahvinkeittimiä. Se myy näitä tuotteita Contoso Coffee -sivustossa.</span><span class="sxs-lookup"><span data-stu-id="5eed5-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="5eed5-107">Yritys aloitti äskettäin tilaustoiminnan asiakkaille, jotka hakevat kahvia säännöllisesti.</span><span class="sxs-lookup"><span data-stu-id="5eed5-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="5eed5-108">Yrityksen tavoitteena on selvittää, ketkä tilauksen tehneet asiakkaat saattavat peruuttaa tilauksensa seuraavien kuukausien aikana.</span><span class="sxs-lookup"><span data-stu-id="5eed5-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="5eed5-109">Sen tietäminen, ketkä asiakkaat **todennäköisesti vaihtuvat**, voi auttaa yritystä säästämään markkinointitoimia keskittymällä kyseisten asiakkaiden säilyttämiseen.</span><span class="sxs-lookup"><span data-stu-id="5eed5-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5eed5-110">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="5eed5-110">Prerequisites</span></span>

- <span data-ttu-id="5eed5-111">Vähintään [osallistujan oikeudet](permissions.md) Customer Insightsissa.</span><span class="sxs-lookup"><span data-stu-id="5eed5-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="5eed5-112">Seuraavat vaiheet on suositeltavaa toteuttaa [uudessa ympäristössä](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="5eed5-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="5eed5-113">Tehtävä 1 – tietojen käsitteleminen</span><span class="sxs-lookup"><span data-stu-id="5eed5-113">Task 1 - Ingest Data</span></span>

<span data-ttu-id="5eed5-114">Tutustu etenkin artikkeleihin, joissa on [tietoja tietojen käsittelystä](data-sources.md) ja [tietolähteiden tuomisestä Power Query -yhdistimiä](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="5eed5-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="5eed5-115">Seuraavissa tiedoissa oletetaan, että tietojen käsittely on yleisesti ottaen tuttua.</span><span class="sxs-lookup"><span data-stu-id="5eed5-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="5eed5-116">Asiakas tietojen käsitteleminen sähköisen kaupankäynnin ympäristössä</span><span class="sxs-lookup"><span data-stu-id="5eed5-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="5eed5-117">Luo **eCommerce**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.</span><span class="sxs-lookup"><span data-stu-id="5eed5-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="5eed5-118">Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="5eed5-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="5eed5-119">Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="5eed5-120">Päivitä seuraavien sarakkeiden tietotyyppi:</span><span class="sxs-lookup"><span data-stu-id="5eed5-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="5eed5-121">**DateOfBirth**: päivämäärä</span><span class="sxs-lookup"><span data-stu-id="5eed5-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="5eed5-122">**CreatedOn**: päivämäärä, aika ja aikavyöhyke</span><span class="sxs-lookup"><span data-stu-id="5eed5-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="5eed5-123">![Syntymäpäivän muuttaminen päivämääräksi](media/ecommerce-dob-date.PNG "syntymäpäivän muuntaminen päivämääräksi")</span><span class="sxs-lookup"><span data-stu-id="5eed5-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="5eed5-124">Vaihda oikean ruudun Nimi-kentän tietolähteen nimi. Vanha nimi on **Query** ja uusi on **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="5eed5-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="5eed5-125">Tallenna tietolähde.</span><span class="sxs-lookup"><span data-stu-id="5eed5-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="5eed5-126">Asiakastietojen käyttäminen kanta-asiakasrakenteesta</span><span class="sxs-lookup"><span data-stu-id="5eed5-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="5eed5-127">Luo **LoyaltyScheme**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.</span><span class="sxs-lookup"><span data-stu-id="5eed5-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="5eed5-128">Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="5eed5-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="5eed5-129">Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="5eed5-130">Päivitä seuraavien sarakkeiden tietotyyppi:</span><span class="sxs-lookup"><span data-stu-id="5eed5-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="5eed5-131">**DateOfBirth**: päivämäärä</span><span class="sxs-lookup"><span data-stu-id="5eed5-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="5eed5-132">**RewardsPoints**: kokonaisluku</span><span class="sxs-lookup"><span data-stu-id="5eed5-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="5eed5-133">**CreatedOn**: päivämäärä, aika</span><span class="sxs-lookup"><span data-stu-id="5eed5-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="5eed5-134">Vaihda oikean ruudun Nimi-kentän tietolähteen nimi. Vanha nimi on **Query** ja uusi on **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="5eed5-135">Tallenna tietolähde.</span><span class="sxs-lookup"><span data-stu-id="5eed5-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="5eed5-136">Tilaustietojen käsitteleminen</span><span class="sxs-lookup"><span data-stu-id="5eed5-136">Ingest subscription information</span></span>

1. <span data-ttu-id="5eed5-137">Luo **SubscriptionHistory**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.</span><span class="sxs-lookup"><span data-stu-id="5eed5-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="5eed5-138">Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="5eed5-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="5eed5-139">Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="5eed5-140">Päivitä seuraavien sarakkeiden tietotyyppi:</span><span class="sxs-lookup"><span data-stu-id="5eed5-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="5eed5-141">**SubscriptioID**: kokonaisluku</span><span class="sxs-lookup"><span data-stu-id="5eed5-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="5eed5-142">**SubscriptionAmount**: valuutta</span><span class="sxs-lookup"><span data-stu-id="5eed5-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="5eed5-143">**SubscriptionEndDate**: päivämäärä, aika</span><span class="sxs-lookup"><span data-stu-id="5eed5-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="5eed5-144">**SubscriptionStartDate**: päivämäärä, aika</span><span class="sxs-lookup"><span data-stu-id="5eed5-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="5eed5-145">**TransactionDate**: päivämäärä, aika</span><span class="sxs-lookup"><span data-stu-id="5eed5-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="5eed5-146">**IsRecurring**: tosi, epätosi</span><span class="sxs-lookup"><span data-stu-id="5eed5-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="5eed5-147">**Is_auto_renew**: tosi, epätosi</span><span class="sxs-lookup"><span data-stu-id="5eed5-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="5eed5-148">**RecurringFrequencyInMonths**: kokonaisluku</span><span class="sxs-lookup"><span data-stu-id="5eed5-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="5eed5-149">Vaihda oikean ruudun Nimi-kentän tietolähteen nimi. Vanha nimi on **Query** ja uusi on **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-149">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="5eed5-150">Tallenna tietolähde.</span><span class="sxs-lookup"><span data-stu-id="5eed5-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="5eed5-151">Sivustoarvioista saatujen asiakastietojen käsitteleminen</span><span class="sxs-lookup"><span data-stu-id="5eed5-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="5eed5-152">Luo **Website**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.</span><span class="sxs-lookup"><span data-stu-id="5eed5-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="5eed5-153">Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="5eed5-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="5eed5-154">Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="5eed5-155">Päivitä seuraavien sarakkeiden tietotyyppi:</span><span class="sxs-lookup"><span data-stu-id="5eed5-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="5eed5-156">**ReviewRating**: kokonaisluku</span><span class="sxs-lookup"><span data-stu-id="5eed5-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="5eed5-157">**ReviewDate**: päivämäärä</span><span class="sxs-lookup"><span data-stu-id="5eed5-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="5eed5-158">Vaihda oikean ruudun Nimi-kentän tietolähteen nimi. Vanha nimi on **Query** ja uusi on **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="5eed5-159">Tehtävä 2 – tietojen yhtenäistäminen</span><span class="sxs-lookup"><span data-stu-id="5eed5-159">Task 2 - Data unification</span></span>

<span data-ttu-id="5eed5-160">Kun tiedot on käsitelty, aloitettavalla **yhdistämismäärityksen, vastaavuuden, yhdistämisen** prosessilla luodaan yhtenäistetty asiakasprofiili.</span><span class="sxs-lookup"><span data-stu-id="5eed5-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="5eed5-161">Lisätietoja on kohdassa [Tietojen yhtenäistäminen](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="5eed5-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="5eed5-162">Liitä</span><span class="sxs-lookup"><span data-stu-id="5eed5-162">Map</span></span>

1. <span data-ttu-id="5eed5-163">Kun tiedot on käsitelty, tee eCommerce- ja Loyalty-tietojen yhdistämismääritys yleisiin tietotyyppeihin.</span><span class="sxs-lookup"><span data-stu-id="5eed5-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="5eed5-164">Valitse **Tiedot** > **Yhtenäistä** > **Määritä vastaavuus**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="5eed5-165">Valitse asiakasprofiilin ilmaisevat entiteetit: **eCommerceContacts** ja **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="ecommerce- ja loyalty-tietolähteiden yhtenäistäminen":::

1. <span data-ttu-id="5eed5-167">Valitse **ContactId** **eCommerceContacts**-perusavaimeksi ja **LoyaltyID** **loyCustomers**-perusavaimeksi.</span><span class="sxs-lookup"><span data-stu-id="5eed5-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Yhtenäistäminen LoyaltyId-perusavaimena":::

### <a name="match"></a><span data-ttu-id="5eed5-169">Täsmäytä</span><span class="sxs-lookup"><span data-stu-id="5eed5-169">Match</span></span>

1. <span data-ttu-id="5eed5-170">Valitse **Täsmäytä**-välilehdessä **Määritä järjestys**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="5eed5-171">Valitse avattavassa **Ensisijainen**-luettelossa **eCommerceContacts : eCommerce** ensisijaiseksi lähteeksi ja sisällytä kaikki tietueet.</span><span class="sxs-lookup"><span data-stu-id="5eed5-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="5eed5-172">Valitse avattavassa **Entiteetti 2** -luettelossa **loyCustomers : LoyaltyScheme** ja sisällytä kaikki tietueet.</span><span class="sxs-lookup"><span data-stu-id="5eed5-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="eCommerce- ja Loyalty-täsmäytyksen yhtenäistäminen":::

1. <span data-ttu-id="5eed5-174">Valitse **Luo uusi sääntö**</span><span class="sxs-lookup"><span data-stu-id="5eed5-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="5eed5-175">Lisää ensimmäinen ehto FullName-kentässä.</span><span class="sxs-lookup"><span data-stu-id="5eed5-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="5eed5-176">eCommerceContacts: valitse **FullName** avattavassa kentässä.</span><span class="sxs-lookup"><span data-stu-id="5eed5-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="5eed5-177">loyCustomers: valitse **FullName** avattavassa kentässä.</span><span class="sxs-lookup"><span data-stu-id="5eed5-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="5eed5-178">Valitse avattava **Normalisoi**-luettelo ja valitse sitten **Tyyppi (puhelin, nimi, osoite...)**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="5eed5-179">Määritä **Tarkkuustaso**: **Perustaso** ja **Arvo**: **Suuri**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="5eed5-180">Anna uuden säännön **FullName, Email**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="5eed5-181">Lisää sähköpostiosoitteen toinen ehto valitsemalla **Lisää ehto**</span><span class="sxs-lookup"><span data-stu-id="5eed5-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="5eed5-182">Valitse entiteetin eCommerceContacts-asetukseksi avattavassa luettelossa **EMail**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="5eed5-183">Valitse entiteetin loyCustomers-asetukseksi avattavassa luettelossa **EMail**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="5eed5-184">Jätä Normalisoi-kohta tyhjäksi.</span><span class="sxs-lookup"><span data-stu-id="5eed5-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="5eed5-185">Määritä **Tarkkuustaso**: **Perustaso** ja **Arvo**: **Suuri**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Nimen ja sähköpostin vastaavuussäännön yhtenäistäminen":::

7. <span data-ttu-id="5eed5-187">Valitse **Tallenna** ja **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="5eed5-188">Yhdistä</span><span class="sxs-lookup"><span data-stu-id="5eed5-188">Merge</span></span>

1. <span data-ttu-id="5eed5-189">Siirry **Yhdistä**-välilehteen.</span><span class="sxs-lookup"><span data-stu-id="5eed5-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="5eed5-190">Vaihda **loyCustomers**-entiteetin **ContactId**-kohdassa näyttönimeksi **ContactIdLOYALTY** erottamaan se muista käsitellyistä tunnuksista.</span><span class="sxs-lookup"><span data-stu-id="5eed5-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="kanta-asiakastunnuksen contactid-nimen vaihtaminen":::

1. <span data-ttu-id="5eed5-192">Aloita yhdistämisprosessi valitsemalla **Tallenna** ja **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="5eed5-193">Tehtävä 3 – tilauksen vaihtuvuusennusteen määrittäminen</span><span class="sxs-lookup"><span data-stu-id="5eed5-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="5eed5-194">Kun asiakasprofiilit on yhtenäistetty, tilauksen vaihtuvuusennusteet voidaan nyt suorittaa.</span><span class="sxs-lookup"><span data-stu-id="5eed5-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="5eed5-195">Artikkelissa [Tilauksen vaihtuvuusennuste (esiversio)](predict-subscription-churn.md) on tarkat ohjeet.</span><span class="sxs-lookup"><span data-stu-id="5eed5-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="5eed5-196">Valitse **Analytiikka** > **Tutustu** ja valitse sitten **Asiakasvaihtuvuusmalli**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="5eed5-197">Valitse ensin **Tilaus**-vaihtoehto ja sitten **Aloita**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="5eed5-198">Valitse **OOB-tilauksen vaihtuvuusennuste** ja tuloste-entiteetti **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="5eed5-199">Määritä vaihtuvuusmallille kaksi ehtoa:</span><span class="sxs-lookup"><span data-stu-id="5eed5-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="5eed5-200">**Päiviä tilauksen päättymisestä**: **vähintään 60** päivää.</span><span class="sxs-lookup"><span data-stu-id="5eed5-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="5eed5-201">Jos asiakas ei ole uusinut tilaustaan tänä aikana tilauksen päättymisen jälkeen, sitä pidetään vaihtuneena.</span><span class="sxs-lookup"><span data-stu-id="5eed5-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="5eed5-202">**Vaihtuvuusmääritelmä**: **vähintään 93** päivää.</span><span class="sxs-lookup"><span data-stu-id="5eed5-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="5eed5-203">Kesto, jonka malli ennustaa asiakkaiden vaihtuvuudelle.</span><span class="sxs-lookup"><span data-stu-id="5eed5-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="5eed5-204">Mitä pidemmälle tulevaisuuteen tarkastelu ulottuu, sitä epätarkemmat tulokset ovat.</span><span class="sxs-lookup"><span data-stu-id="5eed5-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Mallin ennusteikkunan ja vaihtuvuusmääritelmän valitseminen":::

1. <span data-ttu-id="5eed5-206">Valitse **Lisää pakolliset tiedot** ja valitse tilaushistorian osalta **Lisää tiedot**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="5eed5-207">Lisää **Subscription : SubscriptionHistory** -entiteetti ja yhdistä eCommercen kentät vastaaviin mallin edellyttämiin kenttiin.</span><span class="sxs-lookup"><span data-stu-id="5eed5-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="5eed5-208">Liitä **Subscription : SubscriptionHistory** -entiteetti **eCommerceContacts : eCommerce** -entiteettiin ja anna suhteen nimeksi **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="eCommerce-entiteettien liittäminen":::

1. <span data-ttu-id="5eed5-210">Lisää **webReviews : Website** -entiteetti asiakasaktiviteeteissa ja yhdistä webReviews-kentät vastaaviin mallin edellyttämiin kenttiin.</span><span class="sxs-lookup"><span data-stu-id="5eed5-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="5eed5-211">Perusavain: ReviewId</span><span class="sxs-lookup"><span data-stu-id="5eed5-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="5eed5-212">Aikaleima: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="5eed5-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="5eed5-213">Tapahtuma: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="5eed5-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="5eed5-214">Määritä sivustoarvioaktiviteetti.</span><span class="sxs-lookup"><span data-stu-id="5eed5-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="5eed5-215">Valitse **Arvio**-aktiviteetti ja liitä **webReviews : Website** -entiteetti ja **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="5eed5-216">Määritä mallin aikataulu valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="5eed5-217">Mallia on koulutettava säännöllisesti, jotta se oppii uusia malleja, kun uusia tietoja käsitellään.</span><span class="sxs-lookup"><span data-stu-id="5eed5-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="5eed5-218">Valitse tässä esimerkissä **Kuukausittain**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="5eed5-219">Kun tiedot on tarkistettu, valitse **Tallenna ja suorita**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="5eed5-220">Tehtävä 4 – mallin tulosten ja selitysten tarkistaminen</span><span class="sxs-lookup"><span data-stu-id="5eed5-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="5eed5-221">Anna mallin suorittaa tietojen kouluttaminen ja pisteyttäminen.</span><span class="sxs-lookup"><span data-stu-id="5eed5-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="5eed5-222">Voit nyt tarkastella tilauksen vaihtuvuusmallin selityksiä.</span><span class="sxs-lookup"><span data-stu-id="5eed5-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="5eed5-223">Lisätietoja on kohdassa [Ennusteen tilan ja tulosten tarkasteleminen](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="5eed5-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="5eed5-224">Tehtävä 5 – Suuren vaihtuvuusriskin asiakkaiden segmentin luominen</span><span class="sxs-lookup"><span data-stu-id="5eed5-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="5eed5-225">Tuotantomallin suorittaminen luo uuden entiteetin, jonka saa näkyviin valitsemalla **Tiedot** > **Entiteetit**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="5eed5-226">Voit luoda uuden segmentin mallin luoman entiteetin perusteella.</span><span class="sxs-lookup"><span data-stu-id="5eed5-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="5eed5-227">Valitse **Segmentit**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-227">Go to **Segments**.</span></span> <span data-ttu-id="5eed5-228">Valitse ensin **Uusi** ja sitten **Luominen kohteesta** > **Analytiikka**.</span><span class="sxs-lookup"><span data-stu-id="5eed5-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Segmentin luominen mallin tulosteen avulla":::

1. <span data-ttu-id="5eed5-230">Valitse **OOBSubscriptionChurnPrediction**-päätepiste ja määritä segmentti:</span><span class="sxs-lookup"><span data-stu-id="5eed5-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="5eed5-231">Kenttä: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="5eed5-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="5eed5-232">Operaattori: suurempi kuin</span><span class="sxs-lookup"><span data-stu-id="5eed5-232">Operator: greater than</span></span>
   - <span data-ttu-id="5eed5-233">Arvo: 0,6</span><span class="sxs-lookup"><span data-stu-id="5eed5-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Tilauksen vaihtuvuussegmentin määrittäminen":::

<span data-ttu-id="5eed5-235">Käytössä on nyt dynaamisesti päivitettävä segmentti, joka määrittää tämän tilausliiketoiminnan suuren vaihtuvuusriskin asiakkaat.</span><span class="sxs-lookup"><span data-stu-id="5eed5-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="5eed5-236">Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).</span><span class="sxs-lookup"><span data-stu-id="5eed5-236">For more information, see [Create and manage segments](segments.md).</span></span>
