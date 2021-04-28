---
title: Customer Insightsin tietojen vieminen Mailchimpiin
description: Tietoja yhteyden määrittämisestä ja viennistä Mailchimpiin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b94a8e8b6bb867ca04a64007d592b22fbd700618
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759874"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="e6527-103">Segmenttiluetteloiden vieminen Mailchimpiin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="e6527-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="e6527-104">Uutiskirjeiden ja sähköpostikampanjoiden luonti viemällä yhtenäistettyjä asiakasprofiilisegmenttejä Mailchimpiin.</span><span class="sxs-lookup"><span data-stu-id="e6527-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e6527-105">Yhteyden edellytykset</span><span class="sxs-lookup"><span data-stu-id="e6527-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="e6527-106">[Mailchimp-tili](https://mailchimp.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="e6527-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e6527-107">Mailchimpissa on aiemmin luotuja käyttäjäryhmiä ja vastaavia tunnuksia.</span><span class="sxs-lookup"><span data-stu-id="e6527-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="e6527-108">Lisätietoja on kohdassa [Mailchimp-käyttäjäryhmät](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="e6527-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="e6527-109">[Segmentit on määritetty](segments.md)</span><span class="sxs-lookup"><span data-stu-id="e6527-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="e6527-110">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="e6527-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e6527-111">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="e6527-111">Known limitations</span></span>

- <span data-ttu-id="e6527-112">Enintään 1 miljoona profiilia kussakin Mailchimp-viennissä.</span><span class="sxs-lookup"><span data-stu-id="e6527-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="e6527-113">MailChimp-vienti on rajoitettu segmentteihin</span><span class="sxs-lookup"><span data-stu-id="e6527-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="e6527-114">Miljoonan profiilin viennissä voi kestää kolme tuntia.</span><span class="sxs-lookup"><span data-stu-id="e6527-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="e6527-115">Mailchimpiin vietävien profiilien määrä määräytyy Mailchimp-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.</span><span class="sxs-lookup"><span data-stu-id="e6527-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="e6527-116">Määritä yhteys Mailchimpiin</span><span class="sxs-lookup"><span data-stu-id="e6527-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="e6527-117">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="e6527-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e6527-118">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Autopilot**.</span><span class="sxs-lookup"><span data-stu-id="e6527-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="e6527-119">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="e6527-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e6527-120">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="e6527-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e6527-121">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="e6527-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e6527-122">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="e6527-122">Choose who can use this connection.</span></span> <span data-ttu-id="e6527-123">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="e6527-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e6527-124">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e6527-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e6527-125">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="e6527-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e6527-126">Alusta yhteys Mailchimpiin valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="e6527-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="e6527-127">Valitse **Todenna Mailchimpin avulla** ja anna Mailchimp-tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="e6527-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="e6527-128">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="e6527-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e6527-129">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="e6527-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="e6527-130">Yhdistimen määrittäminen</span><span class="sxs-lookup"><span data-stu-id="e6527-130">Configure the connector</span></span>

<span data-ttu-id="e6527-131">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="e6527-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e6527-132">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e6527-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e6527-133">Siirry kohtaan **Tiedot**> **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="e6527-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="e6527-134">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="e6527-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e6527-135">Valitse **Yhteys vientiä varten** -kentässä yhteys Mailchimp-osasta.</span><span class="sxs-lookup"><span data-stu-id="e6527-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="e6527-136">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="e6527-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e6527-137">Anna **[Mailchimp-käyttäjäryhmän tunnus](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="e6527-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="e6527-138">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="e6527-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="e6527-139">Voit myös viedä **etunimen** ja **sukunimen** yksilöllisempien sähköpostiviestien luomiseksi.</span><span class="sxs-lookup"><span data-stu-id="e6527-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="e6527-140">Yhdistä nämä kenttä valitsemalla **Lisää määrite**.</span><span class="sxs-lookup"><span data-stu-id="e6527-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e6527-141">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="e6527-141">Select the segments you want to export.</span></span> <span data-ttu-id="e6527-142">Voit viedä yhteensä enintään 1 000 000 asiakasprofiilia MailChimpiin.</span><span class="sxs-lookup"><span data-stu-id="e6527-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="e6527-143">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="e6527-143">Select **Save**.</span></span>

<span data-ttu-id="e6527-144">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="e6527-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e6527-145">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="e6527-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e6527-146">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e6527-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e6527-147">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="e6527-147">Data privacy and compliance</span></span>

<span data-ttu-id="e6527-148">Kun tietojen lähetys Mailchimpiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="e6527-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e6527-149">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Mailchimp noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="e6527-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e6527-150">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e6527-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e6527-151">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="e6527-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
