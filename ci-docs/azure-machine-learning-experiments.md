---
title: Azuren automaattianalyysipalveluihin perustuvien mallien käyttäminen
description: Azuren automaattianalyysipalveluihin perustuvien mallien käyttäminen Dynamics 365 Customer Insightsissa.
ms.date: 09/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d9c9324ea4840b585b9af1a58d505ccaea6f18e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609821"
---
# <a name="use-azure-machine-learning-based-models"></a>Azuren automaattianalyysipalveluihin perustuvien mallien käyttäminen

Dynamics 365 Customer Insightsin yhtenäistetyt tiedot ovat sellaisten koneoppimismallien muodostamisen lähde, joilla voidaan luoda lisää merkityksellisiä liiketoimintatietoja. Azuren automaattianalyysipalveluihin integroituvalla Customer Insightsilla voi käyttää omia mukautettuja malleja.

## <a name="prerequisites"></a>Edellytykset

- Customer Insightsin käyttöoikeus
- Aktiivinen Azure Enterprise -tilaus
- [Yhdistetyt asiakasprofiilit](data-unification.md)
- [Entiteettivienti Azure Blob -säilöön](export-azure-blob-storage.md) määritetty

## <a name="set-up-azure-machine-learning-workspace"></a>Azuren automaattianalyysipalvelujen työtilan määrittäminen

1. [Azuren automaattianalyysipalvelujen työtilan luonti](/azure/machine-learning/concept-workspace#-create-a-workspace) sisältää lisätietoja työtilan luontivaihtoehdoista. Paras tulos saadaan luomalla työtila sillä Azure-alueella, joka on maantieteellisesti lähinnä Customer Insights -ympäristöä.

1. Työtilaa käytetään [Azuren koneoppimisstudion](https://ml.azure.com/) kautta. Työtilaa voi [käyttää eri tavoin](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction).

## <a name="work-with-azure-machine-learning-designer"></a>Azuren automaattianalyysipalvelujen suunnitteluohjelman käyttäminen

Azuren koneoppimisen suunnittelija tarjoaa visuaalisen pohjan, johon voit vetää ja pudottaa tietojoukkoja ja moduuleja. Suunnitteluohjelmassa luotu eräjakso voidaan integroida Customer Insightsiin, jos määritykset sen sallivat. 

## <a name="working-with-azure-machine-learning-sdk"></a>Azuren automaattianalyysipalvelujen SDK:n käyttäminen

Data-analyytikot ja tekoälykehittäjät luovat koneoppisen työnkulkuja käyttämällä [Azuren automaattianalyysipalvelujen SDK:ta](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py). Tällä hetkellä SDK:lla koulutettuja malleja ei voi integroida suoraan Customer Insightsiin. Customer Insights -integrointiin tarvitaan mallia käyttävä eräpäättelyjakso.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Customer Insights -integroinnin eräjaksovaatimukset

### <a name="dataset-configuration"></a>Tietojoukon määritys

Tietojoukkoja luodaan käyttämään Customer Insightsin entiteettitietoja eräpäättelyjaksossa. Nämä tietojoukot rekisteröidään työtilassa. Tällä tuetaan vain [taukokkomuotoisia tietojoukkoja](/azure/machine-learning/how-to-create-register-datasets#tabulardataset), joiden muoto on.csv. Entiteettitietoja vastaavat tietojoukot muutetaan jaksoparametreiksi.

- Suunnitteluohjelman tietojoukkoparametrit

  Avaa suunnitteluohjelmassa **Valitse tietojoukon sarakkeet** ja valitse **Määritä jaksoparametrina**, jossa annetaan parametrin nimi.

  :::image type="content" source="media/intelligence-designer-dataset-parameters.png" alt-text="Suunnitteluohjelman tietojoukon muuttaminen parametreiksi.":::

- SDK:n tietojoukkoparametri (Python)

   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Eräpäättelyjakso
  
- Koulutusjaksoa käytetään suunnitteluohjelmassa luomaan tai päivittämään päättelyjakso. Tällä tuetaan vain eräpäättelyjaksoja.

- Jakso voidaan julkaista SDK:n avulla päätepisteeseen. Tällä hetkellä Customer Insights integroi koneoppimistyötilassa oletusjakson eräjakson päätepisteessä.

   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Jaksotietojen tuominen Customer Insightsiin

- Suunnitteluohjelmassa on [tietojen vientimoduuli](/azure/machine-learning/algorithm-module-reference/export-data), jolla jakson tuloste voidaan viedä Azure-tallennustilaan. Tällä hetkellä moduulin tietosäilön tyypin on oltava **Azure Blob -säilö**, minkä lisäksi **tietosäilö** ja suhteellinen **polku** on muutettava parametreiksi. Customer Insights korvaa nämä molemmat parametrit suorituksen aikana tietosäilöllä ja polulla, jota tuote voi käyttää.

  :::image type="content" source="media/intelligence-designer-importdata.png" alt-text="Tietojen vientimoduulin määritys.":::

- Kun päättelytuloksen kirjoittamiseen käytetään koodia, tulos voidaan ladata polkuun työtilan *rekisteröidyssä tietosäilössä*. Jos polku ja tietosäilö on muutettu parametreiksi jaksossa, Customer insights voi lukea ja tuoda päättelytulosteen. Tällä hetkellä tuetaan yhtä taulukkomuotoista tulostetta, jonka muoto on csv. Polun on sisällettävä hakemisto ja tiedostonimi.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]