---
title: Customer Insights -tietojen vieminen RollWorksiin
description: Tietoja yhteyden määrittämisestä ja viennistä RollWorksiin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124085"
---
# <a name="export-segments-to-rollworks-preview"></a><span data-ttu-id="a1c02-103">Segmenttien vieminen RollWorksiin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="a1c02-103">Export segments to RollWorks (preview)</span></span>

<span data-ttu-id="a1c02-104">Vie yhtenäisten asiakasprofiilien segmentit RollWorksiin ja käytä niitä mainontaan.</span><span class="sxs-lookup"><span data-stu-id="a1c02-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="a1c02-105">Yhteyden edellytykset</span><span class="sxs-lookup"><span data-stu-id="a1c02-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="a1c02-106">Sinulla on [RollWorks-tili](https://www.rollworks.com/) ja sitä vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="a1c02-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a1c02-107">Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a1c02-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a1c02-108">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="a1c02-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a1c02-109">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="a1c02-109">Known limitations</span></span>

- <span data-ttu-id="a1c02-110">Voit viedä RollWorksiin enintään 250 000 profiilia yhdessä viennissä.</span><span class="sxs-lookup"><span data-stu-id="a1c02-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="a1c02-111">Alle 100 profiilin segmenttejä ei voi viedä RollWorksiin.</span><span class="sxs-lookup"><span data-stu-id="a1c02-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="a1c02-112">Vieminen RollWorksiin rajoittuu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="a1c02-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="a1c02-113">250 000 profiilin vienti RollWorksiin saattaa kestää noin 10 minuuttia.</span><span class="sxs-lookup"><span data-stu-id="a1c02-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="a1c02-114">RollWorksiin vietävien profiilien määrä on riippuvainen ja rajoitettu RollWorks-sopimuksen mukaan.</span><span class="sxs-lookup"><span data-stu-id="a1c02-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="a1c02-115">Määritä yhteys RollWorksiin</span><span class="sxs-lookup"><span data-stu-id="a1c02-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="a1c02-116">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="a1c02-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a1c02-117">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **RollWorks**.</span><span class="sxs-lookup"><span data-stu-id="a1c02-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="a1c02-118">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="a1c02-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a1c02-119">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="a1c02-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a1c02-120">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="a1c02-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a1c02-121">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="a1c02-121">Choose who can use this connection.</span></span> <span data-ttu-id="a1c02-122">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="a1c02-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a1c02-123">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a1c02-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a1c02-124">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="a1c02-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a1c02-125">Alusta yhteys RollWorksiin valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="a1c02-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="a1c02-126">Valitse **Todenna RollWorksin avulla** ja anna RollWorksin järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="a1c02-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="a1c02-127">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="a1c02-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a1c02-128">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="a1c02-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a1c02-129">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="a1c02-129">Configure an export</span></span>

<span data-ttu-id="a1c02-130">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="a1c02-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a1c02-131">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a1c02-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a1c02-132">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="a1c02-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a1c02-133">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="a1c02-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a1c02-134">Valitse **Yhteys vientiä varten** -kentässä yhteys RollWorks-osasta.</span><span class="sxs-lookup"><span data-stu-id="a1c02-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="a1c02-135">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="a1c02-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a1c02-136">Anna **RollWorks-mainostajatunnus** [RollWorks-mainostettava](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="a1c02-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="a1c02-137">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="a1c02-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a1c02-138">RollWorksiin pitää viedä segmenttejä.</span><span class="sxs-lookup"><span data-stu-id="a1c02-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="a1c02-139">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="a1c02-139">Select the segments you want to export.</span></span> <span data-ttu-id="a1c02-140">Valitse segmentti, jossa on vähintään 100 jäsentä.</span><span class="sxs-lookup"><span data-stu-id="a1c02-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="a1c02-141">Pienempiä segmenttejä ei voi viedä.</span><span class="sxs-lookup"><span data-stu-id="a1c02-141">You can't export smaller segments.</span></span> <span data-ttu-id="a1c02-142">Lisäksi vietävän segmentin enimmäiskoko on 250 000 jäsentä per vienti.</span><span class="sxs-lookup"><span data-stu-id="a1c02-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="a1c02-143">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="a1c02-143">Select **Save**.</span></span>

<span data-ttu-id="a1c02-144">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="a1c02-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a1c02-145">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="a1c02-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a1c02-146">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a1c02-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a1c02-147">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="a1c02-147">Data privacy and compliance</span></span>

<span data-ttu-id="a1c02-148">Kun otat tietojen siirron käyttöön Dynamics 365 Customer Insightsista RollWorksiin, sallit tietojen siirtämisen Dynamics 365 Customer Insightsin vaatimustenmukaisuuden rajojen ulkopuolelle, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilötiedot.</span><span class="sxs-lookup"><span data-stu-id="a1c02-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a1c02-149">Microsoft siirtää nämä tiedot ohjeesi mukaisesti, mutta olet vastuussa siitä, että RollWorks täyttää mahdolliset tietosuoja- tai tietoturvavelvollisuudet.</span><span class="sxs-lookup"><span data-stu-id="a1c02-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a1c02-150">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a1c02-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a1c02-151">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="a1c02-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
