---
title: Power Automate -yhdistin | Microsoft Docs
description: Työnkulkujen luominen Microsoft Power Automatessa Dynamics 365 Customer Insightsista.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597921"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="3ccab-103">Power Automate -yhdistin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="3ccab-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="3ccab-104">Käynnistä tietyt tapahtumat automaattisesti, kun tiedot muuttuvat ja hallitse monimutkaisempia työnkulkuja suoraan [Power Automatessa](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="3ccab-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="3ccab-105">Power Automaten käynnistimet</span><span class="sxs-lookup"><span data-stu-id="3ccab-105">Power Automate triggers</span></span>

<span data-ttu-id="3ccab-106">Käynnistimien avulla voit luoda pilven työnkulkuja ja automatisoida toistuvia tehtäviä, kuten ilmoituksia tai lisätoimintoja.</span><span class="sxs-lookup"><span data-stu-id="3ccab-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="3ccab-107">Käynnistin, kun tietolähteen päivitys epäonnistuu.</span><span class="sxs-lookup"><span data-stu-id="3ccab-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="3ccab-108">Käynnistin, kun tietolähteen päivitys onnistuu.</span><span class="sxs-lookup"><span data-stu-id="3ccab-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="3ccab-109">Käynnistin, kun segmentin raja ylitetään.</span><span class="sxs-lookup"><span data-stu-id="3ccab-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="3ccab-110">Käynnistin rajoittuu rajan yläpuolen ylittämiseen.</span><span class="sxs-lookup"><span data-stu-id="3ccab-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="3ccab-111">Käynnistin, kun segmentin raja ylitetään liiketoiminnan mittarilla.</span><span class="sxs-lookup"><span data-stu-id="3ccab-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="3ccab-112">Käynnistin rajoittuu rajan yläpuolen ylittämiseen.</span><span class="sxs-lookup"><span data-stu-id="3ccab-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="3ccab-113">Käynnistä, kun (tietolähteiden, segmenttien, mittojen,...) täysi päivitys on valmis.</span><span class="sxs-lookup"><span data-stu-id="3ccab-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="3ccab-114">Käynnistä, kun yhdistämisprosessi (eri yhdistämisvaihtoehdot) on valmis.</span><span class="sxs-lookup"><span data-stu-id="3ccab-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="3ccab-115">[Käynnistimien määrittäminen Power Automatessa](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="3ccab-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="3ccab-116">Power Automate -toiminnot</span><span class="sxs-lookup"><span data-stu-id="3ccab-116">Power Automate actions</span></span>
<span data-ttu-id="3ccab-117">Power Automate -yhdistin määrittää muut toiminnot kuin käytettävissä olevat käynnistimet.</span><span class="sxs-lookup"><span data-stu-id="3ccab-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="3ccab-118">Lisätietoja on julkaisussa [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="3ccab-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="3ccab-119">Power Automaten työnkulun luominen</span><span class="sxs-lookup"><span data-stu-id="3ccab-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="3ccab-120">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="3ccab-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3ccab-121">Valitse **Power Automate** -ruudussa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="3ccab-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="3ccab-122">Näyttöön avautuu Customer Insightsin yhdistin (esimatselu) Power Automatessa.</span><span class="sxs-lookup"><span data-stu-id="3ccab-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="3ccab-123">**Kirjaudu** Power Automateiin.</span><span class="sxs-lookup"><span data-stu-id="3ccab-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="3ccab-124">Valitse jokin käytettävissä olevista käynnistimistä ja lisää vaiheita uuteen työnkulkuun.</span><span class="sxs-lookup"><span data-stu-id="3ccab-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="3ccab-125">Lisätietoja on kohdassa [Pilven työnkulun luominen Power Automatessa](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="3ccab-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="3ccab-126">Seuraavassa on esimerkkejä työnkulkujen käytöstä:</span><span class="sxs-lookup"><span data-stu-id="3ccab-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="3ccab-127">Julkaise viesti Microsoft Teams -kanavassa, jos tietolähteen päivitys epäonnistuu.</span><span class="sxs-lookup"><span data-stu-id="3ccab-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="3ccab-128">Lähetä sähköpostia tietojen omistajille, kun segmentin raja-arvo ylittyy.</span><span class="sxs-lookup"><span data-stu-id="3ccab-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]