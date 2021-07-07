---
title: Asiakkaan elinkaariarvoennuste esimerkkioppaassa
description: Tämän esimerkkioppaan avulla voit kokeilla asiakkaan ennustearvoa.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306345"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="dc362-103">Asiakkaan elinkaariarvoennuste (CLV) esimerkkioppaassa</span><span class="sxs-lookup"><span data-stu-id="dc362-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="dc362-104">Tässä oppaassa kerrotaan esimerkkidatan avulla asiakkaan elinkaariarvon (CLV) ennakoinnista Customer Insightsissa alusta loppuun asti.</span><span class="sxs-lookup"><span data-stu-id="dc362-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="dc362-105">Skenaario</span><span class="sxs-lookup"><span data-stu-id="dc362-105">Scenario</span></span>

<span data-ttu-id="dc362-106">Contoso on yritys, joka tuottaa laadukkaat kahvi- ja kahvikoneet.</span><span class="sxs-lookup"><span data-stu-id="dc362-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="dc362-107">He myyvät tuotteita Contoso Coffee-verkkosivustonsa kautta.</span><span class="sxs-lookup"><span data-stu-id="dc362-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="dc362-108">Yritys haluaa ymmärtää arvon (tuoton), jonka asiakkaat voivat luoda seuraavien 12 kuukauden aikana.</span><span class="sxs-lookup"><span data-stu-id="dc362-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="dc362-109">Tietäen asiakkaiden odotetun arvon seuraavien 12 kuukauden aikana auttavat heitä ohjaamaan markkinointia suuriarvoisiin asiakkaisiin.</span><span class="sxs-lookup"><span data-stu-id="dc362-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dc362-110">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="dc362-110">Prerequisites</span></span>

- <span data-ttu-id="dc362-111">Ainakin [Osallistujan oikeudet](permissions.md) kohdeyleisön käyttöoikeuksissa.</span><span class="sxs-lookup"><span data-stu-id="dc362-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="dc362-112">Seuraavat vaiheet on suositeltavaa toteuttaa [uudessa ympäristössä](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="dc362-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="dc362-113">Tehtävä 1 – Tietojen käsitteleminen</span><span class="sxs-lookup"><span data-stu-id="dc362-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="dc362-114">Tutustu artikkeleihin [tietojen käsittelystä](data-sources.md) ja [tietolähteiden käsittelystä Power Query -yhdistimien avulla](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="dc362-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="dc362-115">Seuraavissa tiedoissa oletetaan, että tietojen käsittely on yleisesti ottaen tuttua.</span><span class="sxs-lookup"><span data-stu-id="dc362-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="dc362-116">Asiakas tietojen käsitteleminen sähköisen kaupankäynnin ympäristössä</span><span class="sxs-lookup"><span data-stu-id="dc362-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="dc362-117">Luo **eCommerce**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.</span><span class="sxs-lookup"><span data-stu-id="dc362-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="dc362-118">Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="dc362-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="dc362-119">Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.</span><span class="sxs-lookup"><span data-stu-id="dc362-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="dc362-120">Päivitä seuraavien sarakkeiden tietotyyppi:</span><span class="sxs-lookup"><span data-stu-id="dc362-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="dc362-121">**DateOfBirth**: päivämäärä</span><span class="sxs-lookup"><span data-stu-id="dc362-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="dc362-122">**CreatedOn**: päivämäärä, aika ja aikavyöhyke</span><span class="sxs-lookup"><span data-stu-id="dc362-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Syntymäpäivän muuntaminen päivämääräksi.":::

1. <span data-ttu-id="dc362-124">Vaihda oikean ruudun Nimi-kentän tietolähteen nimi. Vanha nimi on **Query** ja uusi on **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="dc362-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="dc362-125">**Tallenna** tietolähde.</span><span class="sxs-lookup"><span data-stu-id="dc362-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="dc362-126">Verkko-ostostietojen käsitteleminen</span><span class="sxs-lookup"><span data-stu-id="dc362-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="dc362-127">Lisää toinen tietojoukko samaan **eCommerce**-tietolähteeseen.</span><span class="sxs-lookup"><span data-stu-id="dc362-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="dc362-128">Valitse **Text/CSV**-yhdistin uudelleen.</span><span class="sxs-lookup"><span data-stu-id="dc362-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="dc362-129">Anna **Verkko-ostokset**-tietojen URL-osoite https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="dc362-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="dc362-130">Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.</span><span class="sxs-lookup"><span data-stu-id="dc362-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="dc362-131">Päivitä seuraavien sarakkeiden tietotyyppi:</span><span class="sxs-lookup"><span data-stu-id="dc362-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="dc362-132">**PurchasedOn**: päivämäärä ja aika</span><span class="sxs-lookup"><span data-stu-id="dc362-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="dc362-133">**TotalPrice**: valuutta</span><span class="sxs-lookup"><span data-stu-id="dc362-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="dc362-134">Vaihda sivuruudun **Nimi**-kentän tietolähteen nimi. Vanha nimi on **Query** ja uusi on **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="dc362-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="dc362-135">**Tallenna** tietolähde.</span><span class="sxs-lookup"><span data-stu-id="dc362-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="dc362-136">Asiakastietojen käyttäminen kanta-asiakasrakenteesta</span><span class="sxs-lookup"><span data-stu-id="dc362-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="dc362-137">Luo **LoyaltyScheme**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.</span><span class="sxs-lookup"><span data-stu-id="dc362-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="dc362-138">Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="dc362-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="dc362-139">Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.</span><span class="sxs-lookup"><span data-stu-id="dc362-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="dc362-140">Päivitä seuraavien sarakkeiden tietotyyppi:</span><span class="sxs-lookup"><span data-stu-id="dc362-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="dc362-141">**DateOfBirth**: päivämäärä</span><span class="sxs-lookup"><span data-stu-id="dc362-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="dc362-142">**RewardsPoints**: kokonaisluku</span><span class="sxs-lookup"><span data-stu-id="dc362-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="dc362-143">**CreatedOn**: päivämäärä, aika</span><span class="sxs-lookup"><span data-stu-id="dc362-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="dc362-144">Vaihda oikeanpuoleisen ruudun **Nimi**-kentässä tietolähteen nimi **Query** nimeksi **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="dc362-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="dc362-145">**Tallenna** tietolähde.</span><span class="sxs-lookup"><span data-stu-id="dc362-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="dc362-146">Sivustoarvioista saatujen asiakastietojen käsitteleminen</span><span class="sxs-lookup"><span data-stu-id="dc362-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="dc362-147">Luo **Website**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.</span><span class="sxs-lookup"><span data-stu-id="dc362-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="dc362-148">Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="dc362-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="dc362-149">Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.</span><span class="sxs-lookup"><span data-stu-id="dc362-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="dc362-150">Päivitä seuraavien sarakkeiden tietotyyppi:</span><span class="sxs-lookup"><span data-stu-id="dc362-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="dc362-151">**Arvosteluarvosana**: desimaaliluku</span><span class="sxs-lookup"><span data-stu-id="dc362-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="dc362-152">**ReviewDate**: päivämäärä</span><span class="sxs-lookup"><span data-stu-id="dc362-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="dc362-153">Nimeä tietolähteesi oikeanpuoleisen ruudun Nimi-kenttä **Kyselystä** **Arvosteluiksi**.</span><span class="sxs-lookup"><span data-stu-id="dc362-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="dc362-154">**Tallenna** tietolähde.</span><span class="sxs-lookup"><span data-stu-id="dc362-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="dc362-155">Tehtävä 2 – tietojen yhtenäistäminen</span><span class="sxs-lookup"><span data-stu-id="dc362-155">Task 2 - Data unification</span></span>

<span data-ttu-id="dc362-156">Tietojen purkamisen jälkeen aloitetaan nyt tietojen yhdistäminen ja luodaan yhtenäinen asiakasprofiili.</span><span class="sxs-lookup"><span data-stu-id="dc362-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="dc362-157">Lisätietoja on kohdassa [Tietojen yhtenäistäminen](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="dc362-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="dc362-158">Liitä</span><span class="sxs-lookup"><span data-stu-id="dc362-158">Map</span></span>

1. <span data-ttu-id="dc362-159">Kun tiedot on käsitelty, tee eCommerce- ja Loyalty-tietojen yhdistämismääritys yleisiin tietotyyppeihin.</span><span class="sxs-lookup"><span data-stu-id="dc362-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="dc362-160">Valitse **Tiedot** > **Yhtenäistä** > **Määritä vastaavuus**.</span><span class="sxs-lookup"><span data-stu-id="dc362-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="dc362-161">Valitse asiakasprofiilin ilmaisevat entiteetit: **eCommerceContacts** ja **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="dc362-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="dc362-162">Valitse **Käytä**.</span><span class="sxs-lookup"><span data-stu-id="dc362-162">Then, select **Apply**.</span></span>

   ![ecommerce- ja loyalty-tietolähteiden yhtenäistäminen](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="dc362-164">Valitse **ContactId** **eCommerceContacts**-perusavaimeksi ja **LoyaltyID** **loyCustomers**-perusavaimeksi.</span><span class="sxs-lookup"><span data-stu-id="dc362-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Yhtenäistäminen LoyaltyId-perusavaimena](media/unify-loyaltyid.png)

1. <span data-ttu-id="dc362-166">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="dc362-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="dc362-167">Täsmäytä</span><span class="sxs-lookup"><span data-stu-id="dc362-167">Match</span></span>

1. <span data-ttu-id="dc362-168">Valitse **Täsmäytä**-välilehdessä **Määritä järjestys**.</span><span class="sxs-lookup"><span data-stu-id="dc362-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="dc362-169">Valitse avattavasta **Ensisijainen**-luettelosta ensisijaiseksi lähteeksi **eCommerceContacts: eCommerce** ja sisällytä kaikki tietueet.</span><span class="sxs-lookup"><span data-stu-id="dc362-169">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="dc362-170">Valitse avattavasta **Entiteetti 2** -luettelosta **loyCustomers: LoyaltyScheme** ja sisällytä kaikki tietueet.</span><span class="sxs-lookup"><span data-stu-id="dc362-170">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![eCommerce- ja Loyalty-täsmäytyksen yhtenäistäminen](media/unify-match-order.png)

1. <span data-ttu-id="dc362-172">Valitse **Lisää sääntö**</span><span class="sxs-lookup"><span data-stu-id="dc362-172">Select **Add rule**</span></span>

1. <span data-ttu-id="dc362-173">Lisää ensimmäinen ehto FullName-kentässä.</span><span class="sxs-lookup"><span data-stu-id="dc362-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="dc362-174">Valitse eCommerceContacts-kohdassa avattavasta valikosta **FullName**.</span><span class="sxs-lookup"><span data-stu-id="dc362-174">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="dc362-175">Valitse loyCustomers-kohdassa avattavasta valikosta **FullName**.</span><span class="sxs-lookup"><span data-stu-id="dc362-175">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="dc362-176">Valitse avattava **Normalisoi**-luettelo ja valitse sitten **Tyyppi (puhelin, nimi, osoite,...)**.</span><span class="sxs-lookup"><span data-stu-id="dc362-176">Select the **Normalize** dropdown and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="dc362-177">Määritä **Tarkkuustaso**: **Perustaso** ja **Arvo**: **Suuri**.</span><span class="sxs-lookup"><span data-stu-id="dc362-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="dc362-178">Anna uuden säännön **FullName, Email**.</span><span class="sxs-lookup"><span data-stu-id="dc362-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="dc362-179">Lisää sähköpostiosoitteen toinen ehto valitsemalla **Lisää ehto**</span><span class="sxs-lookup"><span data-stu-id="dc362-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="dc362-180">Valitse entity eCommerceContacts-kohdassa avattavasta valikosta **Sähköposti**.</span><span class="sxs-lookup"><span data-stu-id="dc362-180">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="dc362-181">Valitse entity loyCustomers-kohdassa avattavasta valikosta **Sähköposti**.</span><span class="sxs-lookup"><span data-stu-id="dc362-181">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="dc362-182">Jätä Normalisoi-kohta tyhjäksi.</span><span class="sxs-lookup"><span data-stu-id="dc362-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="dc362-183">Määritä **Tarkkuustaso**: **Perustaso** ja **Arvo**: **Suuri**.</span><span class="sxs-lookup"><span data-stu-id="dc362-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Nimen ja sähköpostin vastaavuussäännön yhtenäistäminen](media/unify-match-rule.png)

1. <span data-ttu-id="dc362-185">Valitse **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="dc362-185">Select **Done**.</span></span>

1. <span data-ttu-id="dc362-186">Valitse **Tallenna** ja **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="dc362-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="dc362-187">Yhdistä</span><span class="sxs-lookup"><span data-stu-id="dc362-187">Merge</span></span>

1. <span data-ttu-id="dc362-188">Siirry **Yhdistä**-välilehteen.</span><span class="sxs-lookup"><span data-stu-id="dc362-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="dc362-189">Vaihda **loyCustomers**-entiteetin **ContactId**-kohdassa näyttönimeksi **ContactIdLOYALTY** erottamaan se muista käsitellyistä tunnuksista.</span><span class="sxs-lookup"><span data-stu-id="dc362-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![kanta-asiakastunnuksen contactid-nimen vaihtaminen](media/unify-merge-contactid.png)

1. <span data-ttu-id="dc362-191">Valitse **Tallenna** ja **Suorita yhdistäminen ja sitä seuraavat prosessit**.</span><span class="sxs-lookup"><span data-stu-id="dc362-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="dc362-192">Tehtävä 3 ‑ Määritä asiakkaan elinkaariarvon ennuste</span><span class="sxs-lookup"><span data-stu-id="dc362-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="dc362-193">Kun yhtenäiset asiakasprofiilit ovat käytössä, voidaan nyt suorittaa asiakkaan elinkaariarvon ennuste.</span><span class="sxs-lookup"><span data-stu-id="dc362-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="dc362-194">Yksityiskohtaiset ohjeet ovat kohdassa [Asiakkaan elinkaariarvo ennuste (esiversio) ](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="dc362-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="dc362-195">Siirry kohtaan **Älykäs toiminto**  > **Ennusteet** ja valitse **Asiakkaan elinkaariarvomalli**.</span><span class="sxs-lookup"><span data-stu-id="dc362-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="dc362-196">Käy sivuruudun tiedot läpi ja valitse **Aloitus**.</span><span class="sxs-lookup"><span data-stu-id="dc362-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="dc362-197">Anna mallille nimeksi **OOB eCommerce CLV-ennuste** ja tulosentiteetille **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="dc362-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="dc362-198">Määritä CLV-mallin malliasetukset:</span><span class="sxs-lookup"><span data-stu-id="dc362-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="dc362-199">**Ennusteajanjakso**: **12 kuukautta tai 1 vuosi**.</span><span class="sxs-lookup"><span data-stu-id="dc362-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="dc362-200">Tämä asetus määrittää, miten paljon tulevaisuudessa voidaan ennustaa asiakkaan elinkaariarvoa.</span><span class="sxs-lookup"><span data-stu-id="dc362-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="dc362-201">**Aktiiviset asiakkaat**: määritä, mitä aktiiviset asiakkaat tarkoittavat liiketoiminnassa.</span><span class="sxs-lookup"><span data-stu-id="dc362-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="dc362-202">Määritä historiallinen ajanjakso, jolloin asiakkaalla on oltava vähintään yksi tapahtuma, jotta häntä voidaan pitää aktiivisena.</span><span class="sxs-lookup"><span data-stu-id="dc362-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="dc362-203">Malli ennustaa vain aktiivisten asiakkaiden asiakkaan elinkaaren arvon.</span><span class="sxs-lookup"><span data-stu-id="dc362-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="dc362-204">Valitse, annetaanko mallin laskea ajanjakso historiallisten tapahtumien tietojen perusteella vai antaa aikaväli.</span><span class="sxs-lookup"><span data-stu-id="dc362-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="dc362-205">Tässä esimerkkioppaassa **mallin avulla voi laskea ostovälin**, joka on oletusvaihtoehto.</span><span class="sxs-lookup"><span data-stu-id="dc362-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="dc362-206">**Erittäin arvokkaat asiakkaat**: Määritä arvokkaat asiakkaat prosenttipisteeksi eniten maksavista asiakkaista.</span><span class="sxs-lookup"><span data-stu-id="dc362-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="dc362-207">Mallin avulla saadaan tuloksia, jotka sopivat yrityksen arvokkaisiin asiakkaisiin.</span><span class="sxs-lookup"><span data-stu-id="dc362-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="dc362-208">Voit antaa mallin määrittää korkean arvon asiakkaat.</span><span class="sxs-lookup"><span data-stu-id="dc362-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="dc362-209">Se käyttää heuristista sääntöä, joka johtaa prosenttipisteen.</span><span class="sxs-lookup"><span data-stu-id="dc362-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="dc362-210">Voit myös määrittää arvokkaat asiakkaat prosenttipisteeksi eniten maksavista tulevista asiakkaista.</span><span class="sxs-lookup"><span data-stu-id="dc362-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="dc362-211">Tässä esimerkkioppaassa määritetään manuaalisesti arvokkaat asiakkaat **ylimmäksi 30 prosentiksi aktiivisista maksavista asiakkaista** ja valitaan **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="dc362-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV-mallin ohjatun käyttökokemuksen asetukset-vaihe.":::

1. <span data-ttu-id="dc362-213">Valitse **Pakolliset tiedot** -vaiheessa **Lisää tietoja**, jotta saat tapahtumahistoriatiedot.</span><span class="sxs-lookup"><span data-stu-id="dc362-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="dc362-214">Lisää **eCommercePurchases : eCommerce** -entiteetti ja yhdistä mallin edellyttämät määritteet:</span><span class="sxs-lookup"><span data-stu-id="dc362-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="dc362-215">Tapahtuman tunnus: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="dc362-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="dc362-216">Tapahtuman päivämäärä: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="dc362-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="dc362-217">Tapahtuman summa: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="dc362-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="dc362-218">Tuotetunnus: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="dc362-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="dc362-219">Valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="dc362-219">Select **Next**.</span></span>

1. <span data-ttu-id="dc362-220">Määritä **eCommercePurchases : eCommerce**-entiteetin ja **eCommerceContacts : eCommerce**-entiteetin välinen suhde.</span><span class="sxs-lookup"><span data-stu-id="dc362-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="dc362-221">**Lisätiedot (valinnainen)**-vaiheen avulla voit lisätä asiakasaktiviteettitietoja.</span><span class="sxs-lookup"><span data-stu-id="dc362-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="dc362-222">Näiden tietojen avulla saat enemmän tietoja asiakkaan kanssakäynnistä yrityksesi kanssa, mikä voi auttaa CLV:ssä.</span><span class="sxs-lookup"><span data-stu-id="dc362-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="dc362-223">Lisäämällä tärkeitä asiakasvuorovaikutuksia, kuten verkkolokeja, asiakaspalvelulokeja tai palkitsemisohjelmahistoriaa, voi parantaa ennusteiden tarkkuutta.</span><span class="sxs-lookup"><span data-stu-id="dc362-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="dc362-224">Valitse **Lisää tietoja**, jos haluat lisätä asiakasaktiviteettitietoja.</span><span class="sxs-lookup"><span data-stu-id="dc362-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="dc362-225">Lisää asiakasaktiviteettientiteetti ja yhdistä sen kenttien nimet vastaaviin mallin edellyttämiin kenttiin:</span><span class="sxs-lookup"><span data-stu-id="dc362-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="dc362-226">Asiakasaktiviteettientiteetti: Arviot:Verkkosivusto</span><span class="sxs-lookup"><span data-stu-id="dc362-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="dc362-227">Perusavain: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="dc362-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="dc362-228">Aikaleima: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="dc362-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="dc362-229">Tapahtuma (aktiviteetin nimi): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="dc362-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="dc362-230">Tiedot (summa tai arvo): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="dc362-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="dc362-231">Valitse **Seuraava** ja määritä aktiviteetti sekä tapahtumatietojen ja asiakastietojen välinen suhde:</span><span class="sxs-lookup"><span data-stu-id="dc362-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="dc362-232">Aktiviteetin tyyppi: Valitse olemassa oleva</span><span class="sxs-lookup"><span data-stu-id="dc362-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="dc362-233">Aktiviteetin selite: Arvostelu</span><span class="sxs-lookup"><span data-stu-id="dc362-233">Activity label: Review</span></span>
   - <span data-ttu-id="dc362-234">Vastaava otsikko: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="dc362-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="dc362-235">Asiakasentiteetti: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="dc362-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="dc362-236">Suhde: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="dc362-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="dc362-237">Määritä mallin aikataulu valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="dc362-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="dc362-238">Mallin täytyy opetella säännöllisesti oppiakseen uusia kaavoja, kun uusia tietoja on sisäistetty.</span><span class="sxs-lookup"><span data-stu-id="dc362-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="dc362-239">Valitse tässä esimerkissä **Kuukausittain**.</span><span class="sxs-lookup"><span data-stu-id="dc362-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="dc362-240">Kun tiedot on tarkistettu, valitse **Tallenna ja suorita**.</span><span class="sxs-lookup"><span data-stu-id="dc362-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="dc362-241">Tehtävä 4 – mallin tulosten ja selitysten tarkistaminen</span><span class="sxs-lookup"><span data-stu-id="dc362-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="dc362-242">Anna mallin suorittaa tietojen kouluttaminen ja pisteyttäminen.</span><span class="sxs-lookup"><span data-stu-id="dc362-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="dc362-243">Seuraavaksi voit tarkastella CLV-mallin tuloksia ja selityksiä.</span><span class="sxs-lookup"><span data-stu-id="dc362-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="dc362-244">Lisätietoja on kohdassa [Ennusteen tilan ja tulosten tarkasteleminen](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="dc362-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="dc362-245">Tehtävä 5 ‑ Luo segmentti arvokkaista asiakkaista</span><span class="sxs-lookup"><span data-stu-id="dc362-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="dc362-246">Mallin käyttö luo uuden entiteetin, joka näkyy **Tieto** > **Entiteetit** -kohdassa.</span><span class="sxs-lookup"><span data-stu-id="dc362-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="dc362-247">Voit luoda uuden asiakassegmentin mallin luoman entiteetin perusteella.</span><span class="sxs-lookup"><span data-stu-id="dc362-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="dc362-248">Valitse **Segmentit**.</span><span class="sxs-lookup"><span data-stu-id="dc362-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="dc362-249">Valitse ensin **Uusi** ja sitten **Luominen kohteesta** > **Analytiikka**.</span><span class="sxs-lookup"><span data-stu-id="dc362-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Segmentin luominen mallin tulosteen avulla](media/segment-intelligence.png)

1. <span data-ttu-id="dc362-251">Valitse **OOBeCommerceCLVPrediction**-entiteetti ja määritä segmentti:</span><span class="sxs-lookup"><span data-stu-id="dc362-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="dc362-252">Kenttä: CLVScore</span><span class="sxs-lookup"><span data-stu-id="dc362-252">Field: CLVScore</span></span>
  - <span data-ttu-id="dc362-253">Operaattori: suurempi kuin</span><span class="sxs-lookup"><span data-stu-id="dc362-253">Operator: greater than</span></span>
  - <span data-ttu-id="dc362-254">Arvo: 1500</span><span class="sxs-lookup"><span data-stu-id="dc362-254">Value: 1500</span></span>

1. <span data-ttu-id="dc362-255">Valitse **Tarkista** ja **Tallenna** segmentti.</span><span class="sxs-lookup"><span data-stu-id="dc362-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="dc362-256">Sinulla on nyt segmentti, joka tunnistaa asiakkaat, joiden ennustetaan tuottavan yli 1500 $:n tuloja seuraavan 12 kuukauden aikana.</span><span class="sxs-lookup"><span data-stu-id="dc362-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="dc362-257">Tämä segmentti päivittyy dynaamisesti, jos enemmän tietoja on nautittu.</span><span class="sxs-lookup"><span data-stu-id="dc362-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="dc362-258">Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).</span><span class="sxs-lookup"><span data-stu-id="dc362-258">For more information, see [Create and manage segments](segments.md).</span></span>
