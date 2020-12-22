---
title: Entiteetit ja tietojoukot
description: Tietojen näyttäminen Entiteetit-sivulla.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e3f41c0424b2cd756d72ae6af9d5225ebba92628
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405590"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="0019f-103">Käyttäjäryhmän merkityksellisten tietojen entiteetit</span><span class="sxs-lookup"><span data-stu-id="0019f-103">Entities in audience insights</span></span>

<span data-ttu-id="0019f-104">Kun [tietolähteet on määritetty](data-sources.md), siirry **Entiteetit**-sivulle arvioimaan käsiteltyjen tietojen laatua.</span><span class="sxs-lookup"><span data-stu-id="0019f-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="0019f-105">Entiteettejä pidetään tietojoukkoina.</span><span class="sxs-lookup"><span data-stu-id="0019f-105">Entities are considered datasets.</span></span> <span data-ttu-id="0019f-106">Monet Dynamics 365 Customer Insights -ominaisuudet perustuvat näihin entiteetteihin.</span><span class="sxs-lookup"><span data-stu-id="0019f-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="0019f-107">Niiden huolellinen tarkastelu voi auttaa tarkistamaan kyseisten ominaisuuksien tuloksia.</span><span class="sxs-lookup"><span data-stu-id="0019f-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="0019f-108">**Entiteetit**-sivulla on luettelo entiteeteistä, ja siinä on useita sarakkeita:</span><span class="sxs-lookup"><span data-stu-id="0019f-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="0019f-109">**Nimi**: Tietoentiteetin nimi.</span><span class="sxs-lookup"><span data-stu-id="0019f-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="0019f-110">Jos entiteetin nimen vieressä on varoitussymboli, kyseisen entiteetin tietojen lataus ei onnistunut.</span><span class="sxs-lookup"><span data-stu-id="0019f-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="0019f-111">**Lähde**: entiteetin käsitelleen tietolähteen tyyppi.</span><span class="sxs-lookup"><span data-stu-id="0019f-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="0019f-112">**Luonut**: entiteetin luoneen henkilön nimi.</span><span class="sxs-lookup"><span data-stu-id="0019f-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="0019f-113">**Luotu**: entiteetin luontipäivä ja -aika.</span><span class="sxs-lookup"><span data-stu-id="0019f-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="0019f-114">**Päivittäjä**: entiteetin päivittäneen henkilön nimi.</span><span class="sxs-lookup"><span data-stu-id="0019f-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="0019f-115">**Viimeksi päivitetty**: entiteetin viimeisin päivityspäivä ja -aika.</span><span class="sxs-lookup"><span data-stu-id="0019f-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="0019f-116">**Päivitetty viimeksi**: tietojen viimeisin päivityspäivä ja -aika.</span><span class="sxs-lookup"><span data-stu-id="0019f-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="0019f-117">Tutustuminen tietyn entiteetin tietoihin</span><span class="sxs-lookup"><span data-stu-id="0019f-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="0019f-118">Valitse entiteetti, jonka kenttiin ja tietueisiin haluat tutustua.</span><span class="sxs-lookup"><span data-stu-id="0019f-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0019f-119">![Valitse entiteetti](media/data-manager-entities-data.png "Valitse entiteetti")</span><span class="sxs-lookup"><span data-stu-id="0019f-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="0019f-120">**Tiedot**-välilehti valitaan oletusarvoisesti, ja siinä olevassa taulukossa on tietoja entiteetin yksittäisistä tietueista.</span><span class="sxs-lookup"><span data-stu-id="0019f-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0019f-121">![Kentät-taulukko](media/data-manager-entities-fields.PNG "Kentät-taulukko")</span><span class="sxs-lookup"><span data-stu-id="0019f-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="0019f-122">**Kentät**-välilehdessä on taulukko, jossa voi tarkastella valitun entiteetin tietoja, kuten kentän nimeä, tietotyyppejä ja tyyppejä.</span><span class="sxs-lookup"><span data-stu-id="0019f-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="0019f-123">**Tyyppi**-sarakkeessa näkyy liittyviä Common Data Model -tyyppejä, jotka järjestelmä joko tunnistaa automaattisesti tai jotka käyttäjät [yhdistävät manuaalisesti](map-entities.md).</span><span class="sxs-lookup"><span data-stu-id="0019f-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="0019f-124">Nämä ovat sementtisia tyyppejä, jotka eroavat määritetteiden tietotyypeistä. Esimerkiksi alla olevan *Sähköposti*-kentän tietotyyppi on *Teksti*, mutta sen (semanttinen) Common Data Model -tyyppi voi olla *Sähköposti* tai *EmailAddress*.</span><span class="sxs-lookup"><span data-stu-id="0019f-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="0019f-125">Kummassakin taulukossa näkyy vain osa entiteetin tiedoista.</span><span class="sxs-lookup"><span data-stu-id="0019f-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="0019f-126">Voit tarkastella koko tietojoukkoa siirtymällä **Tietolähteet**-sivulle, valitsemalla entiteetin, valitsemalla **Muokka** ja tarkastelemalla entiteetin tietoja Power Query -editorissa kohdassa [Tietolähteet](data-sources.md) kuvatulla tavalla.</span><span class="sxs-lookup"><span data-stu-id="0019f-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="0019f-127">Lisätietoja entiteetissä käsitellyistä tiedoista on **Yhteenveto**-sarakkeessa, jossa on joitakin tärkeitä tietoja tietojen ominaisuuksista, kuten tyhjäarvot, puuttuvat arvot, yksilöivät arvot, määrät ja jakelut.</span><span class="sxs-lookup"><span data-stu-id="0019f-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="0019f-128">Näet tietojen yhteenvedon valitsemalla kaaviokuvakkeen.</span><span class="sxs-lookup"><span data-stu-id="0019f-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0019f-129">![Yhteenvetosymboli](media/data-manager-entities-summary.png "Tietojen yhteenvetotaulukko")</span><span class="sxs-lookup"><span data-stu-id="0019f-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="0019f-130">Seuraava vaihe</span><span class="sxs-lookup"><span data-stu-id="0019f-130">Next step</span></span>

<span data-ttu-id="0019f-131">Ohjeaiheessa [Yhdistäminen](data-unification.md) on lisätietoja käsiteltyjen tietojen *vastaavuusmäärityksestä*, *täsmäytyksestä* ja *yhdistämisestä*.</span><span class="sxs-lookup"><span data-stu-id="0019f-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>
