---
title: Power Automate -yhdistin | Microsoft Docs
description: Luo työnkulkuja Microsoft Power Automatessa Dynamics 365 Customer Insightsista.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405579"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="388ad-103">Power Automate -yhdistin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="388ad-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="388ad-104">Käynnistä tietyt tapahtumat automaattisesti, kun tiedot muuttuvat ja hallitse monimutkaisempia työnkulkuja suoraan [Power Automatessa](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="388ad-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="388ad-105">Power Automaten käynnistimet</span><span class="sxs-lookup"><span data-stu-id="388ad-105">Power Automate triggers</span></span>

<span data-ttu-id="388ad-106">Voit käyttää erilaisia käynnistimiä, joiden avulla voit luoda työnkulkuja toistuvien tehtävien, kuten ilmoitusten tai edistyneiden toimintojen, automatisoimiseksi.</span><span class="sxs-lookup"><span data-stu-id="388ad-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="388ad-107">Käynnistin, kun tietolähteen päivitys epäonnistuu.</span><span class="sxs-lookup"><span data-stu-id="388ad-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="388ad-108">Käynnistin, kun tietolähteen päivitys onnistuu.</span><span class="sxs-lookup"><span data-stu-id="388ad-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="388ad-109">Käynnistin, kun segmentin raja ylitetään.</span><span class="sxs-lookup"><span data-stu-id="388ad-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="388ad-110">Käynnistin rajoittuu rajan yläpuolen ylittämiseen.</span><span class="sxs-lookup"><span data-stu-id="388ad-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="388ad-111">Käynnistin, kun segmentin raja ylitetään liiketoiminnan mittarilla.</span><span class="sxs-lookup"><span data-stu-id="388ad-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="388ad-112">Käynnistin rajoittuu rajan yläpuolen ylittämiseen.</span><span class="sxs-lookup"><span data-stu-id="388ad-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="388ad-113">Käynnistä, kun (tietolähteiden, segmenttien, mittojen,...) täysi päivitys on valmis.</span><span class="sxs-lookup"><span data-stu-id="388ad-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="388ad-114">Käynnistä, kun yhdistämisprosessi (eri yhdistämisvaihtoehdot) on valmis.</span><span class="sxs-lookup"><span data-stu-id="388ad-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="388ad-115">[Käynnistimien määrittäminen Power Automatessa](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="388ad-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="388ad-116">Power Automate -toiminnot</span><span class="sxs-lookup"><span data-stu-id="388ad-116">Power Automate actions</span></span>
<span data-ttu-id="388ad-117">Power Automate -yhdistin määrittää muut toiminnot kuin käytettävissä olevat käynnistimet.</span><span class="sxs-lookup"><span data-stu-id="388ad-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="388ad-118">Lisätietoja on julkaisussa [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="388ad-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="388ad-119">Power Automaten työnkulun luominen käyttäjäryhmän merkityksellisissä tiedoissa</span><span class="sxs-lookup"><span data-stu-id="388ad-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="388ad-120">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Järjestelmä**.</span><span class="sxs-lookup"><span data-stu-id="388ad-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="388ad-121">Valitse **Järjestelmä**-sivulla **Tila**-välilehti.</span><span class="sxs-lookup"><span data-stu-id="388ad-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="388ad-122">Valitse **Tietolähteet**-kohdassa **Työnkulut** ja valitse sitten avattavasta luettelosta **Luo työnkulku**.</span><span class="sxs-lookup"><span data-stu-id="388ad-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="388ad-123">![Power Automate -yhdistin, jossa näkyy Luo työnkulku -toiminto](media/power-automate-connector-create-flow.png "Power Automate -yhdistin, jossa näkyy Luo työnkulku -toiminto")</span><span class="sxs-lookup"><span data-stu-id="388ad-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="388ad-124">Luo haluamasi työnkulku Power Automatessa valitsemalla jokin käytettävissä olevista käynnistimistä.</span><span class="sxs-lookup"><span data-stu-id="388ad-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="388ad-125">Jos olet luomassa ensimmäistä työnkulkua, Power Automate -yhdistin on ensin todennettava.</span><span class="sxs-lookup"><span data-stu-id="388ad-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
