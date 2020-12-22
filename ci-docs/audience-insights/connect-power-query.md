---
title: Tietojen käyttäminen Power Query -yhdistimen avulla
description: Power Queryyn perustuvien tietolähteiden yhdistimet.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405603"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="046ec-103">Yhteyden muodostaminen Power Query -tietolähteeseen</span><span class="sxs-lookup"><span data-stu-id="046ec-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="046ec-104">Power Queryssä on laaja valikoima tietojen käsittelyyn tarkoitettuja yhdistimiä.</span><span class="sxs-lookup"><span data-stu-id="046ec-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="046ec-105">Dynamics 365 Customer Insights tukee suurinta osaa näistä yhdistimistä.</span><span class="sxs-lookup"><span data-stu-id="046ec-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="046ec-106">Power Query -yhdistimiin perustuvia tietolähteitä lisätään yleensä seuraavassa osassa kuvattujen vaiheiden mukaisesti.</span><span class="sxs-lookup"><span data-stu-id="046ec-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="046ec-107">Käytettävä yhdistin kuitenkin määrittää, mitä tietoja tarvitaan.</span><span class="sxs-lookup"><span data-stu-id="046ec-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="046ec-108">Lisätietoja yhdistinkohtaisista ohjeista on [Power Query -yhdistimien viitesivulla](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="046ec-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="046ec-109">Uuden tietolähteen luominen</span><span class="sxs-lookup"><span data-stu-id="046ec-109">Create a new data source</span></span>

1. <span data-ttu-id="046ec-110">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.</span><span class="sxs-lookup"><span data-stu-id="046ec-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="046ec-111">Valitse **Lisää tietolähde**.</span><span class="sxs-lookup"><span data-stu-id="046ec-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="046ec-112">Valitse **Tuo tiedot** -menetelmä ja valitse sitten **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="046ec-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="046ec-113">Anna tietolähteelle **nimi** ja luo tietolähde valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="046ec-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="046ec-114">Valitse jokin [käytettävissä olevista yhdistimistä](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="046ec-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="046ec-115">Tässä esimerkissä valitaan **Text/CSV**-yhdistin.</span><span class="sxs-lookup"><span data-stu-id="046ec-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="046ec-116">Anna valitun yhdistimen pakolliset tiedot **Yhteysasetukset**-kohdassa ja esikatsele tiedot valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="046ec-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="046ec-117">Valitse **Muunna tiedot**.</span><span class="sxs-lookup"><span data-stu-id="046ec-117">Select **Transform data**.</span></span> <span data-ttu-id="046ec-118">Tässä vaiheessa tietolähteisiin lisätään entiteettejä.</span><span class="sxs-lookup"><span data-stu-id="046ec-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="046ec-119">Entiteetit ovat tietojoukkoja.</span><span class="sxs-lookup"><span data-stu-id="046ec-119">Entities are datasets.</span></span> <span data-ttu-id="046ec-120">Jos tietokannassa on useita tietojoukkoja, kukin tietojoukko on oma entiteetti.</span><span class="sxs-lookup"><span data-stu-id="046ec-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="046ec-121">Voit tarkistaa tiedot ja tarkentaa niitä **Power Query – Muokkaa kyselyjä** -valintaikkunassa.</span><span class="sxs-lookup"><span data-stu-id="046ec-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="046ec-122">Vasemmassa ruudussa näkyvät ne entiteetit, jotka järjestelmät tunnistivat valitussa tietolähteessä.</span><span class="sxs-lookup"><span data-stu-id="046ec-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="046ec-123">![Muokkaa kyselyjä -ikkuna](media/data-manager-configure-edit-queries.png "Muokkaa kyselyjä -ikkuna")</span><span class="sxs-lookup"><span data-stu-id="046ec-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="046ec-124">Voit myös muuntaa tietoja.</span><span class="sxs-lookup"><span data-stu-id="046ec-124">You can also transform your data.</span></span> <span data-ttu-id="046ec-125">Valitse muokattava tai muunnettava entiteetti.</span><span class="sxs-lookup"><span data-stu-id="046ec-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="046ec-126">Tee muunnokset Power Query -ikkunassa olevilla asetuksilla.</span><span class="sxs-lookup"><span data-stu-id="046ec-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="046ec-127">Jokainen muunnos mainitaan **Käytössä olevat vaiheet** -luettelossa.</span><span class="sxs-lookup"><span data-stu-id="046ec-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="046ec-128">Power Query sisältää useita valmiita muunnosvaihtoehtoja.</span><span class="sxs-lookup"><span data-stu-id="046ec-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="046ec-129">Lisätietoja on kohdassa [Power Query -muunnokset](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="046ec-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="046ec-130">Voit lisätä tietolähteeseen entiteettejä valitsemalla **Nouda tiedot** **Muokkaa kyselyjä** -valintaikkunassa.</span><span class="sxs-lookup"><span data-stu-id="046ec-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="046ec-131">Seuraavien muunnosten tekeminen on suositeltavaa:</span><span class="sxs-lookup"><span data-stu-id="046ec-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="046ec-132">Jos käsiteltävät tiedot saadaan CSV-tiedostosta, ensimmäisellä rivillä on usein otsikoita.</span><span class="sxs-lookup"><span data-stu-id="046ec-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="046ec-133">Valitse ensin **Muunna taulukko** ja sitten **Käytä otsikoita ensimmäisenä rivinä**.</span><span class="sxs-lookup"><span data-stu-id="046ec-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="046ec-134">Varmista, että tietotyyppi on määritetty oikein.</span><span class="sxs-lookup"><span data-stu-id="046ec-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="046ec-135">Tallenna muunnokset valitsemalla Power Query -ikkunan alareunassa **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="046ec-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="046ec-136">Tietolähteeseen voi siirtyä tallentamisen jälkeen valitsemalla **Tiedot** > **Tietolähteet**.</span><span class="sxs-lookup"><span data-stu-id="046ec-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="046ec-137">**Tietolähteet**-sivulla uuden tietolähteen tila on **Päivittyy**.</span><span class="sxs-lookup"><span data-stu-id="046ec-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="046ec-138">Käytettävissä olevat Power Query -tietolähteet</span><span class="sxs-lookup"><span data-stu-id="046ec-138">Available Power Query data sources</span></span>

<span data-ttu-id="046ec-139">[Power Query -yhdistimien viitesivulla](https://docs.microsoft.com/power-query/connectors/) on ajantasainen luettelo yhdistimistä, jotka voidaan valita tuomaan tietoja Customer Insightsiin.</span><span class="sxs-lookup"><span data-stu-id="046ec-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="046ec-140">Yhdistimiä, joiden **Customer Insights (tietovuot)** -sarakkeessa on valintamerkki, voidaan käyttää uusien Power Queryyn perustuvien tietolähteiden luomiseen.</span><span class="sxs-lookup"><span data-stu-id="046ec-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="046ec-141">Kun yhdistimen dokumentaatiossa on lisätietoja sen edellytyksistä, rajoituksista ja muista tiedoista.</span><span class="sxs-lookup"><span data-stu-id="046ec-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="046ec-142">Power Query -tietolähteiden muokkaaminen</span><span class="sxs-lookup"><span data-stu-id="046ec-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="046ec-143">Jos jokin sovelluksen prosessi (kuten *segmentointi*, *vastaavuus* tai *yhdistäminen*) käyttää tietolähteitä, niin ei ehkä voi tehdä muutoksia.</span><span class="sxs-lookup"><span data-stu-id="046ec-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="046ec-144">Voit seurata **Asetukset**-sivulla kunkin aktiivisen prosessin etenemistä.</span><span class="sxs-lookup"><span data-stu-id="046ec-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="046ec-145">Kun prosessi valmistuu, voit palata **Tietolähteet**-sivulle ja tehdä muutokset.</span><span class="sxs-lookup"><span data-stu-id="046ec-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="046ec-146">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.</span><span class="sxs-lookup"><span data-stu-id="046ec-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="046ec-147">Valitse muutettavan tietolähteen vieressä olevat pystysuorat kolme pistettä ja valitse avattavasta valikosta **Muokkaa**.</span><span class="sxs-lookup"><span data-stu-id="046ec-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="046ec-148">![Muokkaa-asetus](media/edit-option-data-sources.png "Muokkaa-asetus")</span><span class="sxs-lookup"><span data-stu-id="046ec-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="046ec-149">Lisätietoja muutosten ja muunnosten käyttämisestä **Power Query – Muokkaa kyselyjä** -ikkunassa on kohdassa [Uuden tietolähteen luominen](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="046ec-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="046ec-150">Kun lopetat muokkaamisen, tallenna muutokset valitsemalla **Tallenna** Power Queryssä.</span><span class="sxs-lookup"><span data-stu-id="046ec-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
