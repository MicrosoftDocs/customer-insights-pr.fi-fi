---
title: Customer Insights -tietojen vieminen Azure Blob Storage -säilöön
description: Tietoja yhteyden määrittämisestä ja viennistä Blob-säilöön.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976130"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="b61e4-103">Segmenttiluettelon ja muiden tietojen vieminen Azure Blob Storage -säilöön (esiversio)</span><span class="sxs-lookup"><span data-stu-id="b61e4-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="b61e4-104">Tallenna Customer Insights -tietosi Blob-säilöön, tai käytä sitä tietojesi siirtämiseen muihin sovelluksiin.</span><span class="sxs-lookup"><span data-stu-id="b61e4-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="b61e4-105">Määritä yhteys Blob-säilöön</span><span class="sxs-lookup"><span data-stu-id="b61e4-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="b61e4-106">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="b61e4-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b61e4-107">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Azure Blob Storage**.</span><span class="sxs-lookup"><span data-stu-id="b61e4-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="b61e4-108">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="b61e4-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b61e4-109">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="b61e4-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b61e4-110">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="b61e4-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b61e4-111">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="b61e4-111">Choose who can use this connection.</span></span> <span data-ttu-id="b61e4-112">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="b61e4-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b61e4-113">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b61e4-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b61e4-114">Anna **Tilin nimi**, **Tilin avain** ja **Säilö** Blob-tallennustilille.</span><span class="sxs-lookup"><span data-stu-id="b61e4-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="b61e4-115">Lisätietoja Blob-tallennustilatilin nimen ja tiliavaimen löytämisestä on ohjeaiheessa [Azure-portaalin tallennustilatilin asetusten hallinta](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="b61e4-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="b61e4-116">Lisätietoja säilön luomisesta on kohdassa [Säilön luominen](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="b61e4-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="b61e4-117">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="b61e4-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="b61e4-118">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="b61e4-118">Configure an export</span></span>

<span data-ttu-id="b61e4-119">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="b61e4-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b61e4-120">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b61e4-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b61e4-121">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="b61e4-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b61e4-122">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="b61e4-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b61e4-123">Valitse **Yhteys vientiä varten** -kentässä yhteys Azure Blob Storage -osasta.</span><span class="sxs-lookup"><span data-stu-id="b61e4-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="b61e4-124">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="b61e4-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b61e4-125">Valitse tähän kohteeseen vietävien entiteettien vieressä oleva valintaruutu.</span><span class="sxs-lookup"><span data-stu-id="b61e4-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="b61e4-126">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="b61e4-126">Select **Save**.</span></span>

<span data-ttu-id="b61e4-127">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="b61e4-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b61e4-128">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="b61e4-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="b61e4-129">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b61e4-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="b61e4-130">Viedyt tiedot tallennetaan määritettyyn Blob-tallennussäilöön.</span><span class="sxs-lookup"><span data-stu-id="b61e4-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="b61e4-131">Säilöön luodaan automaattisesti seuraavat kansiopolut:</span><span class="sxs-lookup"><span data-stu-id="b61e4-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="b61e4-132">Lähde-entiteetit ja järjestelmän luomat entiteetit: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="b61e4-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="b61e4-133">Esimerkki: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="b61e4-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="b61e4-134">Vietyjen entiteettien model.json-arvo on tasolla %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="b61e4-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="b61e4-135">Esimerkki: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="b61e4-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
