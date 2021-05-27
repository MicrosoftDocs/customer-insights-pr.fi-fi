---
title: Customer Insights -tietojen vieminen Azure Synapse -analytiikkaan
description: Tietoja yhteyden määrittämisestä ja viennistä Azure Synapse -analytiikkaan.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977373"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="88fb2-103">Vie tietoja Azure Synapse -analytiikkaan (esiversio)</span><span class="sxs-lookup"><span data-stu-id="88fb2-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="88fb2-104">Azure Synapse on analytiikkapalvelu, joka nopeuttaa merkityksellisten tietojen saamista tietovarastoista ja massadatajärjestelmistä.</span><span class="sxs-lookup"><span data-stu-id="88fb2-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="88fb2-105">Voit käsitellä ja käyttää Customer Insights -tietojasi -sivustolla [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="88fb2-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="88fb2-106">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="88fb2-106">Prerequisites</span></span>

<span data-ttu-id="88fb2-107">Seuraavien edellytysten on täytyttävä, jotta yhteys Customer Insightsista Azure Synapseen voidaan määrittää.</span><span class="sxs-lookup"><span data-stu-id="88fb2-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="88fb2-108">Varmista, että määrität kaikki **roolimääritykset** kuvatulla tavalla.</span><span class="sxs-lookup"><span data-stu-id="88fb2-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="88fb2-109">Edellytykset Customer Insightsissa</span><span class="sxs-lookup"><span data-stu-id="88fb2-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="88fb2-110">Sinulla on  **Järjestelmänvalvoja**-rooli käyttäjäryhmän merkityksellisissä tiedoissa.</span><span class="sxs-lookup"><span data-stu-id="88fb2-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="88fb2-111">Lisätietoja [käyttöoikeuksien määrittämisestä käyttäjäryhmän merkityksellisissä tiedoissa](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="88fb2-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="88fb2-112">Azuressa:</span><span class="sxs-lookup"><span data-stu-id="88fb2-112">In Azure:</span></span> 

- <span data-ttu-id="88fb2-113">Aktiivinen Azure-tilaus.</span><span class="sxs-lookup"><span data-stu-id="88fb2-113">An active Azure subscription.</span></span>

- <span data-ttu-id="88fb2-114">Käytettäessä uutta Azure Data Lake Storage Gen2 tiliä, *käyttäjäryhmän merkityksellisten tietojen palvelun pää* tarvitsee **Storage Blob Data Contributor** -oikeudet.</span><span class="sxs-lookup"><span data-stu-id="88fb2-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="88fb2-115">Lue lisää [yhteyden muodostamisesta Azure Data Lake Storage Gen2- tiliin Azuren palvelun pään avulla käyttäjäryhmän merkityksellisillä tiedoilla](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="88fb2-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="88fb2-116">Data Lake Storage Gen2:ssa **on oltava käytössä** [hierarkkinen](/azure/storage/blobs/data-lake-storage-namespace) nimiavaruus.</span><span class="sxs-lookup"><span data-stu-id="88fb2-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="88fb2-117">Resurssiryhmässä, jossa Azure Synapse -työtila sijaitsee, *palvelun pää* ja *käyttäjäryhmän merkitykselliset tiedot* tarvitsevat vähintään **Lukija**-oikeudet.</span><span class="sxs-lookup"><span data-stu-id="88fb2-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="88fb2-118">Lisätietoja on kohdassa [Azure-roolien määrittäminen Azure-portaalin avulla](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="88fb2-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="88fb2-119">*Käyttäjä* tarvitsee **Storage Blob Data Contributor** -oikeudet Azure Data Lake Storage Gen2 -tilillä, jossa tiedot ovat ja josta ne on linkitetty Azure Synapse -työtilaan.</span><span class="sxs-lookup"><span data-stu-id="88fb2-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="88fb2-120">Lisätietoja [Azure-portaalin käyttämisestä Azure-roolin määrittämiseen blob- ja jonotiedoille](/azure/storage/common/storage-auth-aad-rbac-portal) sekä [Storage Blob Data Contributor -oikeuksista](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="88fb2-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="88fb2-121">*[Azure Synapse -työtilassa hallittu identiteetti](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* tarvitsee **Storage Blob Data Contributor** -oikeudet Azure Data Lake Storage Gen2 tilille, jossa tiedot ovat ja josta ne on linkitetty Azure Synapse -työtilaan.</span><span class="sxs-lookup"><span data-stu-id="88fb2-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="88fb2-122">Lisätietoja [Azure-portaalin käyttämisestä Azure-roolin määrittämiseen blob- ja jonotiedoille](/azure/storage/common/storage-auth-aad-rbac-portal) sekä [Storage Blob Data Contributor -oikeuksista](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="88fb2-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="88fb2-123">Azure Synapse-työtilassa *käyttäjäryhmän merkityksellisten tietojen pää* tarvitsee **Synapsen järjestelmänvalvoja** -roolin.</span><span class="sxs-lookup"><span data-stu-id="88fb2-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="88fb2-124">Lisätietoja on kohdassa [Käytönvalvonnan määrittäminen Synapse-työtilaa varten](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="88fb2-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="88fb2-125">Määritä yhteys ja vie Azure Synapseen</span><span class="sxs-lookup"><span data-stu-id="88fb2-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="88fb2-126">Yhteyden määrittäminen</span><span class="sxs-lookup"><span data-stu-id="88fb2-126">Configure a connection</span></span>

1. <span data-ttu-id="88fb2-127">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="88fb2-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="88fb2-128">Valitse **Lisää yhteys** ja valitse **Azure Synapse -analytiikka** tai valitse **Määritä** **Azure Synapse -analytiikka** -ruudussa yhteyden määrittämistä varten.</span><span class="sxs-lookup"><span data-stu-id="88fb2-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="88fb2-129">Anna yhteydelle tunnistettava nimi Näyttönimi-kentässä.</span><span class="sxs-lookup"><span data-stu-id="88fb2-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="88fb2-130">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="88fb2-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="88fb2-131">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="88fb2-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="88fb2-132">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="88fb2-132">Choose who can use this connection.</span></span> <span data-ttu-id="88fb2-133">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="88fb2-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="88fb2-134">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="88fb2-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="88fb2-135">Valitse tai etsi tilaus, jossa haluat käyttää Customer Insights -tietoja.</span><span class="sxs-lookup"><span data-stu-id="88fb2-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="88fb2-136">Kun tilaus on valittuna, voit myös valita **työtilan**, **tallennustilan tilin** ja **säilön**.</span><span class="sxs-lookup"><span data-stu-id="88fb2-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="88fb2-137">Tallenna yhteys valisemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="88fb2-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="88fb2-138">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="88fb2-138">Configure an export</span></span>

<span data-ttu-id="88fb2-139">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="88fb2-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="88fb2-140">Lisätietoja on aiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="88fb2-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="88fb2-141">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="88fb2-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="88fb2-142">Luo uusi vienti valitsemalla **Lisää vienti**.</span><span class="sxs-lookup"><span data-stu-id="88fb2-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="88fb2-143">Valitse **Yhteys vientiä varten** -kentässä yhteys **Azure Synapse -analytiikka** -osasta.</span><span class="sxs-lookup"><span data-stu-id="88fb2-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="88fb2-144">Jos et näe tämän osan nimeä, tämäntyyppisiä [yhteyksiä](connections.md) ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="88fb2-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="88fb2-145">Anna viennille tunnistettava **Näyttönimi** ja **Tietokannan nimi**.</span><span class="sxs-lookup"><span data-stu-id="88fb2-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="88fb2-146">Valitse Azure Synapse -analytiikkaan vietävät entiteetit.</span><span class="sxs-lookup"><span data-stu-id="88fb2-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="88fb2-147">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="88fb2-147">Select **Save**.</span></span>

<span data-ttu-id="88fb2-148">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="88fb2-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="88fb2-149">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="88fb2-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="88fb2-150">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="88fb2-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="88fb2-151">Viennin päivittäminen</span><span class="sxs-lookup"><span data-stu-id="88fb2-151">Update an export</span></span>

1. <span data-ttu-id="88fb2-152">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="88fb2-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="88fb2-153">Valitse **Muokkaa** viennille, jota haluat päivittää.</span><span class="sxs-lookup"><span data-stu-id="88fb2-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="88fb2-154">**Lisää** tai **Poista** entiteettejä valinnasta.</span><span class="sxs-lookup"><span data-stu-id="88fb2-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="88fb2-155">Jos entiteetit poistetaan valinnasta, niitä ei poisteta Synapse Analytics -tietokannasta.</span><span class="sxs-lookup"><span data-stu-id="88fb2-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="88fb2-156">Tulevat tietojen päivitykset eivät kuitenkaan päivitä tietokannan poistettuja entiteettejä.</span><span class="sxs-lookup"><span data-stu-id="88fb2-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="88fb2-157">**Tietokannan nimen muuttaminen** luo uuden Synapse Analytics -tietokannan.</span><span class="sxs-lookup"><span data-stu-id="88fb2-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="88fb2-158">Tietokanta, jonka nimi on määritetty aiemmin, ei saa päivityksiä tulevissa päivityksissä.</span><span class="sxs-lookup"><span data-stu-id="88fb2-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
