---
title: Azuren automaattianalyysipalvelujen kokeileminen
description: Azuren automaattianalyysipalveluihin perustuvien mallien käyttäminen Dynamics 365 Customer Insightsissa.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: 6f00d3202dc29d810bdd218d06c7d04e551846e8
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668764"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="87d3c-103">Azuren automaattianalyysipalveluihin perustuvien mallien käyttäminen</span><span class="sxs-lookup"><span data-stu-id="87d3c-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="87d3c-104">Dynamics 365 Customer Insightsin yhtenäistetyt tiedot ovat sellaisten koneoppimismallien muodostamisen lähde, joilla voidaan luoda lisää merkityksellisiä liiketoimintatietoja.</span><span class="sxs-lookup"><span data-stu-id="87d3c-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="87d3c-105">Integroituneet Customer Insights sekä koneoppimisstudio (perinteinen) ja Azuren automaattianalyysipalvelut käyttävät käyttäjän mukautettuja malleja.</span><span class="sxs-lookup"><span data-stu-id="87d3c-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="87d3c-106">Kohdassa [Koneoppimisstudion (perinteinen) kokeileminen](machine-learning-studio-experiments.md) on esimerkkejä kokeiluista, jotka perustuvat koneoppimisstudioon (perinteinen).</span><span class="sxs-lookup"><span data-stu-id="87d3c-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="87d3c-107">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="87d3c-107">Prerequisites</span></span>

- <span data-ttu-id="87d3c-108">Customer Insightsin käyttöoikeus</span><span class="sxs-lookup"><span data-stu-id="87d3c-108">Access to Customer Insights</span></span>
- <span data-ttu-id="87d3c-109">Aktiivinen Azure Enterprise -tilaus</span><span class="sxs-lookup"><span data-stu-id="87d3c-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="87d3c-110">Yhdistetyt asiakasprofiilit</span><span class="sxs-lookup"><span data-stu-id="87d3c-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="87d3c-111">[Entiteettivienti Azure Blob -säilöön](export-azure-blob-storage.md) määritetty</span><span class="sxs-lookup"><span data-stu-id="87d3c-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="87d3c-112">Azuren automaattianalyysipalvelujen työtilan määrittäminen</span><span class="sxs-lookup"><span data-stu-id="87d3c-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="87d3c-113">[Azuren automaattianalyysipalvelujen työtilan luonti](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) sisältää lisätietoja työtilan luontivaihtoehdoista.</span><span class="sxs-lookup"><span data-stu-id="87d3c-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="87d3c-114">Paras tulos saadaan luomalla työtila sillä Azure-alueella, joka on maantieteellisesti lähinnä Customer Insights -ympäristöä.</span><span class="sxs-lookup"><span data-stu-id="87d3c-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="87d3c-115">Työtilaa käytetään [Azuren koneoppimisstudion](https://ml.azure.com/) kautta.</span><span class="sxs-lookup"><span data-stu-id="87d3c-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="87d3c-116">Työtilaa voi [käyttää eri tavoin](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction).</span><span class="sxs-lookup"><span data-stu-id="87d3c-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="87d3c-117">Azuren automaattianalyysipalvelujen suunnitteluohjelman käyttäminen</span><span class="sxs-lookup"><span data-stu-id="87d3c-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="87d3c-118">Azuren automaattianalyysipalvelujen suunnitteluohjelma on visuaalinen kaavio, jossa tietojoukkoja ja moduuleja voi vetää ja pudottaa samalla tavoin kuin koneoppimisstudiossa (perinteinen).</span><span class="sxs-lookup"><span data-stu-id="87d3c-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="87d3c-119">Suunnitteluohjelmassa luotu eräjakso voidaan integroida Customer Insightsiin, jos määritykset sen sallivat.</span><span class="sxs-lookup"><span data-stu-id="87d3c-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="87d3c-120">Azuren automaattianalyysipalvelujen SDK:n käyttäminen</span><span class="sxs-lookup"><span data-stu-id="87d3c-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="87d3c-121">Data-analyytikot ja tekoälykehittäjät luovat koneoppisen työnkulkuja käyttämällä [Azuren automaattianalyysipalvelujen SDK:ta](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="87d3c-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="87d3c-122">Tällä hetkellä SDK:lla koulutettuja malleja ei voi integroida suoraan Customer Insightsiin.</span><span class="sxs-lookup"><span data-stu-id="87d3c-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="87d3c-123">Customer Insights -integrointiin tarvitaan mallia käyttävä eräpäättelyjakso.</span><span class="sxs-lookup"><span data-stu-id="87d3c-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="87d3c-124">Customer Insights -integroinnin eräjaksovaatimukset</span><span class="sxs-lookup"><span data-stu-id="87d3c-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="87d3c-125">Tietojoukon määritys</span><span class="sxs-lookup"><span data-stu-id="87d3c-125">Dataset Configuration</span></span>

<span data-ttu-id="87d3c-126">Luotavien tietojoukkojen on käytettävä Customer Insightsin entiteettitietoja eräpäättelyjaksoon.</span><span class="sxs-lookup"><span data-stu-id="87d3c-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="87d3c-127">Nämä tietojoukot on rekisteröitävä työtilassa.</span><span class="sxs-lookup"><span data-stu-id="87d3c-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="87d3c-128">Tällä tuetaan vain [taukokkomuotoisia tietojoukkoja](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset), joiden muoto on.csv.</span><span class="sxs-lookup"><span data-stu-id="87d3c-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="87d3c-129">Entiteettitietoja vastaavat tietojoukot on muutettava jaksoparametreiksi.</span><span class="sxs-lookup"><span data-stu-id="87d3c-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="87d3c-130">Suunnitteluohjelman tietojoukkoparametrit</span><span class="sxs-lookup"><span data-stu-id="87d3c-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="87d3c-131">Avaa suunnitteluohjelmassa **Valitse tietojoukon sarakkeet** ja valitse **Määritä jaksoparametrina**, jossa annetaan parametrin nimi.</span><span class="sxs-lookup"><span data-stu-id="87d3c-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="87d3c-132">![Suunnitteluohjelman tietojoukon muuttaminen parametreiksi](media/intelligence-designer-dataset-parameters.png "Tietojoukon muuttaminen parametreiksi suunnitteluohjelmassa")</span><span class="sxs-lookup"><span data-stu-id="87d3c-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="87d3c-133">SDK:n tietojoukkoparametri (Python)</span><span class="sxs-lookup"><span data-stu-id="87d3c-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="87d3c-134">Eräpäättelyjakso</span><span class="sxs-lookup"><span data-stu-id="87d3c-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="87d3c-135">Koulutusjaksoa voidaan käyttää suunnitteluohjelmassa luomaan tai päivittämään päättelyjakso.</span><span class="sxs-lookup"><span data-stu-id="87d3c-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="87d3c-136">Tällä tuetaan vain eräpäättelyjaksoja.</span><span class="sxs-lookup"><span data-stu-id="87d3c-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="87d3c-137">Jakso voidaan julkaista SDK:n avulla päätepisteeseen.</span><span class="sxs-lookup"><span data-stu-id="87d3c-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="87d3c-138">Tällä hetkellä Customer Insights integroi koneoppimistyötilassa oletusjakson eräjakson päätepisteessä.</span><span class="sxs-lookup"><span data-stu-id="87d3c-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="87d3c-139">Jaksotietojen tuominen Customer Insightsiin</span><span class="sxs-lookup"><span data-stu-id="87d3c-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="87d3c-140">Suunnitteluohjelmassa on [tietojen vientimoduuli](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data), jolla jakson tuloste voidaan viedä Azure-tallennustilaan.</span><span class="sxs-lookup"><span data-stu-id="87d3c-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="87d3c-141">Tällä hetkellä moduulin tietosäilön tyypin on oltava **Azure Blob -säilö**, minkä lisäksi **tietosäilö** ja suhteellinen **polku** on muutettava parametreiksi.</span><span class="sxs-lookup"><span data-stu-id="87d3c-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="87d3c-142">Customer Insights korvaa nämä molemmat parametrit suorituksen aikana tietosäilöllä ja polulla, jota tuote voi käyttää.</span><span class="sxs-lookup"><span data-stu-id="87d3c-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="87d3c-143">![Tietojen vientimoduulin määritys](media/intelligence-designer-importdata.png "Tietojen vientimoduulin määritys")</span><span class="sxs-lookup"><span data-stu-id="87d3c-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="87d3c-144">Kun päättelytulosteen kirjoittamiseen käytetään koodia, tuloste voidaan ladata polkuun työtilan *rekisteröidyssä tietosäilössä*.</span><span class="sxs-lookup"><span data-stu-id="87d3c-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="87d3c-145">Jos polku ja tietosäilö on muutettu parametreiksi jaksossa, Customer insights voi lukea ja tuoda päättelytulosteen.</span><span class="sxs-lookup"><span data-stu-id="87d3c-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="87d3c-146">Tällä hetkellä tuetaan yhtä taulukkomuotoista tulostetta, jonka muoto on csv.</span><span class="sxs-lookup"><span data-stu-id="87d3c-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="87d3c-147">Polun on sisällettävä hakemisto ja tiedostonimi.</span><span class="sxs-lookup"><span data-stu-id="87d3c-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```
