---
title: Asiakkaan merkityksellisten tietojen vieminen ActiveCampaign-ratkaisuun
description: Lisätietoja yhteyden ja viemisen määrittämisestä ActiveCampaign-ratkaisuun
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314605"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="c3c26-103">Segmenttien vieminen ActiveCampaign-ratkaisuun (esiversio)</span><span class="sxs-lookup"><span data-stu-id="c3c26-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="c3c26-104">Vie yhdistettyjen asiakasprofiilien segmentit ActiveCampaign-ratkaisuun ja käytä niitä markkinointiaktiviteeteissa.</span><span class="sxs-lookup"><span data-stu-id="c3c26-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c3c26-105">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="c3c26-105">Prerequisites</span></span>

-   <span data-ttu-id="c3c26-106">Sinulla on [ActiveCampaign-tili](https://www.activecampaign.com/) ja vastaavat järjestelmänvalvojan valtuustiedot.</span><span class="sxs-lookup"><span data-stu-id="c3c26-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c3c26-107">Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c3c26-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c3c26-108">Viedyissä segmenteissä yhdenmukaistetut asiakasprofiilit sisältävät kentän, jolla on sähköpostiosoite.</span><span class="sxs-lookup"><span data-stu-id="c3c26-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c3c26-109">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="c3c26-109">Known limitations</span></span>

- <span data-ttu-id="c3c26-110">Yhdessä viennissä ActiveCampaign-ratkaisuun voi olla enintään miljoona profiilia. Vienti voi kestää 90 minuuttia.</span><span class="sxs-lookup"><span data-stu-id="c3c26-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="c3c26-111">Vieminen ActiveCampaign-ratkaisuun on rajoitettu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="c3c26-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="c3c26-112">ActiveCampaign-ratkaisuun vietävien profiilien enimmäismäärä riippuu ActiveCampaign-sopimuksesta.</span><span class="sxs-lookup"><span data-stu-id="c3c26-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="c3c26-113">Yhteyden määrittäminen ActiveCampaign-ratkaisuun</span><span class="sxs-lookup"><span data-stu-id="c3c26-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="c3c26-114">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="c3c26-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c3c26-115">Määritä yhteys valitsemalla **Lisää yhteys**. Valitse lopuksi **ActiveCampaign**.</span><span class="sxs-lookup"><span data-stu-id="c3c26-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="c3c26-116">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="c3c26-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c3c26-117">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="c3c26-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c3c26-118">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="c3c26-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c3c26-119">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="c3c26-119">Choose who can use this connection.</span></span> <span data-ttu-id="c3c26-120">Oletusarvoisesti vain järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="c3c26-120">By default, it's only administrators.</span></span> <span data-ttu-id="c3c26-121">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c3c26-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c3c26-122">Syötä [ActiveCampaign-ohjelmointirajapinnan avain ja REST-päätepisteen isäntänimi](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="c3c26-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="c3c26-123">REST-päätepisteen hostname on vain isäntänimi ilman https://.</span><span class="sxs-lookup"><span data-stu-id="c3c26-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="c3c26-124">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="c3c26-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c3c26-125">Valitse **Muodosta yhteys** ja muodosta yhteys ActiveCampaign-ratkaisuun.</span><span class="sxs-lookup"><span data-stu-id="c3c26-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="c3c26-126">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="c3c26-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c3c26-127">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="c3c26-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="c3c26-128">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="c3c26-128">Configure an export</span></span>

<span data-ttu-id="c3c26-129">Voit määrittää viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="c3c26-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="c3c26-130">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c3c26-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c3c26-131">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="c3c26-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c3c26-132">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="c3c26-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c3c26-133">Valitse **Yhteys vientiä varten** -kentässä yhteys ActiveCampaign-osasta.</span><span class="sxs-lookup"><span data-stu-id="c3c26-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="c3c26-134">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="c3c26-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c3c26-135">Syötä [**ActiveCampaign-luettelon tunnus**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="c3c26-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="c3c26-136">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="c3c26-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c3c26-137">Segmenttien vieminen ActiveCampaign-ratkaisuun on pakollista.</span><span class="sxs-lookup"><span data-stu-id="c3c26-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="c3c26-138">Vaihtoehtoisesti voit viedä etunimen, sukunimen tai puhelinnumeron mukaan. Näin voit luoda mukautettuja sähköpostiviestejä.</span><span class="sxs-lookup"><span data-stu-id="c3c26-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="c3c26-139">Yhdistä nämä kenttä valitsemalla Lisää määrite.</span><span class="sxs-lookup"><span data-stu-id="c3c26-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="c3c26-140">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="c3c26-140">Select **Save**.</span></span>

<span data-ttu-id="c3c26-141">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="c3c26-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c3c26-142">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="c3c26-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c3c26-143">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c3c26-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c3c26-144">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="c3c26-144">Data privacy and compliance</span></span>

<span data-ttu-id="c3c26-145">Kun otat käyttöön Dynamics 365 Customer Insightsin tietojen siirtämiseksi ActiveCampaign-ratkaisuun, sallit tietojen siirtämisen säännöstenmukaisuuden rajan ulkopuolelle Dynamics 365 Customer Insightsissa, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilökohtaiset tiedot.</span><span class="sxs-lookup"><span data-stu-id="c3c26-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c3c26-146">Microsoft siirtää nämä tiedot pyyntösi mukaisesti, mutta olet vastuussa siitä, että ActiveCampaign täyttää kaikki liiketoimintaasi koskevat tietosuoja- tai tietoturvavelvoitteet.</span><span class="sxs-lookup"><span data-stu-id="c3c26-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c3c26-147">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c3c26-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="c3c26-148">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="c3c26-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
