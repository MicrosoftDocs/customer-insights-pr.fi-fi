---
title: Customer Insightsin tietojen vieminen Autopilotiin
description: Tietoja yhteyden määrittämisestä ja viennistä Autopilotiin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760139"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="f2f83-103">Segmenttien vieminen Autopilotiin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="f2f83-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="f2f83-104">Vie yhdistettyjen asiakasprofiilien segmentit Autopilotiin ja käytä niitä Autopilotin sähköpostimarkkinoinnissa.</span><span class="sxs-lookup"><span data-stu-id="f2f83-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f2f83-105">Yhteyden edellytykset</span><span class="sxs-lookup"><span data-stu-id="f2f83-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f2f83-106">[Autopilot-tili](https://www.autopilothq.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="f2f83-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f2f83-107">Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).</span><span class="sxs-lookup"><span data-stu-id="f2f83-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f2f83-108">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="f2f83-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f2f83-109">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="f2f83-109">Known limitations</span></span>

- <span data-ttu-id="f2f83-110">Voit viedä yhteensä enintään 100 000 asiakasprofiilia Autopilotiin.</span><span class="sxs-lookup"><span data-stu-id="f2f83-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="f2f83-111">Autopilot-vienti on rajoitettu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="f2f83-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="f2f83-112">100 000 profiilin vieminen Autopilotiin voi kestää muutaman tunnin.</span><span class="sxs-lookup"><span data-stu-id="f2f83-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="f2f83-113">Autopilotiin vietävien profiilien määrä määräytyy Autopilot-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.</span><span class="sxs-lookup"><span data-stu-id="f2f83-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="f2f83-114">Määritä yhteys Autopilotiin</span><span class="sxs-lookup"><span data-stu-id="f2f83-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="f2f83-115">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="f2f83-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f2f83-116">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Autopilot**.</span><span class="sxs-lookup"><span data-stu-id="f2f83-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="f2f83-117">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="f2f83-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f2f83-118">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="f2f83-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f2f83-119">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="f2f83-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f2f83-120">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="f2f83-120">Choose who can use this connection.</span></span> <span data-ttu-id="f2f83-121">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="f2f83-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f2f83-122">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f2f83-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="f2f83-123">Anna [Autopilotin API-avain](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="f2f83-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="f2f83-124">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="f2f83-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f2f83-125">Käynnistä Autopilot-yhteys valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="f2f83-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="f2f83-126">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="f2f83-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f2f83-127">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="f2f83-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f2f83-128">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="f2f83-128">Configure an export</span></span>

<span data-ttu-id="f2f83-129">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="f2f83-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f2f83-130">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f2f83-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f2f83-131">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="f2f83-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f2f83-132">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="f2f83-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f2f83-133">Valitse **Yhteys vientiä varten** -kentässä yhteys Autopilot-osasta.</span><span class="sxs-lookup"><span data-stu-id="f2f83-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="f2f83-134">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="f2f83-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="f2f83-135">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="f2f83-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f2f83-136">Toimi samalla tavalla muiden valinnaisten kenttien osalta. Näitä kenttiä ovat esimerkiksi **Etunimi**, **Sukunimi**.</span><span class="sxs-lookup"><span data-stu-id="f2f83-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="f2f83-137">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="f2f83-137">Select the segments you want to export.</span></span> <span data-ttu-id="f2f83-138">On erittäin **suositeltavaa, että asiakastietueita viedään enintään 100 000** Autopilotiin.</span><span class="sxs-lookup"><span data-stu-id="f2f83-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="f2f83-139">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="f2f83-139">Select **Save**.</span></span>

<span data-ttu-id="f2f83-140">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="f2f83-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f2f83-141">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="f2f83-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f2f83-142">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f2f83-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f2f83-143">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="f2f83-143">Data privacy and compliance</span></span>

<span data-ttu-id="f2f83-144">Kun tietojen lähetys Autopilotiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="f2f83-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f2f83-145">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Autopilot noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="f2f83-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f2f83-146">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f2f83-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f2f83-147">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="f2f83-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
