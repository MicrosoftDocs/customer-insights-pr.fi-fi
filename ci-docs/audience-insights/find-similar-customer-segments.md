---
title: Samankaltaisten asiakkaiden etsiminen tekoälyn avulla
description: Etsi samankaltaisia asiakassegmenttejä tekoälyn avulla.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: b9b2e7fa862b595c6a364a7208e42295b4f9df83
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268866"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="899cc-103">Samankaltaiset asiakkaat (esiversio)</span><span class="sxs-lookup"><span data-stu-id="899cc-103">Similar Customers (preview)</span></span>

<span data-ttu-id="899cc-104">Tämän ominaisuuden avulla voit etsiä samanlaisia asiakkaita asiakaskunnasta käyttämällä tekoälyä.</span><span class="sxs-lookup"><span data-stu-id="899cc-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="899cc-105">Tämän ominaisuuden käyttäminen edellyttää vähintään yhden segmentin luomista.</span><span class="sxs-lookup"><span data-stu-id="899cc-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="899cc-106">Laajentamalla aiemmin luodun segmentin ehtoja voit etsiä segmentin kanssa samankaltaisia asiakkaita.</span><span class="sxs-lookup"><span data-stu-id="899cc-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="899cc-107">*Etsi samankaltaiset asiakkaat* käyttää automaattisia menetelmiä tietojen arviointiin ja ennusteissa, joten sitä voidaan käyttää profilointimenetelmänä, koska kyseinen käsite on määritetty yleisessä tietosuoja-asetuksessa (GDPR).</span><span class="sxs-lookup"><span data-stu-id="899cc-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="899cc-108">Asiakkaat käyttävät tätä toimintoa tietojen käsittelyyn. GDPR tai muut lait tai säädökset saattavat ohjata toiminnon käyttöä.</span><span class="sxs-lookup"><span data-stu-id="899cc-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="899cc-109">Olet vastuussa siitä, että Dynamics 365 Customer Insightsin käyttäminen, myös ennusteiden käyttäminen, on kaikkien lakien ja säädösten mukaista. Näihin kuuluvat yksityisyyteen, henkilökohtaisiin tietoihin, biometrisiin tietoihin, tietosuojaan ja viestintäsalaisuuteen liittyvät lait.</span><span class="sxs-lookup"><span data-stu-id="899cc-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="899cc-110">Samankaltaisten asiakkaiden löytäminen</span><span class="sxs-lookup"><span data-stu-id="899cc-110">Finding similar customers</span></span>

1. <span data-ttu-id="899cc-111">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Segmentit** ja valitse sitten segmentti, johon uusi segmentti perustuu.</span><span class="sxs-lookup"><span data-stu-id="899cc-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="899cc-112">Tämä on *lähdesegmentti*.</span><span class="sxs-lookup"><span data-stu-id="899cc-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="899cc-113">Valitse toimintoriviltä **Etsi samankaltaisia asiakkaita**.</span><span class="sxs-lookup"><span data-stu-id="899cc-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="899cc-114">Tarkista uuden segmentin ehdotettu nimi ja muuta sitä tarvittaessa.</span><span class="sxs-lookup"><span data-stu-id="899cc-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="899cc-115">Tarkista kentät, jotka määrittävät uuden segmentin.</span><span class="sxs-lookup"><span data-stu-id="899cc-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="899cc-116">Näissä kentissä määritetään, millä perusteella järjestelmä yrittää etsiä samanlaisia asiakkaita lähdesegmentistä.</span><span class="sxs-lookup"><span data-stu-id="899cc-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="899cc-117">Järjestelmä valitsee oletusarvoisesti suositellut kentät.</span><span class="sxs-lookup"><span data-stu-id="899cc-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="899cc-118">Kentät, jotka voivat merkittävästi vähentää mallin tehokkuutta, jätetään automaattisesti pois:</span><span class="sxs-lookup"><span data-stu-id="899cc-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="899cc-119">Kentät, joiden tieto tyyppi on jokin seuraavista: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="899cc-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="899cc-120">Kentät, joiden kardinaliteetti (kentän elementtien määrä) on alle 2 tai yli 30</span><span class="sxs-lookup"><span data-stu-id="899cc-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="899cc-121">Valitse, haluatko sisällyttää **Kaikki asiakkaat** vai vain **tietyn aiemmin luodun segmentin** asiakkaat uuteen segmenttiin.</span><span class="sxs-lookup"><span data-stu-id="899cc-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="899cc-122">Sulje pois asiakkaat lähdesegmentissä valitsemalla **Jätä pois kaikki lähdesegmentissä** -valintaruutu.</span><span class="sxs-lookup"><span data-stu-id="899cc-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="899cc-123">Oletusarvon mukaan järjestelmä ehdottaa, että tulosteessa on vain 20 prosenttia kohdeyleisöstä.</span><span class="sxs-lookup"><span data-stu-id="899cc-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="899cc-124">Muokkaa tätä raja-arvoa tarpeen mukaan.</span><span class="sxs-lookup"><span data-stu-id="899cc-124">Edit this threshold as needed.</span></span> <span data-ttu-id="899cc-125">Kynnyksen suurentaminen vähentää tarkkuutta.</span><span class="sxs-lookup"><span data-stu-id="899cc-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="899cc-126">Aloita binaarisen luokituksen tehtävä (koneoppimisen menetelmä), joka analysoi tietojoukon, valitsemalla sivun alareunasta **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="899cc-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="899cc-127">Samanlaisen segmentin tarkasteleminen</span><span class="sxs-lookup"><span data-stu-id="899cc-127">View the similar segment</span></span>

<span data-ttu-id="899cc-128">Kun olet käsitellyt samankaltaisen segmentin, löydät uuden segmentin **Segmentit**-sivulta.</span><span class="sxs-lookup"><span data-stu-id="899cc-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="899cc-129">![Samankaltainen asiakassegmentti](media/expanded-segment.png "Samankaltainen asiakassegmentti")</span><span class="sxs-lookup"><span data-stu-id="899cc-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="899cc-130">Avaa segmentin erittely valitsemalla toiminto palkissa **Näytä**.</span><span class="sxs-lookup"><span data-stu-id="899cc-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="899cc-131">Tässä näkymässä on tietoja [samankaltaisuuksien tulosten](#about-similarity-scores) jakautumisesta.</span><span class="sxs-lookup"><span data-stu-id="899cc-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="899cc-132">Löydät myös samankaltaisuuksien pistearvot kohdassa **Segmentin jäsenten esikatselu**.</span><span class="sxs-lookup"><span data-stu-id="899cc-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="899cc-133">Samankaltaisen segmentin tuloksen käyttäminen</span><span class="sxs-lookup"><span data-stu-id="899cc-133">Use the output of a similar segment</span></span>

<span data-ttu-id="899cc-134">Voit [käsitellä samanlaisen segmentin tulosta](segments.md) samalla tavalla kuin muitakin segmenttejä.</span><span class="sxs-lookup"><span data-stu-id="899cc-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="899cc-135">Voit esimerkiksi viedä segmentin tai luoda mittarin.</span><span class="sxs-lookup"><span data-stu-id="899cc-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="899cc-136">Samanlaisen segmentin päivittäminen ja muokkaaminen</span><span class="sxs-lookup"><span data-stu-id="899cc-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="899cc-137">Jos haluat päivittää samanlaisen segmentin, valitse se **Segmentit**-sivulla ja valitse toimintoriviltä **Päivitä**.</span><span class="sxs-lookup"><span data-stu-id="899cc-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="899cc-138">Jos muokkaat samankaltaista segmenttiä, tiedot käsitellään uudelleen.</span><span class="sxs-lookup"><span data-stu-id="899cc-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="899cc-139">Aiemmin luotu segmentti päivittyy päivitetyillä tiedoilla.</span><span class="sxs-lookup"><span data-stu-id="899cc-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="899cc-140">Jos haluat muokata samanlaisen segmentin, valitse se **Segmentit**-sivulla ja valitse toimintoriviltä **Muokkaa**.</span><span class="sxs-lookup"><span data-stu-id="899cc-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="899cc-141">Ota muutokset käyttöön ja aloita käsittely valitsemalla **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="899cc-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="899cc-142">Samanlaisen segmentin poistaminen</span><span class="sxs-lookup"><span data-stu-id="899cc-142">Delete a similar segment</span></span>

<span data-ttu-id="899cc-143">Jos haluat poistaa samanlaisen segmentin, valitse se **Segmentit**-sivulla ja valitse toimintoriviltä **Poista**.</span><span class="sxs-lookup"><span data-stu-id="899cc-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="899cc-144">Vahvista sitten poisto.</span><span class="sxs-lookup"><span data-stu-id="899cc-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="899cc-145">Tietoja samanlaisuuden pisteytyksestä</span><span class="sxs-lookup"><span data-stu-id="899cc-145">About similarity scores</span></span>

<span data-ttu-id="899cc-146">Binaariluokittelun koneoppimismalli määrittää pistemäärän samanlaisessa segmentissä oleville asiakkaille.</span><span class="sxs-lookup"><span data-stu-id="899cc-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="899cc-147">Pistemäärä perustuu lähdesegmentin asiakkaiden samankaltaisuuteen.</span><span class="sxs-lookup"><span data-stu-id="899cc-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="899cc-148">Ne asiakkaat, joiden samankaltaisuuspisteet ovat alle 0,55, ovat asiakkaita, jotka luokitellaan lähdesegmentin asiakkaiden kanssa määritteellä *ei samankaltainen*.</span><span class="sxs-lookup"><span data-stu-id="899cc-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="899cc-149">Samankaltaisuuspisteet välillä 0,55–0,7 luokitellaan *hieman samankaltaisiksi*</span><span class="sxs-lookup"><span data-stu-id="899cc-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="899cc-150">Samankaltaisuuspisteet välillä 0,7–0,85 luokitellaan *samankaltaisiksi*</span><span class="sxs-lookup"><span data-stu-id="899cc-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="899cc-151">Samankaltaisuuspisteet välillä 0,85–1 ovat asiakkaita, jotka luokitellaan *hyvin samankaltaisiksi*</span><span class="sxs-lookup"><span data-stu-id="899cc-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="899cc-152">Asiakkaat, joilla samankaltaisuutta koskevia pisteitä on alle 0,4, eivät sisälly mallin tuotokseen.</span><span class="sxs-lookup"><span data-stu-id="899cc-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="899cc-153">Järjestelmä ei pidä niitä tarpeeksi samankaltaisina lähdesegmentin kanssa.</span><span class="sxs-lookup"><span data-stu-id="899cc-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]