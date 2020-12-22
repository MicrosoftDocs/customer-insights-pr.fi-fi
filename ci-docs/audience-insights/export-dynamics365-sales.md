---
title: Customer Insights -tietojen vienti Dynamics 365 Salesiin
description: Tutustu Dynamics 365 Sales -yhteyden määrittämiseen.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643814"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="a9438-103">Dynamics 365 Salesin yhdistin (esikatselu)</span><span class="sxs-lookup"><span data-stu-id="a9438-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a9438-104">Asiakastietojen avulla voit luoda markkinointiluetteloita, seurata työnkulkuja ja lähettää kampanjoita Dynamics 365 Salesin avulla.</span><span class="sxs-lookup"><span data-stu-id="a9438-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="a9438-105">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="a9438-105">Prerequisite</span></span>

<span data-ttu-id="a9438-106">[Common Data Servicella käytetyt Dynamics 365 Salesin](connect-power-query.md) yhteyshenkilötietueet.</span><span class="sxs-lookup"><span data-stu-id="a9438-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="a9438-107">Määritä Salesin yhdistin</span><span class="sxs-lookup"><span data-stu-id="a9438-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="a9438-108">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="a9438-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a9438-109">Valitse **Dynamics 365 Sales** -kohdassa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="a9438-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="a9438-110">Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="a9438-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a9438-111">Syötä organisaatiosi Sales-URL-osoite **Palvelinosoite**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="a9438-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="a9438-112">Valitse **Palvelimen järjestelmänvalvojan tili** -osassa **Kirjaudu sisään** ja valitse sitten Dynamics 365 Sales -tili.</span><span class="sxs-lookup"><span data-stu-id="a9438-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="a9438-113">Yhdistä asiakastunnuskenttä Dynamics 365 -yhteyshenkilön tunnukseen.</span><span class="sxs-lookup"><span data-stu-id="a9438-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="a9438-114">Valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="a9438-114">Select **Next**.</span></span>

1. <span data-ttu-id="a9438-115">Valitse vähintään yksi segmentti.</span><span class="sxs-lookup"><span data-stu-id="a9438-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="a9438-116">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="a9438-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a9438-117">Tietojen vieminen</span><span class="sxs-lookup"><span data-stu-id="a9438-117">Export the data</span></span>

<span data-ttu-id="a9438-118">Voit [viedä tietoja tarvittaessa](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a9438-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a9438-119">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="a9438-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
