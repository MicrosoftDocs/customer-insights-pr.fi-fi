---
title: Tietojen käsitteleminen tietolähteiden avulla
description: Tietoja tietojen tuomisesta eri lähteistä.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643949"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="b69dd-103">Tietolähteiden yleiskatsaus</span><span class="sxs-lookup"><span data-stu-id="b69dd-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b69dd-104">Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuus yhdistää tietoihin monenlaisista lähteistä.</span><span class="sxs-lookup"><span data-stu-id="b69dd-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="b69dd-105">Tietolähteen yhdistämistä kutsutaan usein *tietojen käsittelyprosessiksi*.</span><span class="sxs-lookup"><span data-stu-id="b69dd-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="b69dd-106">Kun tiedot on käsitelty, ne voidaan [yhdistää](data-unification.md) ja niissä voidaan tehdä toimintoja.</span><span class="sxs-lookup"><span data-stu-id="b69dd-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="b69dd-107">Lisää tietolähde</span><span class="sxs-lookup"><span data-stu-id="b69dd-107">Add a data source</span></span>

<span data-ttu-id="b69dd-108">Lisätietoja tietolähteen lisäämisestä on artikkeleissa, joissa käsitellään valittua vaihtoehtoa.</span><span class="sxs-lookup"><span data-stu-id="b69dd-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="b69dd-109">Tietolähde voidaan lisätä pääasiassa kolmella tavalla:</span><span class="sxs-lookup"><span data-stu-id="b69dd-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="b69dd-110">Käyttämällä kymmeniä Power Query -yhdistimiä</span><span class="sxs-lookup"><span data-stu-id="b69dd-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="b69dd-111">Common Data Model -kansiosta</span><span class="sxs-lookup"><span data-stu-id="b69dd-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="b69dd-112">Omasta Common Data Servicen Data Lake -tallennustilasta</span><span class="sxs-lookup"><span data-stu-id="b69dd-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="b69dd-113">Tietoja ei voi vielä listä paikallisista tietolähteistä.</span><span class="sxs-lookup"><span data-stu-id="b69dd-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="b69dd-114">Käsiteltyjen tietojen tarkistaminen</span><span class="sxs-lookup"><span data-stu-id="b69dd-114">Review ingested data</span></span>

<span data-ttu-id="b69dd-115">Näkyvissä on kunkin käsitellyn tietolähteen nimi, sen tilan ja kyseisen tietolähteen tietojen viimeisimmän päivityskerran.</span><span class="sxs-lookup"><span data-stu-id="b69dd-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="b69dd-116">Tietolähdeluettelon voi lajitella kunkin sarakkeen mukaan.</span><span class="sxs-lookup"><span data-stu-id="b69dd-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b69dd-117">![Tietolähde lisättiin](media/configure-data-datasource-added.png "Tietolähde lisättiin")</span><span class="sxs-lookup"><span data-stu-id="b69dd-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="b69dd-118">Tila</span><span class="sxs-lookup"><span data-stu-id="b69dd-118">Status</span></span>  |<span data-ttu-id="b69dd-119">Kuvaus</span><span class="sxs-lookup"><span data-stu-id="b69dd-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b69dd-120">Onnistui</span><span class="sxs-lookup"><span data-stu-id="b69dd-120">Successful</span></span>   |<span data-ttu-id="b69dd-121">Tietolähde on käsitelty, jos **Päivitetty**-sarakkeessa on aika.</span><span class="sxs-lookup"><span data-stu-id="b69dd-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="b69dd-122">Ei aloitettu</span><span class="sxs-lookup"><span data-stu-id="b69dd-122">Not started</span></span>   |<span data-ttu-id="b69dd-123">Tietolähteessä ei ole vielä käsiteltyjä tietoja tai se on edelleen luonnostilassa.</span><span class="sxs-lookup"><span data-stu-id="b69dd-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="b69dd-124">Päivittää</span><span class="sxs-lookup"><span data-stu-id="b69dd-124">Refreshing</span></span>    |<span data-ttu-id="b69dd-125">Tietoja käsittely on meneillään.</span><span class="sxs-lookup"><span data-stu-id="b69dd-125">Data ingestion is in progress.</span></span> <span data-ttu-id="b69dd-126">Voit peruuttaa tämän toiminnon valitsemalla **Pysäytä päivittäminen** **Toiminnot**-sarakkeessa.</span><span class="sxs-lookup"><span data-stu-id="b69dd-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="b69dd-127">Tietolähteen päivittämisen pysäyttäminen palauttaa sen tilaan, jossa se on viimeksi päivitetty.</span><span class="sxs-lookup"><span data-stu-id="b69dd-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="b69dd-128">Epäonnistunut</span><span class="sxs-lookup"><span data-stu-id="b69dd-128">Failed</span></span>     |<span data-ttu-id="b69dd-129">Tietojen käsittelyssä havaittiin virheitä.</span><span class="sxs-lookup"><span data-stu-id="b69dd-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="b69dd-130">Valitsemalla **Päivityksen tila** voit tarkastella lisätietoja päivityksen tilasta, kuten virhetiedot ja jäljempänä tapahtuvat prosessipäivitykset.</span><span class="sxs-lookup"><span data-stu-id="b69dd-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="b69dd-131">Tietojen lataaminen voi kestää jonkin aikaa.</span><span class="sxs-lookup"><span data-stu-id="b69dd-131">Loading data can take some time.</span></span> <span data-ttu-id="b69dd-132">Kun päivitys on onnistunut, käsiteltyjä tietoja voi tarkastella **Entiteetit**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="b69dd-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="b69dd-133">Lisätietoja on kohdassa [Entiteetit](entities.md).</span><span class="sxs-lookup"><span data-stu-id="b69dd-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="b69dd-134">Tietolähteen päivittäminen</span><span class="sxs-lookup"><span data-stu-id="b69dd-134">Refresh a data source</span></span>

<span data-ttu-id="b69dd-135">Tietolähteet voidaan päivittää automaattisen aikataulun mukaan tai manuaalisesti tarvittaessa.</span><span class="sxs-lookup"><span data-stu-id="b69dd-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="b69dd-136">Määritä kaikkien käsiteltyjen tietolähteiden ajoitetut päivitykset valitsemalla **Hallinta** > **Järjestelmä** > [**Ajoitus**](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b69dd-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="b69dd-137">Tietolähde päivitetään tarvittaessa seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="b69dd-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="b69dd-138">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**</span><span class="sxs-lookup"><span data-stu-id="b69dd-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="b69dd-139">Valitse päivitettävän tietolähteen vieressä kolme allekkaista pistettä ja valitse sitten avattavassa luettelossa **Päivitä**.</span><span class="sxs-lookup"><span data-stu-id="b69dd-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="b69dd-140">Tietolähde on nyt valmis manuaaliseen päivitykseen.</span><span class="sxs-lookup"><span data-stu-id="b69dd-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="b69dd-141">Tietolähteen päivittäminen päivittää sekä entiteettirakenteen että kaikkien tietolähteessä määritettyjen entiteettien tiedot.</span><span class="sxs-lookup"><span data-stu-id="b69dd-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="b69dd-142">Valitse **Pysäytä päivittäminen**, jos haluat peruuttaa nykyisen päivityksen, jolloin tietolähde palautuu viimeksi päivitettyyn tilaan.</span><span class="sxs-lookup"><span data-stu-id="b69dd-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="b69dd-143">Tietolähteen poistaminen</span><span class="sxs-lookup"><span data-stu-id="b69dd-143">Delete a data source</span></span>

1. <span data-ttu-id="b69dd-144">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.</span><span class="sxs-lookup"><span data-stu-id="b69dd-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="b69dd-145">Valitse poistettavan tietolähteen vieressä olevat pystysuorat kolme pistettä ja valitse avattavasta valikosta **Poista**.</span><span class="sxs-lookup"><span data-stu-id="b69dd-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="b69dd-146">Vahvista poisto.</span><span class="sxs-lookup"><span data-stu-id="b69dd-146">Confirm your deletion.</span></span>
