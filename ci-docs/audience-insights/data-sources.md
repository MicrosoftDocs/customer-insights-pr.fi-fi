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
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887890"
---
# <a name="data-sources-overview"></a><span data-ttu-id="bcea0-103">Tietolähteiden yleiskatsaus</span><span class="sxs-lookup"><span data-stu-id="bcea0-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="bcea0-104">Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuus yhdistää tietoihin monenlaisista lähteistä.</span><span class="sxs-lookup"><span data-stu-id="bcea0-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="bcea0-105">Tietolähteen yhdistämistä kutsutaan usein *tietojen käsittelyprosessiksi*.</span><span class="sxs-lookup"><span data-stu-id="bcea0-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="bcea0-106">Kun tiedot on käsitelty, ne voidaan [yhdistää](data-unification.md) ja niissä voidaan tehdä toimintoja.</span><span class="sxs-lookup"><span data-stu-id="bcea0-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="bcea0-107">Lisää tietolähde</span><span class="sxs-lookup"><span data-stu-id="bcea0-107">Add a data source</span></span>

<span data-ttu-id="bcea0-108">Lisätietoja tietolähteen lisäämisestä on artikkeleissa, joissa käsitellään valittua vaihtoehtoa.</span><span class="sxs-lookup"><span data-stu-id="bcea0-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="bcea0-109">Tietolähde voidaan lisätä pääasiassa kolmella tavalla:</span><span class="sxs-lookup"><span data-stu-id="bcea0-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="bcea0-110">Käyttämällä kymmeniä Power Query -yhdistimiä</span><span class="sxs-lookup"><span data-stu-id="bcea0-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="bcea0-111">Common Data Model -kansiosta</span><span class="sxs-lookup"><span data-stu-id="bcea0-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="bcea0-112">Omasta Common Data Servicen Data Lake -tallennustilasta</span><span class="sxs-lookup"><span data-stu-id="bcea0-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="bcea0-113">Tietojen lisääminen paikallisista tietolähteistä</span><span class="sxs-lookup"><span data-stu-id="bcea0-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="bcea0-114">Tietojen käsittelyä paikallisista tietolähteistä Audience Insightsissa tuetaan Power Platform -tietovirtojen perusteella.</span><span class="sxs-lookup"><span data-stu-id="bcea0-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="bcea0-115">Tietovirtaukset voidaan ottaa käyttöön Customer Insightsissa [antamalla Microsoft Dataverse -ympäristön URL-osoite](manage-environments.md#create-an-environment-in-an-existing-organization) ympäristöä määritettäessä.</span><span class="sxs-lookup"><span data-stu-id="bcea0-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="bcea0-116">Kun Dataverse-ympäristö on liitetty Customer Insights -tietoihin, luodut tietolähteet käyttävät oletusarvoisesti [Power Platform -tietovirtoja](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="bcea0-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="bcea0-117">Tietovirtaukset tukevat paikallisia yhteyksiä tietoyhdyskäytävien avulla.</span><span class="sxs-lookup"><span data-stu-id="bcea0-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="bcea0-118">Poista ja luo uudelleen tietolähteet, jotka olivat olemassa ennen Dataverse-ympäristön liittämistä paikallisen tietoyhdyskäytävien käyttöön.</span><span class="sxs-lookup"><span data-stu-id="bcea0-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="bcea0-119">Aiemmin luodun Power BI- tai Power Apps -ympäristön tietoyhdyskäytävät ovat näkyvissä, ja voit käyttää niitä uudelleen Customer Insightsissa.</span><span class="sxs-lookup"><span data-stu-id="bcea0-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="bcea0-120">Tietolähteiden sivulla on linkkejä Power Platform -ympäristöön, jossa voit tarkastella ja määrittää paikallisia yhdyskäytäviä.</span><span class="sxs-lookup"><span data-stu-id="bcea0-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Näyttökuva tietolähteiden sivusta, jossa on Power Platform -ympäristöön osoittavat linkit.":::

## <a name="review-ingested-data"></a><span data-ttu-id="bcea0-122">Käsiteltyjen tietojen tarkistaminen</span><span class="sxs-lookup"><span data-stu-id="bcea0-122">Review ingested data</span></span>

<span data-ttu-id="bcea0-123">Näkyvissä on kunkin käsitellyn tietolähteen nimi, sen tilan ja kyseisen tietolähteen tietojen viimeisimmän päivityskerran.</span><span class="sxs-lookup"><span data-stu-id="bcea0-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="bcea0-124">Tietolähdeluettelon voi lajitella kunkin sarakkeen mukaan.</span><span class="sxs-lookup"><span data-stu-id="bcea0-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bcea0-125">![Tietolähde lisättiin](media/configure-data-datasource-added.png "Tietolähde lisättiin")</span><span class="sxs-lookup"><span data-stu-id="bcea0-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="bcea0-126">Tila</span><span class="sxs-lookup"><span data-stu-id="bcea0-126">Status</span></span>  |<span data-ttu-id="bcea0-127">Kuvaus</span><span class="sxs-lookup"><span data-stu-id="bcea0-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="bcea0-128">Onnistui</span><span class="sxs-lookup"><span data-stu-id="bcea0-128">Successful</span></span>   |<span data-ttu-id="bcea0-129">Tietolähde on käsitelty, jos **Päivitetty**-sarakkeessa on aika.</span><span class="sxs-lookup"><span data-stu-id="bcea0-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="bcea0-130">Ei aloitettu</span><span class="sxs-lookup"><span data-stu-id="bcea0-130">Not started</span></span>   |<span data-ttu-id="bcea0-131">Tietolähteessä ei ole vielä käsiteltyjä tietoja tai se on edelleen luonnostilassa.</span><span class="sxs-lookup"><span data-stu-id="bcea0-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="bcea0-132">Päivittää</span><span class="sxs-lookup"><span data-stu-id="bcea0-132">Refreshing</span></span>    |<span data-ttu-id="bcea0-133">Tietoja käsittely on meneillään.</span><span class="sxs-lookup"><span data-stu-id="bcea0-133">Data ingestion is in progress.</span></span> <span data-ttu-id="bcea0-134">Voit peruuttaa tämän toiminnon valitsemalla **Pysäytä päivittäminen** **Toiminnot**-sarakkeessa.</span><span class="sxs-lookup"><span data-stu-id="bcea0-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="bcea0-135">Tietolähteen päivittämisen pysäyttäminen palauttaa sen tilaan, jossa se on viimeksi päivitetty.</span><span class="sxs-lookup"><span data-stu-id="bcea0-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="bcea0-136">Epäonnistunut</span><span class="sxs-lookup"><span data-stu-id="bcea0-136">Failed</span></span>     |<span data-ttu-id="bcea0-137">Tietojen käsittelyssä havaittiin virheitä.</span><span class="sxs-lookup"><span data-stu-id="bcea0-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="bcea0-138">Valitse jonkin tietolähteen **Tila**-sarakkeen arvo, jos haluat tarkastella lisätietoja.</span><span class="sxs-lookup"><span data-stu-id="bcea0-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="bcea0-139">Laajenna **Edistymisen tiedot** -ruudussa **Tietolähteet**-kohta.</span><span class="sxs-lookup"><span data-stu-id="bcea0-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="bcea0-140">Valitsemalla **Katso tiedot** -kohdan voit tarkastella lisätietoja päivityksen tilasta, kuten virhetiedot ja jäljempänä tapahtuvat prosessipäivitykset.</span><span class="sxs-lookup"><span data-stu-id="bcea0-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="bcea0-141">Tietojen lataaminen voi kestää jonkin aikaa.</span><span class="sxs-lookup"><span data-stu-id="bcea0-141">Loading data can take some time.</span></span> <span data-ttu-id="bcea0-142">Kun päivitys on onnistunut, käsiteltyjä tietoja voi tarkastella **Entiteetit**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="bcea0-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="bcea0-143">Lisätietoja on kohdassa [Entiteetit](entities.md).</span><span class="sxs-lookup"><span data-stu-id="bcea0-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="bcea0-144">Tietolähteen päivittäminen</span><span class="sxs-lookup"><span data-stu-id="bcea0-144">Refresh a data source</span></span>

<span data-ttu-id="bcea0-145">Tietolähteet voidaan päivittää automaattisen aikataulun mukaan tai manuaalisesti tarvittaessa.</span><span class="sxs-lookup"><span data-stu-id="bcea0-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="bcea0-146">Määritä kaikkien käsiteltyjen tietolähteiden ajoitetut päivitykset valitsemalla **Hallinta** > **Järjestelmä** > [**Ajoitus**](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bcea0-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="bcea0-147">Tietolähde päivitetään tarvittaessa seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="bcea0-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="bcea0-148">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**</span><span class="sxs-lookup"><span data-stu-id="bcea0-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="bcea0-149">Valitse päivitettävän tietolähteen vieressä kolme allekkaista pistettä ja valitse sitten avattavassa luettelossa **Päivitä**.</span><span class="sxs-lookup"><span data-stu-id="bcea0-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="bcea0-150">Tietolähde on nyt valmis manuaaliseen päivitykseen.</span><span class="sxs-lookup"><span data-stu-id="bcea0-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="bcea0-151">Jos päivität tietolähteen, päivitetään tietolähteessä määritettyjen entiteettien sekä tiedot että entiteettirakenne.</span><span class="sxs-lookup"><span data-stu-id="bcea0-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="bcea0-152">Valitse **Pysäytä päivittäminen**, jos haluat peruuttaa nykyisen päivityksen, jolloin tietolähde palautuu viimeksi päivitettyyn tilaan.</span><span class="sxs-lookup"><span data-stu-id="bcea0-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="bcea0-153">Tietolähteen poistaminen</span><span class="sxs-lookup"><span data-stu-id="bcea0-153">Delete a data source</span></span>

1. <span data-ttu-id="bcea0-154">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.</span><span class="sxs-lookup"><span data-stu-id="bcea0-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="bcea0-155">Valitse poistettavan tietolähteen vieressä olevat pystysuorat kolme pistettä ja valitse avattavasta valikosta **Poista**.</span><span class="sxs-lookup"><span data-stu-id="bcea0-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="bcea0-156">Vahvista poisto.</span><span class="sxs-lookup"><span data-stu-id="bcea0-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
