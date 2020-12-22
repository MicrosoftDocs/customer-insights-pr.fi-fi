---
title: Mittareiden luominen ja mukauttaminen
description: Määritä asiakkaaseen liittyvät mittarit tiettyjen liiketoiminta-alueiden suorituskyvyn analysointia ja kuvailua varten.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405622"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="afff7-103">Mittojen määrittäminen ja hallinta</span><span class="sxs-lookup"><span data-stu-id="afff7-103">Define and manage measures</span></span>

<span data-ttu-id="afff7-104">**Mittarit** edustavat tunnuslukuja, jotka kuvaavat tiettyjen liiketoiminta-alueiden suorituskykyä ja tilaa.</span><span class="sxs-lookup"><span data-stu-id="afff7-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="afff7-105">Mittareiden luonti käyttäjäryhmän merkityksellisissä tiedoissa tapahtuu intuitiivisesti kyselyn muodostimessa, jossa ei tarvitse käyttää koodia eikä vahvistaa mittareita manuaalisesti.</span><span class="sxs-lookup"><span data-stu-id="afff7-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="afff7-106">Voit seurata liiketoiminnan mittareita **aloitussivulla**, katsoa tiettyjen asiakkaiden mittareita **asiakaskortin** avulla ja käyttää mittareita asiakassegmenttien määrittämisessä **Segmentit**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="afff7-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="afff7-107">Luo mittari</span><span class="sxs-lookup"><span data-stu-id="afff7-107">Create a measure</span></span>

<span data-ttu-id="afff7-108">Tässä osassa luodaan mittari alusta alkaen.</span><span class="sxs-lookup"><span data-stu-id="afff7-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="afff7-109">Voit luoda mittareita useiden asiakasentiteetin kautta yhdistettyjen tietolähteiden tiedoista.</span><span class="sxs-lookup"><span data-stu-id="afff7-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="afff7-110">Käytössä on jotakin [palvelurajoituksia](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="afff7-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="afff7-111">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Mittarit**.</span><span class="sxs-lookup"><span data-stu-id="afff7-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="afff7-112">Valitse **Uusi mittari**.</span><span class="sxs-lookup"><span data-stu-id="afff7-112">Select **New measure**.</span></span>

3. <span data-ttu-id="afff7-113">Valitse mittarin **tyyppi** seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="afff7-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="afff7-114">**Asiakasmäärite**: Asiakkaan yksittäinen kenttä, joka näyttää asiakkaan pisteet, arvon tai tilan.</span><span class="sxs-lookup"><span data-stu-id="afff7-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="afff7-115">Asiakkaan määritteet luodaan määritteinä uudessa järjestelmän luomassa entiteetissä, jonka nimi on **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="afff7-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="afff7-116">**Asiakasmittari**: Tietoja asiakkaan toiminnasta eriteltynä valittujen dimensioiden mukaan.</span><span class="sxs-lookup"><span data-stu-id="afff7-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="afff7-117">Jokaiselle mittarille luodaan uusi entiteetti. Se sisältää mahdollisesti useita tietueita asiakasta kohti.</span><span class="sxs-lookup"><span data-stu-id="afff7-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="afff7-118">**Liiketoiminnan mittari**: Seuraa liiketoiminnan suorituskykyä ja tilaa.</span><span class="sxs-lookup"><span data-stu-id="afff7-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="afff7-119">Liiketoiminnan mittareilla voi olla kaksi eri tulostetta: numeerinen tuloste, joka osoittaa **aloitussivun** tai uuden entiteetin, joka löytyy **Entiteetit**-sivulta.</span><span class="sxs-lookup"><span data-stu-id="afff7-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="afff7-120">Anna **nimi** ja valinnainen **näyttönimi** ja valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="afff7-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="afff7-121">Valitse **Entiteetit**-osassa ensin entiteetti avattavasta luettelosta.</span><span class="sxs-lookup"><span data-stu-id="afff7-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="afff7-122">Tässä vaiheessa sinun on päätettävä, tarvitaanko mittarin määrityksessä useampia entiteettejä.</span><span class="sxs-lookup"><span data-stu-id="afff7-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="afff7-123">![Mittarin määritys](media/measure-definition.png "Mittarin määritys")</span><span class="sxs-lookup"><span data-stu-id="afff7-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="afff7-124">Jos lisäät entiteettejä, valitse **Lisää entiteetti** ja valitse mittarissa käytettävät entiteetit.</span><span class="sxs-lookup"><span data-stu-id="afff7-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="afff7-125">Voit valita vain entiteettejä, joilla on suhde aloittavaan entiteettiin.</span><span class="sxs-lookup"><span data-stu-id="afff7-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="afff7-126">Lisätietoja suhteiden määrittämisestä on kohdassa [Suhteet](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="afff7-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="afff7-127">Vaihtoehtoisesti voit määrittää muuttujia.</span><span class="sxs-lookup"><span data-stu-id="afff7-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="afff7-128">Valitse **Muuttujat**-osassa **Uusi muuttuja**.</span><span class="sxs-lookup"><span data-stu-id="afff7-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="afff7-129">Muuttujat ovat laskelmia, jotka tehdään jokaiselle valitulle tietueelle.</span><span class="sxs-lookup"><span data-stu-id="afff7-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="afff7-130">Voit esimerkiksi laskea yhteen myyntipisteen verkkomyynnin jokaiselle asiakastietueelle.</span><span class="sxs-lookup"><span data-stu-id="afff7-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="afff7-131">Anna muuttujalle **nimi**.</span><span class="sxs-lookup"><span data-stu-id="afff7-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="afff7-132">Valitse **Lauseke**-alueessa kenttä, jonka aloittaa laskelman.</span><span class="sxs-lookup"><span data-stu-id="afff7-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="afff7-133">Kirjoita lauseke **Lauseke**-alueeseen ja valitse lisää laskelmaan lisättäviä kenttiä.</span><span class="sxs-lookup"><span data-stu-id="afff7-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="afff7-134">Tällä hetkellä tuetaan vain aritmeettisia lausekkeita.</span><span class="sxs-lookup"><span data-stu-id="afff7-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="afff7-135">Lisäksi muuttujan laskelma ei tue muiden [entiteettipolkujen](relationships.md) entiteettejä.</span><span class="sxs-lookup"><span data-stu-id="afff7-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="afff7-136">Valitse **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="afff7-136">Select **Done**.</span></span>

11. <span data-ttu-id="afff7-137">**Mittarin määritys** -osassa määritetään, miten valitut entiteetit ja lasketut muuttujat yhdistetään uudessa mittarientiteetissä tai määritteessä.</span><span class="sxs-lookup"><span data-stu-id="afff7-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="afff7-138">Valitse **Uusi dimensio**.</span><span class="sxs-lookup"><span data-stu-id="afff7-138">Select **New dimension**.</span></span> <span data-ttu-id="afff7-139">Dimension voi ajatella olevan *ryhmittelytoiminto*.</span><span class="sxs-lookup"><span data-stu-id="afff7-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="afff7-140">Mittarientiteetin tai -määritteen tietotuloste ryhmitellään kaikkien määritettyjen dimensioiden mukaan.</span><span class="sxs-lookup"><span data-stu-id="afff7-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="afff7-141">![Valitse yhdistämisjakso](media/measures-businessreport-measure-definition2.png "Valitse yhdistämisjakso")</span><span class="sxs-lookup"><span data-stu-id="afff7-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="afff7-142">Valitse tai syötä seuraavat tiedot dimension määrityksen osaksi:</span><span class="sxs-lookup"><span data-stu-id="afff7-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="afff7-143">**Entiteetti**: Jos määrität mittarientiteetin, sisällytä vähintään yksi määrite.</span><span class="sxs-lookup"><span data-stu-id="afff7-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="afff7-144">Jos määrität mittarimääritteen, se sisältää oletusarvoisesti vain yhden määritteen.</span><span class="sxs-lookup"><span data-stu-id="afff7-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="afff7-145">Tämä valinta koskee sellaisen entiteetin valitsemista, joka sisältää kyseisen määritteen.</span><span class="sxs-lookup"><span data-stu-id="afff7-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="afff7-146">**Kenttä**: Valitse tietty määrite, joka sisällytetään joko mittarientiteettiin tai -määritteeseen.</span><span class="sxs-lookup"><span data-stu-id="afff7-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="afff7-147">**Säilö**: Määritä, haluatko yhdistää tiedot päivittäin, kuukausittain vai vuosittain.</span><span class="sxs-lookup"><span data-stu-id="afff7-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="afff7-148">Se on pakollinen valinta vain, jos olet valinnut päivämäärätyyppimääritteen.</span><span class="sxs-lookup"><span data-stu-id="afff7-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="afff7-149">**Kohteena**: Määrittää uuden kentän nimen.</span><span class="sxs-lookup"><span data-stu-id="afff7-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="afff7-150">**Näyttönimi**: Määrittää kentän näyttönimen.</span><span class="sxs-lookup"><span data-stu-id="afff7-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="afff7-151">Liiketoiminnan mittari tallennetaan yksinumeroisena entiteettinä. Se näkyy **aloitussivulla**, jos et lisää muita dimensioita mittariin.</span><span class="sxs-lookup"><span data-stu-id="afff7-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="afff7-152">Kun olet lisännyt dimensioita, mittari *ei* näy **aloitussivulla**.</span><span class="sxs-lookup"><span data-stu-id="afff7-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="afff7-153">Vaihtoehtoisesti voit lisätä yhdistämistoimintoja.</span><span class="sxs-lookup"><span data-stu-id="afff7-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="afff7-154">Kaikki luodut yhdistämiset luovat uuden arvon mittarientiteettiin tai -määritteeseen.</span><span class="sxs-lookup"><span data-stu-id="afff7-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="afff7-155">Tuettuja yhdistämistoimintoja ovat seuraavat: **Vähintään**, **Enintään**, **Keskiarvo**, **Mediaani**, **Summa**, **Yksilöllinen määrä**, **Ensimmäinen** (poimii dimension arvon ensimmäisen tietueen) ja **Viimeinen** (poimii viimeisen dimension arvoon lisätyn tietueen).</span><span class="sxs-lookup"><span data-stu-id="afff7-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="afff7-156">Valitse **Tallenna**, kun haluat ottaa muutokset käyttöön mittarissa.</span><span class="sxs-lookup"><span data-stu-id="afff7-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="afff7-157">Hallitse mittoja</span><span class="sxs-lookup"><span data-stu-id="afff7-157">Manage your measures</span></span>

<span data-ttu-id="afff7-158">Sen jälkeen kun vähintään yksi mittari on luotu, **Mittarit**-sivulla on mittariluettelo.</span><span class="sxs-lookup"><span data-stu-id="afff7-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="afff7-159">Löydät tietoja mittarin tyypistä, tekijästä, luontipäivämäärästä ja -ajasta, edellisestä muokkauspäivämäärästä ja -ajasta, tilasta (mittarin tila voi olla Aktiivinen, Passiivinen tai Epäonnistunut) ja edellisestä päivityspäivämäärästä ja -ajasta.</span><span class="sxs-lookup"><span data-stu-id="afff7-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="afff7-160">Kun valitset mitan luettelosta, näet esikatselun sen tulosteesta.</span><span class="sxs-lookup"><span data-stu-id="afff7-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="afff7-161">Jos haluat päivittää kaikki mitat samalla kertaa, valitse **Päivitä kaikki** valitsematta tiettyä mittaa.</span><span class="sxs-lookup"><span data-stu-id="afff7-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="afff7-162">![Yksittäisten mittojen hallintatoiminnot](media/measure-actions.png "Yksittäisten mittojen hallintatoiminnot")</span><span class="sxs-lookup"><span data-stu-id="afff7-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="afff7-163">Voit vaihtoehtoisesti valita mitan luettelosta ja suorittaa jonkin seuraavista toiminnoista:</span><span class="sxs-lookup"><span data-stu-id="afff7-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="afff7-164">Voit tarkastella tietoja valitsemalla mitan nimen.</span><span class="sxs-lookup"><span data-stu-id="afff7-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="afff7-165">**Muokkaa** mitan määritystä.</span><span class="sxs-lookup"><span data-stu-id="afff7-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="afff7-166">**Nimeä uudelleen** mitta.</span><span class="sxs-lookup"><span data-stu-id="afff7-166">**Rename** the measure.</span></span>
- <span data-ttu-id="afff7-167">**Poista** mitta.</span><span class="sxs-lookup"><span data-stu-id="afff7-167">**Delete** the measure.</span></span>
- <span data-ttu-id="afff7-168">Valitse kolme pistettä (...) ja sitten **Päivitä**, kun haluat aloittaa mitan päivitysprosessin.</span><span class="sxs-lookup"><span data-stu-id="afff7-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="afff7-169">Valitse kolme pistettä (...) ja sitten **Lataa** saadaksesi mitan .CSV-tiedoston.</span><span class="sxs-lookup"><span data-stu-id="afff7-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="afff7-170">Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="afff7-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="afff7-171">Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="afff7-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="afff7-172">Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja.</span><span class="sxs-lookup"><span data-stu-id="afff7-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="afff7-173">Kun työn jossakin tehtävissä on valittu **Näytä tiedot**, saat lisätietoja: käsittelyajan, viimeisimmän käsittelypäivämäärän sekä kaikki tehtävään liitetyt virheet ja varoitukset.</span><span class="sxs-lookup"><span data-stu-id="afff7-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="afff7-174">Seuraava vaihe</span><span class="sxs-lookup"><span data-stu-id="afff7-174">Next step</span></span>

<span data-ttu-id="afff7-175">Voit luoda ensimmäisen asiakassegmentin **Segmentit**-sivulla olemassa olevien mittareiden avulla.</span><span class="sxs-lookup"><span data-stu-id="afff7-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="afff7-176">Lisätietoja on kohdassa [Segmentit](segments.md).</span><span class="sxs-lookup"><span data-stu-id="afff7-176">For more information, see [Segments](segments.md).</span></span>
