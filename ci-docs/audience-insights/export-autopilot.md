---
title: Customer Insightsin tietojen vieminen Autopilotiin
description: Tietoja yhteyden määrittämisestä Autopilotiin.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269234"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="5031c-103">Autopilot-yhdistin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="5031c-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="5031c-104">Vie yhdistettyjen asiakasprofiilien segmentit Autopilotiin ja käytä niitä Autopilotin sähköpostimarkkinoinnissa.</span><span class="sxs-lookup"><span data-stu-id="5031c-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="5031c-105">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="5031c-105">Prerequisites</span></span>

-   <span data-ttu-id="5031c-106">[Autopilot-tili](https://www.autopilothq.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="5031c-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5031c-107">Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).</span><span class="sxs-lookup"><span data-stu-id="5031c-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5031c-108">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="5031c-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="5031c-109">Muodosta yhteys Autopilotiin</span><span class="sxs-lookup"><span data-stu-id="5031c-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="5031c-110">Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="5031c-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="5031c-111">Valitse **Autopilot**-kohdassa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="5031c-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="5031c-112">Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="5031c-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Autopilot-yhteyden määritysruutu.":::

1. <span data-ttu-id="5031c-114">Anna **Autopilotin ohjelmointirajapinnan avain** [Autopilotin ohjelmointirajapinnan avain](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="5031c-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="5031c-115">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="5031c-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5031c-116">Käynnistä Autopilot-yhteys valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="5031c-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="5031c-117">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="5031c-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5031c-118">Määritä vienti valitsemalla **Next**.</span><span class="sxs-lookup"><span data-stu-id="5031c-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="5031c-119">Yhdistimen määrittäminen</span><span class="sxs-lookup"><span data-stu-id="5031c-119">Configure the connector</span></span>

1. <span data-ttu-id="5031c-120">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="5031c-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="5031c-121">Toimi samalla tavalla muiden valinnaisten kenttien osalta. Näitä kenttiä ovat esimerkiksi **Etunimi**, **Sukunimi**.</span><span class="sxs-lookup"><span data-stu-id="5031c-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="5031c-122">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="5031c-122">Select the segments you want to export.</span></span> <span data-ttu-id="5031c-123">On erittäin **suositeltavaa, että asiakastietueita viedään enintään 100 000** Autopilotiin.</span><span class="sxs-lookup"><span data-stu-id="5031c-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="5031c-124">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="5031c-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="5031c-125">Tietojen vieminen</span><span class="sxs-lookup"><span data-stu-id="5031c-125">Export the data</span></span>

<span data-ttu-id="5031c-126">Voit [viedä tietoja tarvittaessa](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5031c-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="5031c-127">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="5031c-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5031c-128">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="5031c-128">Known limitations</span></span>

- <span data-ttu-id="5031c-129">Voit viedä yhteensä enintään 100 000 asiakasprofiilia Autopilotiin.</span><span class="sxs-lookup"><span data-stu-id="5031c-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="5031c-130">Autopilot-vienti on rajoitettu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="5031c-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="5031c-131">100 000 profiilin vieminen Autopilotiin voi kestää muutaman tunnin.</span><span class="sxs-lookup"><span data-stu-id="5031c-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="5031c-132">Autopilotiin vietävien profiilien määrä määräytyy Autopilot-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.</span><span class="sxs-lookup"><span data-stu-id="5031c-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5031c-133">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="5031c-133">Data privacy and compliance</span></span>

<span data-ttu-id="5031c-134">Kun tietojen lähetys Autopilotiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="5031c-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5031c-135">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Autopilot noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="5031c-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="5031c-136">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5031c-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5031c-137">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="5031c-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]