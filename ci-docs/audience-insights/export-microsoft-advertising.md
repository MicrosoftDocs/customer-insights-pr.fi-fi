---
title: Customer Insights -tietojen vieminen Microsoft Advertisingiin
description: Tietoja yhteyden määrittämisestä ja viennistä Microsoft Advertisingiin.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124480"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="81ff7-103">Segmenttien vieminen Microsoft Advertisingiin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="81ff7-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="81ff7-104">Vie Customer Insights -segmentit Microsoft Advertisingiin, jotta voit luoda asiakkaiden vastineen kohdeyleisöille.</span><span class="sxs-lookup"><span data-stu-id="81ff7-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="81ff7-105">Käytä näitä kohderyhmiä mainoskampanjoissasi.</span><span class="sxs-lookup"><span data-stu-id="81ff7-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="81ff7-106">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="81ff7-106">Prerequisites</span></span>

-   <span data-ttu-id="81ff7-107">[Microsoft Advertising -tili](https://ads.microsoft.com/) ja sitä vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="81ff7-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="81ff7-108">Olet hyväksynyt asiakkaan vastineen käyttöehdot.</span><span class="sxs-lookup"><span data-stu-id="81ff7-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="81ff7-109">[Määritetyt segmentit](segments.md) käyttäjäryhmän merkityksellisissä tiedoissa.</span><span class="sxs-lookup"><span data-stu-id="81ff7-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="81ff7-110">Viedyissä segmenteissä yhdenmukaistetut asiakasprofiilit sisältävät kentän, jolla on sähköpostiosoite.</span><span class="sxs-lookup"><span data-stu-id="81ff7-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="81ff7-111">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="81ff7-111">Known limitations</span></span>

- <span data-ttu-id="81ff7-112">Voit viedä Microsoft Advertisingiin enintään 500 000 profiilia yhdessä viennissä.</span><span class="sxs-lookup"><span data-stu-id="81ff7-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="81ff7-113">Vieminen Microsoft Advertisingiin rajoittuu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="81ff7-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="81ff7-114">500 000:n profiilin vienti Microsoft Advertisingiin saattaa kestää noin 10 minuuttia.</span><span class="sxs-lookup"><span data-stu-id="81ff7-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="81ff7-115">Määritä yhteys Microsoft Advertisingiin</span><span class="sxs-lookup"><span data-stu-id="81ff7-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="81ff7-116">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="81ff7-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="81ff7-117">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Microsoft Advertising**.</span><span class="sxs-lookup"><span data-stu-id="81ff7-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="81ff7-118">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="81ff7-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="81ff7-119">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="81ff7-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="81ff7-120">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="81ff7-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="81ff7-121">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="81ff7-121">Choose who can use this connection.</span></span> <span data-ttu-id="81ff7-122">Oletusarvo on järjestelmänvalvoja.</span><span class="sxs-lookup"><span data-stu-id="81ff7-122">The default is administrators.</span></span> <span data-ttu-id="81ff7-123">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="81ff7-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="81ff7-124">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="81ff7-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="81ff7-125">Alusta yhteys Microsoft Advertisingiin valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="81ff7-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="81ff7-126">Valitse **Todenna Microsoft Advertisingin avulla** ja anna Microsoft Advertisingin järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="81ff7-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="81ff7-127">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="81ff7-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="81ff7-128">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="81ff7-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="81ff7-129">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="81ff7-129">Configure an export</span></span>

<span data-ttu-id="81ff7-130">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="81ff7-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="81ff7-131">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="81ff7-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="81ff7-132">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="81ff7-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="81ff7-133">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="81ff7-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="81ff7-134">Valitse **Yhteys vientiä varten** -kentässä yhteys Microsoft Advertising -osasta.</span><span class="sxs-lookup"><span data-stu-id="81ff7-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="81ff7-135">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="81ff7-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="81ff7-136">Valitse vietävät segmentit.</span><span class="sxs-lookup"><span data-stu-id="81ff7-136">Select the segments to export.</span></span> <span data-ttu-id="81ff7-137">Microsoft Advertisingin customer match -kohdeyleisöt luodaan automaattisesti viennissä valittujen segmenttien nimellä.</span><span class="sxs-lookup"><span data-stu-id="81ff7-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="81ff7-138">Kustakin segmentistä tulee erillinen Customer Match -yleisö.</span><span class="sxs-lookup"><span data-stu-id="81ff7-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="81ff7-139">Anna **Microsoft Advertisingin asiakastunnuksesi ja tilitunnuksesi**.</span><span class="sxs-lookup"><span data-stu-id="81ff7-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="81ff7-140">URL-osoitteen parametreista löydät asiakastunnuksen (`cid`) ja tilitunnuksen (`aid`), kun kirjaudut Microsoft Advertisingiin.</span><span class="sxs-lookup"><span data-stu-id="81ff7-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="81ff7-141">Valitse **Tietojen täsmäytys** -osassa **Sähköposti**-kentässä yhdistetyn asiakasprofiilisi kenttä, jossa on asiakkaan sähköpostiosoite.</span><span class="sxs-lookup"><span data-stu-id="81ff7-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="81ff7-142">Microsoft Advertisingiin pitää viedä segmenttejä.</span><span class="sxs-lookup"><span data-stu-id="81ff7-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="81ff7-143">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="81ff7-143">Select **Save**.</span></span>

<span data-ttu-id="81ff7-144">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="81ff7-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="81ff7-145">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="81ff7-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="81ff7-146">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="81ff7-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="81ff7-147">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="81ff7-147">Data privacy and compliance</span></span>

<span data-ttu-id="81ff7-148">Kun otat tietojen siirron käyttöön Dynamics 365 Customer Insightsista Microsoft Advertisingiin, sallit tietojen siirtämisen Dynamics 365 Customer Insightsin vaatimustenmukaisuuden rajojen ulkopuolelle, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilötiedot.</span><span class="sxs-lookup"><span data-stu-id="81ff7-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="81ff7-149">Microsoft siirtää nämä tiedot ohjeesi mukaisesti, mutta olet vastuussa siitä, että Microsoft Advertising täyttää mahdolliset tietosuoja- tai tietoturvavelvollisuudet.</span><span class="sxs-lookup"><span data-stu-id="81ff7-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="81ff7-150">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="81ff7-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="81ff7-151">Dynamics 365 Customer Insights -järjestelmänvalvojasi voi poistaa tämän vientikohteen milloin tahansa, jos haluat lopettaa tämän toiminnon käytön.</span><span class="sxs-lookup"><span data-stu-id="81ff7-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
