---
title: Reaaliaikainen tietojen käsittely ja rajoitukset
description: Yleisiä tietoja käyttäjäryhmän merkityksellisten tietojen reaaliaikaisista ominaisuuksista
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270276"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="427d6-103">Reaaliaikainen tietojen käsittely (esiversio)</span><span class="sxs-lookup"><span data-stu-id="427d6-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="427d6-104">Lähes reaaliaikaisen toiminnon ansiosta voit nähdä muutamassa sekunnissa asiakkaiden vuorovaikutukset tuotteiden tai palveluiden kanssa.</span><span class="sxs-lookup"><span data-stu-id="427d6-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="427d6-105">[Ajoitetut päivitykset](system.md#schedule-tab) sisältävät suuren määrän tietueita ja useita monimutkaisia toimintoja.</span><span class="sxs-lookup"><span data-stu-id="427d6-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="427d6-106">Tiedot noudetaan ensin tietolähteestä.</span><span class="sxs-lookup"><span data-stu-id="427d6-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="427d6-107">Seuraavaksi tiedot on yhdistetään ja täydennetään lisätiedoilla.</span><span class="sxs-lookup"><span data-stu-id="427d6-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="427d6-108">Prosessin jokainen suoritus voi kestää minuuteista tunteihin.</span><span class="sxs-lookup"><span data-stu-id="427d6-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="427d6-109">Reaaliaikaisista toiminnoista saadaan heti tietoja käyttöön siihen saakka, että seuraava ajoitettu päivitys hakee nämä tiedot tietolähteestä.</span><span class="sxs-lookup"><span data-stu-id="427d6-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="427d6-110">Reaaliaikaisissa päivityksissä on vanhentumisaika, jonka jälkeen ne eivät enää korvaa tietolähteen arvoa:</span><span class="sxs-lookup"><span data-stu-id="427d6-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="427d6-111">Profiilipäivitykset säilytetään 4 tunnin ajan</span><span class="sxs-lookup"><span data-stu-id="427d6-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="427d6-112">Aktiviteetit säilytetään 30 päivän ajan.</span><span class="sxs-lookup"><span data-stu-id="427d6-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="427d6-113">Nämä arvot ovat API-kutsuparametreja, joita voi muuttaa.</span><span class="sxs-lookup"><span data-stu-id="427d6-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="427d6-114">Niiden tarkoituksena on varmistaa, että lähdetiedot säilyvät paikkansa pitävinä.</span><span class="sxs-lookup"><span data-stu-id="427d6-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="427d6-115">Jos haluat reaaliaikaisten päivitysten sisältyvän kauemmin, ne on lisättävä tietolähteeseen siten, että ne noudetaan seuraavassa ajoitetussa päivityksessä.</span><span class="sxs-lookup"><span data-stu-id="427d6-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="427d6-116">Yhtenäistetyn asiakasprofiilin kenttien reaaliaikainen päivitys</span><span class="sxs-lookup"><span data-stu-id="427d6-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="427d6-117">Päivitetyt profiilit näkyvät asiakaskorttinäkymässä tai muissa visualisoinneissa muutamassa sekunnissa.</span><span class="sxs-lookup"><span data-stu-id="427d6-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="427d6-118">Koska reaaliaikaiset toiminnot tapahtuvat tietojen yhdistämisen jälkeen, ne koskevat vain yhdistettyjä asiakasprofiileja.</span><span class="sxs-lookup"><span data-stu-id="427d6-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="427d6-119">Näin ollen reaaliaikaiset profiili muutokset eivät päivitä mittoja, segmentin jäseniä tai rikastuksia.</span><span class="sxs-lookup"><span data-stu-id="427d6-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="427d6-120">Rajoitukset</span><span class="sxs-lookup"><span data-stu-id="427d6-120">Limitations</span></span>

- <span data-ttu-id="427d6-121">Asiakasprofiilit voidaan päivittää, mutta niitä ei voi luoda tai poistaa.</span><span class="sxs-lookup"><span data-stu-id="427d6-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="427d6-122">Reaaliaikaisten päivitysten vieminen ulkoisiin järjestelmiin, kuten Power BI:hin, ei ole tällä hetkellä mahdollista.</span><span class="sxs-lookup"><span data-stu-id="427d6-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="427d6-123">Aktiviteettien reaaliaikainen luominen</span><span class="sxs-lookup"><span data-stu-id="427d6-123">Real-time creation of activities</span></span>

<span data-ttu-id="427d6-124">Reaaliaikaisen ohjelmointirajapinnan avulla voi julkaista uuden aktiviteetin lähdejärjestelmästä (yksittäisestä lähdetietueesta) yhtenäiseen asiakasprofiiliin.</span><span class="sxs-lookup"><span data-stu-id="427d6-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="427d6-125">Uusi aktiviteetti on käytettävissä yhtenäisenä aktiviteettina, joka on yhdistetty asiakasprofiilin aikajanalla muutamassa sekunnissa.</span><span class="sxs-lookup"><span data-stu-id="427d6-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="427d6-126">Aikajana näkyy asiakaskorttinäkymässä tai muussa määritetyssä aikajanaintegraatiossa.</span><span class="sxs-lookup"><span data-stu-id="427d6-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="427d6-127">Aktiviteetit ovat muuttumattomia.</span><span class="sxs-lookup"><span data-stu-id="427d6-127">Activities are immutable.</span></span> <span data-ttu-id="427d6-128">Ne eivät muutu luonnin jälkeen.</span><span class="sxs-lookup"><span data-stu-id="427d6-128">They don't change once created.</span></span>
> - <span data-ttu-id="427d6-129">Tällä hetkellä segmenttejä ja mittoja ei voi päivittää uuden aktiviteetin perusteella.</span><span class="sxs-lookup"><span data-stu-id="427d6-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="427d6-130">Vain reaaliaikaisen ohjelmointirajapinnan kautta lisätyt aktiviteetit eivät ole osa vientiä, eivätkä ne näy PowerBI:ssä.</span><span class="sxs-lookup"><span data-stu-id="427d6-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="427d6-131">Reaaliaikainen ohjelmointirajapinta voidaan yhdistää kahdella tavalla:</span><span class="sxs-lookup"><span data-stu-id="427d6-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="427d6-132">[epäsuorasti](#connect-via-the-dynamics-365-customer-insights-connector) käyttämällä [Dynamics 365 Customer Insights -liitintä](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="427d6-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="427d6-133">[suoraan](#connect-directly-to-the-real-time-api) koodin kautta</span><span class="sxs-lookup"><span data-stu-id="427d6-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="427d6-134">Seuraavat edellytykset koskevat molempia tapoja:</span><span class="sxs-lookup"><span data-stu-id="427d6-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="427d6-135">Customer Insights -ympäristö</span><span class="sxs-lookup"><span data-stu-id="427d6-135">A Customer Insights environment</span></span>
- <span data-ttu-id="427d6-136">Yhdistetyt asiakasprofiilit</span><span class="sxs-lookup"><span data-stu-id="427d6-136">Unified customer profiles</span></span>
- <span data-ttu-id="427d6-137">Määritetyt ja suoritetut aktiviteetit</span><span class="sxs-lookup"><span data-stu-id="427d6-137">Activities configured and run</span></span>
- <span data-ttu-id="427d6-138">Osallistujan tai järjestelmänvalvojan oikeudet tilin todentamiseen</span><span class="sxs-lookup"><span data-stu-id="427d6-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="427d6-139">Yhdistä Dynamics 365 Customer Insights -liittimen kautta</span><span class="sxs-lookup"><span data-stu-id="427d6-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="427d6-140">Reaaliaikainen ohjelmointirajapinta voi käsitellä tietoja erityisestä Power Platform -liittimestä, [Dynamics 365 Customer Insights -liittimestä](https://docs.microsoft.com/connectors/customerinsights/), ilman että sinun tarvitsee kirjoittaa ja ottaa käyttöön mitään koodia.</span><span class="sxs-lookup"><span data-stu-id="427d6-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="427d6-141">Yhdistin voi tehdä samat reaaliaikaiset toiminnot kuin ohjelmointirajapinta.</span><span class="sxs-lookup"><span data-stu-id="427d6-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="427d6-142">Tarvitset kelvollisen käyttöoikeuden premium-liittimiin.</span><span class="sxs-lookup"><span data-stu-id="427d6-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="427d6-143">Lisätietoja:[Power Appsin ja Power Automaten käyttöoikeuksien usein kysytyt kysymykset](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="427d6-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="427d6-144">Power Platform [Power Apps ja/tai Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="427d6-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="427d6-145">Azure [Logic-sovellukset](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="427d6-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="427d6-146">Lisätietoja virtojen luomisesta on [Power Automate -ohjeessa](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="427d6-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="427d6-147">Yhteyden muodostaminen suoraan reaaliaikaiseen ohjelmointirajapintaan</span><span class="sxs-lookup"><span data-stu-id="427d6-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="427d6-148">Voit käyttää reaaliaikaisia ominaisuuksia muodostamalla oman jakson ja yhdistämällä suoraan reaaliaikaiseen ohjelmointirajapintaan.</span><span class="sxs-lookup"><span data-stu-id="427d6-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="427d6-149">Voit lähettää aktiviteetin lähdejärjestelmän muodossa tai UnifiedActivity-muodossa.</span><span class="sxs-lookup"><span data-stu-id="427d6-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="427d6-150">Hae muoto tekemällä API-kutsu kohteeseen /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="427d6-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="427d6-151">Tietoja tästä ohjelmointirajapinnasta, kuten parametrit ja vastaukset, on **EntityData**-osassa [Customer Insights -ohjelmointirajapintojen viitteessä](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="427d6-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="427d6-152">Lisätietoja on kohdassa [Customer Insights -ohjelmointirajapintojen käyttäminen](apis.md).</span><span class="sxs-lookup"><span data-stu-id="427d6-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="427d6-153">Tietoja reaaliaikaisesta käytöstä telemetriatietojen avulla</span><span class="sxs-lookup"><span data-stu-id="427d6-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="427d6-154">Yleiskatsaus reaaliaikaiseen ohjelmointirajapintaan tehtyjen pyyntöjen määrästä ja tietoja järjestelmässä mahdollisesti esiintyvistä ongelmista.</span><span class="sxs-lookup"><span data-stu-id="427d6-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="427d6-155">Voit [käyttää reaaliaikaista telemetriaa](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="427d6-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]