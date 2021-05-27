---
title: Tietojen käsitteleminen tietolähteiden avulla
description: Tietoja tietojen tuomisesta eri lähteistä.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085526"
---
# <a name="data-sources-overview"></a><span data-ttu-id="cd71e-103">Tietolähteiden yleiskatsaus</span><span class="sxs-lookup"><span data-stu-id="cd71e-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="cd71e-104">Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuus yhdistää tietoihin monenlaisista lähteistä.</span><span class="sxs-lookup"><span data-stu-id="cd71e-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="cd71e-105">Tietolähteen yhdistämistä kutsutaan usein *tietojen käsittelyprosessiksi*.</span><span class="sxs-lookup"><span data-stu-id="cd71e-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="cd71e-106">Kun tiedot on käsitelty, ne voidaan [yhdistää](data-unification.md) ja niissä voidaan tehdä toimintoja.</span><span class="sxs-lookup"><span data-stu-id="cd71e-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="cd71e-107">Lisää tietolähde</span><span class="sxs-lookup"><span data-stu-id="cd71e-107">Add a data source</span></span>

<span data-ttu-id="cd71e-108">Lisätietoja tietolähteen lisäämisestä on artikkeleissa, joissa käsitellään valittua vaihtoehtoa.</span><span class="sxs-lookup"><span data-stu-id="cd71e-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="cd71e-109">Tietolähde voidaan lisätä pääasiassa kolmella tavalla:</span><span class="sxs-lookup"><span data-stu-id="cd71e-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="cd71e-110">Käyttämällä kymmeniä Power Query -yhdistimiä</span><span class="sxs-lookup"><span data-stu-id="cd71e-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="cd71e-111">Common Data Model -kansiosta</span><span class="sxs-lookup"><span data-stu-id="cd71e-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="cd71e-112">Omasta Common Data Servicen Data Lake -tallennustilasta</span><span class="sxs-lookup"><span data-stu-id="cd71e-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="cd71e-113">Tietojen lisääminen paikallisista tietolähteistä</span><span class="sxs-lookup"><span data-stu-id="cd71e-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="cd71e-114">Tietojen käsittelyä paikallisista tietolähteistä Audience Insightsissa tuetaan Power Platform -tietovirtojen perusteella.</span><span class="sxs-lookup"><span data-stu-id="cd71e-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="cd71e-115">Tietovirtaukset voidaan ottaa käyttöön Customer Insightsissa [antamalla Microsoft Dataverse -ympäristön URL-osoite](manage-environments.md#create-an-environment-in-an-existing-organization) ympäristöä määritettäessä.</span><span class="sxs-lookup"><span data-stu-id="cd71e-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="cd71e-116">Kun Dataverse-ympäristö on liitetty Customer Insights -tietoihin, luodut tietolähteet käyttävät oletusarvoisesti [Power Platform -tietovirtoja](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="cd71e-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="cd71e-117">Tietovuot tukevat paikallisia yhteyksiä tietoyhdyskäytävän avulla.</span><span class="sxs-lookup"><span data-stu-id="cd71e-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="cd71e-118">Poista ja luo uudelleen tietolähteet, jotka olivat olemassa ennen Dataverse-ympäristön liittämistä [paikallisten tietoyhdyskäytävien käyttöön](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="cd71e-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="cd71e-119">Aiemmin luodun Power BI- tai Power Apps -ympäristön tietoyhdyskäytävät ovat näkyvissä, ja voit käyttää niitä uudelleen Customer Insightsissa.</span><span class="sxs-lookup"><span data-stu-id="cd71e-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="cd71e-120">Tietolähteiden sivulla on linkkejä Power Platform -ympäristöön, jossa voit tarkastella ja määrittää paikallisia yhdyskäytäviä.</span><span class="sxs-lookup"><span data-stu-id="cd71e-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="cd71e-121">Käsiteltyjen tietojen tarkistaminen</span><span class="sxs-lookup"><span data-stu-id="cd71e-121">Review ingested data</span></span>

<span data-ttu-id="cd71e-122">Näkyvissä on kunkin käsitellyn tietolähteen nimi, sen tilan ja kyseisen tietolähteen tietojen viimeisimmän päivityskerran.</span><span class="sxs-lookup"><span data-stu-id="cd71e-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="cd71e-123">Tietolähdeluettelon voi lajitella kunkin sarakkeen mukaan.</span><span class="sxs-lookup"><span data-stu-id="cd71e-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cd71e-124">![Tietolähde lisättiin](media/configure-data-datasource-added.png "Tietolähde lisättiin")</span><span class="sxs-lookup"><span data-stu-id="cd71e-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="cd71e-125">Tila</span><span class="sxs-lookup"><span data-stu-id="cd71e-125">Status</span></span>  |<span data-ttu-id="cd71e-126">Kuvaus</span><span class="sxs-lookup"><span data-stu-id="cd71e-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="cd71e-127">Onnistui</span><span class="sxs-lookup"><span data-stu-id="cd71e-127">Successful</span></span>   |<span data-ttu-id="cd71e-128">Tietolähde on käsitelty, jos **Päivitetty**-sarakkeessa on aika.</span><span class="sxs-lookup"><span data-stu-id="cd71e-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="cd71e-129">Ei aloitettu</span><span class="sxs-lookup"><span data-stu-id="cd71e-129">Not started</span></span>   |<span data-ttu-id="cd71e-130">Tietolähteessä ei ole vielä käsiteltyjä tietoja tai se on edelleen luonnostilassa.</span><span class="sxs-lookup"><span data-stu-id="cd71e-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="cd71e-131">Päivittää</span><span class="sxs-lookup"><span data-stu-id="cd71e-131">Refreshing</span></span>    |<span data-ttu-id="cd71e-132">Tietoja käsittely on meneillään.</span><span class="sxs-lookup"><span data-stu-id="cd71e-132">Data ingestion is in progress.</span></span> <span data-ttu-id="cd71e-133">Voit peruuttaa tämän toiminnon valitsemalla **Pysäytä päivittäminen** **Toiminnot**-sarakkeessa.</span><span class="sxs-lookup"><span data-stu-id="cd71e-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="cd71e-134">Tietolähteen päivittämisen pysäyttäminen palauttaa sen tilaan, jossa se on viimeksi päivitetty.</span><span class="sxs-lookup"><span data-stu-id="cd71e-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="cd71e-135">Epäonnistunut</span><span class="sxs-lookup"><span data-stu-id="cd71e-135">Failed</span></span>     |<span data-ttu-id="cd71e-136">Tietojen käsittelyssä havaittiin virheitä.</span><span class="sxs-lookup"><span data-stu-id="cd71e-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="cd71e-137">Valitse jonkin tietolähteen **Tila**-sarakkeen arvo, jos haluat tarkastella lisätietoja.</span><span class="sxs-lookup"><span data-stu-id="cd71e-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="cd71e-138">Laajenna **Edistymisen tiedot** -ruudussa **Tietolähteet**-kohta.</span><span class="sxs-lookup"><span data-stu-id="cd71e-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="cd71e-139">Valitsemalla **Katso tiedot** -kohdan voit tarkastella lisätietoja päivityksen tilasta, kuten virhetiedot ja jäljempänä tapahtuvat prosessipäivitykset.</span><span class="sxs-lookup"><span data-stu-id="cd71e-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="cd71e-140">Tietojen lataaminen voi kestää jonkin aikaa.</span><span class="sxs-lookup"><span data-stu-id="cd71e-140">Loading data can take some time.</span></span> <span data-ttu-id="cd71e-141">Kun päivitys on onnistunut, käsiteltyjä tietoja voi tarkastella **Entiteetit**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="cd71e-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="cd71e-142">Lisätietoja on kohdassa [Entiteetit](entities.md).</span><span class="sxs-lookup"><span data-stu-id="cd71e-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="cd71e-143">Tietolähteen päivittäminen</span><span class="sxs-lookup"><span data-stu-id="cd71e-143">Refresh a data source</span></span>

<span data-ttu-id="cd71e-144">Tietolähteet voidaan päivittää automaattisen aikataulun mukaan tai manuaalisesti tarvittaessa.</span><span class="sxs-lookup"><span data-stu-id="cd71e-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="cd71e-145">Määritä kaikkien käsiteltyjen tietolähteiden ajoitetut päivitykset valitsemalla **Hallinta** > **Järjestelmä** > [**Ajoitus**](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cd71e-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="cd71e-146">Tietolähde päivitetään tarvittaessa seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="cd71e-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="cd71e-147">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**</span><span class="sxs-lookup"><span data-stu-id="cd71e-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="cd71e-148">Valitse päivitettävän tietolähteen vieressä kolme allekkaista pistettä ja valitse sitten avattavassa luettelossa **Päivitä**.</span><span class="sxs-lookup"><span data-stu-id="cd71e-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="cd71e-149">Tietolähde on nyt valmis manuaaliseen päivitykseen.</span><span class="sxs-lookup"><span data-stu-id="cd71e-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="cd71e-150">Jos päivität tietolähteen, päivitetään tietolähteessä määritettyjen entiteettien sekä tiedot että entiteettirakenne.</span><span class="sxs-lookup"><span data-stu-id="cd71e-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="cd71e-151">Valitse **Pysäytä päivittäminen**, jos haluat peruuttaa nykyisen päivityksen, jolloin tietolähde palautuu viimeksi päivitettyyn tilaan.</span><span class="sxs-lookup"><span data-stu-id="cd71e-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="cd71e-152">Tietolähteen poistaminen</span><span class="sxs-lookup"><span data-stu-id="cd71e-152">Delete a data source</span></span>

1. <span data-ttu-id="cd71e-153">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.</span><span class="sxs-lookup"><span data-stu-id="cd71e-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="cd71e-154">Valitse poistettavan tietolähteen vieressä olevat pystysuorat kolme pistettä ja valitse avattavasta valikosta **Poista**.</span><span class="sxs-lookup"><span data-stu-id="cd71e-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="cd71e-155">Vahvista poisto.</span><span class="sxs-lookup"><span data-stu-id="cd71e-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
