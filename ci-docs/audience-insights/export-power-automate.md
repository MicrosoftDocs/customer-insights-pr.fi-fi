---
title: Power Automate -yhdistin | Microsoft Docs
description: Työnkulkujen luominen Microsoft Power Automatessa Dynamics 365 Customer Insightsista.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305060"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="46316-103">Power Automate -yhdistin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="46316-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="46316-104">Käynnistä tietyt tapahtumat automaattisesti, kun tiedot muuttuvat ja hallitse monimutkaisempia työnkulkuja suoraan [Power Automatessa](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="46316-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="46316-105">Power Automaten käynnistimet</span><span class="sxs-lookup"><span data-stu-id="46316-105">Power Automate triggers</span></span>

<span data-ttu-id="46316-106">Käynnistimien avulla voit luoda pilven työnkulkuja ja automatisoida toistuvia tehtäviä, kuten ilmoituksia tai lisätoimintoja.</span><span class="sxs-lookup"><span data-stu-id="46316-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="46316-107">Käynnistin, kun tietolähteen päivitys epäonnistuu.</span><span class="sxs-lookup"><span data-stu-id="46316-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="46316-108">Käynnistin, kun tietolähteen päivitys onnistuu.</span><span class="sxs-lookup"><span data-stu-id="46316-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="46316-109">Käynnistin, kun segmentin raja ylitetään.</span><span class="sxs-lookup"><span data-stu-id="46316-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="46316-110">Käynnistin rajoittuu rajan yläpuolen ylittämiseen.</span><span class="sxs-lookup"><span data-stu-id="46316-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="46316-111">Käynnistin, kun segmentin raja ylitetään liiketoiminnan mittarilla.</span><span class="sxs-lookup"><span data-stu-id="46316-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="46316-112">Vain liiketoimintamittareita, joilla ei ole dimensiota, tuetaan.</span><span class="sxs-lookup"><span data-stu-id="46316-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="46316-113">Käynnistin rajoittuu rajan yläpuolen ylittämiseen.</span><span class="sxs-lookup"><span data-stu-id="46316-113">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="46316-114">Käynnistä, kun kohteen (esimerkiksi tietolähteet, segmentit tai mittarit) täysi päivitys on valmis.</span><span class="sxs-lookup"><span data-stu-id="46316-114">Trigger when a full refresh of (data sources, segments, measures, ...) is completed.</span></span>
- <span data-ttu-id="46316-115">Käynnistä, kun yhdistämisprosessi (eri yhdistämisvaihtoehdot) on valmis.</span><span class="sxs-lookup"><span data-stu-id="46316-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

[<span data-ttu-id="46316-116">Määritä käynnistimet Power Automatessa.</span><span class="sxs-lookup"><span data-stu-id="46316-116">Configure your triggers in Power Automate.</span></span>](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a><span data-ttu-id="46316-117">Power Automate -toiminnot</span><span class="sxs-lookup"><span data-stu-id="46316-117">Power Automate actions</span></span>

<span data-ttu-id="46316-118">Power Automate -yhdistin määrittää muut toiminnot kuin käytettävissä olevat käynnistimet.</span><span class="sxs-lookup"><span data-stu-id="46316-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="46316-119">Lisätietoja on julkaisussa [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="46316-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="46316-120">Power Automaten työnkulun luominen</span><span class="sxs-lookup"><span data-stu-id="46316-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="46316-121">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="46316-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="46316-122">Valitse **Power Automate** -ruudussa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="46316-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="46316-123">Näyttöön avautuu Customer Insightsin yhdistin (esimatselu) Power Automatessa.</span><span class="sxs-lookup"><span data-stu-id="46316-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="46316-124">**Kirjaudu** Power Automateiin.</span><span class="sxs-lookup"><span data-stu-id="46316-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="46316-125">Valitse jokin käytettävissä olevista käynnistimistä ja lisää vaiheita uuteen työnkulkuun.</span><span class="sxs-lookup"><span data-stu-id="46316-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="46316-126">Lisätietoja on kohdassa [Pilven työnkulun luominen Power Automatessa](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="46316-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="46316-127">Seuraavassa on esimerkkejä työnkulkujen käytöstä:</span><span class="sxs-lookup"><span data-stu-id="46316-127">Examples of how to use flows:</span></span> 
- <span data-ttu-id="46316-128">Julkaise viesti Microsoft Teams -kanavassa, jos tietolähteen päivitys epäonnistuu.</span><span class="sxs-lookup"><span data-stu-id="46316-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="46316-129">Lähetä sähköpostia tietojen omistajille, kun segmentin raja-arvo ylittyy.</span><span class="sxs-lookup"><span data-stu-id="46316-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
