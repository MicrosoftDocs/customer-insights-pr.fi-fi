---
title: Käyttöoikeuksien hallinta
description: Tietoja käyttöoikeuksista ja käyttäjärooleista.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e58bb1a3bd4c0920ff984daffabbf16162185f3d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595698"
---
# <a name="user-permissions"></a><span data-ttu-id="2005c-103">Käyttäjien käyttöoikeudet</span><span class="sxs-lookup"><span data-stu-id="2005c-103">User permissions</span></span>

<span data-ttu-id="2005c-104">**Käyttöoikeudet**-sivulla määritetään käyttäjäryhmän merkityksellisten tietojen rooli ja käyttöoikeudet.</span><span class="sxs-lookup"><span data-stu-id="2005c-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="2005c-105">Sivun näyttämiseen tarvitaan järjestelmänvalvojan käyttöoikeudet.</span><span class="sxs-lookup"><span data-stu-id="2005c-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="2005c-106">Voit siirtyä käyttäjäryhmän merkityksellisten tietojen käyttöoikeussivulle valitsemalla **Hallinta** > **Käyttöoikeudet**.</span><span class="sxs-lookup"><span data-stu-id="2005c-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="2005c-107">Roolityyppejä on kolme:</span><span class="sxs-lookup"><span data-stu-id="2005c-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="2005c-108">Katselija</span><span class="sxs-lookup"><span data-stu-id="2005c-108">Viewer</span></span>

- <span data-ttu-id="2005c-109">**Aloitus**- ja **Segmentit**-sivuilla voi tutustua merkityksellisiin tietoihin ja segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="2005c-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="2005c-110">Hae ja suodata asiakasprofiileja **Asiakkaat**-sivun avulla.</span><span class="sxs-lookup"><span data-stu-id="2005c-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="2005c-111">Kentistä on voitava tehdä hakuja.</span><span class="sxs-lookup"><span data-stu-id="2005c-111">Fields must be searchable.</span></span>
- <span data-ttu-id="2005c-112">Tutustu **Rikastaminen**-sivuun.</span><span class="sxs-lookup"><span data-stu-id="2005c-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="2005c-113">Tuutustu entiteetteihin ja vie niitä **Entiteetit**-sivun avulla.</span><span class="sxs-lookup"><span data-stu-id="2005c-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="2005c-114">Näytä järjestelmän käsittelyn tila **Järjestelmä**-sivun avulla.</span><span class="sxs-lookup"><span data-stu-id="2005c-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="2005c-115">Vie segmenttejä **Segmentit**-sivulta.</span><span class="sxs-lookup"><span data-stu-id="2005c-115">Export segments from the **Segments** page.</span></span>
- <span data-ttu-id="2005c-116">Asenna **Power BI Customer Insights** -koontinäyttö ja käytä sitä.</span><span class="sxs-lookup"><span data-stu-id="2005c-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="2005c-117">Osallistuja</span><span class="sxs-lookup"><span data-stu-id="2005c-117">Contributor</span></span>

- <span data-ttu-id="2005c-118">Kaikki katselijan oikeudet.</span><span class="sxs-lookup"><span data-stu-id="2005c-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="2005c-119">Lataa ja muunna tietoja **Tietolähteet**-sivun avulla.</span><span class="sxs-lookup"><span data-stu-id="2005c-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="2005c-120">Täydennä *Tietojen yhdistäminen*-osat (**Vastaavuus**, **Täsmäyttäminen** ja **Yhdistäminen**). joiden tuloksena saadaan yhdistetty asiakasprofiilientiteetti.</span><span class="sxs-lookup"><span data-stu-id="2005c-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="2005c-121">Määritä **suhteet** ja **aktiviteetit**.</span><span class="sxs-lookup"><span data-stu-id="2005c-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="2005c-122">Luo segmenttejä **Segmentit**-sivun avulla.</span><span class="sxs-lookup"><span data-stu-id="2005c-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="2005c-123">Luo mittareita **Mittarit**-sivun avulla.</span><span class="sxs-lookup"><span data-stu-id="2005c-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="2005c-124">Hallitse määrityksiä ja täydennä asiakasprofiilit **Täydennä**-sivulla (vain ensimmäisen osapuolen täydennykset).</span><span class="sxs-lookup"><span data-stu-id="2005c-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>

## <a name="administrator"></a><span data-ttu-id="2005c-125">Järjestelmänvalvoja</span><span class="sxs-lookup"><span data-stu-id="2005c-125">Administrator</span></span>

- <span data-ttu-id="2005c-126">Kaikki osallistujan oikeudet.</span><span class="sxs-lookup"><span data-stu-id="2005c-126">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="2005c-127">Muuta asetuksia **Järjestelmä**-sivulla, myös työskentelykieli, ja päivitä järjestelmäprosessien aikataulut.</span><span class="sxs-lookup"><span data-stu-id="2005c-127">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="2005c-128">Tarkastele ja lisää oikeuksia **Käyttöoikeudet**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="2005c-128">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="2005c-129">Määritä Asiakkaat-sivun haku- ja suodatusmääritelmät **Hae ja suodata indeksi** -sivulla (käytettävissä **Asiakkaat**-sivulla).</span><span class="sxs-lookup"><span data-stu-id="2005c-129">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="2005c-130">Määritä Dynamics 365 Sales -segmentin kohteet käyttämällä **Vientikohteet**-sivua.</span><span class="sxs-lookup"><span data-stu-id="2005c-130">Define Dynamics 365 Sales segment destinations using the **Export destinations** page.</span></span>
- <span data-ttu-id="2005c-131">Hallitse määrityksiä ja täydennä asiakasprofiilit **Täydennä**-sivulla (kaikki täydennykset).</span><span class="sxs-lookup"><span data-stu-id="2005c-131">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="2005c-132">Asenna **asiakaskortin apuohjelma** ja käytä sitä.</span><span class="sxs-lookup"><span data-stu-id="2005c-132">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="2005c-133">Lisää **Power Apps -yhdistin** ja käytä sitä.</span><span class="sxs-lookup"><span data-stu-id="2005c-133">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="2005c-134">Ota [Customer Insights -ohjelmointirajapinnat](apis.md) käyttöön.</span><span class="sxs-lookup"><span data-stu-id="2005c-134">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="2005c-135">Delegoi roolit ja oikeudet</span><span class="sxs-lookup"><span data-stu-id="2005c-135">Assign roles and permissions</span></span>

1. <span data-ttu-id="2005c-136">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Käyttöoikeudet**</span><span class="sxs-lookup"><span data-stu-id="2005c-136">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="2005c-137">Avaa **Lisää tai muokkaa oikeuksia** -ruutu valitsemalla **Lisää käyttäjiä**.</span><span class="sxs-lookup"><span data-stu-id="2005c-137">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="2005c-138">Etsi **Hae**-kentän avulla Azure Active Directoryn käyttäjä tai ryhmä, jonka käyttöoikeuksia haluat muokata.</span><span class="sxs-lookup"><span data-stu-id="2005c-138">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="2005c-139">Valitse **Rooli**, joka liitetään käyttäjälle tai ryhmälle.</span><span class="sxs-lookup"><span data-stu-id="2005c-139">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="2005c-140">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="2005c-140">Select **Save**.</span></span> <span data-ttu-id="2005c-141">Nykyinen ympäristö jaetaan automaattisen sen käyttäjän tai niiden ryhmän jäsenten kanssa, joiden käyttöoikeuksia on muutettu.</span><span class="sxs-lookup"><span data-stu-id="2005c-141">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="2005c-142">Käyttäjät voivat käyttää Customer Insights -sovellusta ja käyttää sitä määritetyn roolinsa mukaisesti.</span><span class="sxs-lookup"><span data-stu-id="2005c-142">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="2005c-143">Tarkastele nykyisiä oikeuksia</span><span class="sxs-lookup"><span data-stu-id="2005c-143">View current permissions</span></span>

<span data-ttu-id="2005c-144">Valitsemalla käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Käyttöoikeudet** näet, mitkä roolimääritykset ovat aktiivisia.</span><span class="sxs-lookup"><span data-stu-id="2005c-144">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="2005c-145">**Tyyppi**-sarake määrittää yhden käyttäjän, ryhmän tai sovelluksen.</span><span class="sxs-lookup"><span data-stu-id="2005c-145">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="2005c-146">Järjestelmä tukee yksittäisiä käyttäjiä ja ryhmiä.</span><span class="sxs-lookup"><span data-stu-id="2005c-146">The system supports individual users and groups.</span></span>
- <span data-ttu-id="2005c-147">Roolit määritetään **Rooli**-sarakkeessa.</span><span class="sxs-lookup"><span data-stu-id="2005c-147">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="2005c-148">Valitse sarakkeen otsikko, jos haluat lajitella tulokset kyseisen sarakkeen arvon mukaan.</span><span class="sxs-lookup"><span data-stu-id="2005c-148">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="2005c-149">Etsi tietyt käyttäjät sivun yläosassa olevan **Hae**-kentän avulla.</span><span class="sxs-lookup"><span data-stu-id="2005c-149">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]