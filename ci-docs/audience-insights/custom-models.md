---
title: Mukautetut koneoppimisen mallit | Microsoft-dokumentit
description: Azuren automaattianalyysipalvelujen mukautettujen mallien käyttäminen Dynamics 365 Customer Insightsissa.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 87fb517e9f0b380f9721f77470dceb3bcb7e5616
ms.sourcegitcommit: 55c00ea61c78db7b3b54894c01afb3246dff31c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2021
ms.locfileid: "5700664"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="5a9dc-103">Mukautetut koneoppimisen mallit</span><span class="sxs-lookup"><span data-stu-id="5a9dc-103">Custom machine learning models</span></span>

<span data-ttu-id="5a9dc-104">Valitsemalla **Analytiikka** > **Mukautetut mallit** voit hallita Azuren automaattianalyysipalvelumalleihin perustuvia työnkulkuja.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="5a9dc-105">Työnkulut auttavat valitsemaan tiedot, joista halutaan muodostaa merkityksellisiä tietoja, ja yhdistää tulokset yhtenäistettyihin asiakastietoihin.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="5a9dc-106">Lisätietoja mukautettujen koneoppimismallien muodostamisesta on kohdassa [Azuren automaattianalyysipalveluihin perustuvien mallien käyttäminen](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="5a9dc-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="5a9dc-107">Tekoälyn vastuullinen käyttö</span><span class="sxs-lookup"><span data-stu-id="5a9dc-107">Responsible AI</span></span>

<span data-ttu-id="5a9dc-108">Ennusteiden ominaisuuksilla voi luoda parempia asiakaskokemuksia sekä parantaa liiketoimintaominaisuuksia ja tulovirtoja.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="5a9dc-109">On erittäin suositeltavaa tasapainottaa eettisesti ennusteen arvo sekä sen vaikutukset ja mahdolliset puolueellisuudet.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="5a9dc-110">Lisätietoja tavasta, jolla Microsoft [ottaa tekoälyn vastuullisen käytön huomioon](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="5a9dc-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="5a9dc-111">Saat myös lisätietoja Azuren automaattianalyysipalveluja koskevista [vastuullisten automaattianalyysipalvelujen tekniikoista ja prosesseista](/azure/machine-learning/concept-responsible-ml).</span><span class="sxs-lookup"><span data-stu-id="5a9dc-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5a9dc-112">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="5a9dc-112">Prerequisites</span></span>

- <span data-ttu-id="5a9dc-113">Tämä toiminto tukee tällä hetkellä verkkopalveluja, jotka on julkaistu [koneoppimisstudiossa (perinteinen)](https://studio.azureml.net) ja [Azuren automaattianalyysipalvelujen eräjaksoissa](/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="5a9dc-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="5a9dc-114">Tämän toiminnon käyttöä varten tarvitaan Azure Data Lake Gen2 -tallennustilin, joka on liitetty Azure-studioesiintymään.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="5a9dc-115">Lisätietoja on kohdassa [Azure Data Lake Storage Gen2 -tallennustilatilin luominen](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span><span class="sxs-lookup"><span data-stu-id="5a9dc-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="5a9dc-116">Azure-automaattianalyysin työtiloja, joissa on putkia varten tarvitset Azure-automaattianalyysin työtilan omistajan tai järjestelmänvalvojan käyttöoikeudet.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5a9dc-117">Tiedot siirretään Customer Insights -ilmentymien ja työnkulun valittujen Azure-verkkopalveluiden tai -putkien välillä.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="5a9dc-118">Kun siirrät tietoja Azure-palveluun, varmista, että palvelu on määritetty käsittelemään tietoja tavalla ja sijainnilla, jotka ovat organisaatiotasi tai näitä tietoja koskevien juridisten tai lakisääteisten vaatimusten mukaisia.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="5a9dc-119">Uuden työnkulun lisääminen</span><span class="sxs-lookup"><span data-stu-id="5a9dc-119">Add a new workflow</span></span>

1. <span data-ttu-id="5a9dc-120">Valitse **Analytiikka** > **Mukautetut mallit** ja valitse **Uusi työnkulku**.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="5a9dc-121">Anna mukautetulle mallille tunnistettava nimi **Nimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5a9dc-122">![Näyttökuva Uusi työnkulku -ruudusta](media/new-workflowv2.png "Näyttökuva Uusi työnkulku -ruudusta")</span><span class="sxs-lookup"><span data-stu-id="5a9dc-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="5a9dc-123">Valitse organisaatio, joka sisältää verkkopalvelun **Vuokraaja, joka sisältää verkkopalvelun** -kohdassa.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="5a9dc-124">Jos Azuren koneoppimispalvelun tilaus on eri vuokraajassa kuin Customer Insights, valitse **sisäänkirjaus** valtuustiedoilla valitussa organisaatiossa.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="5a9dc-125">Valitse verkkopalveluun liitetyt **työtilat**.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="5a9dc-126">Luettelossa on kaksi osaa: toinen on Azuren automaattianalyysipalvelujen v1 (koneoppimisstudio (perinteinen)) ja toinen Azuren automaattianalyysipalvelut v2 (Azuren automaattianalyysipalvelut).</span><span class="sxs-lookup"><span data-stu-id="5a9dc-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="5a9dc-127">Jos ole varma, mikä työtila sopii omaan Koneoppimisstudio (perinteinen) -työtilaan, valitse **Mikä tahansa**.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="5a9dc-128">Valitse Koneoppimisstudio (perinteinen) -verkkopalvelu tai Azuren automaattianalyysipalvelut -putki avattavassa **WWW-palvelu, joka sisältää mallin** -luettelossa.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="5a9dc-129">Valitse sitten **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="5a9dc-130">Lisätietoja [verkkopalvelun julkaisemisesta koneoppimisstudiossa (perinteinen)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="5a9dc-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="5a9dc-131">Lisätietoja [jakson julkaisemisesta Azuren automaattianalyysipalveluissa suunnitteluohjelman](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) tai [SDK:n](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) avulla.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="5a9dc-132">Jakso on julkaistava [jakson päätepisteessä](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="5a9dc-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="5a9dc-133">Valitse kullekin **verkkopalvelun syötteelle** vastaava **Entiteetti** käyttäjäryhmän merkityksellisissä tiedoissa ja valitse sitten **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="5a9dc-134">Mukautettu mallityönkulku käyttää heuristiikkaa verkkopalvelun syöttökenttien yhdistämisessä entiteettimääritteisiin kentän nimen ja tietotyypin perusteella.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="5a9dc-135">Näkyviin tulee virhe, jos verkkopalvelun kenttää ei voi yhdistää entiteettiin.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5a9dc-136">![Työnkulun määrittäminen](media/intelligence-screen2-updated.png "Työnkulun määrittäminen")</span><span class="sxs-lookup"><span data-stu-id="5a9dc-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="5a9dc-137">Määritä seuraavat ominaisuudet **Mallin tulosteparametrit** -vaiheessa:</span><span class="sxs-lookup"><span data-stu-id="5a9dc-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="5a9dc-138">Koneoppimisstudio (perinteinen)</span><span class="sxs-lookup"><span data-stu-id="5a9dc-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="5a9dc-139">Anna sen tulosteen **entiteetin nimi**, johon haluat verkkopalvelun tulosten siirtyvän.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="5a9dc-140">Azuren automaattianalyysipalvelut</span><span class="sxs-lookup"><span data-stu-id="5a9dc-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="5a9dc-141">Anna sen tulosteen **entiteetin nimi**, johon haluat jakson tulosten siirtyvän.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="5a9dc-142">Valitse avattavassa luettelossa eränjakson **Tulostetietosäilön parametrin nimi**.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="5a9dc-143">Valitse avattavassa luettelossa eränjakson **Tulostepolun parametrin nimi**.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="5a9dc-144">![Mallin tulosteparametri -ruutu](media/intelligence-screen3-outputparameters.png "Mallin tulosteparametri -ruutu")</span><span class="sxs-lookup"><span data-stu-id="5a9dc-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="5a9dc-145">Valitse vastaava määrite siinä avattavassa **Asiakastunnus tuloksissa** -luettelossa, joka määrittää asiakkaat, ja valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-145">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5a9dc-146">![Tulosten liittäminen Asiakastiedot-ruutuun](media/intelligence-screen4-relatetocustomer.png "Tulosten liittäminen Asiakastiedot-ruutuun")</span><span class="sxs-lookup"><span data-stu-id="5a9dc-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="5a9dc-147">Näkyviin tulee **Työnkulku tallennettu** -näyttö, jossa ovat työnkulun tiedot.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="5a9dc-148">Azuren automaattianalyysipalvelut -jaksolle määritettiin työnkulku, käyttäjäryhmän merkitykselliset tiedot liitetään jakson sisältävään työtilaan.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="5a9dc-149">Käyttäjäryhmän merkityksellisten tietojen rooli Azure-työtilassa on **Osallistuja**.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="5a9dc-150">Valitse **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-150">Select **Done**.</span></span>

1. <span data-ttu-id="5a9dc-151">Työnkulku voidaan nyt suorittaa **Mukautetut mallit** -sivulta.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="5a9dc-152">Työnkulun muokkaaminen</span><span class="sxs-lookup"><span data-stu-id="5a9dc-152">Edit a workflow</span></span>

1. <span data-ttu-id="5a9dc-153">Valitse **Mukautetut mallit** -sivulla **Toiminnot**-sarakkeen pystysuorat kolme pistettä aiemmin luodun työnkulun vieressä ja valitse **Muokkaa**.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="5a9dc-154">Vaikka voit päivittää työnkulun tunnistettavan nimen **Näyttönimi**-kentässä, et voi muuttaa määritettyä verkkopalvelua tai jaksoa.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="5a9dc-155">Valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-155">Select **Next**.</span></span>

1. <span data-ttu-id="5a9dc-156">Kullekin **verkkopalvelun syötteelle** voidaan päivittää vastaava **Entiteetti** käyttäjäryhmän merkityksellisissä tiedoissa.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="5a9dc-157">Valitse sitten **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="5a9dc-158">Määritä seuraavat ominaisuudet **Mallin tulosteparametrit** -vaiheessa:</span><span class="sxs-lookup"><span data-stu-id="5a9dc-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="5a9dc-159">Koneoppimisstudio (perinteinen)</span><span class="sxs-lookup"><span data-stu-id="5a9dc-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="5a9dc-160">Anna sen tulosteen **entiteetin nimi**, johon haluat verkkopalvelun tulosten siirtyvän.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="5a9dc-161">Azuren automaattianalyysipalvelut</span><span class="sxs-lookup"><span data-stu-id="5a9dc-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="5a9dc-162">Anna sen tulosteen **entiteetin nimi**, johon haluat jakson tulosten siirtyvän.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="5a9dc-163">Valitse testijaksolle **Tulostetietosäilön parametrin nimi**.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="5a9dc-164">Valitse testijaksolle **Tulostepolun parametrin nimi**.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="5a9dc-165">Valitse vastaava määrite siinä avattavassa **Asiakastunnus tuloksissa** -luettelossa, joka määrittää asiakkaat, ja valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-165">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="5a9dc-166">Päättelytulosteesta on valittava määrite, jossa on samankaltaiset arvot kuin asiakasentiteetin Asiakastunnus-sarakkeessa.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="5a9dc-167">Jos tietojoukossa ei ole kyseistä saraketta, valitse määrite, joka määrittää rivin yksilöivästi.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="5a9dc-168">Työnkulun suorittaminen</span><span class="sxs-lookup"><span data-stu-id="5a9dc-168">Run a workflow</span></span>

1. <span data-ttu-id="5a9dc-169">Valitse **Mukautetut mallit** -sivulla **Toiminnot**-sarakkeen pystysuorat kolme pistettä aiemmin luodun työnkulun vieressä ja valitse Muokkaa.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="5a9dc-170">Valitse **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-170">Select **Run**.</span></span>

<span data-ttu-id="5a9dc-171">Työnkulku suoritetaan myös automaattisesti jokaisen ajoitetun päivityksen yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="5a9dc-172">Lisätietoja [aikataulutettujen päivitysten määrittämisestä](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5a9dc-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="5a9dc-173">Työnkulun poistaminen</span><span class="sxs-lookup"><span data-stu-id="5a9dc-173">Delete a workflow</span></span>

1. <span data-ttu-id="5a9dc-174">Valitse **Mukautetut mallit** -sivulla **Toiminnot**-sarakkeen pystysuorat kolme pistettä aiemmin luodun työnkulun vieressä ja valitse Muokkaa.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="5a9dc-175">Valitse **Poista** ja vahvista poistaminen.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="5a9dc-176">Työnkulku poistetaan.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-176">Your workflow will be deleted.</span></span> <span data-ttu-id="5a9dc-177">[Entiteetti](entities.md), joka luotiin työnkulun yhteydessä, on yhä olemassa. Voit tarkastella sitä **Entiteetit**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="5a9dc-178">Tulokset</span><span class="sxs-lookup"><span data-stu-id="5a9dc-178">Results</span></span>

<span data-ttu-id="5a9dc-179">Työnkulun tulokset tallennetaan mallituotoksen parametrivaiheen aikana määritettyön entiteettiin.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="5a9dc-180">Voit käyttää näitä tietoja [entiteettisivulta](entities.md) tai [API-liittymän](apis.md) kautta.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="5a9dc-181">Ohjelmointirajapinnan käyttö</span><span class="sxs-lookup"><span data-stu-id="5a9dc-181">API Access</span></span>

<span data-ttu-id="5a9dc-182">Jos haluat saada tietoja mukautetusta mallientiteetistä, käytä tiettyä OData-kyselyä seuraavassa muodossa:</span><span class="sxs-lookup"><span data-stu-id="5a9dc-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="5a9dc-183">Korvaa `<your instance id>` Customer Insights -ympäristön tunnuksella, jonka löydät selaimen osoiterivillä, kun käytät Customer Insights -tietoja.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="5a9dc-184">Korvaa `<custom model output entity>` mukautetun mallin määrityksen mallitulosteparametrien vaiheessa annetulla entiteetin nimellä.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="5a9dc-185">Korvaa `<guid value>` sen asiakkaan asiakastunnuksella, jonka tietuetta haluat käyttää.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="5a9dc-186">Tämä tunnus löytyy yleensä [Asiakasprofiilit-sivun](customer-profiles.md) CustomerID-kentästä.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="5a9dc-187">Usein kysyttyjä kysymyksiä</span><span class="sxs-lookup"><span data-stu-id="5a9dc-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="5a9dc-188">Miksi en näe myyntiputkea mukautetun mallin työnkulun määrittämisen aikana?</span><span class="sxs-lookup"><span data-stu-id="5a9dc-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="5a9dc-189">Tämä ongelma johtuu usein putken määritysongelmasta.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="5a9dc-190">Varmista, että [syöteparametri on määritetty](azure-machine-learning-experiments.md#dataset-configuration) ja [tulostetietosäilö ja polkuparametrit](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) on myös määritetty.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="5a9dc-191">Mitä "Älykkään toiminnon työnkulkua ei voi tallentaa" -virhe tarkoittaa?</span><span class="sxs-lookup"><span data-stu-id="5a9dc-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="5a9dc-192">Käyttäjät näkevät tämän virhesanoman yleensä silloin, kun heillä ei ole työtilan omistajan tai käyttäjän järjestelmänvalvojakäyttöoikeuksia.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="5a9dc-193">Käyttäjä tarvitsee korkeamman käyttöoikeustason, jotta Customer Insights voi käsitellä työnkulkua palveluna sen sijaan, että hän voi käyttää käyttäjätietoja työnkulun myöhemmissä vaiheissa.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
