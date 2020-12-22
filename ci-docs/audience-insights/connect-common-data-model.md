---
title: Common Data Model -tietojen yhdistäminen Azure Data Lake -tiliin
description: Common Data Model -tietojen käyttäminen Azure Data Lake Storagen avulla.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643454"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="8deb1-103">Common Data Model -kansioon yhdistäminen Azure Data Lake -tilillä</span><span class="sxs-lookup"><span data-stu-id="8deb1-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="8deb1-104">Tässä artikkelissa on tietoja Common Data Model -kansion tietojen käsittelemisestä Azure Data Lake Storage Gen2 -tilin avulla.</span><span class="sxs-lookup"><span data-stu-id="8deb1-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="8deb1-105">Tärkeitä huomioon otettavia seikkoja</span><span class="sxs-lookup"><span data-stu-id="8deb1-105">Important considerations</span></span>

- <span data-ttu-id="8deb1-106">Azure Data Lake -tallennustilassa olevien tietojen muodon on oltava Common Data Model -standardin mukaisia.</span><span class="sxs-lookup"><span data-stu-id="8deb1-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="8deb1-107">Muita muotoja ei tueta tällä hetkellä.</span><span class="sxs-lookup"><span data-stu-id="8deb1-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="8deb1-108">Tietojen käsittely tukee ainoastaan Azure Data Lake *Gen2* -tallennustilejä.</span><span class="sxs-lookup"><span data-stu-id="8deb1-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="8deb1-109">Azure Data Lake Gen1 -tallennustilejä ei voi käyttää tietojen käsittelyyn.</span><span class="sxs-lookup"><span data-stu-id="8deb1-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="8deb1-110">Azure-palveluobjektin käyttäminen todentaminen edellyttää, että se on määritetty vuokraajassa.</span><span class="sxs-lookup"><span data-stu-id="8deb1-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="8deb1-111">Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="8deb1-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="8deb1-112">Azure Data Lake -tallennustilan, joka halutaan yhdistää ja jonka tietoja halutaan käsitellä, on oltava samalla Azure-alueella kuin Dynamics 365 Customer Insights -ympäristö.</span><span class="sxs-lookup"><span data-stu-id="8deb1-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="8deb1-113">Yhteyksiä Common Data Model -kansioon toisen Azure-alueen Data Lake -tallennustilasta ei tueta.</span><span class="sxs-lookup"><span data-stu-id="8deb1-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="8deb1-114">Ympäristön Azure-alueen voi tarkistaa valitsemalla käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Järjestelmä** > **Tietoja**.</span><span class="sxs-lookup"><span data-stu-id="8deb1-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="8deb1-115">Online-palveluihin tallennetut tiedot voivat olla tallennettu eri sijaintiin kuin missä tietoja käsitellään ja mihin ne tallennetaan Dynamics 365 Customer Insightsissa.</span><span class="sxs-lookup"><span data-stu-id="8deb1-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="8deb1-116"> Tuomalla verkkopalveluun tallennetut tiedot tai muodostamalla niihin yhteyden hyväksyt, että tiedot voidaan siirtää ja tallentaa yhdessä Dynamics 365 Customer Insightsin kanssa.  [Lisätietoja on Microsoftin luottamuskeskuksessa.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="8deb1-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="8deb1-117">Muodosta yhteys Common Data Model -kansioon</span><span class="sxs-lookup"><span data-stu-id="8deb1-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="8deb1-118">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.</span><span class="sxs-lookup"><span data-stu-id="8deb1-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="8deb1-119">Valitse **Lisää tietolähde**.</span><span class="sxs-lookup"><span data-stu-id="8deb1-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="8deb1-120">Valitse **Muodosta yhteys Common Data Model -kansioon**, anna tietolähteelle **Nimi** ja valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="8deb1-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span>

1. <span data-ttu-id="8deb1-121">Voit valita, käytetäänkö todennukseen resurssi- vai tilausperusteista vaihtoehtoa.</span><span class="sxs-lookup"><span data-stu-id="8deb1-121">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="8deb1-122">Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="8deb1-122">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="8deb1-123">Anna **säilön** tiedot ja valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="8deb1-123">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8deb1-124">![Valintaikkuna Azure Data Laken yhteystietojen antamiseen](media/enter-new-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="8deb1-124">![Dialog box to enter connection details for Azure Data Lake](media/enter-new-storage-details.png)</span></span>

1. <span data-ttu-id="8deb1-125">Valitse **Common Data Model -kansion valitseminen** -valintaikkunassa model.json-tiedosto, josta tietoja tuodaan, ja valitse sitten **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="8deb1-125">In the **Select a Common Data Model folder** dialog, select the model.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="8deb1-126">Toiseen ympäristön tietolähteeseen liitetyt model.json-tiedostot eivät näy luettelossa.</span><span class="sxs-lookup"><span data-stu-id="8deb1-126">Any model.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="8deb1-127">Näkyviin tulee luettelo valitussa model.json-tiedoston käytettävissä olevista entiteeteistä.</span><span class="sxs-lookup"><span data-stu-id="8deb1-127">You'll get a list of available entities in the selected model.json file.</span></span> <span data-ttu-id="8deb1-128">Voit tarkistaa sen ja valita käytettävissä olevien entiteettien luettelosta. Valitse sitten **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="8deb1-128">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="8deb1-129">Kaikki valitut entiteetit käsitellään uudesta tietolähteestä.</span><span class="sxs-lookup"><span data-stu-id="8deb1-129">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8deb1-130">![Valintaikkuna, jossa on model.json-tiedostosta saatu entiteettiluettelo](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="8deb1-130">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="8deb1-131">Määritä, missä tietoyksikköihin tietojen profilointi halutaan ottaa käyttöön ja valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="8deb1-131">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="8deb1-132">Tietojen profilointi mahdollistaa analytiikan ja muut ominaisuudet.</span><span class="sxs-lookup"><span data-stu-id="8deb1-132">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="8deb1-133">Voit valita koko entiteetin, jolloin kaikki entiteetin määritteet valitaan, tai valita tietyt valitut määritteet.</span><span class="sxs-lookup"><span data-stu-id="8deb1-133">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="8deb1-134">Tietojen profilointi ei ole oletusarvoisesti otettu käyttöön missään entiteetissä.</span><span class="sxs-lookup"><span data-stu-id="8deb1-134">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8deb1-135">![Valintaikkuna, jossa näkyy tietojen profilointi](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="8deb1-135">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="8deb1-136">Kun olet tallentanut valinnat, näkyviin tulee **Tietolähteet**-sivu.</span><span class="sxs-lookup"><span data-stu-id="8deb1-136">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="8deb1-137">Sinun pitäisi nyt nähdä Common Data Model -kansion yhteys tietolähteenä.</span><span class="sxs-lookup"><span data-stu-id="8deb1-137">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="8deb1-138">Model.json-tiedosto voidaan liittää vain yhteen tietolähteeseen samassa ympäristössä.</span><span class="sxs-lookup"><span data-stu-id="8deb1-138">A model.json file can only associate with one data source in the same environment.</span></span> <span data-ttu-id="8deb1-139">Samaa model.json-tiedostoa voi kuitenkin käyttää tietolähteissä useissa ympäristöissä.</span><span class="sxs-lookup"><span data-stu-id="8deb1-139">However, the same model.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="8deb1-140">Common Data Model -kansion tietolähteen muokkaaminen</span><span class="sxs-lookup"><span data-stu-id="8deb1-140">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="8deb1-141">Voit päivittää Common Data Model -kansion sisältävän tallennustilin käyttöoikeusavaimen.</span><span class="sxs-lookup"><span data-stu-id="8deb1-141">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="8deb1-142">Voit myös vaihtaa model.json-tiedoston.</span><span class="sxs-lookup"><span data-stu-id="8deb1-142">You may also change the model.json file.</span></span> <span data-ttu-id="8deb1-143">Jos haluat muodostaa yhteyden toiseen säilöön tallennustilatililtä tai muuttaa tilin nimeä, sinun on [luotava uusi tietolähdeyhteys](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="8deb1-143">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="8deb1-144">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.</span><span class="sxs-lookup"><span data-stu-id="8deb1-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="8deb1-145">Valitse päivitettävän tietolähteen vieressä kolme pistettä.</span><span class="sxs-lookup"><span data-stu-id="8deb1-145">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="8deb1-146">Valitse luettelossa **Muokkaa**-vaihtoehto.</span><span class="sxs-lookup"><span data-stu-id="8deb1-146">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="8deb1-147">Valinnaisesti voit päivittää **käyttöoikeusavaimen** ja valita **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="8deb1-147">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Valintaikkuna aiemmin luodun tietolähteen käyttöoikeusavaimen muokkaamiseen ja päivittämiseen](media/edit-access-key.png)

5. <span data-ttu-id="8deb1-149">Voit myös tehdä päivityksen käyttöoikeusavaimen yhteydessä resurssi- tai tilausperusteiseen yhteyteen.</span><span class="sxs-lookup"><span data-stu-id="8deb1-149">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="8deb1-150">Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="8deb1-150">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="8deb1-151">**Säilö**-tietoja ei voi muuttaa yhteyttä päivitettäessä.</span><span class="sxs-lookup"><span data-stu-id="8deb1-151">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8deb1-152">![Valintaikkuna Azure Data Laken yhteystietojen antamiseen](media/enter-existing-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="8deb1-152">![Dialog box to enter connection details for Azure Data Lake](media/enter-existing-storage-details.png)</span></span>

6. <span data-ttu-id="8deb1-153">Valinnaisesti voit valita säilössä toisen model.json-tiedoston, jossa on erilainen entiteettijoukko.</span><span class="sxs-lookup"><span data-stu-id="8deb1-153">Optionally, choose a different model.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="8deb1-154">Voit myös valita lisää käsiteltäviä entiteettejä.</span><span class="sxs-lookup"><span data-stu-id="8deb1-154">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="8deb1-155">Voit myös poistaa kaikki jo valitut entiteetit, jos riippuvuuksia ei ole.</span><span class="sxs-lookup"><span data-stu-id="8deb1-155">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="8deb1-156">Jos nykyisessä model.json-tiedostossa ja entiteettijoukossa on riippuvuuksia, näkyviin tulee virhesanoma eikä toista model.json-tiedostoa voi valita.</span><span class="sxs-lookup"><span data-stu-id="8deb1-156">If there are dependencies on the existing model.json file and the set of entities, you'll see an error message and can't select a different model.json file.</span></span> <span data-ttu-id="8deb1-157">Poista kyseiset riippuvuudet ennen model.json-tiedoston vaihtamista tai luo uusi tietolähde, joka sisältää haluamasi model.json-tiedoston, jolloin riippuvuuksia ei tarvitse poistaa.</span><span class="sxs-lookup"><span data-stu-id="8deb1-157">Remove those dependencies before changing the model.json file or create a new data source with the model.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="8deb1-158">Voit myös valita lisää määritteitä tai entiteettejä, jossa tietojen profilointi otetaan käyttöön tai poistaa jo valitut käytöstä.</span><span class="sxs-lookup"><span data-stu-id="8deb1-158">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   
