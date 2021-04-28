---
title: Käyttöoikeuksien hallinta
description: Tietoja käyttöoikeuksista ja käyttäjärooleista.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760369"
---
# <a name="user-permissions"></a><span data-ttu-id="469b2-103">Käyttäjien käyttöoikeudet</span><span class="sxs-lookup"><span data-stu-id="469b2-103">User permissions</span></span>

<span data-ttu-id="469b2-104">**Käyttöoikeudet**-sivulla määritetään käyttäjäryhmän merkityksellisten tietojen rooli ja käyttöoikeudet.</span><span class="sxs-lookup"><span data-stu-id="469b2-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="469b2-105">Sivun näyttämiseen tarvitaan järjestelmänvalvojan käyttöoikeudet.</span><span class="sxs-lookup"><span data-stu-id="469b2-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="469b2-106">Voit siirtyä käyttäjäryhmän merkityksellisten tietojen käyttöoikeussivulle valitsemalla **Hallinta** > **Käyttöoikeudet**.</span><span class="sxs-lookup"><span data-stu-id="469b2-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="469b2-107">Roolityyppejä on kolme:</span><span class="sxs-lookup"><span data-stu-id="469b2-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="469b2-108">Katselija</span><span class="sxs-lookup"><span data-stu-id="469b2-108">Viewer</span></span>

- <span data-ttu-id="469b2-109">**Aloitus**- ja **Segmentit**-sivuilla voi tutustua merkityksellisiin tietoihin ja segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="469b2-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="469b2-110">Hae ja suodata asiakasprofiileja **Asiakkaat**-sivun avulla.</span><span class="sxs-lookup"><span data-stu-id="469b2-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="469b2-111">Kentistä on voitava tehdä hakuja.</span><span class="sxs-lookup"><span data-stu-id="469b2-111">Fields must be searchable.</span></span>
- <span data-ttu-id="469b2-112">Tutustu **Rikastaminen**-sivuun.</span><span class="sxs-lookup"><span data-stu-id="469b2-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="469b2-113">Tuutustu entiteetteihin ja vie niitä **Entiteetit**-sivun avulla.</span><span class="sxs-lookup"><span data-stu-id="469b2-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="469b2-114">Näytä järjestelmän käsittelyn tila **Järjestelmä**-sivun avulla.</span><span class="sxs-lookup"><span data-stu-id="469b2-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="469b2-115">Vientien tarkasteleminen **Viennit**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="469b2-115">View exports in **Exports** page.</span></span>
- <span data-ttu-id="469b2-116">Asenna **Power BI Customer Insights** -koontinäyttö ja käytä sitä.</span><span class="sxs-lookup"><span data-stu-id="469b2-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="469b2-117">Osallistuja</span><span class="sxs-lookup"><span data-stu-id="469b2-117">Contributor</span></span>

- <span data-ttu-id="469b2-118">Kaikki katselijan oikeudet.</span><span class="sxs-lookup"><span data-stu-id="469b2-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="469b2-119">Lataa ja muunna tietoja **Tietolähteet**-sivun avulla.</span><span class="sxs-lookup"><span data-stu-id="469b2-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="469b2-120">Täydennä *Tietojen yhdistäminen*-osat (**Vastaavuus**, **Täsmäyttäminen** ja **Yhdistäminen**). joiden tuloksena saadaan yhdistetty asiakasprofiilientiteetti.</span><span class="sxs-lookup"><span data-stu-id="469b2-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="469b2-121">Määritä **suhteet** ja **aktiviteetit**.</span><span class="sxs-lookup"><span data-stu-id="469b2-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="469b2-122">Luo segmenttejä **Segmentit**-sivun avulla.</span><span class="sxs-lookup"><span data-stu-id="469b2-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="469b2-123">Luo mittareita **Mittarit**-sivun avulla.</span><span class="sxs-lookup"><span data-stu-id="469b2-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="469b2-124">Hallitse määrityksiä ja täydennä asiakasprofiilit **Täydennä**-sivulla (vain ensimmäisen osapuolen täydennykset).</span><span class="sxs-lookup"><span data-stu-id="469b2-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>
- <span data-ttu-id="469b2-125">Hallitse ja luo vientejä osallistujien kanssa jaettujen yhteyksien perusteella.</span><span class="sxs-lookup"><span data-stu-id="469b2-125">Manage and create exports based on connections shared with contributors.</span></span> <span data-ttu-id="469b2-126">[Lisätietoja siitä, miten järjestelmänvalvojat voivat sallia osallistujien käyttää yhteyttä vienneissä.](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="469b2-126">[Learn more about how administrators allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

## <a name="administrator"></a><span data-ttu-id="469b2-127">Järjestelmänvalvoja</span><span class="sxs-lookup"><span data-stu-id="469b2-127">Administrator</span></span>

- <span data-ttu-id="469b2-128">Kaikki osallistujan oikeudet.</span><span class="sxs-lookup"><span data-stu-id="469b2-128">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="469b2-129">Muuta asetuksia **Järjestelmä**-sivulla, myös työskentelykieli, ja päivitä järjestelmäprosessien aikataulut.</span><span class="sxs-lookup"><span data-stu-id="469b2-129">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="469b2-130">Tarkastele ja lisää oikeuksia **Käyttöoikeudet**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="469b2-130">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="469b2-131">Määritä Asiakkaat-sivun haku- ja suodatusmääritelmät **Hae ja suodata indeksi** -sivulla (käytettävissä **Asiakkaat**-sivulla).</span><span class="sxs-lookup"><span data-stu-id="469b2-131">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="469b2-132">Voit hallita yhteyksiä ja sallia niitä muille käyttäjärooleille **Yhteydet**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="469b2-132">Manage connections and allow them for other user roles on **Connections** page.</span></span>
- <span data-ttu-id="469b2-133">Hallitse määrityksiä ja täydennä asiakasprofiilit **Täydennä**-sivulla (kaikki täydennykset).</span><span class="sxs-lookup"><span data-stu-id="469b2-133">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="469b2-134">Hallitse ja luo vientejä **Viennit**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="469b2-134">Manage and create exports on **Exports** page.</span></span>
- <span data-ttu-id="469b2-135">Asenna **asiakaskortin apuohjelma** ja käytä sitä.</span><span class="sxs-lookup"><span data-stu-id="469b2-135">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="469b2-136">Lisää **Power Apps -yhdistin** ja käytä sitä.</span><span class="sxs-lookup"><span data-stu-id="469b2-136">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="469b2-137">Ota [Customer Insights -ohjelmointirajapinnat](apis.md) käyttöön.</span><span class="sxs-lookup"><span data-stu-id="469b2-137">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="469b2-138">Delegoi roolit ja oikeudet</span><span class="sxs-lookup"><span data-stu-id="469b2-138">Assign roles and permissions</span></span>

1. <span data-ttu-id="469b2-139">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Käyttöoikeudet**</span><span class="sxs-lookup"><span data-stu-id="469b2-139">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="469b2-140">Avaa **Lisää tai muokkaa oikeuksia** -ruutu valitsemalla **Lisää käyttäjiä**.</span><span class="sxs-lookup"><span data-stu-id="469b2-140">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="469b2-141">Etsi **Hae**-kentän avulla Azure Active Directoryn käyttäjä tai ryhmä, jonka käyttöoikeuksia haluat muokata.</span><span class="sxs-lookup"><span data-stu-id="469b2-141">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="469b2-142">Valitse **Rooli**, joka liitetään käyttäjälle tai ryhmälle.</span><span class="sxs-lookup"><span data-stu-id="469b2-142">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="469b2-143">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="469b2-143">Select **Save**.</span></span> <span data-ttu-id="469b2-144">Nykyinen ympäristö jaetaan automaattisen sen käyttäjän tai niiden ryhmän jäsenten kanssa, joiden käyttöoikeuksia on muutettu.</span><span class="sxs-lookup"><span data-stu-id="469b2-144">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="469b2-145">Käyttäjät voivat käyttää Customer Insights -sovellusta ja käyttää sitä määritetyn roolinsa mukaisesti.</span><span class="sxs-lookup"><span data-stu-id="469b2-145">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="469b2-146">Tarkastele nykyisiä oikeuksia</span><span class="sxs-lookup"><span data-stu-id="469b2-146">View current permissions</span></span>

<span data-ttu-id="469b2-147">Valitsemalla käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Käyttöoikeudet** näet, mitkä roolimääritykset ovat aktiivisia.</span><span class="sxs-lookup"><span data-stu-id="469b2-147">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="469b2-148">**Tyyppi**-sarake määrittää yhden käyttäjän, ryhmän tai sovelluksen.</span><span class="sxs-lookup"><span data-stu-id="469b2-148">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="469b2-149">Järjestelmä tukee yksittäisiä käyttäjiä ja ryhmiä.</span><span class="sxs-lookup"><span data-stu-id="469b2-149">The system supports individual users and groups.</span></span>
- <span data-ttu-id="469b2-150">Roolit määritetään **Rooli**-sarakkeessa.</span><span class="sxs-lookup"><span data-stu-id="469b2-150">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="469b2-151">Valitse sarakkeen otsikko, jos haluat lajitella tulokset kyseisen sarakkeen arvon mukaan.</span><span class="sxs-lookup"><span data-stu-id="469b2-151">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="469b2-152">Etsi tietyt käyttäjät sivun yläosassa olevan **Hae**-kentän avulla.</span><span class="sxs-lookup"><span data-stu-id="469b2-152">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
