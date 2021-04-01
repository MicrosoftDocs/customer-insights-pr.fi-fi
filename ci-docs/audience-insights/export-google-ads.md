---
title: Customer Insightsin tietojen vieminen Google Adsiin
description: Tietoja yhteyden määrittämisestä Google Adsiin.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598243"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="2d050-103">Google Ads -yhdistin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="2d050-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="2d050-104">Vie yhtenäistettyjen asiakasprofiilien segmentit Google Adsin käyttäjäryhmäluetteloon ja käytä profiileja mainontaan Google Haussa, YouTubessa, Gmailissa ja Google Display-verkostossa.</span><span class="sxs-lookup"><span data-stu-id="2d050-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="2d050-105">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="2d050-105">Prerequisites</span></span>

-   <span data-ttu-id="2d050-106">[Google Ads -tili](https://ads.google.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="2d050-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2d050-107">Google Adsissa on aiemmin luotuja käyttäjäryhmiä ja vastaavia tunnuksia.</span><span class="sxs-lookup"><span data-stu-id="2d050-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="2d050-108">Lisätietoja on kohdassa [Google Ads -käyttäjäryhmät](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="2d050-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="2d050-109">[Segmentit on määritetty](segments.md)</span><span class="sxs-lookup"><span data-stu-id="2d050-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="2d050-110">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta, etunimeä ja sukunimeä vastaavat kentät.</span><span class="sxs-lookup"><span data-stu-id="2d050-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="2d050-111">Yhdistä Google Adsiin</span><span class="sxs-lookup"><span data-stu-id="2d050-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="2d050-112">Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="2d050-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="2d050-113">Valitse **Google Ads** -kohdassa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="2d050-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="2d050-114">Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="2d050-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="2d050-115">Anna **[Google Ads -asiakastunnus](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="2d050-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="2d050-116">Anna **[Google Adsin hyväksymä kehittäjätunnus](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="2d050-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="2d050-117">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="2d050-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2d050-118">Käynnistä yhteys Google Adsiin antamalla **[Google Ads -käyttäjäryhmän tunnus](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** ja valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="2d050-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="2d050-119">Valitse **Todenna Google Adsin avulla** ja anna Google Ads -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="2d050-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="2d050-120">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="2d050-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Näyttökuva viennin Google Ads -yhteydestä":::

1. <span data-ttu-id="2d050-122">Määritä vienti valitsemalla **Next**.</span><span class="sxs-lookup"><span data-stu-id="2d050-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="2d050-123">Yhdistimen määrittäminen</span><span class="sxs-lookup"><span data-stu-id="2d050-123">Configure the connector</span></span>

1. <span data-ttu-id="2d050-124">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="2d050-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2d050-125">Toimi samalla tavalla **Etunimi**- ja **Sukunimi**-kenttien osalta.</span><span class="sxs-lookup"><span data-stu-id="2d050-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="2d050-126">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="2d050-126">Select the segments you want to export.</span></span> <span data-ttu-id="2d050-127">Voit viedä yhteensä enintään 1 000 000 asiakasprofiilia Google Adsiin.</span><span class="sxs-lookup"><span data-stu-id="2d050-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="2d050-128">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="2d050-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="2d050-129">Tietojen vieminen</span><span class="sxs-lookup"><span data-stu-id="2d050-129">Export the data</span></span>

<span data-ttu-id="2d050-130">Voit [viedä tietoja tarvittaessa](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2d050-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="2d050-131">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="2d050-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2d050-132">Google Adsin segmentit ovat nyt [Google Ads -käyttäjäryhmissä](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="2d050-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2d050-133">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="2d050-133">Known limitations</span></span>

- <span data-ttu-id="2d050-134">Enintään 1 miljoona profiilia kussakin Google Ads -viennissä.</span><span class="sxs-lookup"><span data-stu-id="2d050-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="2d050-135">Google Ads -vienti on rajoitettu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="2d050-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="2d050-136">Yhteensä 1 miljoonan profiilin segmenttien vienti voi kestää 5 minuuttia palveluntoimittajan rajoitusten vuoksi.</span><span class="sxs-lookup"><span data-stu-id="2d050-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="2d050-137">Google Ads -vastaavuuden saavuttaminen voi kestää 48 tuntia.</span><span class="sxs-lookup"><span data-stu-id="2d050-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2d050-138">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="2d050-138">Data privacy and compliance</span></span>

<span data-ttu-id="2d050-139">Kun tietojen lähetys Google Adsiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="2d050-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2d050-140">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Google Ads noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="2d050-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="2d050-141">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2d050-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2d050-142">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="2d050-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]