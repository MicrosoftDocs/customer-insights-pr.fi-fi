---
title: Customer Insightsin tietojen vieminen Marketoon
description: Tietoja yhteyden määrittämisestä ja viennistä Marketoon.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059312"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="d7f58-103">Segmenttien vieminen Marketoon (esiversio)</span><span class="sxs-lookup"><span data-stu-id="d7f58-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="d7f58-104">Viemällä yhtenäisten asiakasprofiilien segmenttejä voit luoda kampanjoita, tuottaa sähköpostimarkkinointia ja käyttää tiettyjä asiakasryhmiä Marketon avulla.</span><span class="sxs-lookup"><span data-stu-id="d7f58-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="d7f58-105">Yhteyden edellytykset</span><span class="sxs-lookup"><span data-stu-id="d7f58-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="d7f58-106">[Marketo-tili](https://login.marketo.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="d7f58-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d7f58-107">Marketossa on aiemmin luotuja luetteloja ja vastaavia tunnuksia.</span><span class="sxs-lookup"><span data-stu-id="d7f58-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="d7f58-108">Lisätietoja on kohdassa [Marketo-luettelot](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="d7f58-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="d7f58-109">[Segmentit on määritetty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d7f58-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="d7f58-110">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="d7f58-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d7f58-111">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="d7f58-111">Known limitations</span></span>

- <span data-ttu-id="d7f58-112">Enintään 1 miljoona profiilia kussakin Marketo-viennissä.</span><span class="sxs-lookup"><span data-stu-id="d7f58-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="d7f58-113">Marketo-vienti on rajoitettu segmentteihin</span><span class="sxs-lookup"><span data-stu-id="d7f58-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="d7f58-114">Yhteensä 1 miljoonan profiilin segmenttien vienti voi kestää 3 tuntia.</span><span class="sxs-lookup"><span data-stu-id="d7f58-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="d7f58-115">Marketoon vietävien profiilien määrä määräytyy Marketo-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.</span><span class="sxs-lookup"><span data-stu-id="d7f58-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="d7f58-116">Määritä yhteys Marketoon</span><span class="sxs-lookup"><span data-stu-id="d7f58-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="d7f58-117">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="d7f58-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d7f58-118">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Marketo**.</span><span class="sxs-lookup"><span data-stu-id="d7f58-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="d7f58-119">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="d7f58-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d7f58-120">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="d7f58-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d7f58-121">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="d7f58-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d7f58-122">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="d7f58-122">Choose who can use this connection.</span></span> <span data-ttu-id="d7f58-123">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="d7f58-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d7f58-124">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d7f58-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d7f58-125">Anna **[Marketon asiakastunnus, asiakasohjelman salasana ja REST-päätepisteen isäntänimi](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="d7f58-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="d7f58-126">REST-päätepisteen hostname on vain isäntänimi ilman `https://`.</span><span class="sxs-lookup"><span data-stu-id="d7f58-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="d7f58-127">Esimerkki: `xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="d7f58-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="d7f58-128">Vahvista **Tietojen yksityisyys ja vaatimustenmukaisuus** valitsemalla **Hyväksyn** ja käynnistä Marketo-yhteys valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="d7f58-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="d7f58-129">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="d7f58-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d7f58-130">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="d7f58-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d7f58-131">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="d7f58-131">Configure an export</span></span>

<span data-ttu-id="d7f58-132">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="d7f58-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d7f58-133">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d7f58-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d7f58-134">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="d7f58-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d7f58-135">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="d7f58-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d7f58-136">Valitse **Yhteys vientiä varten** -kentässä yhteys Marketo-osasta.</span><span class="sxs-lookup"><span data-stu-id="d7f58-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="d7f58-137">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="d7f58-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d7f58-138">Syötä **[Marketo-luettelon tunnus](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span><span class="sxs-lookup"><span data-stu-id="d7f58-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="d7f58-139">Luettelon tunnus on pelkästään numeerinen arvo.</span><span class="sxs-lookup"><span data-stu-id="d7f58-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="d7f58-140">Jos esimerkiksi Marketo-luettelon tunnus on ST12345A7, poista merkki numeroiden edestä ja jäljestä ja kirjoita `12345`.</span><span class="sxs-lookup"><span data-stu-id="d7f58-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="d7f58-141">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="d7f58-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="d7f58-142">Voit myös viedä **etunimen**, **sukunimen**, **paikkakunnan**, **osavaltion** ja **maan/alueen** yksilöllisempien sähköpostiviestien luomiseksi.</span><span class="sxs-lookup"><span data-stu-id="d7f58-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="d7f58-143">Yhdistä nämä kenttä valitsemalla **Lisää määrite**.</span><span class="sxs-lookup"><span data-stu-id="d7f58-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="d7f58-144">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="d7f58-144">Select the segments you want to export.</span></span> <span data-ttu-id="d7f58-145">Voit viedä yhteensä enintään 1 000 000 asiakasprofiilia Marketoon.</span><span class="sxs-lookup"><span data-stu-id="d7f58-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="d7f58-146">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="d7f58-146">Select **Save**.</span></span>

<span data-ttu-id="d7f58-147">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="d7f58-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d7f58-148">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="d7f58-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d7f58-149">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d7f58-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="d7f58-150">Marketon segmentit ovat nyt [Marketo-luetteloissa](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="d7f58-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d7f58-151">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="d7f58-151">Data privacy and compliance</span></span>

<span data-ttu-id="d7f58-152">Kun tietojen lähetys Marketoon otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="d7f58-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d7f58-153">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Marketo noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="d7f58-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d7f58-154">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d7f58-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d7f58-155">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="d7f58-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
