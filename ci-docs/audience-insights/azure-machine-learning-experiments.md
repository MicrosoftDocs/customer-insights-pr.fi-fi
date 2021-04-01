---
title: Azuren automaattianalyysipalvelujen kokeileminen
description: Azuren automaattianalyysipalveluihin perustuvien mallien käyttäminen Dynamics 365 Customer Insightsissa.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: edd2cf488b52cef87b09b90336e48fdc7f470a68
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597415"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="c6c6a-103">Azuren automaattianalyysipalveluihin perustuvien mallien käyttäminen</span><span class="sxs-lookup"><span data-stu-id="c6c6a-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="c6c6a-104">Dynamics 365 Customer Insightsin yhtenäistetyt tiedot ovat sellaisten koneoppimismallien muodostamisen lähde, joilla voidaan luoda lisää merkityksellisiä liiketoimintatietoja.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="c6c6a-105">Integroituneet Customer Insights sekä koneoppimisstudio (perinteinen) ja Azuren automaattianalyysipalvelut käyttävät käyttäjän mukautettuja malleja.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="c6c6a-106">Kohdassa [Koneoppimisstudion (perinteinen) kokeileminen](machine-learning-studio-experiments.md) on esimerkkejä kokeiluista, jotka perustuvat koneoppimisstudioon (perinteinen).</span><span class="sxs-lookup"><span data-stu-id="c6c6a-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c6c6a-107">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="c6c6a-107">Prerequisites</span></span>

- <span data-ttu-id="c6c6a-108">Customer Insightsin käyttöoikeus</span><span class="sxs-lookup"><span data-stu-id="c6c6a-108">Access to Customer Insights</span></span>
- <span data-ttu-id="c6c6a-109">Aktiivinen Azure Enterprise -tilaus</span><span class="sxs-lookup"><span data-stu-id="c6c6a-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="c6c6a-110">Yhdistetyt asiakasprofiilit</span><span class="sxs-lookup"><span data-stu-id="c6c6a-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="c6c6a-111">[Entiteettivienti Azure Blob -säilöön](export-azure-blob-storage.md) määritetty</span><span class="sxs-lookup"><span data-stu-id="c6c6a-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="c6c6a-112">Azuren automaattianalyysipalvelujen työtilan määrittäminen</span><span class="sxs-lookup"><span data-stu-id="c6c6a-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="c6c6a-113">[Azuren automaattianalyysipalvelujen työtilan luonti](/azure/machine-learning/concept-workspace#-create-a-workspace) sisältää lisätietoja työtilan luontivaihtoehdoista.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-113">See [create a Azure Machine Learning workspace](/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="c6c6a-114">Paras tulos saadaan luomalla työtila sillä Azure-alueella, joka on maantieteellisesti lähinnä Customer Insights -ympäristöä.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="c6c6a-115">Työtilaa käytetään [Azuren koneoppimisstudion](https://ml.azure.com/) kautta.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="c6c6a-116">Työtilaa voi [käyttää eri tavoin](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction).</span><span class="sxs-lookup"><span data-stu-id="c6c6a-116">There are several [ways to interact](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="c6c6a-117">Azuren automaattianalyysipalvelujen suunnitteluohjelman käyttäminen</span><span class="sxs-lookup"><span data-stu-id="c6c6a-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="c6c6a-118">Azuren automaattianalyysipalvelujen suunnitteluohjelma on visuaalinen kaavio, jossa tietojoukkoja ja moduuleja voi vetää ja pudottaa samalla tavoin kuin koneoppimisstudiossa (perinteinen).</span><span class="sxs-lookup"><span data-stu-id="c6c6a-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="c6c6a-119">Suunnitteluohjelmassa luotu eräjakso voidaan integroida Customer Insightsiin, jos määritykset sen sallivat.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="c6c6a-120">Azuren automaattianalyysipalvelujen SDK:n käyttäminen</span><span class="sxs-lookup"><span data-stu-id="c6c6a-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="c6c6a-121">Data-analyytikot ja tekoälykehittäjät luovat koneoppisen työnkulkuja käyttämällä [Azuren automaattianalyysipalvelujen SDK:ta](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py).</span><span class="sxs-lookup"><span data-stu-id="c6c6a-121">Data scientists and AI developers use the [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) to build machine learning workflows.</span></span> <span data-ttu-id="c6c6a-122">Tällä hetkellä SDK:lla koulutettuja malleja ei voi integroida suoraan Customer Insightsiin.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="c6c6a-123">Customer Insights -integrointiin tarvitaan mallia käyttävä eräpäättelyjakso.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="c6c6a-124">Customer Insights -integroinnin eräjaksovaatimukset</span><span class="sxs-lookup"><span data-stu-id="c6c6a-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="c6c6a-125">Tietojoukon määritys</span><span class="sxs-lookup"><span data-stu-id="c6c6a-125">Dataset Configuration</span></span>

<span data-ttu-id="c6c6a-126">Luotavien tietojoukkojen on käytettävä Customer Insightsin entiteettitietoja eräpäättelyjaksoon.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="c6c6a-127">Nämä tietojoukot on rekisteröitävä työtilassa.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="c6c6a-128">Tällä tuetaan vain [taukokkomuotoisia tietojoukkoja](/azure/machine-learning/how-to-create-register-datasets#tabulardataset), joiden muoto on.csv.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-128">Currently, we only support [tabular datasets](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="c6c6a-129">Entiteettitietoja vastaavat tietojoukot on muutettava jaksoparametreiksi.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="c6c6a-130">Suunnitteluohjelman tietojoukkoparametrit</span><span class="sxs-lookup"><span data-stu-id="c6c6a-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="c6c6a-131">Avaa suunnitteluohjelmassa **Valitse tietojoukon sarakkeet** ja valitse **Määritä jaksoparametrina**, jossa annetaan parametrin nimi.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="c6c6a-132">![Suunnitteluohjelman tietojoukon muuttaminen parametreiksi](media/intelligence-designer-dataset-parameters.png "Tietojoukon muuttaminen parametreiksi suunnitteluohjelmassa")</span><span class="sxs-lookup"><span data-stu-id="c6c6a-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="c6c6a-133">SDK:n tietojoukkoparametri (Python)</span><span class="sxs-lookup"><span data-stu-id="c6c6a-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="c6c6a-134">Eräpäättelyjakso</span><span class="sxs-lookup"><span data-stu-id="c6c6a-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="c6c6a-135">Koulutusjaksoa voidaan käyttää suunnitteluohjelmassa luomaan tai päivittämään päättelyjakso.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="c6c6a-136">Tällä tuetaan vain eräpäättelyjaksoja.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="c6c6a-137">Jakso voidaan julkaista SDK:n avulla päätepisteeseen.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="c6c6a-138">Tällä hetkellä Customer Insights integroi koneoppimistyötilassa oletusjakson eräjakson päätepisteessä.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="c6c6a-139">Jaksotietojen tuominen Customer Insightsiin</span><span class="sxs-lookup"><span data-stu-id="c6c6a-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="c6c6a-140">Suunnitteluohjelmassa on [tietojen vientimoduuli](/azure/machine-learning/algorithm-module-reference/export-data), jolla jakson tuloste voidaan viedä Azure-tallennustilaan.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-140">The designer provides the [Export Data module](/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="c6c6a-141">Tällä hetkellä moduulin tietosäilön tyypin on oltava **Azure Blob -säilö**, minkä lisäksi **tietosäilö** ja suhteellinen **polku** on muutettava parametreiksi.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="c6c6a-142">Customer Insights korvaa nämä molemmat parametrit suorituksen aikana tietosäilöllä ja polulla, jota tuote voi käyttää.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c6c6a-143">![Tietojen vientimoduulin määritys](media/intelligence-designer-importdata.png "Tietojen vientimoduulin määritys")</span><span class="sxs-lookup"><span data-stu-id="c6c6a-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="c6c6a-144">Kun päättelytulosteen kirjoittamiseen käytetään koodia, tuloste voidaan ladata polkuun työtilan *rekisteröidyssä tietosäilössä*.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="c6c6a-145">Jos polku ja tietosäilö on muutettu parametreiksi jaksossa, Customer insights voi lukea ja tuoda päättelytulosteen.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="c6c6a-146">Tällä hetkellä tuetaan yhtä taulukkomuotoista tulostetta, jonka muoto on csv.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="c6c6a-147">Polun on sisällettävä hakemisto ja tiedostonimi.</span><span class="sxs-lookup"><span data-stu-id="c6c6a-147">The path must include the directory and filename.</span></span>

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]