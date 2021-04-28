---
title: Customer Insights -tietojen vienti Dynamics 365 Salesiin
description: Tietoja yhteyden määrittämisestä ja viennistä Dynamics 365 Salesiin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759587"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="6080f-103">Käytä segmenttejä Dynamics 365 Salesissa (esiversio)</span><span class="sxs-lookup"><span data-stu-id="6080f-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="6080f-104">Asiakastietojen avulla voit luoda markkinointiluetteloita, seurata työnkulkuja ja lähettää kampanjoita Dynamics 365 Salesin avulla.</span><span class="sxs-lookup"><span data-stu-id="6080f-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="6080f-105">Yhteyden edellytys</span><span class="sxs-lookup"><span data-stu-id="6080f-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="6080f-106">Dynamics 365 Salesissa on oltava yhteyshenkiötietueita, ennen kuin voit viedä segmentin Customer Insightsista Salesiin.</span><span class="sxs-lookup"><span data-stu-id="6080f-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="6080f-107">Lisätietoja yhteyshenkilöiden käyttämisestä [Dynamics 365 Salesissa Common Data Servicesin avulla](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="6080f-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="6080f-108">Segmenttien vieminen käyttäjäryhmän tiedoista Salesiin ei luo Sales-esiintymiin uusia yhteyshenkilötietueita.</span><span class="sxs-lookup"><span data-stu-id="6080f-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="6080f-109">Salesin yhteyshenkilötietueet on käsiteltävä käyttäjäryhmän tiedoissa, ja niitä on käytettävä tietolähteenä.</span><span class="sxs-lookup"><span data-stu-id="6080f-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="6080f-110">Ne on myös sisällytettävä yhdistettyyn asiakasentiteettiin, jotta asiakastunnukset voidaan yhdistää yhteyshenkilötunnuksiin ennen segmenttien viemistä.</span><span class="sxs-lookup"><span data-stu-id="6080f-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="6080f-111">Määritä yhteys Salesiin</span><span class="sxs-lookup"><span data-stu-id="6080f-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="6080f-112">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="6080f-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6080f-113">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Dynamics 365 Sales**.</span><span class="sxs-lookup"><span data-stu-id="6080f-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="6080f-114">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="6080f-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6080f-115">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="6080f-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6080f-116">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="6080f-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6080f-117">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="6080f-117">Choose who can use this connection.</span></span> <span data-ttu-id="6080f-118">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="6080f-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6080f-119">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6080f-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6080f-120">Syötä organisaatiosi Sales-URL-osoite **Palvelinosoite**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="6080f-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="6080f-121">Valitse **Palvelimen järjestelmänvalvojan tili** -osassa **Kirjaudu sisään** ja valitse sitten Dynamics 365 Sales -tili.</span><span class="sxs-lookup"><span data-stu-id="6080f-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="6080f-122">Yhdistä asiakastunnuskenttä Dynamics 365 -yhteyshenkilön tunnukseen.</span><span class="sxs-lookup"><span data-stu-id="6080f-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="6080f-123">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="6080f-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="6080f-124">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="6080f-124">Configure an export</span></span>

<span data-ttu-id="6080f-125">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="6080f-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6080f-126">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6080f-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6080f-127">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="6080f-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6080f-128">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="6080f-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6080f-129">Valitse **Yhteys vientiä varten** -kentässä yhteys Dynamics 365 Sales -osasta.</span><span class="sxs-lookup"><span data-stu-id="6080f-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="6080f-130">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="6080f-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6080f-131">Valitse vähintään yksi segmentti.</span><span class="sxs-lookup"><span data-stu-id="6080f-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="6080f-132">Valitse **Tallenna**</span><span class="sxs-lookup"><span data-stu-id="6080f-132">Select **Save**</span></span>

<span data-ttu-id="6080f-133">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="6080f-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6080f-134">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="6080f-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6080f-135">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6080f-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
