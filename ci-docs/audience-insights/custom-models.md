---
title: Mukautetut koneoppimisen mallit | Microsoft-dokumentit
description: Azuren automaattianalyysipalvelujen mukautettujen mallien käyttäminen Dynamics 365 Customer Insightsissa.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267230"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="cc4a2-103">Mukautetut koneoppimisen mallit</span><span class="sxs-lookup"><span data-stu-id="cc4a2-103">Custom machine learning models</span></span>

<span data-ttu-id="cc4a2-104">Valitsemalla **Analytiikka** > **Mukautetut mallit** voit hallita Azuren automaattianalyysipalvelumalleihin perustuvia työnkulkuja.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="cc4a2-105">Työnkulut auttavat valitsemaan tiedot, joista halutaan muodostaa merkityksellisiä tietoja, ja yhdistää tulokset yhtenäistettyihin asiakastietoihin.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="cc4a2-106">Lisätietoja mukautettujen koneoppimismallien muodostamisesta on kohdassa [Azuren automaattianalyysipalveluihin perustuvien mallien käyttäminen](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="cc4a2-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="cc4a2-107">Tekoälyn vastuullinen käyttö</span><span class="sxs-lookup"><span data-stu-id="cc4a2-107">Responsible AI</span></span>

<span data-ttu-id="cc4a2-108">Ennusteiden ominaisuuksilla voi luoda parempia asiakaskokemuksia sekä parantaa liiketoimintaominaisuuksia ja tulovirtoja.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="cc4a2-109">On erittäin suositeltavaa tasapainottaa eettisesti ennusteen arvo sekä sen vaikutukset ja mahdolliset puolueellisuudet.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="cc4a2-110">Lisätietoja tavasta, jolla Microsoft [ottaa tekoälyn vastuullisen käytön huomioon](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="cc4a2-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="cc4a2-111">Saat myös lisätietoja Azuren automaattianalyysipalveluja koskevista [vastuullisten automaattianalyysipalvelujen tekniikoista ja prosesseista](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml).</span><span class="sxs-lookup"><span data-stu-id="cc4a2-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cc4a2-112">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="cc4a2-112">Prerequisites</span></span>

- <span data-ttu-id="cc4a2-113">Tämä toiminto tukee tällä hetkellä verkkopalveluja, jotka on julkaistu [koneoppimisstudiossa (perinteinen)](https://studio.azureml.net) ja [Azuren automaattianalyysipalvelujen eräjaksoissa](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="cc4a2-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="cc4a2-114">Tämän toiminnon käyttöä varten tarvitaan Azure Data Lake Gen2 -tallennustilin, joka on liitetty Azure-studioesiintymään.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="cc4a2-115">Lisätietoja on kohdassa [Azure Data Lake Storage Gen2 -tallennustilatilin luominen](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="cc4a2-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="cc4a2-116">Uuden työnkulun lisääminen</span><span class="sxs-lookup"><span data-stu-id="cc4a2-116">Add a new workflow</span></span>

1. <span data-ttu-id="cc4a2-117">Valitse **Analytiikka** > **Mukautetut mallit** ja valitse **Uusi työnkulku**.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="cc4a2-118">Anna mukautetulle mallille tunnistettava nimi **Nimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cc4a2-119">![Näyttökuva Uusi työnkulku -ruudusta](media/new-workflowv2.png "Näyttökuva Uusi työnkulku -ruudusta")</span><span class="sxs-lookup"><span data-stu-id="cc4a2-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="cc4a2-120">Valitse organisaatio, joka sisältää verkkopalvelun **Vuokraaja, joka sisältää verkkopalvelun** -kohdassa.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="cc4a2-121">Jos Azuren koneoppimispalvelun tilaus on eri vuokraajassa kuin Customer Insights, valitse **sisäänkirjaus** valtuustiedoilla valitussa organisaatiossa.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="cc4a2-122">Valitse verkkopalveluun liitetyt **työtilat**.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="cc4a2-123">Luettelossa on kaksi osaa: toinen on Azuren automaattianalyysipalvelujen v1 (koneoppimisstudio (perinteinen)) ja toinen Azuren automaattianalyysipalvelut v2 (Azuren automaattianalyysipalvelut).</span><span class="sxs-lookup"><span data-stu-id="cc4a2-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="cc4a2-124">Jos ole varma, mikä työtila sopii omaan Koneoppimisstudio (perinteinen) -työtilaan, valitse **Mikä tahansa**.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="cc4a2-125">Valitse Koneoppimisstudio (perinteinen) -verkkopalvelu tai Azuren automaattianalyysipalvelut -putki avattavassa **WWW-palvelu, joka sisältää mallin** -luettelossa.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="cc4a2-126">Valitse sitten **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="cc4a2-127">Lisätietoja [verkkopalvelun julkaisemisesta koneoppimisstudiossa (perinteinen)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="cc4a2-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="cc4a2-128">Lisätietoja [jakson julkaisemisesta Azuren automaattianalyysipalveluissa suunnitteluohjelman](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) tai [SDK:n](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) avulla.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="cc4a2-129">Jakso on julkaistava [jakson päätepisteessä](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="cc4a2-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="cc4a2-130">Valitse kullekin **verkkopalvelun syötteelle** vastaava **Entiteetti** käyttäjäryhmän merkityksellisissä tiedoissa ja valitse sitten **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="cc4a2-131">Mukautettu mallityönkulku käyttää heuristiikkaa verkkopalvelun syöttökenttien yhdistämisessä entiteettimääritteisiin kentän nimen ja tietotyypin perusteella.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-131">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="cc4a2-132">Näkyviin tulee virhe, jos verkkopalvelun kenttää ei voi yhdistää entiteettiin.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-132">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cc4a2-133">![Työnkulun määrittäminen](media/intelligence-screen2-updated.png "Työnkulun määrittäminen")</span><span class="sxs-lookup"><span data-stu-id="cc4a2-133">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>
   
1. <span data-ttu-id="cc4a2-134">Määritä seuraavat ominaisuudet **Mallin tulosteparametrit** -vaiheessa:</span><span class="sxs-lookup"><span data-stu-id="cc4a2-134">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="cc4a2-135">Koneoppimisstudio (perinteinen)</span><span class="sxs-lookup"><span data-stu-id="cc4a2-135">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="cc4a2-136">Anna sen tulosteen **entiteetin nimi**, johon haluat verkkopalvelun tulosten siirtyvän.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-136">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="cc4a2-137">Azuren automaattianalyysipalvelut</span><span class="sxs-lookup"><span data-stu-id="cc4a2-137">Azure Machine Learning</span></span>
      1. <span data-ttu-id="cc4a2-138">Anna sen tulosteen **entiteetin nimi**, johon haluat jakson tulosten siirtyvän.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-138">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="cc4a2-139">Valitse avattavassa luettelossa eränjakson **Tulostetietosäilön parametrin nimi**.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-139">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="cc4a2-140">Valitse avattavassa luettelossa eränjakson **Tulostepolun parametrin nimi**.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-140">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="cc4a2-141">![Mallin tulosteparametri -ruutu](media/intelligence-screen3-outputparameters.png "Mallin tulosteparametri -ruutu")</span><span class="sxs-lookup"><span data-stu-id="cc4a2-141">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="cc4a2-142">Valitse vastaava määrite siinä avattavassa **Asiakastunnus tuloksissa** -luettelossa, joka määrittää asiakkaat, ja valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-142">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cc4a2-143">![Tulosten liittäminen Asiakastiedot-ruutuun](media/intelligence-screen4-relatetocustomer.png "Tulosten liittäminen Asiakastiedot-ruutuun")</span><span class="sxs-lookup"><span data-stu-id="cc4a2-143">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="cc4a2-144">Näkyviin tulee **Työnkulku tallennettu** -näyttö, jossa ovat työnkulun tiedot.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-144">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="cc4a2-145">Azuren automaattianalyysipalvelut -jaksolle määritettiin työnkulku, käyttäjäryhmän merkitykselliset tiedot liitetään jakson sisältävään työtilaan.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-145">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="cc4a2-146">Käyttäjäryhmän merkityksellisten tietojen rooli Azure-työtilassa on **Osallistuja**.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-146">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="cc4a2-147">Valitse **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-147">Select **Done**.</span></span>

1. <span data-ttu-id="cc4a2-148">Työnkulku voidaan nyt suorittaa **Mukautetut mallit** -sivulta.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-148">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="cc4a2-149">Työnkulun muokkaaminen</span><span class="sxs-lookup"><span data-stu-id="cc4a2-149">Edit a workflow</span></span>

1. <span data-ttu-id="cc4a2-150">Valitse **Mukautetut mallit** -sivulla **Toiminnot**-sarakkeen pystysuorat kolme pistettä aiemmin luodun työnkulun vieressä ja valitse **Muokkaa**.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-150">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="cc4a2-151">Vaikka voit päivittää työnkulun tunnistettavan nimen **Näyttönimi**-kentässä, et voi muuttaa määritettyä verkkopalvelua tai jaksoa.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-151">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="cc4a2-152">Valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-152">Select **Next**.</span></span>

1. <span data-ttu-id="cc4a2-153">Kullekin **verkkopalvelun syötteelle** voidaan päivittää vastaava **Entiteetti** käyttäjäryhmän merkityksellisissä tiedoissa.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-153">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="cc4a2-154">Valitse sitten **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-154">Then, select **Next**.</span></span>

1. <span data-ttu-id="cc4a2-155">Määritä seuraavat ominaisuudet **Mallin tulosteparametrit** -vaiheessa:</span><span class="sxs-lookup"><span data-stu-id="cc4a2-155">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="cc4a2-156">Koneoppimisstudio (perinteinen)</span><span class="sxs-lookup"><span data-stu-id="cc4a2-156">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="cc4a2-157">Anna sen tulosteen **entiteetin nimi**, johon haluat verkkopalvelun tulosten siirtyvän.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-157">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="cc4a2-158">Azuren automaattianalyysipalvelut</span><span class="sxs-lookup"><span data-stu-id="cc4a2-158">Azure Machine Learning</span></span>
      1. <span data-ttu-id="cc4a2-159">Anna sen tulosteen **entiteetin nimi**, johon haluat jakson tulosten siirtyvän.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-159">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="cc4a2-160">Valitse testijaksolle **Tulostetietosäilön parametrin nimi**.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-160">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="cc4a2-161">Valitse testijaksolle **Tulostepolun parametrin nimi**.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-161">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="cc4a2-162">Valitse vastaava määrite siinä avattavassa **Asiakastunnus tuloksissa** -luettelossa, joka määrittää asiakkaat, ja valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-162">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="cc4a2-163">Päättelytulosteesta on valittava määrite, jossa on samankaltaiset arvot kuin asiakasentiteetin Asiakastunnus-sarakkeessa.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-163">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="cc4a2-164">Jos tietojoukossa ei ole kyseistä saraketta, valitse määrite, joka määrittää rivin yksilöivästi.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-164">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="cc4a2-165">Työnkulun suorittaminen</span><span class="sxs-lookup"><span data-stu-id="cc4a2-165">Run a workflow</span></span>

1. <span data-ttu-id="cc4a2-166">Valitse **Mukautetut mallit** -sivulla **Toiminnot**-sarakkeen pystysuorat kolme pistettä aiemmin luodun työnkulun vieressä ja valitse Muokkaa.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-166">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="cc4a2-167">Valitse **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-167">Select **Run**.</span></span>

<span data-ttu-id="cc4a2-168">Työnkulku suoritetaan myös automaattisesti jokaisen ajoitetun päivityksen yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-168">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="cc4a2-169">Lisätietoja [aikataulutettujen päivitysten määrittämisestä](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cc4a2-169">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="cc4a2-170">Työnkulun poistaminen</span><span class="sxs-lookup"><span data-stu-id="cc4a2-170">Delete a workflow</span></span>

1. <span data-ttu-id="cc4a2-171">Valitse **Mukautetut mallit** -sivulla **Toiminnot**-sarakkeen pystysuorat kolme pistettä aiemmin luodun työnkulun vieressä ja valitse Muokkaa.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-171">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="cc4a2-172">Valitse **Poista** ja vahvista poistaminen.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-172">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="cc4a2-173">Työnkulku poistetaan.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-173">Your workflow will be deleted.</span></span> <span data-ttu-id="cc4a2-174">[Entiteetti](entities.md), joka luotiin työnkulun yhteydessä, on yhä olemassa. Voit tarkastella sitä **Entiteetit**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="cc4a2-174">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]