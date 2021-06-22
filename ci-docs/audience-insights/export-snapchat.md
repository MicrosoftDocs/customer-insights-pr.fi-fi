---
title: Customer Insights -tietojen vieminen Snapchatiin
description: Tietoja yhteyden määrittämisestä ja viennistä Snapchatiin.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6565ab81599abcc0f94465e1153f08e0bc119839
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124039"
---
# <a name="export-segments-to-snapchat-preview"></a><span data-ttu-id="d5a6b-103">Segmenttien vieminen Snapchatiin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="d5a6b-103">Export segments to Snapchat (preview)</span></span>

<span data-ttu-id="d5a6b-104">Vie yhtenäisten asiakasprofiilien segmentit Snapchatiin ja käytä niitä mainontaan.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="d5a6b-105">Yhteyden edellytykset</span><span class="sxs-lookup"><span data-stu-id="d5a6b-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="d5a6b-106">Sinulla on [Snapchat-yritystili](https://business.snapchat.com/), [Snapchat-mainostili](https://ads.snapchat.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d5a6b-107">Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d5a6b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d5a6b-108">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d5a6b-109">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="d5a6b-109">Known limitations</span></span>

- <span data-ttu-id="d5a6b-110">Vieminen Snapchatiin rajoittuu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="d5a6b-111">Miljoonan profiilin vienti Snapchatiin saattaa kestää noin 15 minuuttia.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="d5a6b-112">Määritä yhteys Snapchatiin</span><span class="sxs-lookup"><span data-stu-id="d5a6b-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="d5a6b-113">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d5a6b-114">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Snapchat**.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="d5a6b-115">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d5a6b-116">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d5a6b-117">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d5a6b-118">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-118">Choose who can use this connection.</span></span> <span data-ttu-id="d5a6b-119">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d5a6b-120">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d5a6b-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d5a6b-121">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="d5a6b-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d5a6b-122">Alusta yhteys Snapchatiin valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="d5a6b-123">Valitse **Todenna Snapchatin avulla** ja anna Snapchatin järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="d5a6b-124">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d5a6b-125">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d5a6b-126">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="d5a6b-126">Configure an export</span></span>

<span data-ttu-id="d5a6b-127">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d5a6b-128">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d5a6b-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d5a6b-129">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d5a6b-130">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d5a6b-131">Valitse **Yhteys vientiä varten** -kentässä yhteys Snapchat-osasta.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="d5a6b-132">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d5a6b-133">Anna [**Snapchat-kohdeyleisön tunnus**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="d5a6b-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="d5a6b-134">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d5a6b-135">Snapchatiin pitää viedä segmenttejä.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="d5a6b-136">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="d5a6b-137">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-137">Select **Save**.</span></span>

<span data-ttu-id="d5a6b-138">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d5a6b-139">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d5a6b-140">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d5a6b-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d5a6b-141">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="d5a6b-141">Data privacy and compliance</span></span>

<span data-ttu-id="d5a6b-142">Kun otat tietojen siirron käyttöön Dynamics 365 Customer Insightsista Snapchatiin, sallit tietojen siirtämisen Dynamics 365 Customer Insightsin vaatimustenmukaisuuden rajojen ulkopuolelle, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilötiedot.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d5a6b-143">Microsoft siirtää nämä tiedot ohjeesi mukaisesti, mutta olet vastuussa siitä, että Snapchat täyttää mahdolliset tietosuoja- tai tietoturvavelvollisuudet.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d5a6b-144">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d5a6b-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d5a6b-145">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="d5a6b-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
