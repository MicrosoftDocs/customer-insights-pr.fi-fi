---
title: Tapahtuman vaihtuvuusennusteen näyteopas
description: Tämän näyteoppaan avulla voi kokeilla valmista tapahtuman vaihtuvuusennustemallia.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 49dad45c951f3c00d77ddd99faec48bfccada8b0
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306116"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="905dd-103">Tapahtuman vaihtuvuusennusteen (esiversio) näyteopas</span><span class="sxs-lookup"><span data-stu-id="905dd-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="905dd-104">Oppaassa käsitellään kattavasti tapahtuman vaihtuvuusennuste-esimerkki Customer Insightsissa käyttämällä alla olevia tietoja.</span><span class="sxs-lookup"><span data-stu-id="905dd-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="905dd-105">Mitkään tässä oppaassa käytetyt tiedot eivät ole todellisia asiakastietoja. Ne ovat osa Contoson tietojoukkoa, joka löytyy Customer Insights -tilauksen *esittely-ympäristöstä*.</span><span class="sxs-lookup"><span data-stu-id="905dd-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="905dd-106">Skenaario</span><span class="sxs-lookup"><span data-stu-id="905dd-106">Scenario</span></span>

<span data-ttu-id="905dd-107">Contoso on yritys, joka tuottaa laadukkaat kahvi- ja kahvikoneet, joita he myyvät Contoso Coffee -verkkosivustonsa kautta.</span><span class="sxs-lookup"><span data-stu-id="905dd-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="905dd-108">Yrityksen tavoitteena on saada tietää, ketkä asiakkaat tyypillisesti ostavat heidän tuotteitaan säännöllisesti, eivät ole enää asiakkaita seuraavan 60 päivän kuluttua.</span><span class="sxs-lookup"><span data-stu-id="905dd-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="905dd-109">Sen tietäminen, ketkä asiakkaat **todennäköisesti vaihtuvat**, voi auttaa yritystä säästämään markkinointitoimia keskittymällä kyseisten asiakkaiden säilyttämiseen.</span><span class="sxs-lookup"><span data-stu-id="905dd-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="905dd-110">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="905dd-110">Prerequisites</span></span>

- <span data-ttu-id="905dd-111">Vähintään [osallistujan oikeudet](permissions.md) Customer Insightsissa.</span><span class="sxs-lookup"><span data-stu-id="905dd-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="905dd-112">Seuraavat vaiheet on suositeltavaa toteuttaa [uudessa ympäristössä](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="905dd-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="905dd-113">Tehtävä 1 – Tietojen käsitteleminen</span><span class="sxs-lookup"><span data-stu-id="905dd-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="905dd-114">Tutustu etenkin artikkeleihin, joissa on [tietoja tietojen käsittelystä](data-sources.md) ja [tietolähteiden tuomisestä Power Query -yhdistimiä](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="905dd-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="905dd-115">Seuraavissa tiedoissa oletetaan, että tietojen käsittely on yleisesti ottaen tuttua.</span><span class="sxs-lookup"><span data-stu-id="905dd-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="905dd-116">Asiakas tietojen käsitteleminen sähköisen kaupankäynnin ympäristössä</span><span class="sxs-lookup"><span data-stu-id="905dd-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="905dd-117">Luo **eCommerce**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.</span><span class="sxs-lookup"><span data-stu-id="905dd-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="905dd-118">Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="905dd-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="905dd-119">Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.</span><span class="sxs-lookup"><span data-stu-id="905dd-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="905dd-120">Päivitä seuraavien sarakkeiden tietotyyppi:</span><span class="sxs-lookup"><span data-stu-id="905dd-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="905dd-121">**DateOfBirth**: päivämäärä</span><span class="sxs-lookup"><span data-stu-id="905dd-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="905dd-122">**CreatedOn**: päivämäärä, aika ja aikavyöhyke</span><span class="sxs-lookup"><span data-stu-id="905dd-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="905dd-123">![Syntymäpäivän muuttaminen päivämääräksi](media/ecommerce-dob-date.PNG "syntymäpäivän muuntaminen päivämääräksi")</span><span class="sxs-lookup"><span data-stu-id="905dd-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="905dd-124">Anna tietolähteelle uusi nimi määrittämällä oikeanpuoleisen ruudun **Nimi**-kenttään **Query**-arvon sijaan **eCommerceContacts**-arvo</span><span class="sxs-lookup"><span data-stu-id="905dd-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="905dd-125">Tallenna tietolähde.</span><span class="sxs-lookup"><span data-stu-id="905dd-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="905dd-126">Verkko-ostostietojen käsitteleminen</span><span class="sxs-lookup"><span data-stu-id="905dd-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="905dd-127">Lisää toinen tietojoukko samaan **eCommerce**-tietolähteeseen.</span><span class="sxs-lookup"><span data-stu-id="905dd-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="905dd-128">Valitse **Text/CSV**-yhdistin uudelleen.</span><span class="sxs-lookup"><span data-stu-id="905dd-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="905dd-129">Anna **Verkko-ostokset**-tietojen URL-osoite https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="905dd-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="905dd-130">Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.</span><span class="sxs-lookup"><span data-stu-id="905dd-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="905dd-131">Päivitä seuraavien sarakkeiden tietotyyppi:</span><span class="sxs-lookup"><span data-stu-id="905dd-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="905dd-132">**PurchasedOn**: päivämäärä ja aika</span><span class="sxs-lookup"><span data-stu-id="905dd-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="905dd-133">**TotalPrice**: valuutta</span><span class="sxs-lookup"><span data-stu-id="905dd-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="905dd-134">Anna tietolähteelle uusi nimi määrittämällä oikeanpuoleisen ruudun **Nimi**-kenttään **Query**-arvon sijaan **eCommercePurchases**-arvo.</span><span class="sxs-lookup"><span data-stu-id="905dd-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="905dd-135">Tallenna tietolähde.</span><span class="sxs-lookup"><span data-stu-id="905dd-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="905dd-136">Asiakastietojen käyttäminen kanta-asiakasrakenteesta</span><span class="sxs-lookup"><span data-stu-id="905dd-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="905dd-137">Luo **LoyaltyScheme**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.</span><span class="sxs-lookup"><span data-stu-id="905dd-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="905dd-138">Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="905dd-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="905dd-139">Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.</span><span class="sxs-lookup"><span data-stu-id="905dd-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="905dd-140">Päivitä seuraavien sarakkeiden tietotyyppi:</span><span class="sxs-lookup"><span data-stu-id="905dd-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="905dd-141">**DateOfBirth**: päivämäärä</span><span class="sxs-lookup"><span data-stu-id="905dd-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="905dd-142">**RewardsPoints**: kokonaisluku</span><span class="sxs-lookup"><span data-stu-id="905dd-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="905dd-143">**CreatedOn**: päivämäärä, aika</span><span class="sxs-lookup"><span data-stu-id="905dd-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="905dd-144">Vaihda oikeanpuoleisen ruudun **Nimi**-kentässä tietolähteen nimi **Query** nimeksi **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="905dd-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="905dd-145">Tallenna tietolähde.</span><span class="sxs-lookup"><span data-stu-id="905dd-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="905dd-146">Tehtävä 2 – tietojen yhtenäistäminen</span><span class="sxs-lookup"><span data-stu-id="905dd-146">Task 2 - Data unification</span></span>

<span data-ttu-id="905dd-147">Kun tiedot on käsitelty, aloitettavalla **yhdistämismäärityksen, vastaavuuden, yhdistämisen** prosessilla luodaan yhtenäistetty asiakasprofiili.</span><span class="sxs-lookup"><span data-stu-id="905dd-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="905dd-148">Lisätietoja on kohdassa [Tietojen yhtenäistäminen](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="905dd-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="905dd-149">Liitä</span><span class="sxs-lookup"><span data-stu-id="905dd-149">Map</span></span>

1. <span data-ttu-id="905dd-150">Kun tiedot on käsitelty, tee eCommerce- ja Loyalty-tietojen yhdistämismääritys yleisiin tietotyyppeihin.</span><span class="sxs-lookup"><span data-stu-id="905dd-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="905dd-151">Valitse **Tiedot** > **Yhtenäistä** > **Määritä vastaavuus**.</span><span class="sxs-lookup"><span data-stu-id="905dd-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="905dd-152">Valitse asiakasprofiilin ilmaisevat entiteetit: **eCommerceContacts** ja **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="905dd-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="ecommerce- ja loyalty-tietolähteiden yhtenäistäminen":::

1. <span data-ttu-id="905dd-154">Valitse **ContactId** **eCommerceContacts**-perusavaimeksi ja **LoyaltyID** **loyCustomers**-perusavaimeksi.</span><span class="sxs-lookup"><span data-stu-id="905dd-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Yhtenäistäminen LoyaltyId-perusavaimena":::

### <a name="match"></a><span data-ttu-id="905dd-156">Täsmäytä</span><span class="sxs-lookup"><span data-stu-id="905dd-156">Match</span></span>

1. <span data-ttu-id="905dd-157">Valitse **Täsmäytä**-välilehdessä **Määritä järjestys**.</span><span class="sxs-lookup"><span data-stu-id="905dd-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="905dd-158">Valitse avattavasta **Ensisijainen**-luettelosta ensisijaiseksi lähteeksi **eCommerceContacts: eCommerce** ja sisällytä kaikki tietueet.</span><span class="sxs-lookup"><span data-stu-id="905dd-158">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="905dd-159">Valitse avattavasta **Entiteetti 2** -luettelosta **loyCustomers: LoyaltyScheme** ja sisällytä kaikki tietueet.</span><span class="sxs-lookup"><span data-stu-id="905dd-159">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="eCommerce- ja Loyalty-täsmäytyksen yhtenäistäminen":::

1. <span data-ttu-id="905dd-161">Valitse **Luo uusi sääntö**</span><span class="sxs-lookup"><span data-stu-id="905dd-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="905dd-162">Lisää ensimmäinen ehto FullName-kentässä.</span><span class="sxs-lookup"><span data-stu-id="905dd-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="905dd-163">Valitse eCommerceContacts-kohdassa avattavasta valikosta **FullName**.</span><span class="sxs-lookup"><span data-stu-id="905dd-163">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="905dd-164">Valitse loyCustomers-kohdassa avattavasta valikosta **FullName**.</span><span class="sxs-lookup"><span data-stu-id="905dd-164">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="905dd-165">Valitse avattava **Normalisoi**-luettelo ja valitse sitten **Tyyppi (puhelin, nimi, osoite...)**.</span><span class="sxs-lookup"><span data-stu-id="905dd-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="905dd-166">Määritä **Tarkkuustaso**: **Perustaso** ja **Arvo**: **Suuri**.</span><span class="sxs-lookup"><span data-stu-id="905dd-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="905dd-167">Anna uuden säännön **FullName, Email**.</span><span class="sxs-lookup"><span data-stu-id="905dd-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="905dd-168">Lisää sähköpostiosoitteen toinen ehto valitsemalla **Lisää ehto**</span><span class="sxs-lookup"><span data-stu-id="905dd-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="905dd-169">Valitse entity eCommerceContacts-kohdassa avattavasta valikosta **Sähköposti**.</span><span class="sxs-lookup"><span data-stu-id="905dd-169">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="905dd-170">Valitse entity loyCustomers-kohdassa avattavasta valikosta **Sähköposti**.</span><span class="sxs-lookup"><span data-stu-id="905dd-170">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="905dd-171">Jätä Normalisoi-kohta tyhjäksi.</span><span class="sxs-lookup"><span data-stu-id="905dd-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="905dd-172">Määritä **Tarkkuustaso**: **Perustaso** ja **Arvo**: **Suuri**.</span><span class="sxs-lookup"><span data-stu-id="905dd-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Nimen ja sähköpostin vastaavuussäännön yhtenäistäminen":::

7. <span data-ttu-id="905dd-174">Valitse **Tallenna** ja **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="905dd-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="905dd-175">Yhdistä</span><span class="sxs-lookup"><span data-stu-id="905dd-175">Merge</span></span>

1. <span data-ttu-id="905dd-176">Siirry **Yhdistä**-välilehteen.</span><span class="sxs-lookup"><span data-stu-id="905dd-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="905dd-177">Vaihda **loyCustomers**-entiteetin **ContactId**-kohdassa näyttönimeksi **ContactIdLOYALTY** erottamaan se muista käsitellyistä tunnuksista.</span><span class="sxs-lookup"><span data-stu-id="905dd-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="kanta-asiakastunnuksen contactid-nimen vaihtaminen":::

1. <span data-ttu-id="905dd-179">Aloita yhdistämisprosessi valitsemalla **Tallenna** ja **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="905dd-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="905dd-180">Tehtävä 3 – tapahtuman vaihtuvuusennusteen määrittäminen</span><span class="sxs-lookup"><span data-stu-id="905dd-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="905dd-181">Kun asiakasprofiilit on yhtenäistetty, tilauksen vaihtuvuusennusteet voidaan nyt suorittaa.</span><span class="sxs-lookup"><span data-stu-id="905dd-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="905dd-182">Artikkelissa [Tilauksen vaihtuvuusennuste (esiversio)](predict-subscription-churn.md) on tarkat ohjeet.</span><span class="sxs-lookup"><span data-stu-id="905dd-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="905dd-183">Valitse **Analytiikka** > **Tutustu** ja valitse sitten **Asiakasvaihtuvuusmalli**.</span><span class="sxs-lookup"><span data-stu-id="905dd-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="905dd-184">Valitse ensin **Tapahtuma**-vaihtoehto ja sitten **Aloita**.</span><span class="sxs-lookup"><span data-stu-id="905dd-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="905dd-185">Valitse **Sähköisen OOB-kaupankäyntitapahtuman vaihtuvuusennuste** ja tuloste-entiteetti **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="905dd-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="905dd-186">Määritä vaihtuvuusmallille kaksi ehtoa:</span><span class="sxs-lookup"><span data-stu-id="905dd-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="905dd-187">**Ennusteikkuna**: **vähintään 60** päivää.</span><span class="sxs-lookup"><span data-stu-id="905dd-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="905dd-188">Tämä asetus määrittää, miten pitkälle tulevaisuuteen asiakasvaihtuvuus halutaan ennustaa.</span><span class="sxs-lookup"><span data-stu-id="905dd-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="905dd-189">**Vaihtuvuusmääritelmä**: **vähintään 60** päivää.</span><span class="sxs-lookup"><span data-stu-id="905dd-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="905dd-190">Kesto ilman ostoksia, jonka jälkeen asiakas katsotaan vaihtuneeksi.</span><span class="sxs-lookup"><span data-stu-id="905dd-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Mallin ennusteikkunan ja vaihtuvuusmääritelmän valitseminen":::

1. <span data-ttu-id="905dd-192">Valitse **Ostohistoria (pakollinen)** ja valitse ostohistorialle **Lisää tiedot** -arvo.</span><span class="sxs-lookup"><span data-stu-id="905dd-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="905dd-193">Lisää **eCommercePurchases : eCommerce** -entiteetti ja yhdistä eCommercen kentät vastaaviin mallin edellyttämiin kenttiin.</span><span class="sxs-lookup"><span data-stu-id="905dd-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="905dd-194">Liitä **eCommercePurchases : eCommerce** -entiteetti **eCommerceContacts : eCommerce** -entiteettiin.</span><span class="sxs-lookup"><span data-stu-id="905dd-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="eCommerce-entiteetit.":::

1. <span data-ttu-id="905dd-196">Määritä mallin aikataulu valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="905dd-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="905dd-197">Mallia on koulutettava säännöllisesti, jotta se oppii uusia malleja, kun uusia tietoja käsitellään.</span><span class="sxs-lookup"><span data-stu-id="905dd-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="905dd-198">Valitse tässä esimerkissä **Kuukausittain**.</span><span class="sxs-lookup"><span data-stu-id="905dd-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="905dd-199">Kun tiedot on tarkistettu, valitse **Tallenna ja suorita**.</span><span class="sxs-lookup"><span data-stu-id="905dd-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="905dd-200">Tehtävä 4 – mallin tulosten ja selitysten tarkistaminen</span><span class="sxs-lookup"><span data-stu-id="905dd-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="905dd-201">Anna mallin suorittaa tietojen kouluttaminen ja pisteyttäminen.</span><span class="sxs-lookup"><span data-stu-id="905dd-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="905dd-202">Voit nyt tarkastella tilauksen vaihtuvuusmallin selityksiä.</span><span class="sxs-lookup"><span data-stu-id="905dd-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="905dd-203">Lisätietoja on kohdassa [Ennusteen tilan ja tulosten tarkasteleminen](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="905dd-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="905dd-204">Tehtävä 5 – Suuren vaihtuvuusriskin asiakkaiden segmentin luominen</span><span class="sxs-lookup"><span data-stu-id="905dd-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="905dd-205">Tuotantomallin suorittaminen luo uuden entiteetin, jonka saa näkyviin valitsemalla **Tiedot** > **Entiteetit**.</span><span class="sxs-lookup"><span data-stu-id="905dd-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="905dd-206">Voit luoda uuden segmentin mallin luoman entiteetin perusteella.</span><span class="sxs-lookup"><span data-stu-id="905dd-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="905dd-207">Valitse **Segmentit**.</span><span class="sxs-lookup"><span data-stu-id="905dd-207">Go to **Segments**.</span></span> <span data-ttu-id="905dd-208">Valitse ensin **Uusi** ja sitten **Luominen kohteesta** > **Analytiikka**.</span><span class="sxs-lookup"><span data-stu-id="905dd-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Segmentin luominen mallin tulosteen avulla":::

1. <span data-ttu-id="905dd-210">Valitse **OOBSubscriptionChurnPrediction**-päätepiste ja määritä segmentti:</span><span class="sxs-lookup"><span data-stu-id="905dd-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="905dd-211">Kenttä: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="905dd-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="905dd-212">Operaattori: suurempi kuin</span><span class="sxs-lookup"><span data-stu-id="905dd-212">Operator: greater than</span></span>
   - <span data-ttu-id="905dd-213">Arvo: 0,6</span><span class="sxs-lookup"><span data-stu-id="905dd-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Tilauksen vaihtuvuussegmentin määrittäminen":::

<span data-ttu-id="905dd-215">Käytössä on nyt dynaamisesti päivitettävä segmentti, joka määrittää tämän tilausliiketoiminnan suuren vaihtuvuusriskin asiakkaat.</span><span class="sxs-lookup"><span data-stu-id="905dd-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="905dd-216">Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).</span><span class="sxs-lookup"><span data-stu-id="905dd-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]