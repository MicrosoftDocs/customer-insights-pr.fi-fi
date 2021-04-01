---
title: Customer Insightsin tietojen vieminen AdRolliin
description: Tietoja yhteyden määrittämisestä AdRolliin.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697070"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="3e414-103">AdRoll-yhdistin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="3e414-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="3e414-104">Vie yhtenäisten asiakasprofiilien segmentit AdRolliin ja käytä niitä mainostarkoituksiin.</span><span class="sxs-lookup"><span data-stu-id="3e414-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="3e414-105">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="3e414-105">Prerequisites</span></span>

-   <span data-ttu-id="3e414-106">[AdRoll-tili](https://www.adroll.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="3e414-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3e414-107">Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).</span><span class="sxs-lookup"><span data-stu-id="3e414-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="3e414-108">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="3e414-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="3e414-109">Muodosta yhteys AdRolliin</span><span class="sxs-lookup"><span data-stu-id="3e414-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="3e414-110">Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="3e414-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3e414-111">Valitse **AdRoll**-kohdassa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="3e414-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="3e414-112">Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="3e414-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="AdRoll-yhteyden määritysruutu.":::

1. <span data-ttu-id="3e414-114">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="3e414-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3e414-115">Käynnistä AdRoll-yhteys valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="3e414-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="3e414-116">Valitse **Todenna AdRollin avulla** ja anna AdRoll-tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="3e414-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="3e414-117">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="3e414-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="3e414-118">Anna **AdRoll-mainostajatunnuksesi** [AdRoll-mainostettava](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="3e414-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="3e414-119">Määritä vienti valitsemalla **Next**.</span><span class="sxs-lookup"><span data-stu-id="3e414-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="3e414-120">Yhdistimen määrittäminen</span><span class="sxs-lookup"><span data-stu-id="3e414-120">Configure the connector</span></span>

1. <span data-ttu-id="3e414-121">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="3e414-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="3e414-122">Segmenttejä on vietävä AdRolliin.</span><span class="sxs-lookup"><span data-stu-id="3e414-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="3e414-123">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="3e414-123">Select the segments you want to export.</span></span> <span data-ttu-id="3e414-124">Valitse segmentti, jossa on vähintään 100 jäsentä.</span><span class="sxs-lookup"><span data-stu-id="3e414-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="3e414-125">Pienempiä segmenttejä ei voi viedä.</span><span class="sxs-lookup"><span data-stu-id="3e414-125">You can't export smaller segments.</span></span> <span data-ttu-id="3e414-126">Lisäksi vietävän segmentin enimmäiskoko on 250 000 jäsentä per vienti.</span><span class="sxs-lookup"><span data-stu-id="3e414-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="3e414-127">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="3e414-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3e414-128">Tietojen vieminen</span><span class="sxs-lookup"><span data-stu-id="3e414-128">Export the data</span></span>

<span data-ttu-id="3e414-129">Voit [viedä tietoja tarvittaessa](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3e414-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="3e414-130">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="3e414-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3e414-131">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="3e414-131">Known limitations</span></span>

- <span data-ttu-id="3e414-132">Voit viedä yhteensä enintään 250 000 asiakasprofiilia per vienti AdRolliin.</span><span class="sxs-lookup"><span data-stu-id="3e414-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="3e414-133">Alle 100 profiilin segmenttejä ei voi viedä AdRolliin.</span><span class="sxs-lookup"><span data-stu-id="3e414-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="3e414-134">AdRoll-vienti on rajoitettu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="3e414-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="3e414-135">Jopa 250 000 profiilin vieminen AdRolliin voi kestää 10 minuuttia.</span><span class="sxs-lookup"><span data-stu-id="3e414-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="3e414-136">AdRolliin vietävien profiilien määrä määräytyy AdRoll-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.</span><span class="sxs-lookup"><span data-stu-id="3e414-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3e414-137">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="3e414-137">Data privacy and compliance</span></span>

<span data-ttu-id="3e414-138">Kun tietojen lähetys AdRolliin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="3e414-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3e414-139">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että AdRoll noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="3e414-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3e414-140">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3e414-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="3e414-141">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="3e414-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
