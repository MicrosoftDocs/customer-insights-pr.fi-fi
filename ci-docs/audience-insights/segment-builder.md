---
title: Segmenttien luonti ja hallinta
description: Luo asiakassegmenttejä ja ryhmittele ne eri määritteiden perusteella.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064933"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="f4c1f-103">Segmenttien luonti ja hallinta</span><span class="sxs-lookup"><span data-stu-id="f4c1f-103">Create and manage segments</span></span>

<span data-ttu-id="f4c1f-104">Määritä yhdistetyn asiakasentiteetin ja siihen liittyvien entiteettien monimutkaiset suodattimet.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="f4c1f-105">Kukin segmentti luo käsittelyn jälkeen joukon asiakastietueita, joita voit viedä ja joihin voit tehdä toimintoja.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="f4c1f-106">Segmenttejä hallitaan **Segmentit**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="f4c1f-107">Seuraava esimerkki kuvaa segmentointiominaisuutta.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="f4c1f-108">Olemme määritelleet segmentin asiakkaille, jotka tilasivat vähintään 500 dollarilla tavaraa viimeisen 90 päivän aikana *ja* jotka olivat mukana eskaloidussa asiakaspalvelupuhelussa.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Näyttökuva segmentin muodostimen käyttöliittymästä, jossa on kaksi ryhmää, jotka määrittävät asiakassegmentin.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="f4c1f-110">Luo uusi segmentti</span><span class="sxs-lookup"><span data-stu-id="f4c1f-110">Create a new segment</span></span>

<span data-ttu-id="f4c1f-111">Uuden segmentin voi luoda useilla tavoilla.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="f4c1f-112">Tässä osassa kuvataan, miten *tyhjä segmentti* luodaan alusta alkaen.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="f4c1f-113">Voit myös luoda *pikasegmentin* olemassa olevien entiteettien perusteella tai käyttää koneoppimismalleja *segmenttiehdotusten* saamiseksi.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="f4c1f-114">Lisätietoja: [Yleiskatsaus segmentteihin](segments.md).</span><span class="sxs-lookup"><span data-stu-id="f4c1f-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="f4c1f-115">Luodessasi segmenttiä voit tallentaa luonnoksen.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="f4c1f-116">Se tallentuu passiiviseksi segmenttiksi, eikä sitä voi aktivoida valmiiksi kelvollisen määrityksen avulla.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="f4c1f-117">Siirry **Segmentit**-sivulle.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="f4c1f-118">Valitse **Uusi** > **Tyhjä segmentti**.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="f4c1f-119">Valitse **Uusi segmentti** -ruudussa segmentin tyyppi:</span><span class="sxs-lookup"><span data-stu-id="f4c1f-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="f4c1f-120">**Dynaamiset segmentit** [päivittyvät](segments.md#refresh-segments) toistuvan aikataulun mukaisesti.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="f4c1f-121">**Staattiset segmentit** suoritetaan kerran, kun ne luodaan.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="f4c1f-122">Anna segmentille **Tulosentiteetin nimi**.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="f4c1f-123">Vaihtoehtoisesti voit antaa näyttönimen ja kuvauksen, joiden avulla segmentin voi tunnistaa.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="f4c1f-124">Kun valitset **Seuraava**, näyttöön avautuu **Segmentin muodostin** -sivu, jolla voit määrittää ryhmän.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="f4c1f-125">Ryhmä on joukko asiakkaita.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="f4c1f-126">Valitse sen määritteen sisältävä entiteetti, jonka mukaan segmentointi tehdään.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="f4c1f-127">Valitse segmentointiperusteen määrite.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="f4c1f-128">Tällä määritteellä voi olla jokin neljästä arvotyypistä: numeerinen, merkkijono, päivämäärä tai totuusarvo.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="f4c1f-129">Valitse operaattori ja arvo valitulle määritteelle.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f4c1f-130">![Mukautettu ryhmäsuodatin](media/customer-group-numbers.png "Asiakkaan ryhmäsuodatin")</span><span class="sxs-lookup"><span data-stu-id="f4c1f-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="f4c1f-131">Määrä</span><span class="sxs-lookup"><span data-stu-id="f4c1f-131">Number</span></span> |<span data-ttu-id="f4c1f-132">Määritelmä</span><span class="sxs-lookup"><span data-stu-id="f4c1f-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="f4c1f-133">1</span><span class="sxs-lookup"><span data-stu-id="f4c1f-133">1</span></span>     |<span data-ttu-id="f4c1f-134">Entity</span><span class="sxs-lookup"><span data-stu-id="f4c1f-134">Entity</span></span>          |
   |<span data-ttu-id="f4c1f-135">2</span><span class="sxs-lookup"><span data-stu-id="f4c1f-135">2</span></span>     |<span data-ttu-id="f4c1f-136">Määrite</span><span class="sxs-lookup"><span data-stu-id="f4c1f-136">Attribute</span></span>          |
   |<span data-ttu-id="f4c1f-137">3</span><span class="sxs-lookup"><span data-stu-id="f4c1f-137">3</span></span>    |<span data-ttu-id="f4c1f-138">Operaattori</span><span class="sxs-lookup"><span data-stu-id="f4c1f-138">Operator</span></span>         |
   |<span data-ttu-id="f4c1f-139">4</span><span class="sxs-lookup"><span data-stu-id="f4c1f-139">4</span></span>    |<span data-ttu-id="f4c1f-140">Arvo</span><span class="sxs-lookup"><span data-stu-id="f4c1f-140">Value</span></span>         |

   1. <span data-ttu-id="f4c1f-141">Jos haluat lisätä ryhmään ehtoja, voit käyttää seuraavaa kahta loogista operaattoria:</span><span class="sxs-lookup"><span data-stu-id="f4c1f-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="f4c1f-142">**JA**-operaattori: Molempien ehtojen on täytyttävä segmentointiprosessin aikana.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="f4c1f-143">Tämä vaihtoehto on hyödyllinen, kun määrität ehtoja eri entiteeteille.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="f4c1f-144">**TAI**-operaattori: Jommankumman ehdoista on täytyttävä segmentointiprosessin aikana.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="f4c1f-145">Tämä vaihtoehto on hyödyllinen, kun määrität useita ehtoja samalle entiteetille.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="f4c1f-146">![TAI-operaattori, jossa jommankumman ehdoista on täytyttävä](media/segmentation-either-condition.png "TAI-operaattori, jossa jommankumman ehdoista on täytyttävä")</span><span class="sxs-lookup"><span data-stu-id="f4c1f-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="f4c1f-147">Tällä hetkellä on mahdollista upottaa **TAI**-operaattoria **JA**-operaattorin sisään, mutta ei toisin päin.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="f4c1f-148">Kukin ryhmä vastaa asiakasjoukkoa.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-148">Each group matches set of customers.</span></span> <span data-ttu-id="f4c1f-149">Voit yhdistää ryhmiä niin, että niihin sisällytetään liiketoimintatapausta varten tarvittavat asiakkaat.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="f4c1f-150">Valitse **Lisää ryhmä**.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="f4c1f-151">![Asiakasryhmä - lisää ryhmä](media/customer-group-add-group.png "Asiakasryhmä - lisää ryhmä")</span><span class="sxs-lookup"><span data-stu-id="f4c1f-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="f4c1f-152">Valitse jokin joukko-operaattoreista: **Unioni**, **Leikkaus** tai **Paitsi**.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f4c1f-153">![Asiakasryhmä - lisää liitos](media/customer-group-union.png "Asiakasryhmä - lisää liitos")</span><span class="sxs-lookup"><span data-stu-id="f4c1f-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="f4c1f-154">**Liitos** yhdistää kaksi ryhmää.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="f4c1f-155">**Leikkaa** asettaa kaksi ryhmää päällekkäin.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="f4c1f-156">Vain molemmille ryhmille *yhteiset* tiedot säilytetään yhdistetyssä ryhmässä.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="f4c1f-157">**Lukuun ottamatta** yhdistää kaksi ryhmää.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-157">**Except** combines the two groups.</span></span> <span data-ttu-id="f4c1f-158">Vain ryhmän A tiedot, jotka *eivät ole yhteisiä* ryhmän B tietojen kanssa, säilytetään.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="f4c1f-159">Jos entiteetti on yhdistetty yhdistettyyn asiakaskohteeseen [suhteen](relationships.md) kautta , sinun täytyy määrittää suhdepolku, jotta voit luoda kelvollisen segmentin.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="f4c1f-160">Lisää entiteetit suhdepolusta, kunnes voit valita **Asiakas : CustomerInsights** -entiteetin avattavasta luettelosta.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="f4c1f-161">Valitse sitten jokaiselle vaiheelle **Kaikki tietueet**.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f4c1f-162">![Suhdepolku segmentin luonnin aikana](media/segments-multiple-relationships.png "Suhdepolku segmentin luonnin aikana")</span><span class="sxs-lookup"><span data-stu-id="f4c1f-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="f4c1f-163">Segmentit luovat oletusarvoisesti tulosentiteetin, joka sisältää kaikki määritettyjä suodattimia vastaavat asiakasprofiilien määritteet.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="f4c1f-164">Jos segmentti perustuu muihin entiteetteihin kuin *Asiakas*-entiteettiin, voit lisätä näistä entiteeteistä lisämääritteitä tulosentiteettiin.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="f4c1f-165">Valitse **Projekti**-määritteet, jos haluat valita tulosentiteettiin liitettävät määritteet.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="f4c1f-166">Esimerkki: Segmentti perustuu entiteettiin, joka sisältää *Asiakas*-entiteettiin liittyviä asiakasaktiviteettitietoja.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="f4c1f-167">Segmentti etsii kaikkia asiakkaita, jotka ovat soittaneet tukipalveluun viimeisen 60 päivän aikana.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="f4c1f-168">Voit liittää puhelun keston ja puheluiden määrän kaikkiin tulosentiteetin vastaaviin asiakastietueisiin.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="f4c1f-169">Nämä tiedot voivat olla hyödyllisiä, jos haluat lähettää sähköpostia, jossa on hyödyllisiä linkkejä online-ohjeartikkeleihin ja usein kysyttyihin kysymyksiin asiakkaille, jotka ovat soittaneet usein.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="f4c1f-170">Projisoidut määritteet koskevat vain entiteettejä, joilla on yksi moneen -suhde asiakasentiteettiin.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="f4c1f-171">Esimerkiksi yhdellä asiakkaalla voi olla useita tilauksia.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="f4c1f-172">Määritteitä voidaan projisoida vain entiteetistä, jota käytetään sen segmenttikyselyn jokaisessa ryhmässä, jota rakennetaan.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="f4c1f-173">Projisoidut määritteet otetaan huomioon, kun joukko-operaattoreita käytetään.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="f4c1f-174">Tallenna segmentti valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="f4c1f-175">Segmentti tallennetaan ja käsitellään, jos kaikki vaatimukset on vahvistettu.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="f4c1f-176">Muussa tapauksessa se tallennetaan luonnoksena.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="f4c1f-177">Valitse **Palaa segmentteihin**, jos haluat siirtyä takaisin **Segmentit**-sivulle.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="f4c1f-178">Pikasegmentit</span><span class="sxs-lookup"><span data-stu-id="f4c1f-178">Quick segments</span></span>

<span data-ttu-id="f4c1f-179">Pikasegmenttien avulla voidaan nopeasti luoda yksinkertaisia segmenttejä yhdellä operaattorilla, jotta merkitykselliset tiedot saadaan nopeammin.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="f4c1f-180">Valitse **Segmentit**-sivulla **Uusi** > **Luo kohteesta**.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="f4c1f-181">Valitse **Profiilit**-vaihtoehto, jos haluat muodostaa segmentin, joka perustuu *yhdistettyyn asiakas* entiteettiin.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="f4c1f-182">Valitse **Mittarit**-vaihtoehto rakentaaksesi segmentin aiemmin luotujen mittareiden perusteella.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="f4c1f-183">Valitse **Analytiikka**-asetus, jos haluat luoda segmentin, joka on luotu käyttämällä joko **Ennusteet**-tai **Mukautetut mallit** -ominaisuuden avulla luotuja tuloskohteita.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="f4c1f-184">Valitse **Uusi pikasegmentti** -valintaikkunasta määrite avattavasta **Kenttä**-valikosta.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="f4c1f-185">Järjestelmä tarjoaa lisätietoja, joiden avulla voit aiempaa helpommin luoda asiakkaille segmenttejä.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="f4c1f-186">Luokkakentille näytetään 10 parasta asiakasmäärää.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="f4c1f-187">Valitse **Arvo** ja valitse sitten **Tarkista**.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="f4c1f-188">Jos määrite on numeerinen, järjestelmä näyttää, mikä määrite kuuluu mihinkin asiakasprosenttipisteeseen.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="f4c1f-189">Valitse **Operaattori** ja **Arvo** ja valitse sitten **Tarkista**.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="f4c1f-190">Järjestelmä näyttää **arvioidun segmentin koon**.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="f4c1f-191">Voit määrittää, luodaanko määritetty segmentti vai avataanko sen ensin, jolloin voit määrittää toisen segmentin koon.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4c1f-192">![Nopean segmentin nimi ja arvioi](media/quick-segment-name.png "Nopean segmentin nimi ja arvioi")</span><span class="sxs-lookup"><span data-stu-id="f4c1f-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="f4c1f-193">Anna segmentille **nimi**.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="f4c1f-194">Vaihtoehtoisesti voit antaa **näyttönimen**.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="f4c1f-195">Luo segmentti valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="f4c1f-196">Kun segmentin käsittely on valmis, voit tarkistaa sen kuten minkä tahansa luodun segmentin.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f4c1f-197">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="f4c1f-197">Next steps</span></span>

<span data-ttu-id="f4c1f-198">[Vie segmentti](export-destinations.md) ja tutustu [asiakaskorttiin](customer-card-add-in.md) ja [yhdistimiin](export-power-bi.md), jotta saat asiakastason tietoja.</span><span class="sxs-lookup"><span data-stu-id="f4c1f-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
