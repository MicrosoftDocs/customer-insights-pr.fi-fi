---
title: Osittaisten tietojen viimeisteleminen ennusteiden avulla
description: Puutteellisten asiakastietojen täydentäminen ennusteiden avulla.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3342328b9eead9bdcb8b41f119a1d0a5823001c8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595897"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="be2ed-103">Osittaisten tietojen viimeisteleminen ennusteiden avulla</span><span class="sxs-lookup"><span data-stu-id="be2ed-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="be2ed-104">Ennusteiden avulla voit helposti luoda ennustettuja arvoja, jotka auttavat ymmärtämään asiakasta aiempaa paremmin.</span><span class="sxs-lookup"><span data-stu-id="be2ed-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="be2ed-105">Valitsemalla **Analytiikka** > **Ennusteet**-sivulla **Omat ennusteet** näkyviin tulee ennusteet, jotka on määritetty toisaalla käyttäjäryhmän merkityksellisissä tiedoissa ja joiden avulla ennusteita voi mukauttaa entisestään.</span><span class="sxs-lookup"><span data-stu-id="be2ed-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="be2ed-106">Et voi käyttää tätä toimintoa, jos ympäristössä on käytössä Azure Data Lake Gen 2 -tallennustila.</span><span class="sxs-lookup"><span data-stu-id="be2ed-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="be2ed-107">Ennustetoiminto käyttää automaattisia ominaisuuksia tietojen arvioinnissa ja se tekee ennusteet näiden tietojen perusteella. Sen vuoksi sitä voi käyttää profiloinnissa. Tämä termi on määritetty yleisissä tietosuoja-asetuksissa (GDPR).</span><span class="sxs-lookup"><span data-stu-id="be2ed-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="be2ed-108">Asiakkaat käyttävät tätä toimintoa tietojen käsittelyyn. GDPR tai muut lait tai säädökset saattavat ohjata toiminnon käyttöä.</span><span class="sxs-lookup"><span data-stu-id="be2ed-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="be2ed-109">Olet vastuussa siitä, että Dynamics 365 Customer Insightsin käyttäminen, myös ennusteiden käyttäminen, on kaikkien lakien ja säädösten mukaista. Näihin kuuluvat yksityisyyteen, henkilökohtaisiin tietoihin, biometrisiin tietoihin, tietosuojaan ja viestintäsalaisuuteen liittyvät lait.</span><span class="sxs-lookup"><span data-stu-id="be2ed-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="be2ed-110">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="be2ed-110">Prerequisites</span></span>

<span data-ttu-id="be2ed-111">Ennen kuin organisaatio voi käyttää ennustetoimintoa, seuraavien edellytykset on toteuduttava:</span><span class="sxs-lookup"><span data-stu-id="be2ed-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="be2ed-112">Organisaatiossa on [Common Data Servicessa määritetty](/ai-builder/build-model#prerequisites) esiintymä, joka on samassa organisaatiossa kuin Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="be2ed-112">Your organization has an instance [set up in the Common Data Service](/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="be2ed-113">Ympäristö on liitetty Common Data Service -esiintymään.</span><span class="sxs-lookup"><span data-stu-id="be2ed-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="be2ed-114">Jos olet [luomassa ensimmäistä ympäristöä](manage-environments.md), määritä se **Luo ympäristö** -valintaikkunassa ja valitse **Lisäasetukset**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="be2ed-115">Jos olet jo luonut ympäristön, siirry sen asetuksiin ja valitse **Lisäasetukset**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="be2ed-116">Anna kummassakin tapauksessa **Käytä ennusteita** -osassa sen Common Data Service -esiintymän URL-osoite, johon haluat liittää ympäristön.</span><span class="sxs-lookup"><span data-stu-id="be2ed-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="be2ed-117">Ennusteen luominen asiakasentiteetissä</span><span class="sxs-lookup"><span data-stu-id="be2ed-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="be2ed-118">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Entiteetit**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="be2ed-119">Valitse **asiakasentiteetti**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="be2ed-120">Valitse **Asiakas: CustomerInsights** -entiteetissä **Kentät**-välilehti.</span><span class="sxs-lookup"><span data-stu-id="be2ed-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="be2ed-121">Etsi sen määritteen nimi, jolle haluat ennustaa arvot, ja valitse sitten **Yleiskatsaus**-kuvake **Yhteenveto**-sarakkeessa.</span><span class="sxs-lookup"><span data-stu-id="be2ed-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="be2ed-122">![Yleiskatsaus-kuvake](media/intelligence-overviewicon.png "Yleiskatsaus-kuvake")</span><span class="sxs-lookup"><span data-stu-id="be2ed-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="be2ed-123">Jos määritteeltä puuttuu paljon arvoja, valitse **Ennusta puuttuvat arvot** ja jatka ennusteen määrittämistä.</span><span class="sxs-lookup"><span data-stu-id="be2ed-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="be2ed-124">![Yleiskatsauksen tila ja ennusteen puuttuvat arvot -painike näkyvissä](media/intelligence-overviewpredictmissingvalues.png "Yleiskatsauksen tila ja ennusteen puuttuvat arvot -painike näkyvissä")</span><span class="sxs-lookup"><span data-stu-id="be2ed-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="be2ed-125">Anna **näyttönimi** ja **tulosentiteetin nimi** ennusteen tuloksia varten.</span><span class="sxs-lookup"><span data-stu-id="be2ed-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="be2ed-126">Näkyviin tulee valmiiksi määritetty asetusluettelo, jossa voit yhdistää arvot ennustettua luokkaa varten.</span><span class="sxs-lookup"><span data-stu-id="be2ed-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="be2ed-127">Tässä tapauksessa luokan asetuksia ovat vain 0 ja 1, koska ne vastaavat tosi-/epätosi-arvoja tai ennusteen binaarista luonnetta.</span><span class="sxs-lookup"><span data-stu-id="be2ed-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="be2ed-128">Yhdistä Luokka-sarakkeessa kentän arvot, jotka haluat luokitella arvolla 0 lopullisessa ennusteessa, ja nimikkeet, jotka haluat luokitella arvolla 1 lopullisessa ennusteessa.</span><span class="sxs-lookup"><span data-stu-id="be2ed-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="be2ed-129">![Esimerkki kentän arvojen ja luokkien yhdistämisestä](media/intelligence-categorymapping.png "Esimerkki kentän arvojen ja luokkien yhdistämisestä")</span><span class="sxs-lookup"><span data-stu-id="be2ed-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="be2ed-130">Valitse **Valmis**. Ennustetta aletaan käsitellä.</span><span class="sxs-lookup"><span data-stu-id="be2ed-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="be2ed-131">Käsittelyn kesto riippuu tietojen koosta ja monimuotoisuudesta.</span><span class="sxs-lookup"><span data-stu-id="be2ed-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="be2ed-132">Tulokset ovat käytettävissä uudessa entiteetissä luodun ennusteen **tulosentiteetin nimen** perusteella.</span><span class="sxs-lookup"><span data-stu-id="be2ed-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="be2ed-133">Luo ennuste segmentin luomisen aikana</span><span class="sxs-lookup"><span data-stu-id="be2ed-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="be2ed-134">Tietyn määritteen puuttuvien arvojen ennustaminen valinnaisesti on mahdollista myös segmentin luomisen aikana.</span><span class="sxs-lookup"><span data-stu-id="be2ed-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="be2ed-135">Erityisesti silloin, kun luot segmentin nopeasti yhdistetyn asiakasentiteetin tai asiakasmittarientiteetin perusteella.</span><span class="sxs-lookup"><span data-stu-id="be2ed-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="be2ed-136">Tämän prosessin osana valitaan tietty määrite, johon segmentti perustuu. Se voi olla vaikkapa asiakastyytyväisyys tai ostojen summa.</span><span class="sxs-lookup"><span data-stu-id="be2ed-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="be2ed-137">Segmenttiä luotaessa järjestelmä ehdottaa tapaa, jolla kyseisen määritteen puuttuvat arvot ennustetaan.</span><span class="sxs-lookup"><span data-stu-id="be2ed-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="be2ed-138">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Segmentit** ja valitse sitten **Profiilit**-ruutu.</span><span class="sxs-lookup"><span data-stu-id="be2ed-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="be2ed-139">Valitse **Kenttä**, jos haluat luoda segmentin, ja valitse sitten **Operaattori**. Valitse lopuksi **Tarkista**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="be2ed-140">Anna segmentille **nimi** ja **näyttönimi**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="be2ed-141">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-141">Select **Save**.</span></span>

5. <span data-ttu-id="be2ed-142">Jos luodun segmentin lähdekentän tiedot ovat vaillinaiset, voit valita puuttuvien arvojen ennustamisen.</span><span class="sxs-lookup"><span data-stu-id="be2ed-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="be2ed-143">![Ennuste-painike](media/segments-predictoption.png "Ennuste-painike")</span><span class="sxs-lookup"><span data-stu-id="be2ed-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="be2ed-144">Anna **näyttönimi** ja **tulosentiteetin nimi** ennusteen tuloksia varten.</span><span class="sxs-lookup"><span data-stu-id="be2ed-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="be2ed-145">Valitse **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-145">Select **Done**.</span></span> <span data-ttu-id="be2ed-146">Ennuste luodaan pian uudessa entiteetissä, jonka nimenä on **Tulosentiteetin nimi** -kohdassa antamasi nimi.</span><span class="sxs-lookup"><span data-stu-id="be2ed-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="be2ed-147">Tarkastele ennustetta</span><span class="sxs-lookup"><span data-stu-id="be2ed-147">View a prediction</span></span>

1. <span data-ttu-id="be2ed-148">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Analytiikka** > **Ennusteet** > **Omat ennusteet**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="be2ed-149">Valitse ennuste, jota haluat tarkastella.</span><span class="sxs-lookup"><span data-stu-id="be2ed-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="be2ed-150">Valitse **Toiminnot**-sarakkeen kolme pistettä ja valitse sitten **Tarkastele**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="be2ed-151">Näkyviin tulee arvopisteiden määrä ennustenäkymässä.</span><span class="sxs-lookup"><span data-stu-id="be2ed-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="be2ed-152">![Ennusteet-sivu](media/intelligence-predictionsviewpage.png "Ennusteet-sivu")</span><span class="sxs-lookup"><span data-stu-id="be2ed-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="be2ed-153">**Ennustetut arvot** osoittavat täsmäytyksen, joka luotiin kentän arvon ja luokan täsmäytysvaiheessa.</span><span class="sxs-lookup"><span data-stu-id="be2ed-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="be2ed-154">Ne ovat tietojoukon arvoja, jotka on yhdistetty tiettyyn luokkaan.</span><span class="sxs-lookup"><span data-stu-id="be2ed-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="be2ed-155">-**Tärkeimmät vaikuttajat** ovat tietojoukon tekijöitä, jotka todennäköisimmin vaikuttavat ennusteen luotettavuuteen kentän arvon ja tietyn luokan täsmäytyksessä.</span><span class="sxs-lookup"><span data-stu-id="be2ed-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="be2ed-156">**Suorituskyky** osoittaa, miten ennusteet onnistuvat.</span><span class="sxs-lookup"><span data-stu-id="be2ed-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="be2ed-157">Valitse tämä linkki, jos haluat lisätietoja.</span><span class="sxs-lookup"><span data-stu-id="be2ed-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="be2ed-158">**Esikatselu**-kohdassa on esimerkkejä ennusteen tulostietojoukosta ja ennustetun arvon todennäköisyys tai luotettavuus. 0 tarkoittaa epävarmaa ja 1 varmaa.</span><span class="sxs-lookup"><span data-stu-id="be2ed-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="be2ed-159">Päivitä ennuste</span><span class="sxs-lookup"><span data-stu-id="be2ed-159">Update a prediction</span></span>

1. <span data-ttu-id="be2ed-160">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Analytiikka** > **Ennusteet** > **Omat ennusteet**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="be2ed-161">Valitse päivitettävä ennuste ja valitse sitten **Päivitä**-kuvake.</span><span class="sxs-lookup"><span data-stu-id="be2ed-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="be2ed-162">Ennuste ajoitetaan käsittelyä varten.</span><span class="sxs-lookup"><span data-stu-id="be2ed-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="be2ed-163">Näet edellisen päivitysajankohdan **Päivitetty**-sarakkeessa **Ennusteet**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="be2ed-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="be2ed-164">Muokkaa ennustetta</span><span class="sxs-lookup"><span data-stu-id="be2ed-164">Edit a prediction</span></span>

<span data-ttu-id="be2ed-165">Kun olet luonut ennusteen, voit mukauttaa mallia AI Builderissa ja tehostaa mallin toimintaa.</span><span class="sxs-lookup"><span data-stu-id="be2ed-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="be2ed-166">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Analytiikka** > **Ennusteet** > **Omat ennusteet**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="be2ed-167">Valitse ennuste, jota haluat muokata.</span><span class="sxs-lookup"><span data-stu-id="be2ed-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="be2ed-168">Valitse **Toiminnot**-sarakkeen kolme pistettä ja valitse sitten **Tarkastele**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="be2ed-169">Valitse **Mukauta AI Builderissa**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="be2ed-170">Päivitä malli AI Builderissa.</span><span class="sxs-lookup"><span data-stu-id="be2ed-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="be2ed-171">[Lisätietoja mallien hallinnasta AI builderissa](/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="be2ed-171">[Learn more about managing models in the AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="be2ed-172">Ennusteen seuraava suoritus käyttää luomaasi päivitettyä mallia.</span><span class="sxs-lookup"><span data-stu-id="be2ed-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="be2ed-173">AI Builderissa luodut uudet mallit eivät näy käyttäjäryhmän merkityksellisissä tiedoissa, ellei mallia luotu edellä mainituista kokemuksista.</span><span class="sxs-lookup"><span data-stu-id="be2ed-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="be2ed-174">Poista ennuste</span><span class="sxs-lookup"><span data-stu-id="be2ed-174">Remove a prediction</span></span>

1. <span data-ttu-id="be2ed-175">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Analytiikka** > **Ennusteet** > **Omat ennusteet**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="be2ed-176">Valitse poistettava ennuste.</span><span class="sxs-lookup"><span data-stu-id="be2ed-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="be2ed-177">Valitse **Toiminnot**-sarakkeen kolme pistettä ja valitse sitten **Poista**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="be2ed-178">Vahvista poisto.</span><span class="sxs-lookup"><span data-stu-id="be2ed-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="be2ed-179">Vianmääritys</span><span class="sxs-lookup"><span data-stu-id="be2ed-179">Troubleshooting</span></span>

<span data-ttu-id="be2ed-180">Jos Common Data Servicen liittämisprosessia ei voi suorittaa virheen vuoksi, voit yrittää suorittaa prosessin manuaalisesti.</span><span class="sxs-lookup"><span data-stu-id="be2ed-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="be2ed-181">Liittämisprosessissa voi esiintyä kaksi tunnettua ongelmaa:</span><span class="sxs-lookup"><span data-stu-id="be2ed-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="be2ed-182">Asiakaskortin apuohjelmaratkaisua ei ole asennettu.</span><span class="sxs-lookup"><span data-stu-id="be2ed-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="be2ed-183">[Asenna ja määritä ratkaisu noudattamalla ohjeita](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="be2ed-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="be2ed-184">Sovellusoikeuksia ei myönnetä.</span><span class="sxs-lookup"><span data-stu-id="be2ed-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="be2ed-185">Siirry [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com)en.</span><span class="sxs-lookup"><span data-stu-id="be2ed-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="be2ed-186">Valitse **Ympäristöt**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="be2ed-187">Valitse sen ympäristön vieressä oleva kolme pistettä, johon haluat lisätä oikeudet, ja valitse sitten **Asetukset**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="be2ed-188">Laajenna **Käyttäjät ja oikeudet** ja valitse **Käyttäjät**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="be2ed-189">Valitse **+ Uusi** ja valitse sitten **Käyttäjä**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="be2ed-190">Valitse **Sovelluksen käyttäjä**, jos sitä ei ole jo valittu, ja anna seuraavat tiedot:</span><span class="sxs-lookup"><span data-stu-id="be2ed-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="be2ed-191">**Käyttäjänimi:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="be2ed-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="be2ed-192">**Sovellustunnus:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="be2ed-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="be2ed-193">**Etunimi:** Customer</span><span class="sxs-lookup"><span data-stu-id="be2ed-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="be2ed-194">**Sukunimi:** Insights</span><span class="sxs-lookup"><span data-stu-id="be2ed-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="be2ed-195">**Ensisijainen sähköposti:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="be2ed-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="be2ed-196">Valitse **Tallenna ja sulje**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="be2ed-197">Valitse juuri luotu käyttäjä.</span><span class="sxs-lookup"><span data-stu-id="be2ed-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="be2ed-198">Valitse yläosan valikkopalkista **Hallitse rooleja**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="be2ed-199">Valitse **Järjestelmänvalvoja** ja valitse sitten **OK**.</span><span class="sxs-lookup"><span data-stu-id="be2ed-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]