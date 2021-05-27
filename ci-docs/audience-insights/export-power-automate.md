---
title: Power Automate -yhdistin | Microsoft Docs
description: Työnkulkujen luominen Microsoft Power Automatessa Dynamics 365 Customer Insightsista.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976084"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="92267-103">Power Automate -yhdistin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="92267-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="92267-104">Käynnistä tietyt tapahtumat automaattisesti, kun tiedot muuttuvat ja hallitse monimutkaisempia työnkulkuja suoraan [Power Automatessa](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="92267-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="92267-105">Power Automaten käynnistimet</span><span class="sxs-lookup"><span data-stu-id="92267-105">Power Automate triggers</span></span>

<span data-ttu-id="92267-106">Käynnistimien avulla voit luoda pilven työnkulkuja ja automatisoida toistuvia tehtäviä, kuten ilmoituksia tai lisätoimintoja.</span><span class="sxs-lookup"><span data-stu-id="92267-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="92267-107">Käynnistin, kun tietolähteen päivitys epäonnistuu.</span><span class="sxs-lookup"><span data-stu-id="92267-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="92267-108">Käynnistin, kun tietolähteen päivitys onnistuu.</span><span class="sxs-lookup"><span data-stu-id="92267-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="92267-109">Käynnistin, kun segmentin raja ylitetään.</span><span class="sxs-lookup"><span data-stu-id="92267-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="92267-110">Käynnistin rajoittuu rajan yläpuolen ylittämiseen.</span><span class="sxs-lookup"><span data-stu-id="92267-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="92267-111">Käynnistin, kun segmentin raja ylitetään liiketoiminnan mittarilla.</span><span class="sxs-lookup"><span data-stu-id="92267-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="92267-112">Vain liiketoimintamittareita, joilla ei ole dimensiota, tuetaan.</span><span class="sxs-lookup"><span data-stu-id="92267-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="92267-113">Käynnistin rajoittuu rajan yläpuolen ylittämiseen.</span><span class="sxs-lookup"><span data-stu-id="92267-113">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="92267-114">Käynnistä, kun (tietolähteiden, segmenttien, mittojen,...) täysi päivitys on valmis.</span><span class="sxs-lookup"><span data-stu-id="92267-114">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="92267-115">Käynnistä, kun yhdistämisprosessi (eri yhdistämisvaihtoehdot) on valmis.</span><span class="sxs-lookup"><span data-stu-id="92267-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="92267-116">[Käynnistimien määrittäminen Power Automatessa](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="92267-116">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="92267-117">Power Automate -toiminnot</span><span class="sxs-lookup"><span data-stu-id="92267-117">Power Automate actions</span></span>
<span data-ttu-id="92267-118">Power Automate -yhdistin määrittää muut toiminnot kuin käytettävissä olevat käynnistimet.</span><span class="sxs-lookup"><span data-stu-id="92267-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="92267-119">Lisätietoja on julkaisussa [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="92267-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="92267-120">Power Automaten työnkulun luominen</span><span class="sxs-lookup"><span data-stu-id="92267-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="92267-121">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="92267-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="92267-122">Valitse **Power Automate** -ruudussa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="92267-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="92267-123">Näyttöön avautuu Customer Insightsin yhdistin (esimatselu) Power Automatessa.</span><span class="sxs-lookup"><span data-stu-id="92267-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="92267-124">**Kirjaudu** Power Automateiin.</span><span class="sxs-lookup"><span data-stu-id="92267-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="92267-125">Valitse jokin käytettävissä olevista käynnistimistä ja lisää vaiheita uuteen työnkulkuun.</span><span class="sxs-lookup"><span data-stu-id="92267-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="92267-126">Lisätietoja on kohdassa [Pilven työnkulun luominen Power Automatessa](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="92267-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="92267-127">Seuraavassa on esimerkkejä työnkulkujen käytöstä:</span><span class="sxs-lookup"><span data-stu-id="92267-127">Examples how to use flows:</span></span> 
- <span data-ttu-id="92267-128">Julkaise viesti Microsoft Teams -kanavassa, jos tietolähteen päivitys epäonnistuu.</span><span class="sxs-lookup"><span data-stu-id="92267-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="92267-129">Lähetä sähköpostia tietojen omistajille, kun segmentin raja-arvo ylittyy.</span><span class="sxs-lookup"><span data-stu-id="92267-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
