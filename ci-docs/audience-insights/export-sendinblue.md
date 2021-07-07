---
title: Asiakkaan merkityksellisten tietojen vieminen Sendinblue-ratkaisuun
description: Lisätietoja yhteyden ja viennin määrittämisestä Sendinblue-ratkaisuun.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314604"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="667ff-103">Segmenttien vieminen Sendinblue-ratkaisuun (esiversio)</span><span class="sxs-lookup"><span data-stu-id="667ff-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="667ff-104">Vie yhdistettyjen asiakasprofiilien segmenttejä luodaksesi kampanjoita, tarjotaksesi sähköpostimarkkinointia ja käyttääksesi tiettyjä asiakasryhmiä Sendinblue-ratkaisun kanssa.</span><span class="sxs-lookup"><span data-stu-id="667ff-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="667ff-105">Yhteyden edellytykset</span><span class="sxs-lookup"><span data-stu-id="667ff-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="667ff-106">Sinulla on [Sendinblue-tili](https://www.sendinblue.com/) ja vastaavat järjestelmänvalvojan valtuustiedot.</span><span class="sxs-lookup"><span data-stu-id="667ff-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="667ff-107">Sendinblue-ratkaisussa on olemassa olevat luettelot ja vastaavat tunnukset.</span><span class="sxs-lookup"><span data-stu-id="667ff-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="667ff-108">[Segmentit on määritetty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="667ff-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="667ff-109">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="667ff-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="667ff-110">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="667ff-110">Known limitations</span></span>

- <span data-ttu-id="667ff-111">Sendinblue-ratkaisu tukee enintään miljoonaa profiilia vientiä kohti.</span><span class="sxs-lookup"><span data-stu-id="667ff-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="667ff-112">Vieminen Sendinblue-ratkaisuun on rajoitettu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="667ff-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="667ff-113">Yhteensä miljoona profiilia sisältävien segmenttien vieminen voi kestää 90 minuuttia.</span><span class="sxs-lookup"><span data-stu-id="667ff-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="667ff-114">Sendinblue-ratkaisuun vietävien profiilien enimmäismäärä riippuu Sendinblue-ratkaisuun liittyvästä sopimuksesta.</span><span class="sxs-lookup"><span data-stu-id="667ff-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="667ff-115">Yhteyden määrittäminen Sendinblue-ratkaisuun</span><span class="sxs-lookup"><span data-stu-id="667ff-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="667ff-116">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="667ff-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="667ff-117">Määritä yhteys valitsemalla **Lisää yhteys**. Valitse lopuksi **Sendinblue**.</span><span class="sxs-lookup"><span data-stu-id="667ff-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="667ff-118">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="667ff-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="667ff-119">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="667ff-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="667ff-120">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="667ff-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="667ff-121">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="667ff-121">Choose who can use this connection.</span></span> <span data-ttu-id="667ff-122">Oletusarvoisesti vain järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="667ff-122">By default it's only administrators.</span></span> <span data-ttu-id="667ff-123">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="667ff-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="667ff-124">Syötä **[SendinBlue-ohjelmointirajapinnan avain](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="667ff-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="667ff-125">Valitse **Hyväksyn**, jos haluat vahvistaa **Tietojen yksityisyys ja vaatimustenmukaisuus** -kohdan. Valitse **Muodosta yhteys**, jolloin yhteys Sendinblue-ratkaisuun muodostetaan.</span><span class="sxs-lookup"><span data-stu-id="667ff-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="667ff-126">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="667ff-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="667ff-127">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="667ff-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="667ff-128">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="667ff-128">Configure an export</span></span>

<span data-ttu-id="667ff-129">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="667ff-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="667ff-130">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="667ff-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="667ff-131">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="667ff-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="667ff-132">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="667ff-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="667ff-133">Valitse **Yhteys vientiä varten** -kentässä yhteys Sendinblue-osasta.</span><span class="sxs-lookup"><span data-stu-id="667ff-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="667ff-134">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="667ff-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="667ff-135">Syötä **Sendinblue-luettelon tunnus**</span><span class="sxs-lookup"><span data-stu-id="667ff-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="667ff-136">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="667ff-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="667ff-137">Vaihtoehtoisesti voit viedä **etunimen**, **sukunimen** tai **puhelinnumeron** mukaan. Näin voit luoda mukautettuja sähköpostiviestejä.</span><span class="sxs-lookup"><span data-stu-id="667ff-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="667ff-138">Yhdistä nämä kenttä valitsemalla **Lisää määrite**.</span><span class="sxs-lookup"><span data-stu-id="667ff-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="667ff-139">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="667ff-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="667ff-140">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="667ff-140">Select **Save**.</span></span>

<span data-ttu-id="667ff-141">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="667ff-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="667ff-142">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="667ff-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="667ff-143">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="667ff-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="667ff-144">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="667ff-144">Data privacy and compliance</span></span>

<span data-ttu-id="667ff-145">Kun otat käyttöön Dynamics 365 Customer Insightsin tietojen siirtämiseksi Sendinblue-ratkaisuun, sallit tietojen siirtämisen säännöstenmukaisuuden rajan ulkopuolelle Dynamics 365 Customer Insightsissa, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilökohtaiset tiedot.</span><span class="sxs-lookup"><span data-stu-id="667ff-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="667ff-146">Microsoft siirtää nämä tiedot pyyntösi mukaisesti, mutta olet vastuussa siitä, että Sendinblue täyttää kaikki liiketoimintaasi koskevat tietosuoja- tai tietoturvavelvoitteet.</span><span class="sxs-lookup"><span data-stu-id="667ff-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="667ff-147">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="667ff-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="667ff-148">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="667ff-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
