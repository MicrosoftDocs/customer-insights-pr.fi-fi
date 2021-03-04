---
title: Customer Insights -tietojen vienti Dynamics 365 Salesiin
description: Tutustu Dynamics 365 Sales -yhteyden määrittämiseen.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269004"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="1069c-103">Dynamics 365 Salesin yhdistin (esikatselu)</span><span class="sxs-lookup"><span data-stu-id="1069c-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="1069c-104">Asiakastietojen avulla voit luoda markkinointiluetteloita, seurata työnkulkuja ja lähettää kampanjoita Dynamics 365 Salesin avulla.</span><span class="sxs-lookup"><span data-stu-id="1069c-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="1069c-105">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="1069c-105">Prerequisite</span></span>

1. <span data-ttu-id="1069c-106">Dynamics 365 Salesissa on oltava yhteyshenkiötietueita, ennen kuin voit viedä segmentin Customer Insightsista Salesiin.</span><span class="sxs-lookup"><span data-stu-id="1069c-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="1069c-107">Lisätietoja yhteyshenkilöiden käyttämisestä [Dynamics 365 Salesissa Common Data Servicesin avulla](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="1069c-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="1069c-108">Segmenttien vieminen käyttäjäryhmän tiedoista Salesiin ei luo Sales-esiintymiin uusia yhteyshenkilötietueita.</span><span class="sxs-lookup"><span data-stu-id="1069c-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="1069c-109">Salesin yhteyshenkilötietueet on käsiteltävä käyttäjäryhmän tiedoissa, ja niitä on käytettävä tietolähteenä.</span><span class="sxs-lookup"><span data-stu-id="1069c-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="1069c-110">Ne on myös sisällytettävä yhdistettyyn asiakasentiteettiin, jotta asiakastunnukset voidaan yhdistää yhteyshenkilötunnuksiin ennen segmenttien viemistä.</span><span class="sxs-lookup"><span data-stu-id="1069c-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="1069c-111">Määritä Salesin yhdistin</span><span class="sxs-lookup"><span data-stu-id="1069c-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="1069c-112">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="1069c-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1069c-113">Valitse **Dynamics 365 Sales** -kohdassa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="1069c-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="1069c-114">Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="1069c-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="1069c-115">Syötä organisaatiosi Sales-URL-osoite **Palvelinosoite**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="1069c-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="1069c-116">Valitse **Palvelimen järjestelmänvalvojan tili** -osassa **Kirjaudu sisään** ja valitse sitten Dynamics 365 Sales -tili.</span><span class="sxs-lookup"><span data-stu-id="1069c-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="1069c-117">Yhdistä asiakastunnuskenttä Dynamics 365 -yhteyshenkilön tunnukseen.</span><span class="sxs-lookup"><span data-stu-id="1069c-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="1069c-118">Valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="1069c-118">Select **Next**.</span></span>

1. <span data-ttu-id="1069c-119">Valitse vähintään yksi segmentti.</span><span class="sxs-lookup"><span data-stu-id="1069c-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="1069c-120">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="1069c-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="1069c-121">Tietojen vieminen</span><span class="sxs-lookup"><span data-stu-id="1069c-121">Export the data</span></span>

<span data-ttu-id="1069c-122">Voit [viedä tietoja tarvittaessa](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="1069c-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="1069c-123">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="1069c-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]