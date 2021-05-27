---
title: Customer Insights -tietojen vienti Dynamics 365 Marketingiin
description: Tietoja yhteyden määrittämisestä ja viennistä Dynamics 365 Marketingiin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976796"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="e5d27-103">Käytä segmenttejä Dynamics 365 Marketingissa (esiversio)</span><span class="sxs-lookup"><span data-stu-id="e5d27-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e5d27-104">Luo [segmenttien](segments.md) avulla kampanjoita ja ota yhteyttä tiettyihin asiakasryhmiin Dynamics 365 Marketingin avulla.</span><span class="sxs-lookup"><span data-stu-id="e5d27-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="e5d27-105">Lisätietoja on kohdassa [Dynamics 365 Customer Insightsin segmenttien käyttäminen Dynamics 365 Marketingin kanssa](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="e5d27-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="e5d27-106">Yhteyden edellytykset</span><span class="sxs-lookup"><span data-stu-id="e5d27-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="e5d27-107">Yhteyshenkilötietueiden on oltava Dynamics 365 Marketingissa, ennen kuin segmentti voidaan viedä Customer Insightsista Marketingiin.</span><span class="sxs-lookup"><span data-stu-id="e5d27-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="e5d27-108">Lisätietoja yhteyshenkilöiden käyttämisestä [Dynamics 365 Marketingissa Common Data Servicesin avulla](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="e5d27-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="e5d27-109">Segmenttien vieminen käyttäjäryhmän tiedoista Marketingiin ei luo Marketing-esiintymiin uusia yhteyshenkilötietueita.</span><span class="sxs-lookup"><span data-stu-id="e5d27-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="e5d27-110">Marketingin yhteyshenkilötietueet on käsiteltävä käyttäjäryhmän tiedoissa, ja niitä on käytettävä tietolähteenä.</span><span class="sxs-lookup"><span data-stu-id="e5d27-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="e5d27-111">Ne on myös sisällytettävä yhdistettyyn asiakasentiteettiin, jotta asiakastunnukset voidaan yhdistää yhteyshenkilötunnuksiin ennen segmenttien viemistä.</span><span class="sxs-lookup"><span data-stu-id="e5d27-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="e5d27-112">Määritä yhteys Marketingiin</span><span class="sxs-lookup"><span data-stu-id="e5d27-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="e5d27-113">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="e5d27-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e5d27-114">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Dynamics 365 Marketing**.</span><span class="sxs-lookup"><span data-stu-id="e5d27-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="e5d27-115">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="e5d27-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e5d27-116">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="e5d27-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e5d27-117">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="e5d27-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e5d27-118">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="e5d27-118">Choose who can use this connection.</span></span> <span data-ttu-id="e5d27-119">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="e5d27-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e5d27-120">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e5d27-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e5d27-121">Syötä organisaatiosi Marketing-URL-osoite **Palvelinosoite**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="e5d27-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="e5d27-122">Valitse **Palvelimen järjestelmänvalvojan tili** -osassa **Kirjaudu sisään** ja valitse sitten Dynamics 365 Marketing -tili.</span><span class="sxs-lookup"><span data-stu-id="e5d27-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="e5d27-123">Yhdistä asiakastunnuskenttä Dynamics 365 -yhteyshenkilön tunnukseen.</span><span class="sxs-lookup"><span data-stu-id="e5d27-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="e5d27-124">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="e5d27-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="e5d27-125">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="e5d27-125">Configure an export</span></span>

<span data-ttu-id="e5d27-126">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="e5d27-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e5d27-127">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e5d27-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e5d27-128">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="e5d27-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e5d27-129">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="e5d27-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e5d27-130">Valitse **Yhteys vientiä varten** -kentässä yhteys Dynamics 365 Marketing -osasta.</span><span class="sxs-lookup"><span data-stu-id="e5d27-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="e5d27-131">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="e5d27-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e5d27-132">Valitse vähintään yksi segmentti.</span><span class="sxs-lookup"><span data-stu-id="e5d27-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="e5d27-133">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="e5d27-133">Select **Save**.</span></span>

<span data-ttu-id="e5d27-134">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="e5d27-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e5d27-135">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="e5d27-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e5d27-136">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e5d27-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
