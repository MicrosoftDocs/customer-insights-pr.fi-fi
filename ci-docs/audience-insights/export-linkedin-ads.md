---
title: Customer Insights -tietojen vieminen LinkedIn Adsiin
description: Tietoja yhteyden määrittämisestä ja viennistä LinkedIniin.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124482"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="6c913-103">Segmenttien vieminen LinkedIniin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="6c913-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="6c913-104">Vie yhdistettyjen asiakasprofiilien segmentit LinkedIn Adsiin ja luo vastaavat kohdeyleisöt.</span><span class="sxs-lookup"><span data-stu-id="6c913-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="6c913-105">Käytä kohdistettuja kohdeyleisöjä yrityksen ja yhteyshenkilöiden kohdistamiseen.</span><span class="sxs-lookup"><span data-stu-id="6c913-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6c913-106">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="6c913-106">Prerequisites</span></span>

-   <span data-ttu-id="6c913-107">Sinulla on [LinkedIn Campaign Manager -tili](https://business.linkedin.com/marketing-solutions/ads) ja sitä vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="6c913-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6c913-108">Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).</span><span class="sxs-lookup"><span data-stu-id="6c913-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="6c913-109">Viedyissä segmenteissä asiakasprofiilit sisältävät kentän, jolla on sähköpostiosoite.</span><span class="sxs-lookup"><span data-stu-id="6c913-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6c913-110">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="6c913-110">Known limitations</span></span>

- <span data-ttu-id="6c913-111">Voit viedä LinkedIn Adsiin enintään 100 000 profiilia yhdessä viennissä.</span><span class="sxs-lookup"><span data-stu-id="6c913-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="6c913-112">Vieminen LinkedIn Adsiin rajoittuu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="6c913-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="6c913-113">100 000 profiilin vienti LinkedIn Adsiin saattaa kestää noin 10 minuuttia.</span><span class="sxs-lookup"><span data-stu-id="6c913-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="6c913-114">Määritä yhteys LinkedIn Adsiin</span><span class="sxs-lookup"><span data-stu-id="6c913-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="6c913-115">Siirry kohdeyleisön merkityksellisissä tiedoissa kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="6c913-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6c913-116">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **LinkedIn Ads**.</span><span class="sxs-lookup"><span data-stu-id="6c913-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="6c913-117">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="6c913-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6c913-118">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="6c913-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6c913-119">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="6c913-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6c913-120">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="6c913-120">Choose who can use this connection.</span></span> <span data-ttu-id="6c913-121">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="6c913-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="6c913-122">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6c913-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6c913-123">Anna [LinkedIn Campaign Manager -tilitunnus](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="6c913-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="6c913-124">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="6c913-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6c913-125">Alusta yhteys Campaign Monitoriin valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="6c913-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="6c913-126">Valitse **Todenna LinkedIn Adsin avulla** ja anna LinkedIn Campaign Manager -järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="6c913-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="6c913-127">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="6c913-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6c913-128">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="6c913-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="6c913-129">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="6c913-129">Configure an export</span></span>

<span data-ttu-id="6c913-130">Voit määrittää viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="6c913-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="6c913-131">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6c913-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6c913-132">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="6c913-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6c913-133">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="6c913-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6c913-134">Valitse **Yhteys vientiä varten** -kentässä yhteys LinkedIn Ads -osasta.</span><span class="sxs-lookup"><span data-stu-id="6c913-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="6c913-135">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="6c913-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6c913-136">Valitse, haluatko viedä tiedot LinkedInissä [yhteyshenkilöiden kohdistamista](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) varten vai [yrityksen kohdistamista](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) varten.</span><span class="sxs-lookup"><span data-stu-id="6c913-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="6c913-137">Valitse **Tietojen täsmäytys** -osassa yhdistetyn asiakasprofiilisi kenttä, joka edustaa asiakkaan sähköpostiosoitetta.</span><span class="sxs-lookup"><span data-stu-id="6c913-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="6c913-138">LinkedIn Adsiin pitää viedä segmenttejä.</span><span class="sxs-lookup"><span data-stu-id="6c913-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="6c913-139">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="6c913-139">Select the segments you want to export.</span></span> <span data-ttu-id="6c913-140">Kohdeyleisöt LinkedIn Campaign Managerissa luodaan automaattisesti valittujen vietävien segmenttien nimellä.</span><span class="sxs-lookup"><span data-stu-id="6c913-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="6c913-141">Kustakin segmentistä tulee erillinen kohdeyleisö.</span><span class="sxs-lookup"><span data-stu-id="6c913-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="6c913-142">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="6c913-142">Select **Save**.</span></span>

<span data-ttu-id="6c913-143">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="6c913-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6c913-144">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="6c913-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6c913-145">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6c913-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6c913-146">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="6c913-146">Data privacy and compliance</span></span>

<span data-ttu-id="6c913-147">Kun otat tietojen siirron käyttöön Dynamics 365 Customer Insightsista LinkedIn Adsiin, sallit tietojen siirtämisen Dynamics 365 Customer Insightsin vaatimustenmukaisuuden rajojen ulkopuolelle, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilötiedot.</span><span class="sxs-lookup"><span data-stu-id="6c913-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6c913-148">Microsoft siirtää nämä tiedot ohjeesi mukaisesti, mutta olet vastuussa siitä, että LinkedIn Ads täyttää mahdolliset tietosuoja- tai tietoturvavelvollisuudet.</span><span class="sxs-lookup"><span data-stu-id="6c913-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="6c913-149">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6c913-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="6c913-150">Dynamics 365 Customer Insights -järjestelmänvalvojasi voi poistaa tämän vientikohteen milloin tahansa, jos haluat lopettaa tämän toiminnon käytön.</span><span class="sxs-lookup"><span data-stu-id="6c913-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
