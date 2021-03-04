---
title: Customer Insights -tietojen vienti Dynamics 365 Marketingiin
description: Tutustu Dynamics 365 Marketing -yhteyden määrittämiseen.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269050"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="ec856-103">Dynamics 365 Marketingin yhdistin (esikatselu)</span><span class="sxs-lookup"><span data-stu-id="ec856-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ec856-104">Luo [segmenttien](segments.md) avulla kampanjoita ja ota yhteyttä tiettyihin asiakasryhmiin Dynamics 365 Marketingin avulla.</span><span class="sxs-lookup"><span data-stu-id="ec856-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="ec856-105">Lisätietoja on kohdassa [Dynamics 365 Customer Insightsin segmenttien käyttäminen Dynamics 365 Marketingin kanssa](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="ec856-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="ec856-106">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="ec856-106">Prerequisite</span></span>

- <span data-ttu-id="ec856-107">Yhteyshenkilötietueiden on oltava Dynamics 365 Marketingissa, ennen kuin segmentti voidaan viedä Customer Insightsista Marketingiin.</span><span class="sxs-lookup"><span data-stu-id="ec856-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="ec856-108">Lisätietoja yhteyshenkilöiden käyttämisestä [Dynamics 365 Marketingissa Common Data Servicesin avulla](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="ec856-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="ec856-109">Segmenttien vieminen käyttäjäryhmän tiedoista Marketingiin ei luo Marketing-esiintymiin uusia yhteyshenkilötietueita.</span><span class="sxs-lookup"><span data-stu-id="ec856-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="ec856-110">Marketingin yhteyshenkilötietueet on käsiteltävä käyttäjäryhmän tiedoissa, ja niitä on käytettävä tietolähteenä.</span><span class="sxs-lookup"><span data-stu-id="ec856-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="ec856-111">Ne on myös sisällytettävä yhdistettyyn asiakasentiteettiin, jotta asiakastunnukset voidaan yhdistää yhteyshenkilötunnuksiin ennen segmenttien viemistä.</span><span class="sxs-lookup"><span data-stu-id="ec856-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="ec856-112">Määritä Marketingin yhdistin</span><span class="sxs-lookup"><span data-stu-id="ec856-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="ec856-113">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="ec856-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ec856-114">Valitse **Dynamics 365 Marketing** -kohdassa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="ec856-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="ec856-115">Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="ec856-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ec856-116">Syötä organisaatiosi Marketing-URL-osoite **Palvelinosoite**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="ec856-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="ec856-117">Valitse **Palvelimen järjestelmänvalvojan tili** -osassa **Kirjaudu sisään** ja valitse sitten Dynamics 365 Marketing -tili.</span><span class="sxs-lookup"><span data-stu-id="ec856-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="ec856-118">Yhdistä asiakastunnuskenttä Dynamics 365 -yhteyshenkilön tunnukseen.</span><span class="sxs-lookup"><span data-stu-id="ec856-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="ec856-119">Valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="ec856-119">Select **Next**.</span></span>

1. <span data-ttu-id="ec856-120">Valitse vähintään yksi segmentti.</span><span class="sxs-lookup"><span data-stu-id="ec856-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="ec856-121">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="ec856-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ec856-122">Tietojen vieminen</span><span class="sxs-lookup"><span data-stu-id="ec856-122">Export the data</span></span>

<span data-ttu-id="ec856-123">Voit [viedä tietoja tarvittaessa](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ec856-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ec856-124">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="ec856-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]