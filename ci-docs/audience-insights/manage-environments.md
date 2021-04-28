---
title: Luo ja hallitse ympäristöjä
description: Tietoja palveluun rekisteröitymisestä ja ympäristöjen hallinnasta.
ms.date: 03/26/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8cc1401251ed7c45c598bd4a8fb33a9709fabbc8
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887982"
---
# <a name="manage-environments"></a><span data-ttu-id="cdd2c-103">Ympäristöjen hallinta</span><span class="sxs-lookup"><span data-stu-id="cdd2c-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="cdd2c-104">Tässä artikkelissa käsitellään uuden organisaation luontia ja ympäristön valmistelua.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="cdd2c-105">Rekisteröityminen ja organisaation luominen</span><span class="sxs-lookup"><span data-stu-id="cdd2c-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="cdd2c-106">Siirry [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) -sivustoon.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="cdd2c-107">Valitse **Aloita**.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="cdd2c-108">Valitse ensin sopiva kirjautumisskenaario ja sitten vastaava linkki.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="cdd2c-109">Aloita organisaation luonti hyväksymällä ehdot ja valitsemalla **Jatka**.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="cdd2c-110">Kun ympäristö on luotu, sinut ohjataan [Customer Insightsiin](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="cdd2c-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="cdd2c-111">Tutustu sovellukseen esittely-ympäristön avulla tai luo uusi ympäristö seuraavan osan vaiheiden avulla.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="cdd2c-112">Kun ympäristön asetukset on määritetty, valitse **Luo**.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="cdd2c-113">Kirjautuminen tapahtuu, kun ympäristö on luotu.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="cdd2c-114">Ympäristön luominen aiemmin luodussa organisaatiossa</span><span class="sxs-lookup"><span data-stu-id="cdd2c-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="cdd2c-115">Uusi ympäristö voidaan luoda kahdella tavalla.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="cdd2c-116">Voit joko määrittää kokonaan uuden määrityksen tai voit kopioida joitakin määritysasetuksia aiemmin luodusta ympäristöstä.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

> [!NOTE]
> <span data-ttu-id="cdd2c-117">Organisaatiot voivat luoda *kaksi* ympäristöä jokaista Customer Insights -käyttöoikeutta varten.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-117">Organizations can create *two* environments for every Customer Insights license.</span></span> <span data-ttu-id="cdd2c-118">Jos organisaatiosi ostaa useamman kuin yhden käyttöoikeuden, [ota yhteyttä tukiryhmäämme](https://go.microsoft.com/fwlink/?linkid=2079641), jotta käytettävissä olevien ympäristöjen määrää voidaan lisätä.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-118">If your organization purchases more than once license, please [contact our support team](https://go.microsoft.com/fwlink/?linkid=2079641) to increase the number of available environments.</span></span> <span data-ttu-id="cdd2c-119">Lisätietoja kapasiteetista ja lisäkapasiteetista on [Dynamics 365:n käyttöoikeusoppaassa](https://go.microsoft.com/fwlink/?LinkId=866544).</span><span class="sxs-lookup"><span data-stu-id="cdd2c-119">For more information about capacity and add-on capacity, download [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544).</span></span>

<span data-ttu-id="cdd2c-120">Ympäristön luominen:</span><span class="sxs-lookup"><span data-stu-id="cdd2c-120">To create an environment:</span></span>

1. <span data-ttu-id="cdd2c-121">Valitse sovelluksen otsikossa **Ympäristö**-valitsin.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-121">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="cdd2c-122">Valitse **Uusi**.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-122">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cdd2c-123">![Ympäristön asetukset](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="cdd2c-123">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="cdd2c-124">Valitse **Luo uusi ympäristö** -valintaikkunassa **Uusi ympäristö**.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-124">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="cdd2c-125">Jos haluat [kopioida tietoja nykyisestä ympäristöstä](#considerations-for-copy-configuration-preview), valitse **Kopioi aiemmasta ympäristöstä**.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-125">If you want to [copy data from the current environment](#considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="cdd2c-126">Näkyviin tulee luettelo kaikista organisaation käytettävissä olevista ympäristöistä, joista voit kopioida tietoja.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-126">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="cdd2c-127">Anna seuraavat tiedot:</span><span class="sxs-lookup"><span data-stu-id="cdd2c-127">Provide the following details:</span></span>
   - <span data-ttu-id="cdd2c-128">**Nimi**: Ympäristön nimi.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-128">**Name**: The name for this environment.</span></span> <span data-ttu-id="cdd2c-129">Tämä kenttä on jo täytetty, jos kopioit tietoja aiemmin luodusta ympäristöstä, mutta voit muuttaa sitä.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-129">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="cdd2c-130">**Alue**: Alue, jossa palvelu otetaan käyttöön ja jossa sitä isännöidään.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-130">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="cdd2c-131">**Tyyppi**: Määritä, haluatko luoda tuotanto- vai eristysympäristön.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-131">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

1. <span data-ttu-id="cdd2c-132">Valinnaisesti voit valita **Lisäasetukset**:</span><span class="sxs-lookup"><span data-stu-id="cdd2c-132">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="cdd2c-133">**Tallenna kaikki tiedot kohteeseen**: Määrittää, minne haluat tallentaa Customer Insightsin tulostiedot.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-133">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="cdd2c-134">Vaihtoehtoja on kaksi: **Customer Insights -tallennustila** (Customer Insights -ryhmän hallitsema Azure Data Lake) ja **Azure Data Lake Storage Gen2** (oma Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="cdd2c-134">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="cdd2c-135">Oletusarvoisesi Customer Insights -tallennustila -vaihtoehto on valittu.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-135">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cdd2c-136">Tallentamalla tiedot Azure Data Lake Storageen hyväksyt, että tiedot siirretään ja tallennetaan kyseisen Azure-tallennustilin asianmukaiseen maantieteelliseen sijaintiin. Tämä sijainti voi olla eri kuin sijainti, johon tiedot on tallennettu Dynamics 365 Customer Insightsissa.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-136">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="cdd2c-137">Lisätietoja on Microsoftin luottamuskeskuksessa.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-137">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="cdd2c-138">Tällä hetkellä käsitellyt entiteetit tallennetaan aina Customer Insightsin hallittuun Data Lake -tallennustilaan.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-138">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="cdd2c-139">Vain sellaisia Azure Data Lake Gen2 -tallennustilejä tuetaan, jotka ovat ympäristöä luotaessa valitulla Azure-alueella.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-139">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="cdd2c-140">Vain sellaisia tallennustilatilejä tuetaan, joissa on otettu käyttöön Azure Data Lake Gen2:n hierarkkinen nimitila.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-140">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="cdd2c-141">Voit valita Azure Data Lake Storage Gen2 -vaihtoehdossa, käytetäänkö todennukseen resurssi- vai tilausperusteista vaihtoehtoa.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-141">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="cdd2c-142">Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="cdd2c-142">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="cdd2c-143">**Säilön** nimeä ei voi muuttaa, ja se on customerinsights.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-143">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="cdd2c-144">Jos haluat käyttää [ennusteita](predictions.md), määritä tietojen jakaminen sovellusten ja ratkaisujen kanssa Microsoft Dataversen perusteella tai ota käyttöön tietojen käsittely paikallisista tietolähteistä, anna Microsoft Dataverse -ympäristön URL-osoite kohdassa **Tietojen jakamisen määrittäminen Microsoft Dataversen kanssa ja lisäominaisuuksien ottaminen käyttöön**.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-144">If you want to use [predictions](predictions.md), configure data sharing with applications and solutions based on Microsoft Dataverse, or enable data ingestion from on-premises data sources, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="cdd2c-145">Valitse **Ota käyttöön tietojen jakaminen**, jos haluat jakaa Customer Insightsin tulostiedot Microsoft Dataversen hallitun Data Laken kanssa.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-145">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="cdd2c-146">Tietojen jakamista Microsoft Dataversen hallitun Data Laken kanssa ei tueta tällä hetkellä, jos kaikki tiedot tallennetaan omaan Azure Data Lake Storage -ratkaisuun.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-146">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="cdd2c-147">[Entiteetin puuttuvien arvojen ennustetta](predictions.md) ei tueta tällä hetkellä, jos tietojen jakaminen Microsoft Dataversen hallitun Data Laken kanssa otetaan käyttöön.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-147">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="cdd2c-148">![Määritysvalinnat tietojen jakamista varten Microsoft Dataversen kanssa](media/datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="cdd2c-148">![Configuration options to enable data sharing with Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="cdd2c-149">Kun suoritat prosesseja, kuten tietojen käsittelyä tai segmenttien luontia, vastaavat kansiot luodaan edellä määritettyyn tallennustiliin.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-149">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="cdd2c-150">Datatiedostoja ja model.json-tiedostoja luodaan ja lisätään asianmukaisiin alikansioihin suorittamasi prosessin perusteella.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-150">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="cdd2c-151">Jos luot useita Customer Insights -ympäristöjä ja valitset kyseisten ympäristöjen tuloste-entiteettien tallentamisen tallennustilille, kullekin ympäristölle luodaan erilliset kansiot siten, että säilössä on ci_<environmentid>.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-151">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="considerations-for-copy-configuration-preview"></a><span data-ttu-id="cdd2c-152">Määrityksien kopiointiin liittyviä näkökohtia (esiversio)</span><span class="sxs-lookup"><span data-stu-id="cdd2c-152">Considerations for copy configuration (preview)</span></span>

<span data-ttu-id="cdd2c-153">Seuraavat määritysasetukset kopioidaan:</span><span class="sxs-lookup"><span data-stu-id="cdd2c-153">The following configuration settings are copied:</span></span>

- <span data-ttu-id="cdd2c-154">Toiminnon määritykset</span><span class="sxs-lookup"><span data-stu-id="cdd2c-154">Feature configurations</span></span>
- <span data-ttu-id="cdd2c-155">Käsitellyt/tuodut tietolähteet</span><span class="sxs-lookup"><span data-stu-id="cdd2c-155">Ingested/imported data sources</span></span>
- <span data-ttu-id="cdd2c-156">Tietojen yhtenäistämisen (yhdistäminen, vastaavuus) määritys</span><span class="sxs-lookup"><span data-stu-id="cdd2c-156">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="cdd2c-157">Segmentit</span><span class="sxs-lookup"><span data-stu-id="cdd2c-157">Segments</span></span>
- <span data-ttu-id="cdd2c-158">Mittarit</span><span class="sxs-lookup"><span data-stu-id="cdd2c-158">Measures</span></span>
- <span data-ttu-id="cdd2c-159">Suhteet</span><span class="sxs-lookup"><span data-stu-id="cdd2c-159">Relationships</span></span>
- <span data-ttu-id="cdd2c-160">Aktiviteetit</span><span class="sxs-lookup"><span data-stu-id="cdd2c-160">Activities</span></span>
- <span data-ttu-id="cdd2c-161">Haku- ja suodatusindeksi</span><span class="sxs-lookup"><span data-stu-id="cdd2c-161">Search & filter Index</span></span>
- <span data-ttu-id="cdd2c-162">Vientikohteet</span><span class="sxs-lookup"><span data-stu-id="cdd2c-162">Export destinations</span></span>
- <span data-ttu-id="cdd2c-163">Ajoitettu päivitys</span><span class="sxs-lookup"><span data-stu-id="cdd2c-163">Scheduled refresh</span></span>
- <span data-ttu-id="cdd2c-164">Rikastukset</span><span class="sxs-lookup"><span data-stu-id="cdd2c-164">Enrichments</span></span>
- <span data-ttu-id="cdd2c-165">Mallien hallinta</span><span class="sxs-lookup"><span data-stu-id="cdd2c-165">Model management</span></span>
- <span data-ttu-id="cdd2c-166">Roolimääritykset</span><span class="sxs-lookup"><span data-stu-id="cdd2c-166">Role assignments</span></span>

<span data-ttu-id="cdd2c-167">Seuraavia asetuksia *ei* kopioida:</span><span class="sxs-lookup"><span data-stu-id="cdd2c-167">The following settings are *not* copied:</span></span>

- <span data-ttu-id="cdd2c-168">Asiakasprofiilit.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-168">Customer profiles.</span></span>
- <span data-ttu-id="cdd2c-169">Tietolähteen tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-169">Data source credentials.</span></span> <span data-ttu-id="cdd2c-170">Sinun on annettava kunkin tietolähteen tunnistetiedot ja päivitettävä tietolähteet manuaalisesti.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-170">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="cdd2c-171">Tietolähteet Common Data Model -kansiosta ja Common Data Service -hallitusta tallennustilasta.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-171">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="cdd2c-172">Nämä tietolähteet on luotava manuaalisesti samalla nimellä kuin lähdeympäristössä.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-172">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="cdd2c-173">Kun kopioit ympäristön, näkyviin tulee vahvistussanoma siitä, että uusi ympäristö on luotu.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-173">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="cdd2c-174">Valitse **Siirry tietolähteisiin**, kun haluat nähdä tietolähteiden luettelon.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-174">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="cdd2c-175">Kaikkien tietolähteiden tilana näkyy **Vaatii tunnistetietoja**.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-175">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="cdd2c-176">Muokkaa tietolähteitä ja päivitä ne syöttämällä tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-176">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cdd2c-177">![Kopioidut tietolähteet](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="cdd2c-177">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="cdd2c-178">Kun olet päivittänyt tietolähteet, siirry kohtaan **Tiedot** > **Yhtenäistäminen**.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-178">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="cdd2c-179">Siellä ovat lähdeympäristön asetukset.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-179">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="cdd2c-180">Voit muokata niitä tarpeen mukaan tai valita **Suorita**, jolloin tietojen yhtenäistämisprosessi alkaa ja yhtenäistetty asiakasentiteetti luodaan.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-180">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="cdd2c-181">Kun tietojen yhtenäistäminen on valmis, päivitä myös kohdat **Mittarit** ja **Segmentit** siirtymällä niihin.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-181">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="cdd2c-182">Aiemmin luodun ympäristön muokkaaminen</span><span class="sxs-lookup"><span data-stu-id="cdd2c-182">Edit an existing environment</span></span>

<span data-ttu-id="cdd2c-183">Voit muokata joitakin aiemmin luotujen ympäristöjen tietoja.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-183">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="cdd2c-184">Valitse sovelluksen otsikossa **Ympäristö**-valitsin.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-184">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="cdd2c-185">Valitse **Muokkaa**-kuvake.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-185">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="cdd2c-186">**Muokkaa ympäristöä** -ruudussa voit päivittää ympäristön **näyttönimen**, mutta et voi muuttaa **aluetta** tai **tyyppiä**.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-186">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="cdd2c-187">Jos ympäristö on määritetty tallentamaan tiedot Azure Data Lake Storage Gen2:ään, voit päivittää **tiliavaimen**.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-187">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="cdd2c-188">Et voi kuitenkaan muuttaa **tilin nimeä** tai **säilön** nimeä.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-188">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="cdd2c-189">Voit myös tehdä päivityksen käyttöoikeusavaimeen perustuvassa yhteydessä resurssi- tai tilausperusteiseen yhteyteen.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-189">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="cdd2c-190">Päivitykseen jälkeen ei ole mahdollista palata käyttöoikeusavaimeen.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-190">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="cdd2c-191">Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="cdd2c-191">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="cdd2c-192">**Säilö**-tietoja ei voi muuttaa yhteyttä päivitettäessä.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-192">You can't change **Container** information when updating the connection.</span></span>

6. <span data-ttu-id="cdd2c-193">Vaihtoehtoisesti voit määrittää Microsoft Dataverse -ympäristön URL-osoitteen kohdassa **Tietojen jakamisen määrittäminen Microsoft Dataversen kanssa ja lisäominaisuuksien ottaminen käyttöön**.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-193">Optionally, you can provide a Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="cdd2c-194">Nämä ominaisuudet sisältävät tietojen jakamisen sovelluksiin ja ratkaisuihin Microsoft Dataverseen perusteella,tietojen käsittelyn paikallisistas tietolähteistä, tai käytä [ennusteita](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="cdd2c-194">These capabilities inlcude data sharing with applications and solutions based on Microsoft Dataverse, data ingestion from on-premises data sources, or the use [predictions](predictions.md).</span></span> <span data-ttu-id="cdd2c-195">Valitse **Ota käyttöön tietojen jakaminen**, jos haluat jakaa Customer Insightsin tulostiedot Microsoft Dataversen hallitun Data Laken kanssa.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-195">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data lake.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="cdd2c-196">Tietojen jakamista Microsoft Dataversen hallitun Data Laken kanssa ei tueta tällä hetkellä, jos kaikki tiedot tallennetaan omaan Azure Data Lake Storage -ratkaisuun.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-196">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
   > - <span data-ttu-id="cdd2c-197">[Entiteettien puuttuvien arvojen ennustetta](predictions.md) ei tueta tällä hetkellä, kun otat tietojen jakamisen käyttöön Microsoft Dataversen hallitun Data Laken kanssa.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-197">[Prediction of missing values in an entity](predictions.md) is currently not supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

   <span data-ttu-id="cdd2c-198">Kun otat käyttöön tietojen jakamisen Microsoft Dataversen kansa, käynnistetään tietolähteiden ja muiden prosessien täydellinen päivitys.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-198">Once you enable data sharing with Microsoft Dataverse, a full refresh of your data sources and other processes will be triggered.</span></span> <span data-ttu-id="cdd2c-199">Jos prosesseja tällä hetkellä suoritetaan ja asetetaan jonoon, et näe mahdollisuutta ottaa tietojen jakamista käyttöön Microsoft Dataversen kanssa.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-199">If processes are currently running and queued, you will not see the option to enable data sharing with Microsoft Dataverse.</span></span> <span data-ttu-id="cdd2c-200">Voit odottaa, että prosessit valmistuvat tai peruutat ne, jotta tietojen jakaminen voidaan ottaa käyttöön.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-200">You can wait for those processes to complete or cancel them to enable data sharing.</span></span> 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Määritysvalinnat tietojen jakamista varten Microsoft Dataversen kanssa.":::
   
   <span data-ttu-id="cdd2c-202">Kun suoritat prosesseja, kuten tietojen käsittelyä tai segmenttien luontia, vastaavat kansiot luodaan edellä määritettyyn tallennustiliin.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-202">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="cdd2c-203">Datatiedostot ja model.json-tiedostot luodaan ja lisätään vastaaviin alikansioihin suoritettavan prosessin mukaan.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-203">Data files and model.json files will be created and added to the respective subfolders, depending on the process you run.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="cdd2c-204">Aiemmin luodun ympäristön palauttaminen</span><span class="sxs-lookup"><span data-stu-id="cdd2c-204">Reset an existing environment</span></span>

<span data-ttu-id="cdd2c-205">Järjestelmänvalvoja voi palauttaa ympäristön tyhjään tilaan, jos haluat poistaa kaikki määritykset ja käsitellyt tiedot.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-205">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="cdd2c-206">Valitse sovelluksen otsikossa **Ympäristö**-valitsin.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-206">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="cdd2c-207">Valitse ympäristö, jonka haluat palauttaa, ja valitse sitten kolme pistettä eli **...**.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-207">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="cdd2c-208">Valitse **Palauta**-vaihtoehto.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-208">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="cdd2c-209">Vahvista poisto antamalla ympäristön nimi ja valitsemalla **Palauta**.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-209">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="cdd2c-210">Aiemmin luodun ympäristön poistaminen (käytettävissä vain järjestelmänvalvojille)</span><span class="sxs-lookup"><span data-stu-id="cdd2c-210">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="cdd2c-211">Järjestelmänvalvoja voi poistaa myös hallitsemasi ympäristön.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-211">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="cdd2c-212">Valitse sovelluksen otsikossa **Ympäristö**-valitsin.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-212">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="cdd2c-213">Valitse ympäristö, jonka haluat palauttaa, ja valitse sitten kolme pistettä eli **...**.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-213">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="cdd2c-214">Valitse **Poista**-vaihtoehto.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-214">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="cdd2c-215">Vahvista poisto antamalla ympäristön nimi ja valitsemalla **Poista**.</span><span class="sxs-lookup"><span data-stu-id="cdd2c-215">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
