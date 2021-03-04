---
title: Customer Insightsin tietojen vieminen DotDigitaliin
description: Tietoja yhteyden määrittämisestä DotDigitaliin.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269096"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="8d7bf-103">DotDigital-yhdistin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="8d7bf-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="8d7bf-104">Vie yhtenäistettyjen asiakasprofiilien segmentit DotDigital-osoitekirjoihin ja käytä niitä kampanjoissa, sähköpostimarkkinoinnissa ja asiakassegmenttien muodostamisessa DotDigitalin kanssa.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="8d7bf-105">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="8d7bf-105">Prerequisites</span></span>

-   <span data-ttu-id="8d7bf-106">[DotDigital-tili](https://dotdigital.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8d7bf-107">DotDigitalissa on aiemmin luotuja osoitekirjoja ja vastaavia tunnuksia.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="8d7bf-108">Tunnus saadaan URL-osoitteesta, kun valitset ja avaat osoitekirjan.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="8d7bf-109">Lisätietoja on kohdassa [DotDigital-osoitekirjat](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="8d7bf-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="8d7bf-110">Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).</span><span class="sxs-lookup"><span data-stu-id="8d7bf-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="8d7bf-111">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="8d7bf-112">Yhdistäminen DotDigitaliin</span><span class="sxs-lookup"><span data-stu-id="8d7bf-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="8d7bf-113">Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8d7bf-114">Valitse **DotDigital**-kohdassa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="8d7bf-115">Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="DotDigital-viennin määritysruutu":::

1. <span data-ttu-id="8d7bf-117">Anna **DotDigitalin käyttäjänimi ja salasana**.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="8d7bf-118">Anna **[DotDigital-osoitekirjan tunnus](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="8d7bf-119">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="8d7bf-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8d7bf-120">Käynnistä DotDigital-yhteys valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="8d7bf-121">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8d7bf-122">Määritä vienti valitsemalla **Next**.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="8d7bf-123">Yhdistimen määrittäminen</span><span class="sxs-lookup"><span data-stu-id="8d7bf-123">Configure the connector</span></span>

1. <span data-ttu-id="8d7bf-124">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8d7bf-125">Toimi samalla tavalla muiden valinnaisten kenttien osalta. Näitä kenttiä ovat esimerkiksi **Etunimi**, **Sukunimi**, **Koko nimi**, **Sukupuoli** ja **Postinumero**.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="8d7bf-126">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-126">Select the segments you want to export.</span></span> <span data-ttu-id="8d7bf-127">Voit viedä yhteensä enintään 1 000 000 asiakasprofiilia DotDigitaliin.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="8d7bf-128">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8d7bf-129">Tietojen vieminen</span><span class="sxs-lookup"><span data-stu-id="8d7bf-129">Export the data</span></span>

<span data-ttu-id="8d7bf-130">Voit [viedä tietoja tarvittaessa](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8d7bf-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8d7bf-131">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8d7bf-132">DotDigitalissa voi etsiä nyt segmenttejä [DotDigital-osoitekirjoissa](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="8d7bf-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8d7bf-133">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="8d7bf-133">Known limitations</span></span>

- <span data-ttu-id="8d7bf-134">Enintään 1 miljoona profiilia kussakin DotDigital-viennissä.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="8d7bf-135">DotDigital-vienti on rajoitettu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="8d7bf-136">Yhteensä 1 miljoonan profiilin segmenttien vienti voi kestää 3 tuntia palveluntoimittajan rajoitusten vuoksi.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="8d7bf-137">DotDigitaliin vietävien profiilien määrä määräytyy DotDigital-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8d7bf-138">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="8d7bf-138">Data privacy and compliance</span></span>

<span data-ttu-id="8d7bf-139">Kun tietojen lähetys DotDigitaliin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8d7bf-140">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että DotDigital noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="8d7bf-141">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8d7bf-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8d7bf-142">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="8d7bf-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]