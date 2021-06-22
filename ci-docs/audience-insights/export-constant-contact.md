---
title: Customer Insights -tietojen vieminen Constant Contactiin
description: Tietoja yhteyden määrittämisestä ja viennistä Constant Contactiin.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124269"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="8ac60-103">Segmenttien vieminen Constant Contactiin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="8ac60-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="8ac60-104">Vie yhtenäisten asiakasprofiilien segmentit Constant Contactiin ja käytä niitä markkinointiaktiviteetteihin.</span><span class="sxs-lookup"><span data-stu-id="8ac60-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="8ac60-105">Yhteyden edellytykset</span><span class="sxs-lookup"><span data-stu-id="8ac60-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="8ac60-106">Sinulla on [Constant Contact -tili](https://www.constantcontact.com/account-home) ja sitä vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="8ac60-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8ac60-107">Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).</span><span class="sxs-lookup"><span data-stu-id="8ac60-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="8ac60-108">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="8ac60-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8ac60-109">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="8ac60-109">Known limitations</span></span>

- <span data-ttu-id="8ac60-110">Voit viedä Constant Contactiin enintään miljoona profiilia yhdessä viennissä.</span><span class="sxs-lookup"><span data-stu-id="8ac60-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="8ac60-111">Vieminen Constant Contactiin rajoittuu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="8ac60-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="8ac60-112">Miljoonan profiilin vienti Constant Contactiin saattaa kestää noin 1 tunnin.</span><span class="sxs-lookup"><span data-stu-id="8ac60-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="8ac60-113">Constant Contactiin vietävien profiilien määrä on riippuvainen ja rajoitettu Constant Contact -sopimuksen mukaan.</span><span class="sxs-lookup"><span data-stu-id="8ac60-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="8ac60-114">Constant Contact -yhteyden määrittäminen</span><span class="sxs-lookup"><span data-stu-id="8ac60-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="8ac60-115">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="8ac60-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8ac60-116">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Constant Contact**.</span><span class="sxs-lookup"><span data-stu-id="8ac60-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="8ac60-117">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="8ac60-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8ac60-118">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="8ac60-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8ac60-119">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="8ac60-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8ac60-120">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="8ac60-120">Choose who can use this connection.</span></span> <span data-ttu-id="8ac60-121">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="8ac60-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8ac60-122">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8ac60-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8ac60-123">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="8ac60-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8ac60-124">Alusta yhteys Constant Contactiin valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="8ac60-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="8ac60-125">Valitse **Todenna AdRollin avulla** ja anna Constant Contactin järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="8ac60-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="8ac60-126">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="8ac60-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8ac60-127">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="8ac60-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="8ac60-128">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="8ac60-128">Configure an export</span></span>

<span data-ttu-id="8ac60-129">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="8ac60-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8ac60-130">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8ac60-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8ac60-131">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="8ac60-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8ac60-132">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="8ac60-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8ac60-133">Valitse **Yhteys vientiä varten** -kentässä yhteys Constant Contact -osasta.</span><span class="sxs-lookup"><span data-stu-id="8ac60-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="8ac60-134">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="8ac60-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8ac60-135">Anna [**Constant Contact -luettelon tunnus**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="8ac60-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="8ac60-136">Avaa luettelo Constant Contactissa, jotta löydät luettelon tunnuksen URL-osoitteesta.</span><span class="sxs-lookup"><span data-stu-id="8ac60-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="8ac60-137">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="8ac60-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8ac60-138">Constant Contactiin pitää viedä segmenttejä.</span><span class="sxs-lookup"><span data-stu-id="8ac60-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="8ac60-139">Vaihtoehtoisesti voit viedä Etunimi- ja Sukunimi-kentät lisäkenttinä, joiden avulla sähköposteja voidaan mukauttaa.</span><span class="sxs-lookup"><span data-stu-id="8ac60-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="8ac60-140">Yhdistä nämä kenttä valitsemalla **Lisää määrite**.</span><span class="sxs-lookup"><span data-stu-id="8ac60-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="8ac60-141">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="8ac60-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="8ac60-142">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="8ac60-142">Select **Save**.</span></span>

<span data-ttu-id="8ac60-143">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="8ac60-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8ac60-144">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="8ac60-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8ac60-145">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8ac60-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8ac60-146">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="8ac60-146">Data privacy and compliance</span></span>

<span data-ttu-id="8ac60-147">Kun otat tietojen siirron käyttöön Dynamics 365 Customer Insightsista Constant Contactiin, sallit tietojen siirtämisen Dynamics 365 Customer Insightsin vaatimustenmukaisuuden rajojen ulkopuolelle, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilötiedot.</span><span class="sxs-lookup"><span data-stu-id="8ac60-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8ac60-148">Microsoft siirtää nämä tiedot ohjeesi mukaisesti, mutta olet vastuussa siitä, että Constant Contact täyttää mahdolliset tietosuoja- tai tietoturvavelvollisuudet.</span><span class="sxs-lookup"><span data-stu-id="8ac60-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8ac60-149">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8ac60-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="8ac60-150">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="8ac60-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
