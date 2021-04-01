---
title: Customer Insightsin tietojen vieminen Mailchimpiin
description: Tietoja yhteyden määrittämisestä MailChimpiin.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598197"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="817b7-103">Mailchimp-yhdistin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="817b7-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="817b7-104">Uutiskirjeiden ja sähköpostikampanjoiden luonti viemällä yhtenäistettyjä asiakasprofiilisegmenttejä Mailchimpiin.</span><span class="sxs-lookup"><span data-stu-id="817b7-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="817b7-105">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="817b7-105">Prerequisites</span></span>

-   <span data-ttu-id="817b7-106">[Mailchimp-tili](https://mailchimp.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="817b7-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="817b7-107">Mailchimpissa on aiemmin luotuja käyttäjäryhmiä ja vastaavia tunnuksia.</span><span class="sxs-lookup"><span data-stu-id="817b7-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="817b7-108">Lisätietoja on kohdassa [Mailchimp-käyttäjäryhmät](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="817b7-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="817b7-109">[Segmentit on määritetty](segments.md)</span><span class="sxs-lookup"><span data-stu-id="817b7-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="817b7-110">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="817b7-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="817b7-111">Yhdistä Mailchimpiin</span><span class="sxs-lookup"><span data-stu-id="817b7-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="817b7-112">Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="817b7-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="817b7-113">Valitse **Mailchimp**-kohdassa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="817b7-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="817b7-114">Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="817b7-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="817b7-115">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="817b7-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="817b7-116">Käynnistä yhteys Mailchimpiin antamalla **[Mailchimp-käyttäjäryhmän tunnus](https://mailchimp.com/help/find-audience-id/)** ja valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="817b7-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="817b7-117">Valitse **Todenna Mailchimpin avulla** ja anna Mailchimp-tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="817b7-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="817b7-118">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="817b7-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Näyttökuva viennin MailChimp-yhteydestä":::

1. <span data-ttu-id="817b7-120">Määritä vienti valitsemalla **Next**.</span><span class="sxs-lookup"><span data-stu-id="817b7-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="817b7-121">Yhdistimen määrittäminen</span><span class="sxs-lookup"><span data-stu-id="817b7-121">Configure the connector</span></span>

1. <span data-ttu-id="817b7-122">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="817b7-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="817b7-123">Vaihtoehtoisesti voit viedä **Etunimi**- ja **Sukunimi**-kentät lisäkenttinä, joiden avulla sähköposteja voidaan mukauttaa.</span><span class="sxs-lookup"><span data-stu-id="817b7-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="817b7-124">Yhdistä nämä kenttä valitsemalla **Lisää määrite**.</span><span class="sxs-lookup"><span data-stu-id="817b7-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="817b7-125">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="817b7-125">Select the segments you want to export.</span></span> <span data-ttu-id="817b7-126">Voit viedä yhteensä enintään 1 000 000 asiakasprofiilia MailChimpiin.</span><span class="sxs-lookup"><span data-stu-id="817b7-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Mailchimpiin vietävien kenttien ja segmenttien valitseminen":::

1. <span data-ttu-id="817b7-128">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="817b7-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="817b7-129">Tietojen vieminen</span><span class="sxs-lookup"><span data-stu-id="817b7-129">Export the data</span></span>

<span data-ttu-id="817b7-130">Voit [viedä tietoja tarvittaessa](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="817b7-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="817b7-131">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="817b7-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="817b7-132">Mailchimpin segmentit ovat nyt [Mailchimp-käyttäjäryhmissä](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="817b7-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="817b7-133">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="817b7-133">Known limitations</span></span>

- <span data-ttu-id="817b7-134">Enintään 1 miljoona profiilia kussakin Mailchimp-viennissä.</span><span class="sxs-lookup"><span data-stu-id="817b7-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="817b7-135">MailChimp-vienti on rajoitettu segmentteihin</span><span class="sxs-lookup"><span data-stu-id="817b7-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="817b7-136">Yhteensä 1 miljoonan profiilin segmenttien vienti voi kestää kolme tuntia palveluntoimittajan rajoitusten vuoksi.</span><span class="sxs-lookup"><span data-stu-id="817b7-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="817b7-137">Mailchimpiin vietävien profiilien määrä määräytyy Mailchimp-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.</span><span class="sxs-lookup"><span data-stu-id="817b7-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="817b7-138">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="817b7-138">Data privacy and compliance</span></span>

<span data-ttu-id="817b7-139">Kun tietojen lähetys Mailchimpiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="817b7-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="817b7-140">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Mailchimp noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="817b7-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="817b7-141">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="817b7-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="817b7-142">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="817b7-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]