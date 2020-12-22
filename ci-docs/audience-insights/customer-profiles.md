---
title: Asiakasprofiilien näyttäminen
description: Yhtenäisten asiakastietojen yhdistelmänäkymän hakeminen.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 13308c2f40cda0d7e813b4d94ab47d53b5ce2115
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653886"
---
# <a name="customer-profiles"></a><span data-ttu-id="5936f-103">Asiakasprofiilit</span><span class="sxs-lookup"><span data-stu-id="5936f-103">Customer profiles</span></span>

<span data-ttu-id="5936f-104">**Asiakas**-sivulla on asiakkaiden yhdistelmänäkymä, joka perustuu [kaikista tietolähteistä](data-sources.md) kerättyihin profiilitietoihin.</span><span class="sxs-lookup"><span data-stu-id="5936f-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="5936f-105">Asiakasprofiilit ovat käytettävissä sen jälkeen kun [luot yhdistetyn asiakasentiteetin](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="5936f-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="5936f-106">Varmista, että tietojen yhdistämisprosessi on valmis, jotta asiakkaat saavat entistä monipuolisempia näkymiä.</span><span class="sxs-lookup"><span data-stu-id="5936f-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="5936f-107">Sivun avulla voit myös hakea asiakkaita.</span><span class="sxs-lookup"><span data-stu-id="5936f-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="5936f-108">Asiakkaat voivat olla henkilöitä tai organisaatioita (esikatselu).</span><span class="sxs-lookup"><span data-stu-id="5936f-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="5936f-109">Jokaista asiakas- tai organisaatioprofiilia edustaa ruutu.</span><span class="sxs-lookup"><span data-stu-id="5936f-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="5936f-110">Valitse ruutu, jos haluat nähdä lisätietoja tietystä asiakkaasta tai organisaatiosta.</span><span class="sxs-lookup"><span data-stu-id="5936f-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="5936f-111">Sivun alaosassa olevien sivutusohjausobjektien avulla voit tarkastella muita tietueita.</span><span class="sxs-lookup"><span data-stu-id="5936f-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="5936f-112">![Kuluttajakaupan asiakasprofiilit](media/profiles-customers.png "Kuluttajakaupan asiakasprofiilit")</span><span class="sxs-lookup"><span data-stu-id="5936f-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="5936f-113">Organisaatiot (esikatselu)</span><span class="sxs-lookup"><span data-stu-id="5936f-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="5936f-114">![Yritysten väliset asiakasprofiilit](media/profile-customers-b2b.png "Yritysten väliset asiakasprofiilit")</span><span class="sxs-lookup"><span data-stu-id="5936f-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="5936f-115">Jos ruutuja ei näy, kun valitset **Asiakkaat** -siirtymisnäkymässä, järjestelmänvalvojan on [määritettävä vähintään yksi haettavissa oleva määrite](search-filter-index.md) kohdassa **Hae ja suodata indeksi**.</span><span class="sxs-lookup"><span data-stu-id="5936f-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="5936f-116">Hae asiakkaita</span><span class="sxs-lookup"><span data-stu-id="5936f-116">Search for customers</span></span>

<span data-ttu-id="5936f-117">Voit hakea asiakkaita kirjoittamalla nimen tai jonkin muun määritteen hakuruutuun.</span><span class="sxs-lookup"><span data-stu-id="5936f-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="5936f-118">Haku toimii vain tietojen yhdistämisprosessin aikana luodussa asiakasprofiilientiteetissä.</span><span class="sxs-lookup"><span data-stu-id="5936f-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="5936f-119">Järjestelmänvalvojana voit määrittää haettavat määritteet käyttämällä **Indeksin hakeminen ja suodattaminen** -sivua.</span><span class="sxs-lookup"><span data-stu-id="5936f-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="5936f-120">Lisätietoja on kohdassa [Indeksin hakemisen ja suodattamisen hallinta](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="5936f-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="5936f-121">Suodata asiakkaat</span><span class="sxs-lookup"><span data-stu-id="5936f-121">Filter customers</span></span>

<span data-ttu-id="5936f-122">Voit suodattaa asiakkaita asiakasprofiilientiteetin kenttien mukaan.</span><span class="sxs-lookup"><span data-stu-id="5936f-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="5936f-123">Kuten haussa, järjestelmänvalvojan täytyy ensin määrittää kentät suodatettaviksi **Indeksin hakeminen ja suodattaminen** -sivun avulla.</span><span class="sxs-lookup"><span data-stu-id="5936f-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="5936f-124">Valitse **Suodatus** **Asiakkaat**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="5936f-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="5936f-125">Valitse niiden määritteiden vieressä olevat ruudut, joiden mukaan haluat suodattaa asiakkaat.</span><span class="sxs-lookup"><span data-stu-id="5936f-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="5936f-126">![Asiakasprofiilit](media/profiles-customers3.png "Asiakasprofiilit")</span><span class="sxs-lookup"><span data-stu-id="5936f-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="5936f-127">Poista kaikki suodattimet valitsemalla **Tyhjennä suodattimet** **Asiakkaat**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="5936f-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="5936f-128">Asiakastiedot-sivu</span><span class="sxs-lookup"><span data-stu-id="5936f-128">Customer details page</span></span>

<span data-ttu-id="5936f-129">Avaa **Asiakastiedot-sivu** valitsemalla jokin asiakasruuduista.</span><span class="sxs-lookup"><span data-stu-id="5936f-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="5936f-130">Tässä näkymässä on valitun asiakkaan yhdistetyt tiedot.</span><span class="sxs-lookup"><span data-stu-id="5936f-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="5936f-131">Asiakastietoja ovat esimerkiksi seuraavat:</span><span class="sxs-lookup"><span data-stu-id="5936f-131">Customer details include:</span></span>

-   <span data-ttu-id="5936f-132">**Asiakasprofiili-ruutu:** Tässä ruudussa näkyy erilaisia yhtenäisen asiakasprofiilientiteetin arvoja.</span><span class="sxs-lookup"><span data-stu-id="5936f-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="5936f-133">Näitä tietoja ovat esimerkiksi sähköpostiosoite, nimi ja kaupunki.</span><span class="sxs-lookup"><span data-stu-id="5936f-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="5936f-134">**Mahdolliset kiinnostuksen kohteet, Mahdolliset tuotemerkit:** Osoittaa, onko ensimmäisen osapuolen rikastaminen määritetty.</span><span class="sxs-lookup"><span data-stu-id="5936f-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="5936f-135">Ilmaisee mahdolliset kiinnostuksen kohteet ja brändiaffiniteetit, joita voi olla tämän asiakkaan profiilia muistuttavalla asiakkaalla.</span><span class="sxs-lookup"><span data-stu-id="5936f-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="5936f-136">Lisätietoja on kohdassa [Asiakasprofiilien rikastaminen brändin ja kiinnostuksen kohteiden affiniteeteillä](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="5936f-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="5936f-137">**Mittarit:** Näyttää tietyn tyyppisen mittareiden määrittäminen: asiakasmääritemittarit.</span><span class="sxs-lookup"><span data-stu-id="5936f-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="5936f-138">Ne sisältävät asiakkaisiin liittyvät lasketut tunnusluvut yksittäisen asiakkaan tasolla.</span><span class="sxs-lookup"><span data-stu-id="5936f-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="5936f-139">Lisätietoja on kohdassa [Mittarien määrittäminen ja hallinta](measures.md).</span><span class="sxs-lookup"><span data-stu-id="5936f-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="5936f-140">**Aktiviteetin aikajana:** Näyttää mahdolliset määritetyt aktiviteetit.</span><span class="sxs-lookup"><span data-stu-id="5936f-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="5936f-141">Aikajananäkymässä on kyseisen asiakkaan kronologisesti lajitellut aktiviteetit viimeisimmistä aktiviteetista alkaen.</span><span class="sxs-lookup"><span data-stu-id="5936f-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="5936f-142">Lisätietoja on kohdassa [Asiakasaktiviteetit](activities.md).</span><span class="sxs-lookup"><span data-stu-id="5936f-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="5936f-143">Palaa asiakkaan hakusivulla valitsemalla **Palaa Asiakkaat-kohtaan**.</span><span class="sxs-lookup"><span data-stu-id="5936f-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5936f-144">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="5936f-144">Next steps</span></span>

<span data-ttu-id="5936f-145">[Voit lisätä enemmän tietolähteitä](data-sources.md) tai [luoda asiakassegmenttejä](segments.md).</span><span class="sxs-lookup"><span data-stu-id="5936f-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>
