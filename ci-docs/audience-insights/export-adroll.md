---
title: Customer Insightsin tietojen vieminen AdRolliin
description: Tietoja yhteyden määrittämisestä ja viennistä AdRolliin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e8f4d4ee6b2c6cdec513b700641db568fa16076d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895955"
---
# <a name="export-segment-lists-to-adroll-preview"></a><span data-ttu-id="6f3af-103">Segmenttiluetteloiden vieminen AdRolliin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="6f3af-103">Export segment lists to AdRoll (preview)</span></span>

<span data-ttu-id="6f3af-104">Vie yhtenäisten asiakasprofiilien segmentit AdRolliin ja käytä niitä mainostarkoituksiin.</span><span class="sxs-lookup"><span data-stu-id="6f3af-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="6f3af-105">Yhteyden edellytykset</span><span class="sxs-lookup"><span data-stu-id="6f3af-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="6f3af-106">[AdRoll-tili](https://www.adroll.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="6f3af-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6f3af-107">Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).</span><span class="sxs-lookup"><span data-stu-id="6f3af-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="6f3af-108">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="6f3af-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6f3af-109">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="6f3af-109">Known limitations</span></span>

- <span data-ttu-id="6f3af-110">Voit viedä yhteensä enintään 250 000 asiakasprofiilia per vienti AdRolliin.</span><span class="sxs-lookup"><span data-stu-id="6f3af-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="6f3af-111">Alle 100 profiilin segmenttejä ei voi viedä AdRolliin.</span><span class="sxs-lookup"><span data-stu-id="6f3af-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="6f3af-112">AdRoll-vienti on rajoitettu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="6f3af-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="6f3af-113">Jopa 250 000 profiilin vieminen AdRolliin voi kestää 10 minuuttia.</span><span class="sxs-lookup"><span data-stu-id="6f3af-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="6f3af-114">AdRolliin vietävien profiilien määrä määräytyy AdRoll-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.</span><span class="sxs-lookup"><span data-stu-id="6f3af-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="6f3af-115">Määritä yhteys AdRolliin</span><span class="sxs-lookup"><span data-stu-id="6f3af-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="6f3af-116">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="6f3af-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6f3af-117">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **AdRoll**.</span><span class="sxs-lookup"><span data-stu-id="6f3af-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="6f3af-118">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="6f3af-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6f3af-119">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="6f3af-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6f3af-120">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="6f3af-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6f3af-121">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="6f3af-121">Choose who can use this connection.</span></span> <span data-ttu-id="6f3af-122">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="6f3af-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6f3af-123">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6f3af-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6f3af-124">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="6f3af-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6f3af-125">Käynnistä AdRoll-yhteys valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="6f3af-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="6f3af-126">Valitse **Todenna AdRollin avulla** ja anna AdRoll-tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="6f3af-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="6f3af-127">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="6f3af-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6f3af-128">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="6f3af-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="6f3af-129">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="6f3af-129">Configure an export</span></span>

<span data-ttu-id="6f3af-130">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="6f3af-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6f3af-131">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6f3af-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6f3af-132">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="6f3af-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6f3af-133">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="6f3af-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6f3af-134">Valitse **Yhteys vientiä varten** -kentässä yhteys AdRoll-osasta.</span><span class="sxs-lookup"><span data-stu-id="6f3af-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="6f3af-135">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="6f3af-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6f3af-136">Anna **AdRoll-mainostajatunnus**. Lisätietoja: [AdRoll-mainostajaprofiilit](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="6f3af-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="6f3af-137">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="6f3af-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="6f3af-138">Segmenttejä on vietävä AdRolliin.</span><span class="sxs-lookup"><span data-stu-id="6f3af-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="6f3af-139">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="6f3af-139">Select the segments you want to export.</span></span> <span data-ttu-id="6f3af-140">Valitse segmentti, jossa on vähintään 100 jäsentä.</span><span class="sxs-lookup"><span data-stu-id="6f3af-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="6f3af-141">Pienempiä segmenttejä ei voi viedä.</span><span class="sxs-lookup"><span data-stu-id="6f3af-141">You can't export smaller segments.</span></span> <span data-ttu-id="6f3af-142">Lisäksi vietävän segmentin enimmäiskoko on 250 000 jäsentä per vienti.</span><span class="sxs-lookup"><span data-stu-id="6f3af-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="6f3af-143">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="6f3af-143">Select **Save**.</span></span>

<span data-ttu-id="6f3af-144">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="6f3af-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6f3af-145">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="6f3af-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6f3af-146">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6f3af-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6f3af-147">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="6f3af-147">Data privacy and compliance</span></span>

<span data-ttu-id="6f3af-148">Kun tietojen lähetys AdRolliin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="6f3af-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6f3af-149">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että AdRoll noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="6f3af-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6f3af-150">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6f3af-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="6f3af-151">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="6f3af-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
