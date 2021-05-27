---
title: Customer Insightsin tietojen vieminen Google Adsiin
description: Tietoja yhteyden määrittämisestä ja viennistä Google Adsiin.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976314"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="b0c12-103">Segmenttien vieminen Google Adsiin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="b0c12-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="b0c12-104">Vie yhtenäistettyjen asiakasprofiilien segmentit Google Adsin käyttäjäryhmäluetteloon ja käytä profiileja mainontaan Google Haussa, YouTubessa, Gmailissa ja Google Display-verkostossa.</span><span class="sxs-lookup"><span data-stu-id="b0c12-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="b0c12-105">Yhteyden edellytykset</span><span class="sxs-lookup"><span data-stu-id="b0c12-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="b0c12-106">[Google Ads -tili](https://ads.google.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="b0c12-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b0c12-107">Sinulla on [hyväksytty Google Ads -kehittäjätunnus](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="b0c12-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="b0c12-108">[Asiakkaan vastaavuuskäytännön](https://support.google.com/adspolicy/answer/6299717) vaatimukset täyttyvät</span><span class="sxs-lookup"><span data-stu-id="b0c12-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="b0c12-109">[Uudelleenmarkkinointiluetteloiden kokojen](https://support.google.com/google-ads/answer/7558048) edellytys on täytettävä</span><span class="sxs-lookup"><span data-stu-id="b0c12-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="b0c12-110">Google Adsissa on aiemmin luotuja käyttäjäryhmiä ja vastaavia tunnuksia.</span><span class="sxs-lookup"><span data-stu-id="b0c12-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="b0c12-111">Lisätietoja on kohdassa [Google Ads -käyttäjäryhmät](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="b0c12-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="b0c12-112">[Segmentit on määritetty](segments.md)</span><span class="sxs-lookup"><span data-stu-id="b0c12-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="b0c12-113">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta, etunimeä ja sukunimeä vastaavat kentät.</span><span class="sxs-lookup"><span data-stu-id="b0c12-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b0c12-114">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="b0c12-114">Known limitations</span></span>

- <span data-ttu-id="b0c12-115">Enintään 1 miljoona profiilia kussakin Google Ads -viennissä.</span><span class="sxs-lookup"><span data-stu-id="b0c12-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="b0c12-116">Google Ads -vienti on rajoitettu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="b0c12-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="b0c12-117">Yhteensä 1 miljoonan profiilin segmenttien vienti voi kestää 5 minuuttia palveluntoimittajan rajoitusten vuoksi.</span><span class="sxs-lookup"><span data-stu-id="b0c12-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="b0c12-118">Google Ads -vastaavuuden saavuttaminen voi kestää 48 tuntia.</span><span class="sxs-lookup"><span data-stu-id="b0c12-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="b0c12-119">Määritä yhteys Google Adsiin</span><span class="sxs-lookup"><span data-stu-id="b0c12-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="b0c12-120">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="b0c12-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b0c12-121">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Google Ads**.</span><span class="sxs-lookup"><span data-stu-id="b0c12-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="b0c12-122">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="b0c12-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b0c12-123">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="b0c12-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b0c12-124">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="b0c12-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b0c12-125">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="b0c12-125">Choose who can use this connection.</span></span> <span data-ttu-id="b0c12-126">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="b0c12-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b0c12-127">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b0c12-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b0c12-128">Anna **[Google Ads -asiakastunnus](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="b0c12-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="b0c12-129">Anna **[Google Adsin hyväksymä kehittäjätunnus](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="b0c12-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="b0c12-130">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="b0c12-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b0c12-131">Valitse **Todenna Google Adsin avulla** ja anna Google Ads -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="b0c12-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="b0c12-132">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="b0c12-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b0c12-133">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="b0c12-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="b0c12-134">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="b0c12-134">Configure an export</span></span>

<span data-ttu-id="b0c12-135">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="b0c12-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b0c12-136">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b0c12-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b0c12-137">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="b0c12-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b0c12-138">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="b0c12-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b0c12-139">Valitse **Yhteys vientiä varten** -kentässä yhteys Google Ads -osasta.</span><span class="sxs-lookup"><span data-stu-id="b0c12-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="b0c12-140">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="b0c12-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b0c12-141">Käynnistä yhteys Google Adsiin antamalla **[Google Ads -käyttäjäryhmän tunnus](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** ja valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="b0c12-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="b0c12-142">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="b0c12-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b0c12-143">Toimi samalla tavalla **Etunimi**- ja **Sukunimi**-kenttien osalta.</span><span class="sxs-lookup"><span data-stu-id="b0c12-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="b0c12-144">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="b0c12-144">Select the segments you want to export.</span></span> <span data-ttu-id="b0c12-145">Voit viedä yhteensä enintään 1 000 000 asiakasprofiilia Google Adsiin.</span><span class="sxs-lookup"><span data-stu-id="b0c12-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="b0c12-146">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="b0c12-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b0c12-147">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="b0c12-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b0c12-148">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b0c12-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b0c12-149">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="b0c12-149">Data privacy and compliance</span></span>

<span data-ttu-id="b0c12-150">Kun tietojen lähetys Google Adsiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="b0c12-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b0c12-151">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Google Ads noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="b0c12-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b0c12-152">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b0c12-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b0c12-153">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="b0c12-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
