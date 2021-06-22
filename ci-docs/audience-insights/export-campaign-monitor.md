---
title: Customer Insights -tietojen vieminen Campaign Monitoriin
description: Tietoja yhteyden määrittämisestä ja viennistä Campaign Monitoriin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124177"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="94ed0-103">Segmenttien vieminen Campaign Monitoriin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="94ed0-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="94ed0-104">Vie yhtenäisten asiakasprofiilien segmentit Campaign Monitoriin ja käytä niitä markkinointiaktiviteetteihin.</span><span class="sxs-lookup"><span data-stu-id="94ed0-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="94ed0-105">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="94ed0-105">Prerequisites</span></span>

-   <span data-ttu-id="94ed0-106">Sinulla on [Campaign Monitor -tili](https://www.campaignmonitor.com/) ja sitä vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="94ed0-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="94ed0-107">Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).</span><span class="sxs-lookup"><span data-stu-id="94ed0-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="94ed0-108">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="94ed0-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="94ed0-109">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="94ed0-109">Known limitations</span></span>

- <span data-ttu-id="94ed0-110">Voit viedä Campaign Monitoriin enintään miljoona profiilia yhdessä viennissä.</span><span class="sxs-lookup"><span data-stu-id="94ed0-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="94ed0-111">Vieminen Campaign Monitoriin rajoittuu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="94ed0-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="94ed0-112">Miljoonan profiilin vienti Campaign Monitoriin saattaa kestää noin 20 minuuttia.</span><span class="sxs-lookup"><span data-stu-id="94ed0-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="94ed0-113">Campaign Monitoriin vietävien profiilien määrä on riippuvainen ja rajoitettu Campaign Monitor -sopimuksen mukaan.</span><span class="sxs-lookup"><span data-stu-id="94ed0-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="94ed0-114">Määritä yhteys Campaign Monitoriin</span><span class="sxs-lookup"><span data-stu-id="94ed0-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="94ed0-115">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="94ed0-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="94ed0-116">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Campaign Monitor**.</span><span class="sxs-lookup"><span data-stu-id="94ed0-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="94ed0-117">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="94ed0-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="94ed0-118">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="94ed0-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="94ed0-119">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="94ed0-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="94ed0-120">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="94ed0-120">Choose who can use this connection.</span></span> <span data-ttu-id="94ed0-121">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="94ed0-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="94ed0-122">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="94ed0-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="94ed0-123">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="94ed0-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="94ed0-124">Alusta yhteys Campaign Monitoriin valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="94ed0-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="94ed0-125">Valitse **Todenna Campaign Monitorin avulla** ja anna Campaign Monitorin järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="94ed0-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="94ed0-126">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="94ed0-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="94ed0-127">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="94ed0-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="94ed0-128">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="94ed0-128">Configure an export</span></span>

<span data-ttu-id="94ed0-129">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="94ed0-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="94ed0-130">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="94ed0-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="94ed0-131">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="94ed0-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="94ed0-132">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="94ed0-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="94ed0-133">Valitse **Yhteys vientiä varten** -kentässä yhteys Campaign Monitor -osasta.</span><span class="sxs-lookup"><span data-stu-id="94ed0-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="94ed0-134">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="94ed0-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="94ed0-135">Anna [**Campaign Monitor -luettelon tunnus**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="94ed0-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="94ed0-136">[Luo API-avain](https://www.campaignmonitor.com/api/getting-started/) Campaign Monitorin **tiliasetuksista**, jotta näet ohjelmointirajapinnan luettelotunnuksen.</span><span class="sxs-lookup"><span data-stu-id="94ed0-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="94ed0-137">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="94ed0-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="94ed0-138">Campaign Monitoriin pitää viedä segmenttejä.</span><span class="sxs-lookup"><span data-stu-id="94ed0-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="94ed0-139">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="94ed0-139">Select **Save**.</span></span>

<span data-ttu-id="94ed0-140">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="94ed0-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="94ed0-141">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="94ed0-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="94ed0-142">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="94ed0-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="94ed0-143">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="94ed0-143">Data privacy and compliance</span></span>

<span data-ttu-id="94ed0-144">Kun otat tietojen siirron käyttöön Dynamics 365 Customer Insightsista Campaign Monitoriin, sallit tietojen siirtämisen Dynamics 365 Customer Insightsin vaatimustenmukaisuuden rajojen ulkopuolelle, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilötiedot.</span><span class="sxs-lookup"><span data-stu-id="94ed0-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="94ed0-145">Microsoft siirtää nämä tiedot ohjeesi mukaisesti, mutta olet vastuussa siitä, että Campaign Monitor täyttää mahdolliset tietosuoja- tai tietoturvavelvollisuudet.</span><span class="sxs-lookup"><span data-stu-id="94ed0-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="94ed0-146">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="94ed0-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="94ed0-147">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="94ed0-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
