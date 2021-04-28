---
title: Customer Insightsin tietojen vieminen Azure Data Lake Storage Gen2:een
description: Tietoja yhteyden määrittämisestä Azure Data Lake Storage Gen2:een.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760047"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="d0c63-103">Määritä yhteys Azure Data Lake Storage Gen2 -säilöön (esiversio)</span><span class="sxs-lookup"><span data-stu-id="d0c63-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="d0c63-104">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="d0c63-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d0c63-105">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Azure Data Lake Gen 2**.</span><span class="sxs-lookup"><span data-stu-id="d0c63-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="d0c63-106">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="d0c63-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d0c63-107">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="d0c63-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d0c63-108">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="d0c63-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d0c63-109">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="d0c63-109">Choose who can use this connection.</span></span> <span data-ttu-id="d0c63-110">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="d0c63-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d0c63-111">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d0c63-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d0c63-112">Anna Azure Data Lake Storage Gen2:lle **tilin nimi**, **tilin avain** ja **säilö**.</span><span class="sxs-lookup"><span data-stu-id="d0c63-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="d0c63-113">Lisätietoja tallennustilin luomisesta Azure Data Lake Storage Gen2:ssa on kohdassa [Tallennustilin luominen](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="d0c63-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="d0c63-114">Lisätietoja Azure Data Lake Gen 2 -tallennustilatilin nimestä ja tiliavaimesta on ohjeaiheessa [Azure-portaalin tallennustilatilin asetusten hallinta](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="d0c63-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="d0c63-115">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="d0c63-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="d0c63-116">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="d0c63-116">Configure an export</span></span>

<span data-ttu-id="d0c63-117">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="d0c63-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d0c63-118">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d0c63-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d0c63-119">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="d0c63-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d0c63-120">Luo uusi vienti valitsemalla **Lisää vienti**.</span><span class="sxs-lookup"><span data-stu-id="d0c63-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="d0c63-121">Valitse **Yhteys vientiä varten** -kentässä yhteys **Azure Data Lake** -osasta.</span><span class="sxs-lookup"><span data-stu-id="d0c63-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="d0c63-122">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="d0c63-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d0c63-123">Valitse tähän kohteeseen vietävien entiteettien vieressä oleva valintaruutu.</span><span class="sxs-lookup"><span data-stu-id="d0c63-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="d0c63-124">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="d0c63-124">Select **Save**.</span></span>

<span data-ttu-id="d0c63-125">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="d0c63-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d0c63-126">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="d0c63-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d0c63-127">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d0c63-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="d0c63-128">Viedyt tiedot tallennetaan määritettyyn Azure Data Lake Gen 2 -tallennussäilöön.</span><span class="sxs-lookup"><span data-stu-id="d0c63-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
