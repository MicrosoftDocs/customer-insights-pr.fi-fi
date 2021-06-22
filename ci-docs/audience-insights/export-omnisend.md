---
title: Customer Insights -tietojen vieminen Omnisendiin
description: Tietoja yhteyden määrittämisestä ja viennistä Omnisendiin.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124481"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="23580-103">Segmenttien vieminen Omnisendiin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="23580-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="23580-104">Vie yhtenäisten asiakasprofiilien segmentit Omnisendiin ja käytä niitä markkinointiaktiviteetteihin.</span><span class="sxs-lookup"><span data-stu-id="23580-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="23580-105">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="23580-105">Prerequisites</span></span>

-   <span data-ttu-id="23580-106">Sinulla on [Omnisend-tili](https://www.omnisend.com/) ja sitä vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="23580-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="23580-107">Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).</span><span class="sxs-lookup"><span data-stu-id="23580-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="23580-108">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="23580-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="23580-109">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="23580-109">Known limitations</span></span>

- <span data-ttu-id="23580-110">Voit viedä kussakin viennissä enintään 1 miljoonaa profiilia Omnisendiin ja se voi kestää jopa 4 tuntia.</span><span class="sxs-lookup"><span data-stu-id="23580-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="23580-111">Vieminen Omnisendiin rajoittuu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="23580-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="23580-112">Profiilien määrä, jonka voi viedä Omnisendiin, määräytyy sen mukaan, millainen sopimus Omnisendin kanssa on solmittu.</span><span class="sxs-lookup"><span data-stu-id="23580-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="23580-113">Määritä yhteys Omnisendiin</span><span class="sxs-lookup"><span data-stu-id="23580-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="23580-114">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="23580-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="23580-115">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Omnisend**.</span><span class="sxs-lookup"><span data-stu-id="23580-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="23580-116">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="23580-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="23580-117">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="23580-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="23580-118">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="23580-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="23580-119">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="23580-119">Choose who can use this connection.</span></span> <span data-ttu-id="23580-120">Oletusarvon mukaan kyse on vain järjestelmänvalvojista.</span><span class="sxs-lookup"><span data-stu-id="23580-120">By default it's only administrators.</span></span> <span data-ttu-id="23580-121">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="23580-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="23580-122">Anna [Omnisendin API-avain](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="23580-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="23580-123">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="23580-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="23580-124">Alusta yhteys Omnisendiin valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="23580-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="23580-125">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="23580-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="23580-126">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="23580-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="23580-127">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="23580-127">Configure an export</span></span>

<span data-ttu-id="23580-128">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="23580-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="23580-129">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="23580-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="23580-130">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="23580-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="23580-131">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="23580-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="23580-132">Valitse **Yhteys vientiä varten** -kentässä yhteys Omnisend-osasta.</span><span class="sxs-lookup"><span data-stu-id="23580-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="23580-133">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="23580-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="23580-134">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="23580-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="23580-135">Omnisendiin pitää viedä segmenttejä.</span><span class="sxs-lookup"><span data-stu-id="23580-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="23580-136">Voit myös viedä etunimen, sukunimen, osoitteen, maan/alueen, osavaltion, kaupungin ja postinumeron yksilöllisempien sähköpostiviestien luomiseksi.</span><span class="sxs-lookup"><span data-stu-id="23580-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="23580-137">Yhdistä nämä kenttä valitsemalla **Lisää määrite**.</span><span class="sxs-lookup"><span data-stu-id="23580-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="23580-138">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="23580-138">Select **Save**.</span></span>

<span data-ttu-id="23580-139">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="23580-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="23580-140">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="23580-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="23580-141">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="23580-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="23580-142">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="23580-142">Data privacy and compliance</span></span>

<span data-ttu-id="23580-143">Kun otat tietojen siirron käyttöön Dynamics 365 Customer Insightsista Ommisendiin, sallit tietojen siirtämisen Dynamics 365 Customer Insightsin vaatimustenmukaisuuden rajojen ulkopuolelle, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilötiedot.</span><span class="sxs-lookup"><span data-stu-id="23580-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="23580-144">Microsoft siirtää nämä tiedot ohjeesi mukaisesti, mutta olet vastuussa siitä, että Ommisend täyttää mahdolliset tietosuoja- tai tietoturvavelvollisuudet.</span><span class="sxs-lookup"><span data-stu-id="23580-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="23580-145">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="23580-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="23580-146">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="23580-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
