---
title: Customer Insightsin tietojen vieminen Marketoon
description: Tietoja yhteyden määrittämisestä Marketoon.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570399"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="bdaaf-103">Marketo-yhdistin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="bdaaf-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="bdaaf-104">Viemällä yhtenäisten asiakasprofiilien segmenttejä voit luoda kampanjoita, tuottaa sähköpostimarkkinointia ja käyttää tiettyjä asiakasryhmiä Marketon avulla.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bdaaf-105">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="bdaaf-105">Prerequisites</span></span>

-   <span data-ttu-id="bdaaf-106">[Marketo-tili](https://login.marketo.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bdaaf-107">Marketossa on aiemmin luotuja luetteloja ja vastaavia tunnuksia.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="bdaaf-108">Lisätietoja on kohdassa [Marketo-luettelot](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="bdaaf-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="bdaaf-109">[Segmentit on määritetty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="bdaaf-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="bdaaf-110">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="bdaaf-111">Yhteyden muodostaminen Marketoon</span><span class="sxs-lookup"><span data-stu-id="bdaaf-111">Connect to Marketo</span></span>

1. <span data-ttu-id="bdaaf-112">Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="bdaaf-113">Valitse **Marketo**-kohdassa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="bdaaf-114">Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="bdaaf-115">Anna **[Marketon asiakastunnus, asiakasohjelman salasana ja REST-päätepisteen isäntänimi](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="bdaaf-116">Anna **[Marketo-luettelon tunnus](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="bdaaf-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="bdaaf-117">Vahvista **Tietojen yksityisyys ja vaatimustenmukaisuus** valitsemalla **Hyväksyn** ja käynnistä Marketo-yhteys valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="bdaaf-118">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Näyttökuva viennin Marketo-yhteydestä":::

1. <span data-ttu-id="bdaaf-120">Määritä vienti valitsemalla **Next**.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="bdaaf-121">Yhdistimen määrittäminen</span><span class="sxs-lookup"><span data-stu-id="bdaaf-121">Configure the connector</span></span>

1. <span data-ttu-id="bdaaf-122">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="bdaaf-123">Vaihtoehtoisesti voit viedä **Etunimi**-, **Sukunimi**-, **Kaupunki**-, **Osavaltio**- ja **Maa tai alue** -kentät lisäkenttinä, joiden avulla sähköposteja voidaan mukauttaa.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="bdaaf-124">Yhdistä nämä kenttä valitsemalla **Lisää määrite**.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="bdaaf-125">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-125">Select the segments you want to export.</span></span> <span data-ttu-id="bdaaf-126">Voit viedä yhteensä enintään 1 000 000 asiakasprofiilia Marketoon.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Marketoon vietävien kenttien ja segmenttien valitseminen":::

1. <span data-ttu-id="bdaaf-128">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="bdaaf-129">Tietojen vieminen</span><span class="sxs-lookup"><span data-stu-id="bdaaf-129">Export the data</span></span>

<span data-ttu-id="bdaaf-130">Voit [viedä tietoja tarvittaessa](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="bdaaf-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="bdaaf-131">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bdaaf-132">Marketon segmentit ovat nyt [Marketo-luetteloissa](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="bdaaf-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bdaaf-133">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="bdaaf-133">Known limitations</span></span>

- <span data-ttu-id="bdaaf-134">Enintään 1 miljoona profiilia kussakin Marketo-viennissä.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="bdaaf-135">Marketo-vienti on rajoitettu segmentteihin</span><span class="sxs-lookup"><span data-stu-id="bdaaf-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="bdaaf-136">Yhteensä 1 miljoonan profiilin segmenttien vienti voi kestää 3 tuntia.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="bdaaf-137">Marketoon vietävien profiilien määrä määräytyy Marketo-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bdaaf-138">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="bdaaf-138">Data privacy and compliance</span></span>

<span data-ttu-id="bdaaf-139">Kun tietojen lähetys Marketoon otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bdaaf-140">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Marketo noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bdaaf-141">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bdaaf-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bdaaf-142">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="bdaaf-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
