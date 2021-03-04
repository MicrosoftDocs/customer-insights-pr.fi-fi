---
title: Customer Insightsin tietojen vieminen Facebookin mainosten hallintaan
description: Opettele määrittämään yhteys Facebook Ads Manageriin.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269970"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="e8a33-103">Yhdistä Facebook Ads Manageriin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="e8a33-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="e8a33-104">Voit luoda kampanjoita Facebookissa ja Instagramissaa viemällä yhdistettyjen asiakasprofiilien segmenttejä Facebook Ads Manageriin.</span><span class="sxs-lookup"><span data-stu-id="e8a33-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e8a33-105">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="e8a33-105">Prerequisites</span></span>

- <span data-ttu-id="e8a33-106">Tarvitset [**Facebook Ad -tilin**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), joka sisältää [**Facebook -yritystilin**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="e8a33-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="e8a33-107">Sinun on oltava [**Facebook Ad -tilin**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) järjestelmänvalvoja.</span><span class="sxs-lookup"><span data-stu-id="e8a33-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="e8a33-108">Yhteyden muodostaminen Facebook Ads Manageriin</span><span class="sxs-lookup"><span data-stu-id="e8a33-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="e8a33-109">Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="e8a33-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e8a33-110">Valitse **Facebook Ads Manager** -kohdassa **määritä**.</span><span class="sxs-lookup"><span data-stu-id="e8a33-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="e8a33-111">Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="e8a33-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e8a33-112">Valitse **Continue with Facebook** kirjautuaksesi Facebook Ad -tiliisi.</span><span class="sxs-lookup"><span data-stu-id="e8a33-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="e8a33-113">Salli **ads_management**-oikeus Facebook-todennuksen jälkeen.</span><span class="sxs-lookup"><span data-stu-id="e8a33-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="e8a33-114">Valitse **Facebook Ad -tili**, jota haluat käyttää.</span><span class="sxs-lookup"><span data-stu-id="e8a33-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="e8a33-115">Valitse yleisö avattavasta **Existing custom audience** -valikosta tai luo uusi **New custom audience** -kohdassa.</span><span class="sxs-lookup"><span data-stu-id="e8a33-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="e8a33-116">Lisätietoja on kohdassa [**Kohdeyleisöt Facebook Ads Managerissa**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="e8a33-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="e8a33-117">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="e8a33-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e8a33-118">Määritä vienti valitsemalla **Next**.</span><span class="sxs-lookup"><span data-stu-id="e8a33-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="e8a33-119">Yhdistimen määrittäminen</span><span class="sxs-lookup"><span data-stu-id="e8a33-119">Configure the connector</span></span>

1. <span data-ttu-id="e8a33-120">Valitse **Choose your key identifier** -kentässä **Email**, **Name and address** tai **Phone**, jonka avulla lähetetään Facebook Ads Manageriin.</span><span class="sxs-lookup"><span data-stu-id="e8a33-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="e8a33-121">Yhdistä yhdistetyn asiakasentiteetin vastaavat määritteet valittua avaintunnistetta varten.</span><span class="sxs-lookup"><span data-stu-id="e8a33-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="e8a33-122">[VIHJE] Paras vaihtoehtosi on se, että valitaan **Email** tunnukseksi.</span><span class="sxs-lookup"><span data-stu-id="e8a33-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="e8a33-123">Lisätunnusten lisääminen voi parantaa vastaavuutta.</span><span class="sxs-lookup"><span data-stu-id="e8a33-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="e8a33-124">Valitsemalla **Add attribute** voit yhdistää Facebook Ads Manageriin lähetettävät lisämääritteet.</span><span class="sxs-lookup"><span data-stu-id="e8a33-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="e8a33-125">Facebook Ads Managerin määritteet yhdistetään seuraaviin kenttien lyhyisiin nimiin: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span><span class="sxs-lookup"><span data-stu-id="e8a33-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="e8a33-126">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="e8a33-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="e8a33-127">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="e8a33-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e8a33-128">Tietojen vieminen</span><span class="sxs-lookup"><span data-stu-id="e8a33-128">Export the data</span></span>

<span data-ttu-id="e8a33-129">Voit [viedä tietoja tarvittaessa](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e8a33-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e8a33-130">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="e8a33-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e8a33-131">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="e8a33-131">Known limitations</span></span>

- <span data-ttu-id="e8a33-132">Enintään 10 miljoonaa asiakasprofiilia Facebookin mainosten hallintaan</span><span class="sxs-lookup"><span data-stu-id="e8a33-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="e8a33-133">Vienti Facebookin mainosten hallintaan on rajoitettu segmentteihin</span><span class="sxs-lookup"><span data-stu-id="e8a33-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="e8a33-134">Yhteensä 10 miljoonan profiilin segmenttien vienti voi kestää 90 minuuttia</span><span class="sxs-lookup"><span data-stu-id="e8a33-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e8a33-135">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="e8a33-135">Data privacy and compliance</span></span>

<span data-ttu-id="e8a33-136">Kun tietojen lähetys Facebookin mainosten hallintaan otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="e8a33-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e8a33-137">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Facebook Ads noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="e8a33-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="e8a33-138">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e8a33-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e8a33-139">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="e8a33-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]