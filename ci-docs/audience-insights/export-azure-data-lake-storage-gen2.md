---
title: Customer Insightsin tietojen vieminen Azure Data Lake Storage Gen2:een
description: Tietoja yhteyden määrittämisestä Azure Data Lake Storage Gen2:een.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477175"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="9d1fa-103">Azure Data Lake Storage Gen2 -yhdistin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="9d1fa-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="9d1fa-104">Tallenna Customer Insightsin tiedot Azure Data Lake Storage Gen2:een tai käytä sitä tietojesi siirtämiseen muihin sovelluksiin.</span><span class="sxs-lookup"><span data-stu-id="9d1fa-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="9d1fa-105">Azure Data Lake Storage Gen2 -yhdistimen määrittäminen</span><span class="sxs-lookup"><span data-stu-id="9d1fa-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="9d1fa-106">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="9d1fa-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9d1fa-107">Valitse **Azure Data Lake Storage Gen2** -kohdassa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="9d1fa-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="9d1fa-108">Anna kohteelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="9d1fa-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="9d1fa-109">Anna Azure Data Lake Storage Gen2:lle **tilin nimi**, **tilin avain** ja **säilö**.</span><span class="sxs-lookup"><span data-stu-id="9d1fa-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="9d1fa-110">Lisätietoja tallennustilin luomisesta Azure Data Lake Storage Gen2:ssa on kohdassa [Tallennustilin luominen](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="9d1fa-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="9d1fa-111">Lisätietoja Azure Data Lake Gen2:n tallennustilin nimestä ja tilin avaimesta on kohdassa [Azure-portaalin tallennustilin asetusten hallinta](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="9d1fa-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="9d1fa-112">Valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="9d1fa-112">Select **Next**.</span></span>

1. <span data-ttu-id="9d1fa-113">Valitse tähän kohteeseen vietävien entiteettien vieressä oleva valintaruutu.</span><span class="sxs-lookup"><span data-stu-id="9d1fa-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="9d1fa-114">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="9d1fa-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9d1fa-115">Tietojen vieminen</span><span class="sxs-lookup"><span data-stu-id="9d1fa-115">Export the data</span></span>

<span data-ttu-id="9d1fa-116">Voit [viedä tietoja tarvittaessa](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9d1fa-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="9d1fa-117">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="9d1fa-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
