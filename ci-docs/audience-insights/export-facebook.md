---
title: Customer Insightsin tietojen vieminen Facebookin mainosten hallintaan
description: Opettele määrittämään yhteys Facebook Ads Manageriin.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643679"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="ffbf1-103">Yhdistä Facebook Ads Manageriin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="ffbf1-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="ffbf1-104">Voit luoda kampanjoita Facebookissa ja Instagramissaa viemällä yhdistettyjen asiakasprofiilien segmenttejä Facebook Ads Manageriin.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ffbf1-105">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="ffbf1-105">Prerequisites</span></span>

- <span data-ttu-id="ffbf1-106">Tarvitset [**Facebook Ad -tilin**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), joka sisältää [**Facebook -yritystilin**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="ffbf1-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="ffbf1-107">Sinun on oltava [**Facebook Ad -tilin**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) järjestelmänvalvoja.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="ffbf1-108">Yhteyden muodostaminen Facebook Ads Manageriin</span><span class="sxs-lookup"><span data-stu-id="ffbf1-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="ffbf1-109">Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ffbf1-110">Valitse **Facebook Ads Manager** -kohdassa **määritä**.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="ffbf1-111">Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ffbf1-112">Valitse **Continue with Facebook** kirjautuaksesi Facebook Ad -tiliisi.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="ffbf1-113">Salli **ads_management**-oikeus Facebook-todennuksen jälkeen.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="ffbf1-114">Valitse **Facebook Ad -tili**, jota haluat käyttää.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="ffbf1-115">Valitse yleisö avattavasta **Existing custom audience** -valikosta tai luo uusi **New custom audience** -kohdassa.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="ffbf1-116">Lisätietoja on kohdassa [**Kohdeyleisöt Facebook Ads Managerissa**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="ffbf1-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="ffbf1-117">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="ffbf1-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ffbf1-118">Määritä vienti valitsemalla **Next**.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="ffbf1-119">Yhdistimen määrittäminen</span><span class="sxs-lookup"><span data-stu-id="ffbf1-119">Configure the connector</span></span>

1. <span data-ttu-id="ffbf1-120">Valitse **Choose your key identifier** -kentässä **Email**, **Name and address** tai **Phone**, jonka avulla lähetetään Facebook Ads Manageriin.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="ffbf1-121">Yhdistä yhdistetyn asiakasentiteetin vastaavat määritteet valittua avaintunnistetta varten.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="ffbf1-122">[VIHJE] Paras vaihtoehtosi on se, että valitaan **Email** tunnukseksi.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="ffbf1-123">Lisätunnusten lisääminen voi parantaa vastaavuutta.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="ffbf1-124">Valitsemalla **Add attribute** voit yhdistää Facebook Ads Manageriin lähetettävät lisämääritteet.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="ffbf1-125">Facebook Ads Managerin määritteet yhdistetään seuraaviin kenttien lyhyisiin nimiin: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span><span class="sxs-lookup"><span data-stu-id="ffbf1-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="ffbf1-126">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="ffbf1-127">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ffbf1-128">Tietojen vieminen</span><span class="sxs-lookup"><span data-stu-id="ffbf1-128">Export the data</span></span>

<span data-ttu-id="ffbf1-129">Voit [viedä tietoja tarvittaessa](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ffbf1-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ffbf1-130">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ffbf1-131">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="ffbf1-131">Data privacy and compliance</span></span>

<span data-ttu-id="ffbf1-132">Kun tietojen lähetys Facebookin mainosten hallintaan otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-132">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ffbf1-133">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Facebook Ads noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ffbf1-134">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ffbf1-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ffbf1-135">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="ffbf1-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
