---
title: Customer Insightsin tietojen vieminen Marketoon
description: Tietoja yhteyden määrittämisestä ja viennistä Marketoon.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759817"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="a6187-103">Segmenttien vieminen Marketoon (esiversio)</span><span class="sxs-lookup"><span data-stu-id="a6187-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="a6187-104">Viemällä yhtenäisten asiakasprofiilien segmenttejä voit luoda kampanjoita, tuottaa sähköpostimarkkinointia ja käyttää tiettyjä asiakasryhmiä Marketon avulla.</span><span class="sxs-lookup"><span data-stu-id="a6187-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="a6187-105">Yhteyden edellytykset</span><span class="sxs-lookup"><span data-stu-id="a6187-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="a6187-106">[Marketo-tili](https://login.marketo.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="a6187-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a6187-107">Marketossa on aiemmin luotuja luetteloja ja vastaavia tunnuksia.</span><span class="sxs-lookup"><span data-stu-id="a6187-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="a6187-108">Lisätietoja on kohdassa [Marketo-luettelot](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="a6187-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="a6187-109">[Segmentit on määritetty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a6187-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="a6187-110">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="a6187-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a6187-111">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="a6187-111">Known limitations</span></span>

- <span data-ttu-id="a6187-112">Enintään 1 miljoona profiilia kussakin Marketo-viennissä.</span><span class="sxs-lookup"><span data-stu-id="a6187-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="a6187-113">Marketo-vienti on rajoitettu segmentteihin</span><span class="sxs-lookup"><span data-stu-id="a6187-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="a6187-114">Yhteensä 1 miljoonan profiilin segmenttien vienti voi kestää 3 tuntia.</span><span class="sxs-lookup"><span data-stu-id="a6187-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="a6187-115">Marketoon vietävien profiilien määrä määräytyy Marketo-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.</span><span class="sxs-lookup"><span data-stu-id="a6187-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="a6187-116">Määritä yhteys Marketoon</span><span class="sxs-lookup"><span data-stu-id="a6187-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="a6187-117">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="a6187-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a6187-118">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Marketo**.</span><span class="sxs-lookup"><span data-stu-id="a6187-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="a6187-119">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="a6187-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a6187-120">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="a6187-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a6187-121">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="a6187-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a6187-122">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="a6187-122">Choose who can use this connection.</span></span> <span data-ttu-id="a6187-123">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="a6187-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a6187-124">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a6187-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a6187-125">Anna **[Marketon asiakastunnus, asiakasohjelman salasana ja REST-päätepisteen isäntänimi](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="a6187-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="a6187-126">Vahvista **Tietojen yksityisyys ja vaatimustenmukaisuus** valitsemalla **Hyväksyn** ja käynnistä Marketo-yhteys valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="a6187-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="a6187-127">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="a6187-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a6187-128">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="a6187-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a6187-129">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="a6187-129">Configure an export</span></span>

<span data-ttu-id="a6187-130">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="a6187-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a6187-131">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a6187-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a6187-132">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="a6187-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a6187-133">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="a6187-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a6187-134">Valitse **Yhteys vientiä varten** -kentässä yhteys Marketo-osasta.</span><span class="sxs-lookup"><span data-stu-id="a6187-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="a6187-135">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="a6187-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a6187-136">Anna **[Marketo-luettelon tunnus](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="a6187-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="a6187-137">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="a6187-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="a6187-138">Voit myös viedä **etunimen**, **sukunimen**, **paikkakunnan**, **osavaltion** ja **maan/alueen** yksilöllisempien sähköpostiviestien luomiseksi.</span><span class="sxs-lookup"><span data-stu-id="a6187-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="a6187-139">Yhdistä nämä kenttä valitsemalla **Lisää määrite**.</span><span class="sxs-lookup"><span data-stu-id="a6187-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="a6187-140">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="a6187-140">Select the segments you want to export.</span></span> <span data-ttu-id="a6187-141">Voit viedä yhteensä enintään 1 000 000 asiakasprofiilia Marketoon.</span><span class="sxs-lookup"><span data-stu-id="a6187-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="a6187-142">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="a6187-142">Select **Save**.</span></span>

<span data-ttu-id="a6187-143">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="a6187-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a6187-144">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="a6187-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a6187-145">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a6187-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="a6187-146">Marketon segmentit ovat nyt [Marketo-luetteloissa](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="a6187-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a6187-147">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="a6187-147">Data privacy and compliance</span></span>

<span data-ttu-id="a6187-148">Kun tietojen lähetys Marketoon otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="a6187-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a6187-149">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Marketo noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="a6187-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a6187-150">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a6187-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a6187-151">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="a6187-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]