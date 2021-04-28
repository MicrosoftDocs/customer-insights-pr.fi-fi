---
title: Rikasta asiakasprofiileja Microsoftin tietojen avulla
description: Microsoftin omistamista tiedoista voit rikastaa asiakastietoja tuotemerkkien ja kiinnostuksen kohteiden tiedoilla.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896598"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="e6a35-103">Asiakasprofiilien täydentäminen tuotemerkillä ja kiinnostuksen kohteilla (esiversio)</span><span class="sxs-lookup"><span data-stu-id="e6a35-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="e6a35-104">Microsoftin omistamista tiedoista voit rikastaa asiakastietoja tuotemerkkien ja kiinnostuksen kohteiden tiedoilla.</span><span class="sxs-lookup"><span data-stu-id="e6a35-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="e6a35-105">Nämä affiniteetit määritetään asiakkaiden demografiatietoja muistuttavia ihmisiä koskevien tietojen perusteella.</span><span class="sxs-lookup"><span data-stu-id="e6a35-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="e6a35-106">Nämä tiedot auttavat ymmärtämään ja segmentoimaan asiakkaita paremmin sen perusteella, mikä on heidän affiniteettinsa tiettyjen brändien ja kiinnostuksenkohteiden osalta.</span><span class="sxs-lookup"><span data-stu-id="e6a35-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="e6a35-107">Valitse käyttäjäryhmän merkityksillisissä tiedoissa **Tiedot** > **Rikastaminen**, jos haluat [määrittää ja tarkastella rikastuksia](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="e6a35-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="e6a35-108">Jos haluat määrittää tuotemerkin affiniteettien täydentämisen, siirry **Tutustu**-välilehteen ja valitse **Täydennä omat tiedot** **Tuotemerkit**-ruudussa.</span><span class="sxs-lookup"><span data-stu-id="e6a35-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="e6a35-109">Jos haluat määrittää kiinnostuksen kohteen affiniteettien täydentämisen, siirry **Tutustu**-välilehteen ja valitse **Täydennä omat tiedot** **Kiinnostuksen kohteet** -ruudussa.</span><span class="sxs-lookup"><span data-stu-id="e6a35-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e6a35-110">![Tuotemerkit- ja Kiinnostuksen kohteet -ruudut](media/BrandsInterest-tile-Hub.png "Tuotemerkit- ja Kiinnostuksen kohteet -ruudut")</span><span class="sxs-lookup"><span data-stu-id="e6a35-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="e6a35-111">Miten määritetään affiniteetit</span><span class="sxs-lookup"><span data-stu-id="e6a35-111">How we determine affinities</span></span>

<span data-ttu-id="e6a35-112">Microsoftin online-hakutietojen avulla voidaan etsiä affiniteetteja tuotemerkkejä ja kiinnostuksen kohteita varten eri demografisille segmenteille (jotka on määritetty iän, sukupuolen tai sijainnin mukaan).</span><span class="sxs-lookup"><span data-stu-id="e6a35-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="e6a35-113">Tuotemerkin tai kiinnostuksen kohteiden online-hakujen määrä määrittää, kuinka paljon demografisessa segmentissä on verrattuna muihin segmentteihin kyseisen tuotemerkin tai kiinnotuksen kohteen merkitystä.</span><span class="sxs-lookup"><span data-stu-id="e6a35-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span> <span data-ttu-id="e6a35-114">tuotemerkki tai kiinnostuksen kohde.</span><span class="sxs-lookup"><span data-stu-id="e6a35-114">brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="e6a35-115">Affiniteettitaso ja pistemäärä</span><span class="sxs-lookup"><span data-stu-id="e6a35-115">Affinity level and score</span></span>

<span data-ttu-id="e6a35-116">Jokaisessa rikastetussa asiakasprofiilissa on kaksi toisiinsa liittyvää arvoa. Ne ovat affiniteettitaso ja affiniteettipisteet.</span><span class="sxs-lookup"><span data-stu-id="e6a35-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="e6a35-117">Nämä arvot määrittävät, miten vahva tuotemerkin tai kiinnostuksen kohteen kyseisen profiilin demografisen segmentin affiniteetti on verrattuna muihin demografisiin segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="e6a35-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="e6a35-118">*Affiniteettitaso* koostuu neljästä tasosta. *Affiniteettipisteet* lasketaan 100 pisteen aseteikolla, joka yhdistetään affiniteettitasoihin.</span><span class="sxs-lookup"><span data-stu-id="e6a35-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="e6a35-119">Affiniteettitaso</span><span class="sxs-lookup"><span data-stu-id="e6a35-119">Affinity level</span></span> |<span data-ttu-id="e6a35-120">Affiniteetin pistemäärä</span><span class="sxs-lookup"><span data-stu-id="e6a35-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="e6a35-121">Erittäin korkea</span><span class="sxs-lookup"><span data-stu-id="e6a35-121">Very high</span></span>     | <span data-ttu-id="e6a35-122">85–100</span><span class="sxs-lookup"><span data-stu-id="e6a35-122">85-100</span></span>       |
|<span data-ttu-id="e6a35-123">Suuri</span><span class="sxs-lookup"><span data-stu-id="e6a35-123">High</span></span>     | <span data-ttu-id="e6a35-124">70–84</span><span class="sxs-lookup"><span data-stu-id="e6a35-124">70-84</span></span>        |
|<span data-ttu-id="e6a35-125">Keskikokoinen</span><span class="sxs-lookup"><span data-stu-id="e6a35-125">Medium</span></span>     | <span data-ttu-id="e6a35-126">35–69</span><span class="sxs-lookup"><span data-stu-id="e6a35-126">35-69</span></span>        |
|<span data-ttu-id="e6a35-127">Matala</span><span class="sxs-lookup"><span data-stu-id="e6a35-127">Low</span></span>     | <span data-ttu-id="e6a35-128">1–34</span><span class="sxs-lookup"><span data-stu-id="e6a35-128">1-34</span></span>        |

<span data-ttu-id="e6a35-129">Affiniteettia mittaavan tarkkuuden mukaan voit käyttää affiniteettitasoa tai pistemäärää.</span><span class="sxs-lookup"><span data-stu-id="e6a35-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="e6a35-130">Affiniteettipisteet antavat aiempaa tarkemman hallinnan.</span><span class="sxs-lookup"><span data-stu-id="e6a35-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="e6a35-131">Tuetut maat ja alueet</span><span class="sxs-lookup"><span data-stu-id="e6a35-131">Supported countries/regions</span></span>

<span data-ttu-id="e6a35-132">Seuraavia maita ja alueita tuetaan tällä hetkellä: Australia, Kanada (englanti), Ranska, Saksa, Yhdistyneet kuningaskunta tai Yhdysvallat (englanti).</span><span class="sxs-lookup"><span data-stu-id="e6a35-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="e6a35-133">Valitse maa avaamalla **Tuotemerkkien rikastus** tai **Kiinnostuksen kohteiden rikastus** ja valitse **Vaihda** **Maa tai alue** -kohdan vieressä.</span><span class="sxs-lookup"><span data-stu-id="e6a35-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="e6a35-134">Valitse **Maa- ja alueasetukset** -ruudussa vaihtoehto ja valitse **Käytä**.</span><span class="sxs-lookup"><span data-stu-id="e6a35-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="e6a35-135">Maan valintaan liittyvät vaikutukset</span><span class="sxs-lookup"><span data-stu-id="e6a35-135">Implications related to country selection</span></span>

- <span data-ttu-id="e6a35-136">Kun [valitset omia tuotemerkkejä](#define-your-brands-or-interests), järjestelmä antaa ehdotuksia valitun maan tai alueen perusteella.</span><span class="sxs-lookup"><span data-stu-id="e6a35-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="e6a35-137">Kun [valitset toimialaa](#define-your-brands-or-interests), saat tärkeimmät tuotemerkit tai kiinnostusten kohteet valitun maan tai alueen perusteella.</span><span class="sxs-lookup"><span data-stu-id="e6a35-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="e6a35-138">Kun [rikastat profiileja](#refresh-enrichment), rikastetaan kaikki asiakasprofiilit, joiden tiedot saadaan valituista tuotemerkeistä ja kiinnostusten kohteista.</span><span class="sxs-lookup"><span data-stu-id="e6a35-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="e6a35-139">Mukaan lukien profiilit, joita valittu maa tai alue ei sisällä.</span><span class="sxs-lookup"><span data-stu-id="e6a35-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="e6a35-140">Jos esimerkiksi valitsit Saksa, Yhdysvalloissa sijaitsevat profiilit rikastetaan, jos valituista tuotemerkeistä ja kiinnostuksen merkeistä on saatavilla tietoja Yhdysvalloissa.</span><span class="sxs-lookup"><span data-stu-id="e6a35-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="e6a35-141">Rikastaminen määritys</span><span class="sxs-lookup"><span data-stu-id="e6a35-141">Configure Enrichment</span></span>

<span data-ttu-id="e6a35-142">Ohjattu kokemus auttaa sinua rikastuksien määrityksessä.</span><span class="sxs-lookup"><span data-stu-id="e6a35-142">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="e6a35-143">Määritä tuotemerkit tai kiinnostuksen kohteet</span><span class="sxs-lookup"><span data-stu-id="e6a35-143">Define your brands or interests</span></span>

<span data-ttu-id="e6a35-144">Mahdolliset vaihtoehdot:</span><span class="sxs-lookup"><span data-stu-id="e6a35-144">Select one of the following options:</span></span>

- <span data-ttu-id="e6a35-145">**Toimiala**: Järjestelmä tunnistaa alasi tärkeimmät tuotemerkit tai kiinnostuksen kohteet ja täydentää asiakastietoja niiden kanssa.</span><span class="sxs-lookup"><span data-stu-id="e6a35-145">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="e6a35-146">**Valitse omasi**: Valitse enintään viisi kohdetta niiden tuotemerkkien tai kiinnostuksen kohteiden luettelosta, jotka ovat organisaation kannalta tärkeimmät.</span><span class="sxs-lookup"><span data-stu-id="e6a35-146">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="e6a35-147">Voit lisätä tuotemerkin tai kiinnostuksen kohteen kirjoittamalla sen syötealueeseen, jolloin saat ehdotuksia hakuehtojen perusteella.</span><span class="sxs-lookup"><span data-stu-id="e6a35-147">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="e6a35-148">Jos etsimääsi tuotemerkkiä tai kiinnostuksen kohteita ei luetella, lähetä meille palautetta **Ehdota**-linkin avulla.</span><span class="sxs-lookup"><span data-stu-id="e6a35-148">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="e6a35-149">Rikastusasetusten tarkasteleminen</span><span class="sxs-lookup"><span data-stu-id="e6a35-149">Review enrichment preferences</span></span>

<span data-ttu-id="e6a35-150">Tarkista oletusarvoiset rikastusasetukset ja päivitä ne tarpeen mukaan.</span><span class="sxs-lookup"><span data-stu-id="e6a35-150">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Näyttökuva rikastusasetusten ikkunasta.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="e6a35-152">Rikastettavan entiteetin valitseminen</span><span class="sxs-lookup"><span data-stu-id="e6a35-152">Select entity to enrich</span></span>

<span data-ttu-id="e6a35-153">Valitse **Rikastettu entiteetti** ja valitse tietojoukko, jonka haluat rikastaa Microsoftin yritystiedoilla.</span><span class="sxs-lookup"><span data-stu-id="e6a35-153">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="e6a35-154">Voit valita asiakasentiteetin, joka rikastaa kaikkia asiakasprofiileja, tai segmenttientiteetin, joka rikastaa vain segmenttiin sisältyviä asiakasprofiileja.</span><span class="sxs-lookup"><span data-stu-id="e6a35-154">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="e6a35-155">Yhdistä kenttäsi</span><span class="sxs-lookup"><span data-stu-id="e6a35-155">Map your fields</span></span>

<span data-ttu-id="e6a35-156">Yhdistä yhdistetyn asiakasentiteetin kentät, jos haluat määrittää demografisen segmentin, jota haluat järjestelmän käyttävän asiakastietojen rikastamisessa.</span><span class="sxs-lookup"><span data-stu-id="e6a35-156">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="e6a35-157">Yhdistä maa/alue ja vähintään syntymäaika- tai sukupuolimääritteet.</span><span class="sxs-lookup"><span data-stu-id="e6a35-157">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="e6a35-158">Lisäksi sinun on yhdistettävä vähintään yksi postitoimipaikka (ja osavaltio/provinssi) tai postinumero.</span><span class="sxs-lookup"><span data-stu-id="e6a35-158">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="e6a35-159">Määritä kenttien yhdistämismääritykset valitsemalla **Yhdistä**. Valitse **Käytä**, kun olet valmis.</span><span class="sxs-lookup"><span data-stu-id="e6a35-159">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="e6a35-160">Viimeistele kenttien yhdistäminen valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="e6a35-160">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="e6a35-161">Seuraavia muotoja ja arvoja tuetaan, kirjainkokoa ei oteta huomioon arvoissa:</span><span class="sxs-lookup"><span data-stu-id="e6a35-161">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="e6a35-162">**Syntymäaika**: Syntymäaika kannattaa muuntaa DateTime-tyypiksi tietojen käsittelyn aikana.</span><span class="sxs-lookup"><span data-stu-id="e6a35-162">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="e6a35-163">Vaihtoehtoisesti se voi olla [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) -muotoinen merkkijono vvvv-KK-pp tai vvvv-KK-ppTHH:mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="e6a35-163">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="e6a35-164">**Sukupuoli**: mies, nainen, tuntematon</span><span class="sxs-lookup"><span data-stu-id="e6a35-164">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="e6a35-165">**Postinumero**: Yhdysvalloissa viisinumeroinen postinumero, vakiopostinumero kaikkialla muualla</span><span class="sxs-lookup"><span data-stu-id="e6a35-165">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="e6a35-166">**Kaupunki**: kaupungin englanninkielinen nimi</span><span class="sxs-lookup"><span data-stu-id="e6a35-166">**City**: City name in English</span></span>
- <span data-ttu-id="e6a35-167">**Osavaltio/provinssi** : Kahden kirjaimen lyhenne Yhdysvalloissa ja Kanadassa.</span><span class="sxs-lookup"><span data-stu-id="e6a35-167">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="e6a35-168">Kahden tai kolmen kirjaimen lyhenne Australiassa.</span><span class="sxs-lookup"><span data-stu-id="e6a35-168">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="e6a35-169">Ei koske Ranskaa, Saksaa tai Yhdistynyttä kuningaskuntaa.</span><span class="sxs-lookup"><span data-stu-id="e6a35-169">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="e6a35-170">**Maa tai alue**:</span><span class="sxs-lookup"><span data-stu-id="e6a35-170">**Country/Region**:</span></span>

  - <span data-ttu-id="e6a35-171">US: Amerikan Yhdysvallat, Yhdysvallat, USA, US, Amerikka</span><span class="sxs-lookup"><span data-stu-id="e6a35-171">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="e6a35-172">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="e6a35-172">CA: Canada, CA</span></span>
  - <span data-ttu-id="e6a35-173">GB: Yhdistynyt kuningaskunta, UK, Iso-Britannia, GB, Ison-Britannian ja Pohjois-Irlannin yhdistynyt kuningaskunta, Ison-Britannian yhdistynyt kuningaskunta.</span><span class="sxs-lookup"><span data-stu-id="e6a35-173">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="e6a35-174">AU: Australia, AU, Australian liittovaltio</span><span class="sxs-lookup"><span data-stu-id="e6a35-174">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="e6a35-175">FR: Ranska, FR, Ranskan tasavalta</span><span class="sxs-lookup"><span data-stu-id="e6a35-175">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="e6a35-176">DE: Saksa, saksa, Deutschland, Allemagne, DE, Saksan liittotasavalta, Saksan tasavalta</span><span class="sxs-lookup"><span data-stu-id="e6a35-176">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="e6a35-177">Rikastuksen tarkistaminen ja nimeäminen</span><span class="sxs-lookup"><span data-stu-id="e6a35-177">Review and name the enrichment</span></span>

<span data-ttu-id="e6a35-178">Lopuksi pääset tarkistamaan tiedot ja antamaan rikastukselle nimen.</span><span class="sxs-lookup"><span data-stu-id="e6a35-178">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Kiinnostuksen kohteiden tarkistuksen ja nimeämisen sivu.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="e6a35-180">Rikastuksen päivittäminen</span><span class="sxs-lookup"><span data-stu-id="e6a35-180">Refresh enrichment</span></span>

<span data-ttu-id="e6a35-181">Suorita rikastus, kun olet konfiguroinut tuotemerkit, kiinnostuksen kohteet ja demografisten tietojen kenttien yhdistämismääritykset.</span><span class="sxs-lookup"><span data-stu-id="e6a35-181">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="e6a35-182">Aloita prosessi valitsemalla tuotemerkin tai kiinnostuksen kohteen määrityssivulla **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="e6a35-182">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="e6a35-183">Voit lisäksi jättää rikastamisen suoritettavaksi automaattisesti aikataulutetun päivityksen osana.</span><span class="sxs-lookup"><span data-stu-id="e6a35-183">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="e6a35-184">Asiakastietojen koon mukaan rikastusaika voi kestää useita minuutteja.</span><span class="sxs-lookup"><span data-stu-id="e6a35-184">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="e6a35-185">Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="e6a35-185">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e6a35-186">Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="e6a35-186">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e6a35-187">Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja.</span><span class="sxs-lookup"><span data-stu-id="e6a35-187">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e6a35-188">Kun työn jossakin tehtävissä on valittu **Näytä tiedot**, saat lisätietoja: käsittelyajan, viimeisimmän käsittelypäivämäärän sekä kaikki tehtävään liitetyt virheet ja varoitukset.</span><span class="sxs-lookup"><span data-stu-id="e6a35-188">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="e6a35-189">Rikastamisen tulokset</span><span class="sxs-lookup"><span data-stu-id="e6a35-189">Enrichment results</span></span>

<span data-ttu-id="e6a35-190">Kun täydennysprosessia suoritetaan, siirry **Omat täydennykset** -kohtaan ja tarkista niiden asiakkaiden kokonaismäärä, joiden tietoja on täydennetty, sekä tuotemerkkien tai kiinnostuksen kohteiden erittely täydennetyissä asiakasprofiileissa.</span><span class="sxs-lookup"><span data-stu-id="e6a35-190">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Tulosten esikatselu rikastamisprosessin suorittamisen jälkeen":::

<span data-ttu-id="e6a35-192">Tarkastele rikastettuja tietoja valitsemalla kaaviossa **Näytä rikastetut tiedot**.</span><span class="sxs-lookup"><span data-stu-id="e6a35-192">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="e6a35-193">Tuotemerkkien rikastetut tiedot siirtyvät **BrandAffinityFromMicrosoft**-entiteettiin.</span><span class="sxs-lookup"><span data-stu-id="e6a35-193">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="e6a35-194">Kiinnostuksen kohteiden tiedot ovat **InterestAffinityFromMicrosoft**-entiteetissä.</span><span class="sxs-lookup"><span data-stu-id="e6a35-194">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="e6a35-195">Nämä entiteetit ilmoitetaan myös **Rikastaminen**-ryhmässä kohdassa **Tiedot** > **Entiteetit**.</span><span class="sxs-lookup"><span data-stu-id="e6a35-195">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="e6a35-196">Rikastamistietojen tarkasteleminen asiakaskortissa</span><span class="sxs-lookup"><span data-stu-id="e6a35-196">See enrichment data on the customer card</span></span>

<span data-ttu-id="e6a35-197">Brändien ja kiinnostuksenkohteiden affiniteetteja voi tarkastella myös yksittäisissä asiakaskorteissa.</span><span class="sxs-lookup"><span data-stu-id="e6a35-197">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="e6a35-198">Valitse ensin **Asiakkaat** ja sitten asiakasprofiili.</span><span class="sxs-lookup"><span data-stu-id="e6a35-198">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="e6a35-199">Asiakaskortissa on tietoja kaavioista tuotemerkkejä tai kiinnostuksen kohteita varten, joita kohtaan henkilöillä asiakkaiden demografisessa profiilissa on affiniteetti.</span><span class="sxs-lookup"><span data-stu-id="e6a35-199">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Asiakaskortin rikastetut tiedot":::

## <a name="next-steps"></a><span data-ttu-id="e6a35-201">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="e6a35-201">Next steps</span></span>

<span data-ttu-id="e6a35-202">Voit hyödyntää rikastettuja asiakastietoja.</span><span class="sxs-lookup"><span data-stu-id="e6a35-202">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e6a35-203">Voit tarjota asiakkaille mukautettuja kokemuksia luomalla [segmenttejä](segments.md) ja [mittoja](measures.md) sekä [viemällä tietoja](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e6a35-203">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
