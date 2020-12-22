---
title: Customer Insights -tietojen vienti Dynamics 365 Marketingiin
description: Tutustu Dynamics 365 Marketing -yhteyden määrittämiseen.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643769"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="8b1ad-103">Dynamics 365 Marketingin yhdistin (esikatselu)</span><span class="sxs-lookup"><span data-stu-id="8b1ad-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8b1ad-104">Luo [segmenttien](segments.md) avulla kampanjoita ja ota yhteyttä tiettyihin asiakasryhmiin Dynamics 365 Marketingin avulla.</span><span class="sxs-lookup"><span data-stu-id="8b1ad-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="8b1ad-105">Lisätietoja on kohdassa [Dynamics 365 Customer Insightsin segmenttien käyttäminen Dynamics 365 Marketingin kanssa](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="8b1ad-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="8b1ad-106">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="8b1ad-106">Prerequisite</span></span>

<span data-ttu-id="8b1ad-107">[Common Data Servicea käyttäneet Dynamics 365 Marketingin](connect-power-query.md) yhteyshenkilötietueet</span><span class="sxs-lookup"><span data-stu-id="8b1ad-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="8b1ad-108">Määritä Marketingin yhdistin</span><span class="sxs-lookup"><span data-stu-id="8b1ad-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="8b1ad-109">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="8b1ad-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8b1ad-110">Valitse **Dynamics 365 Marketing** -kohdassa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="8b1ad-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="8b1ad-111">Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="8b1ad-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8b1ad-112">Syötä organisaatiosi Marketing-URL-osoite **Palvelinosoite**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="8b1ad-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="8b1ad-113">Valitse **Palvelimen järjestelmänvalvojan tili** -osassa **Kirjaudu sisään** ja valitse sitten Dynamics 365 Marketing -tili.</span><span class="sxs-lookup"><span data-stu-id="8b1ad-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="8b1ad-114">Yhdistä asiakastunnuskenttä Dynamics 365 -yhteyshenkilön tunnukseen.</span><span class="sxs-lookup"><span data-stu-id="8b1ad-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="8b1ad-115">Valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="8b1ad-115">Select **Next**.</span></span>

1. <span data-ttu-id="8b1ad-116">Valitse vähintään yksi segmentti.</span><span class="sxs-lookup"><span data-stu-id="8b1ad-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="8b1ad-117">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="8b1ad-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8b1ad-118">Tietojen vieminen</span><span class="sxs-lookup"><span data-stu-id="8b1ad-118">Export the data</span></span>

<span data-ttu-id="8b1ad-119">Voit [viedä tietoja tarvittaessa](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8b1ad-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8b1ad-120">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="8b1ad-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
