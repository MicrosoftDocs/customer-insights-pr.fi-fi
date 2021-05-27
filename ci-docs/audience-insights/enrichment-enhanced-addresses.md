---
title: Osoitteiden parannuksen rikastus
description: Rikasta ja normalisoi asiakasprofiilien osoitetietoja Microsoftin malleilla.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965574"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="e7a4c-103">Asiakasprofiilien rikastaminen parannetuilla osoitteilla</span><span class="sxs-lookup"><span data-stu-id="e7a4c-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="e7a4c-104">Tietojen osoitteet voivat olla rakenteettomia, epätäydellisiä tai virheellisiä.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="e7a4c-105">Microsoftin mallien avulla voit normalisoida ja rikastaa osoitteita [Common Data Model -muotoon](/common-data-model/schema/core/applicationcommon/address) tarkkuuden ja merkityksellisten tietojen parantamiseksi.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="e7a4c-106">Miten parannamme osoitteita</span><span class="sxs-lookup"><span data-stu-id="e7a4c-106">How we enhance addresses</span></span>

<span data-ttu-id="e7a4c-107">Mallimme käy läpi kaksivaiheisen prosessin osoitteen parantamiseksi.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="e7a4c-108">Ensinnäkin se jäsentää osoitteen tunnistaakseen sen komponentit ja asettaa ne jäsenneltyyn muotoon.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="e7a4c-109">Sitten käytämme tekoälyä osoitteen arvojen korjaamiseen, täydentämiseen ja standardointiin.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="e7a4c-110">Esimerkiksi</span><span class="sxs-lookup"><span data-stu-id="e7a4c-110">Example</span></span>

<span data-ttu-id="e7a4c-111">Osoitetiedot saattavat olla epästandardissa muodossa ja sisältää kirjoitusvirheitä.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="e7a4c-112">Malli voi korjata nämä ongelmat ja luoda yhdenmukaisia osoitteita yhtenäisiin asiakasprofiileihin.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="e7a4c-113">Rajoitukset</span><span class="sxs-lookup"><span data-stu-id="e7a4c-113">Limitations</span></span>

<span data-ttu-id="e7a4c-114">Parannetut osoitteet toimivat vain niiden arvojen kanssa, joka ovat jo olemassa käsitellyissä osoitetiedoissa.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="e7a4c-115">Malli ei:</span><span class="sxs-lookup"><span data-stu-id="e7a4c-115">The model doesn't:</span></span> 

1. <span data-ttu-id="e7a4c-116">Tarkista, onko osoite kelvollinen osoite.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="e7a4c-117">Tarkista, onko mitkään arvoista, kuten postinumerot tai katujen nimet, kelvollisia.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="e7a4c-118">Muuta arvoja, joita se ei tunnista.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="e7a4c-119">Malli käyttää koneoppimiseen perustuvia tekniikoita osoitteiden parantamiseen.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="e7a4c-120">Vaikka käytämme korkeaa luottamuskynnystä, kun malli muuttaa syöttöarvoa 100%: n tarkkuutta ei taata, kuten ei missään koneoppimismallissa.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="e7a4c-121">Tuetut maat tai alueet</span><span class="sxs-lookup"><span data-stu-id="e7a4c-121">Supported countries or regions</span></span>

<span data-ttu-id="e7a4c-122">Tuemme tällä hetkellä rikastavia osoitteita näissä maissa tai näillä alueilla:</span><span class="sxs-lookup"><span data-stu-id="e7a4c-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="e7a4c-123">Australia</span><span class="sxs-lookup"><span data-stu-id="e7a4c-123">Australia</span></span>
- <span data-ttu-id="e7a4c-124">Kanada</span><span class="sxs-lookup"><span data-stu-id="e7a4c-124">Canada</span></span>
- <span data-ttu-id="e7a4c-125">Yhdistynyt kuningaskunta</span><span class="sxs-lookup"><span data-stu-id="e7a4c-125">United Kingdom</span></span>
- <span data-ttu-id="e7a4c-126">Yhdysvallat</span><span class="sxs-lookup"><span data-stu-id="e7a4c-126">United States</span></span>

<span data-ttu-id="e7a4c-127">Osoitteissa on oltava maa- tai aluearvo.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="e7a4c-128">Emme käsittele osoitteita maille tai alueille, joita ei tueta, eikä osoitteille, joille ei ole annettu maata tai aluetta.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="e7a4c-129">Määritä rikastus</span><span class="sxs-lookup"><span data-stu-id="e7a4c-129">Configure the enrichment</span></span>

1. <span data-ttu-id="e7a4c-130">Siirry kohtaan **Tiedot** > **Täydentäminen**.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="e7a4c-131">Valitse **Rikasta tietojani** **Rikasta osoitteita** -ruudussa.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Näyttökuva Parannetut osoitteet -ruudusta.":::

1. <span data-ttu-id="e7a4c-133">Valitse **Asiakkaan tietojoukko** ja valitse entiteetti, joka sisältää rikastettavat osoitteet.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="e7a4c-134">Voit valita *Asiakas*-entiteetin rikastaaksesi kaikkien asiakasprofiiliesi osoitteita, tai valita segmenttientiteetin rikastaaksesi osoitteita vain segmentin sisältämissä asiakasprofiileissa.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="e7a4c-135">Valitse, kuinka osoitteet muotoillaan tietojoukossa.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="e7a4c-136">Valitse **Yksimääritteinen osoite**, jos tietojen osoitteet käyttävät yhtä kenttää.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="e7a4c-137">Valitse **Monimääritteinen osoite**, jos tietojen osoitteet käyttävät useampaa kuin yhtä kenttää.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e7a4c-138">Maa tai alue on pakollinen sekä yhden että usean määritteen osoitteessa.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="e7a4c-139">Osoitteita, jotka eivät sisällä kelvollisia tai tuettuja maan tai alueen arvoja, ei rikasteta</span><span class="sxs-lookup"><span data-stu-id="e7a4c-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="e7a4c-140">Yhdistä yhdistetyn asiakasentiteetin osoitekentät.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Parannetun osoitteen kenttien yhdistämissivu.":::

1. <span data-ttu-id="e7a4c-142">Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="e7a4c-143">Anna rikastuksen ja tulosentiteetin nimi.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="e7a4c-144">Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="e7a4c-145">Rikastamisen tulokset</span><span class="sxs-lookup"><span data-stu-id="e7a4c-145">Enrichment results</span></span>

<span data-ttu-id="e7a4c-146">Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e7a4c-147">Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e7a4c-148">Käsittelyaika riippuu asiakastietojen koosta.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="e7a4c-149">Kun rikastamisprosessi on valmis, voit tarkastella juuri rikastettujen asiakasprofiilien tietoja valitsemalla **Omat rikastukset**.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="e7a4c-150">Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e7a4c-151">Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e7a4c-152">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="e7a4c-152">Next steps</span></span>

<span data-ttu-id="e7a4c-153">Voit hyödyntää rikastettuja asiakastietoja.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e7a4c-154">Voit antaa asiakkaille mukautettuja kokemuksia luomalla [segmenttejä](segments.md) ja [mittoja](measures.md) sekä [viemällä tietoja](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e7a4c-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
