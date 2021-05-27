---
title: Aktiviteetin perusteella ehdotetut segmentit.
description: Anna koneoppimisen auttaa sinua löytämään uusia ja mielenkiintoisia segmenttejä asiakasaktiviteettien perusteella.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034067"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="58238-103">Aktiviteettitietojen perusteella ehdotetut segmentit (esiversio)</span><span class="sxs-lookup"><span data-stu-id="58238-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="58238-104">Löydä mielenkiintoisia asiakassegmenttejä asiakasaktiviteettitietojen perusteella, jota Customer Insights käsittelee.</span><span class="sxs-lookup"><span data-stu-id="58238-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="58238-105">Esimerkkejä aktiviteettitiedoista ovat tapahtumat, tukipuhelun kesto, ostot tai palautukset.</span><span class="sxs-lookup"><span data-stu-id="58238-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="58238-106">Aktiviteettitiedoista analysoidaan segmenttien ehdottamista varten niiden viimeaikaisuutta, toistuvuutta ja rahallista arvoa (tai kestoa).</span><span class="sxs-lookup"><span data-stu-id="58238-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="58238-107">Vaihtoehtoisesti voidaan luoda [ehdotettuja segmenttejä mittarin parantamista varten tai ymmärryksen parantamiseksi siitä, mikä vaikuttaa määritteeseen](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="58238-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Ehdotetut segmentit -välilehti, jossa näkyvät aktiviteettiin perustuvat ja määritteisiin perustuvat segmenttiehdotukset.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="58238-109">Luokittele asiakkaat aktiviteetin mukaan</span><span class="sxs-lookup"><span data-stu-id="58238-109">Categorize customers by activity</span></span>

<span data-ttu-id="58238-110">Customer Insightsissa saatavilla olevien [aktiviteettitietojen](activities.md) avulla voimme luoda asiakasryhmiä edustavia ehdotuksia:</span><span class="sxs-lookup"><span data-stu-id="58238-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="58238-111">aktiivisimmat asiakkaat</span><span class="sxs-lookup"><span data-stu-id="58238-111">most active customers</span></span> 
- <span data-ttu-id="58238-112">asiakkaat, jotka ovat tehneet eniten ostoksia</span><span class="sxs-lookup"><span data-stu-id="58238-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="58238-113">asiakkaat, jotka tuottivat eniten tuloja</span><span class="sxs-lookup"><span data-stu-id="58238-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="58238-114">asiakkaat, jotka eivät ole olleet aktiivisia viime aikoina</span><span class="sxs-lookup"><span data-stu-id="58238-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="58238-115">asiakkaat, jotka ovat usein vuorovaikutuksessa yrityksesi kanssa</span><span class="sxs-lookup"><span data-stu-id="58238-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="58238-116">Jos sinulla on vähittäiskauppa, voit selvittää, mitkä asiakkaat tuovat eniten tuottoa, ja palkita heidät kupongilla.</span><span class="sxs-lookup"><span data-stu-id="58238-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="58238-117">Voit myös tunnistaa satunnaisia asiakkaita ja tarjota heille liittymistä palkinto-ohjelmaan, jotta he vierailisivat yrityksessäsi useammin.</span><span class="sxs-lookup"><span data-stu-id="58238-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="58238-118">Jos olet julkisen terveydenhuollon alalla ja tavoitteenasi on minimoida yksittäisten potilaiden kulut.</span><span class="sxs-lookup"><span data-stu-id="58238-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="58238-119">Yksi tapa tehdä se voisi olla toistuvien käyntien vähentäminen tarjoamalla parasta mahdollista hoitoa mahdollisimman harvoilla käynneillä.</span><span class="sxs-lookup"><span data-stu-id="58238-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="58238-120">Tässä tapauksessa tavoitteenasi on pitää käyntitiheys alhaisena ja minimoida potilaiden toistuvat kustannukset.</span><span class="sxs-lookup"><span data-stu-id="58238-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="58238-121">Tai voit tunnistaa sellaisten potilaiden segmentit, joilla on usein toistuvia tapaamisia ja korkeat toistuvat kustannukset ja analysoida näitä tapauksia yksilön hoidon parantamiseksi.</span><span class="sxs-lookup"><span data-stu-id="58238-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="58238-122">Pakolliset tiedot</span><span class="sxs-lookup"><span data-stu-id="58238-122">Required data</span></span>

<span data-ttu-id="58238-123">Ehdotukset luodaan valittujen syötetietojen perusteella.</span><span class="sxs-lookup"><span data-stu-id="58238-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="58238-124">Asiakasprofiilit: Kaikki asiakkaat tai tietyn segmentin jäsenet.</span><span class="sxs-lookup"><span data-stu-id="58238-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="58238-125">Ajanjakso: Viime kuussa, viime vuonna tai millä tahansa mukautetulla aikavälillä.</span><span class="sxs-lookup"><span data-stu-id="58238-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="58238-126">Aktiviteettityyppi: ostot, vähittäismyyntitapahtumat, verkkotapahtumat, asiakastuen palvelupyynnöt, tilaukset ja niin edelleen.</span><span class="sxs-lookup"><span data-stu-id="58238-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="58238-127">Customer Insights -entiteetti, joka sisältää aktiviteettitiedot: UnifiedActivity-entiteetti tai tietyn aktiviteetin entiteetti.</span><span class="sxs-lookup"><span data-stu-id="58238-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="58238-128">Sisällytettävät dimensiot: Viimeaikaisuus, toistuvuus tai rahallinen dimensio riippuen yrityksesi vaatimuksista.</span><span class="sxs-lookup"><span data-stu-id="58238-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="58238-129">Ehdotettujen segmenttien luominen</span><span class="sxs-lookup"><span data-stu-id="58238-129">Generate suggested segments</span></span>

1. <span data-ttu-id="58238-130">Valitse **Segmentit**.</span><span class="sxs-lookup"><span data-stu-id="58238-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="58238-131">Valitse **Ehdotukset (esiversio)** -välilehti.</span><span class="sxs-lookup"><span data-stu-id="58238-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="58238-132">Valitse **Etsi uusia ehdotuksia** ja valitse **Näytä tai ennakoi asiakkaan käyttäytymistä**.</span><span class="sxs-lookup"><span data-stu-id="58238-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="58238-133">Suorita ohjattu käyttökokemus valitsemalla **Käynnistä**.</span><span class="sxs-lookup"><span data-stu-id="58238-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Ohjatun määritystoiminnon ensimmäinen vaihe ehdotetulle segmentille aktiviteetin perusteella.":::

1. <span data-ttu-id="58238-135">Anna tarvittavat syötetiedot ja valitse **Seuraava** jatkaaksesi.</span><span class="sxs-lookup"><span data-stu-id="58238-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="58238-136">Valitse asiakkaat: Sisällytä kaikki asiakkaat tai tietty segmentti.</span><span class="sxs-lookup"><span data-stu-id="58238-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="58238-137">Valitse aktiviteetti: Valitse aktiviteettityyppi ja aktiviteettia kuvaavat entiteetit.</span><span class="sxs-lookup"><span data-stu-id="58238-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="58238-138">Asetukset: Määritä huomioon otettava ajanjakso sekä ehdotuksiin vaikuttavat tekijät ja yhdistä määritteet.</span><span class="sxs-lookup"><span data-stu-id="58238-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="58238-139">Tarkista syötteesi ja valitse **Suorita** suorittaaksesi mallin ja luodaksesi ehdotuksia.</span><span class="sxs-lookup"><span data-stu-id="58238-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="58238-140">Asiakasprofiilien ja valittujen aktiviteettien määrästä riippuen sen suorittamiseen voi mennä muutama minuutti.</span><span class="sxs-lookup"><span data-stu-id="58238-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="58238-141">Ehdotusten luomisen jälkeen niitä voidaan suodattaa kiinnostavimman dimension tai arvon perusteella.</span><span class="sxs-lookup"><span data-stu-id="58238-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="58238-142">Ehdotetun segmentin tietojen tarkasteleminen</span><span class="sxs-lookup"><span data-stu-id="58238-142">View details of a suggested segment</span></span>

<span data-ttu-id="58238-143">Kun ehdotukset on luotu, luettelo niistä näkyy **Segmentit** > **Ehdotukset (esiversio)** **Aktiviteetteihin perustuvat ehdotukset** -osassa.</span><span class="sxs-lookup"><span data-stu-id="58238-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Laajennettu sivuruutu, jossa näkyvät ehdotetun segmentin yksityiskohtaiset tiedot.":::

<span data-ttu-id="58238-145">Valitse **Katso ehdotus** ehdotetusta segmentistä, jos haluat tarkastella segmentin tietoja.</span><span class="sxs-lookup"><span data-stu-id="58238-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="58238-146">Sivuruudussa on tietoja, kuten kunkin dimension laajuus kohderyhmään verrattuna.</span><span class="sxs-lookup"><span data-stu-id="58238-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="58238-147">Segmentin mahdollisten jäsenten määrä ja vastaava prosenttiosuus kaikista asiakkaista näkyvät korostettuina.</span><span class="sxs-lookup"><span data-stu-id="58238-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="58238-148">Jos haluat säilyttää ehdotuksen segmenttinä, valitse **Luo segmentti**.</span><span class="sxs-lookup"><span data-stu-id="58238-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="58238-149">Ehdotuksen tallentaminen segmenttinä</span><span class="sxs-lookup"><span data-stu-id="58238-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="58238-150">Siirry kohtaan **Segmentit** > **Ehdotukset (esiversio)**.</span><span class="sxs-lookup"><span data-stu-id="58238-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="58238-151">Valitse segmentti, jonka haluat tallentaa.</span><span class="sxs-lookup"><span data-stu-id="58238-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="58238-152">Valitse sivuruudussa **Luo segmentti**.</span><span class="sxs-lookup"><span data-stu-id="58238-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="58238-153">Segmentin tallentamisen jälkeen se näkyy segmenttiluettelossa **Kaikki segmentit** -välilehdellä. Se voidaan nyt [päivittää tai poistaa, kuten mikä tahansa muu segmentti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="58238-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="58238-154">Et voi muokata segmentin tietoja.</span><span class="sxs-lookup"><span data-stu-id="58238-154">You can't edit the segment details.</span></span> <span data-ttu-id="58238-155">Voit kuitenkin muuttaa ehdotusten syötteiden ehtoja ja luoda erilaisia ehdotuksia.</span><span class="sxs-lookup"><span data-stu-id="58238-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="58238-156">Ehdotusjoukon päivittäminen tai muokkaaminen</span><span class="sxs-lookup"><span data-stu-id="58238-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="58238-157">Siirry kohtaan **Segmentit**  > **Ehdotukset (esiversio)** ja etsi segmenttiä **Aktiviteetteihin perustuvat ehdotukset** -osasta.</span><span class="sxs-lookup"><span data-stu-id="58238-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="58238-158">Valitse **Päivitä ehdotukset**, jos haluat päivittää ehdotukset ja säilyttää määritetyt määritteet.</span><span class="sxs-lookup"><span data-stu-id="58238-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="58238-159">Voit myös valita **Muokkaa ehdotuksia** määritysten muokkaamista varten.</span><span class="sxs-lookup"><span data-stu-id="58238-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="58238-160">Järjestelmä suorittaa prosessin uudelleen, luo segmenttiehdotukset viimeisimpien tietojen perusteella ja korvaa nykyiset ehdotukset.</span><span class="sxs-lookup"><span data-stu-id="58238-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
