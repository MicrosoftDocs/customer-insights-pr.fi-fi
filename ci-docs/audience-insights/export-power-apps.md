---
title: Power Apps -yhdistin
description: Power Appsin ja Power Automaten yhdistäminen.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598151"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="161f8-103">Microsoft Power Apps -yhdistin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="161f8-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="161f8-104">Tuo yhdistetyt asiakasprofiilit mukautettuihin sovelluksiiin Power Appsin avulla.</span><span class="sxs-lookup"><span data-stu-id="161f8-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="161f8-105">Power Appsin ja Dynamics 365 Customer Insights -ratkaisun yhdistäminen</span><span class="sxs-lookup"><span data-stu-id="161f8-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="161f8-106">Customer Insights on yksi monista [käytettävissä olevista tietolähteistä Power Appsissa ](/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="161f8-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="161f8-107">Katso Power Apps -dokumentaatiosta, miten voit [lisätä tietoyhteyden sovellukseen](/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="161f8-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="161f8-108">Lisäksi kannattaa tutustua siihen, [miten Power Apps käsittelee delegoinnin avulla suuria tietojoukkoja pohjaan perustuvissa sovelluksissa](/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="161f8-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="161f8-109">Käytettävissä olevat entiteetit</span><span class="sxs-lookup"><span data-stu-id="161f8-109">Available entities</span></span>

<span data-ttu-id="161f8-110">Kun Customer Insights on lisätty tietoyhteydeksi, voit valita seuraavat entiteetit Power Appsissa:</span><span class="sxs-lookup"><span data-stu-id="161f8-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="161f8-111">Asiakas: tietojen käyttäminen [yhdistetystä asiakasprofiilista](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="161f8-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="161f8-112">UnifiedActivity: [aktiviteetin aikajanan](activities.md) näyttäminen sovelluksessa.</span><span class="sxs-lookup"><span data-stu-id="161f8-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="161f8-113">Rajoitukset</span><span class="sxs-lookup"><span data-stu-id="161f8-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="161f8-114">Noudettavissa olevat entiteetit</span><span class="sxs-lookup"><span data-stu-id="161f8-114">Retrievable entities</span></span>

<span data-ttu-id="161f8-115">Power Apps-yhdistimen kautta voi noutaa vain entiteettejä **Asiakas**, **UnifiedActivity** ja **Segmentit**.</span><span class="sxs-lookup"><span data-stu-id="161f8-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="161f8-116">Muita entiteettejä näkyy, koska taustalla oleva yhdistin tukee niitä Power Automatessa olevien käynnistimien kautta.</span><span class="sxs-lookup"><span data-stu-id="161f8-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="161f8-117">Delegointi</span><span class="sxs-lookup"><span data-stu-id="161f8-117">Delegation</span></span>

<span data-ttu-id="161f8-118">Delegointi toimii Asiakas-entiteetin ja UnifiedActivity-entiteetin osalta.</span><span class="sxs-lookup"><span data-stu-id="161f8-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="161f8-119">**Asiakas**-entiteetin delegointi: tämän entiteetin delegoinnin käyttö edellyttää, että kentät on indeksoitava [Hae ja suodata indeksi](search-filter-index.md) -kohdassa.</span><span class="sxs-lookup"><span data-stu-id="161f8-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="161f8-120">**UnifiedActivity**-entiteetin delegointi: Tämän enditeeetin delegointi toimii vain kenttien **ActivityId** ja **CustomerId** osalta.</span><span class="sxs-lookup"><span data-stu-id="161f8-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="161f8-121">Lisätietoja delegoinnista: [Power Appsin delegoitavat funktiot ja toiminnot](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="161f8-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="161f8-122">Esimerkki galleria-ohjausobjektista</span><span class="sxs-lookup"><span data-stu-id="161f8-122">Example gallery control</span></span>

<span data-ttu-id="161f8-123">Asiakasprofiileja voi lisätä esimerkiksi [valikoiman ohjausobjektissa](/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="161f8-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="161f8-124">Lisää **Galleria**-ohjausobjekti sovellukseen, jota olet rakentamassa.</span><span class="sxs-lookup"><span data-stu-id="161f8-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="161f8-125">![Lisää valikoimaelementti](media/connector-powerapps9.png "Lisää valikoimaelementti")</span><span class="sxs-lookup"><span data-stu-id="161f8-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="161f8-126">Valitse **Asiakas** nimikkeiden tietolähteeksi.</span><span class="sxs-lookup"><span data-stu-id="161f8-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="161f8-127">![Valitse tietolähde](media/choose-datasource-powerapps.png "Valitse tietolähde")</span><span class="sxs-lookup"><span data-stu-id="161f8-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="161f8-128">Voit muuttaa tietopaneelia oikealla, jos haluat määrittää asiakasentiteetin valikoimassa näytettävän kentän.</span><span class="sxs-lookup"><span data-stu-id="161f8-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="161f8-129">Jos haluat näyttää jonkin valitun asiakkaan kentän valikoimassa, täytä selitteen tekstiominaisuus: **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="161f8-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="161f8-130">Esimerkki: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="161f8-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="161f8-131">Jos haluat näyttää asiakkaan yhdistetyn aikajanan, lisää valikoimaelementti ja lisää sitten nimikkeiden ominaisuus: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="161f8-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="161f8-132">Esimerkki: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="161f8-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]