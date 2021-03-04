---
title: Luo ja hallitse ympäristöjä
description: Tietoja palveluun rekisteröitymisestä ja ympäristöjen hallinnasta.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270108"
---
# <a name="manage-environments"></a><span data-ttu-id="0ce80-103">Ympäristöjen hallinta</span><span class="sxs-lookup"><span data-stu-id="0ce80-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0ce80-104">Tässä artikkelissa käsitellään uuden organisaation luontia ja ympäristön valmistelua.</span><span class="sxs-lookup"><span data-stu-id="0ce80-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="0ce80-105">Rekisteröityminen ja organisaation luominen</span><span class="sxs-lookup"><span data-stu-id="0ce80-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="0ce80-106">Siirry [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) -sivustoon.</span><span class="sxs-lookup"><span data-stu-id="0ce80-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="0ce80-107">Valitse **Aloita**.</span><span class="sxs-lookup"><span data-stu-id="0ce80-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="0ce80-108">Valitse ensin sopiva kirjautumisskenaario ja sitten vastaava linkki.</span><span class="sxs-lookup"><span data-stu-id="0ce80-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="0ce80-109">Aloita organisaation luonti hyväksymällä ehdot ja valitsemalla **Jatka**.</span><span class="sxs-lookup"><span data-stu-id="0ce80-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="0ce80-110">Kun ympäristö on luotu, sinut ohjataan [Customer Insightsiin](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="0ce80-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="0ce80-111">Tutustu sovellukseen esittely-ympäristön avulla tai luo uusi ympäristö seuraavan osan vaiheiden avulla.</span><span class="sxs-lookup"><span data-stu-id="0ce80-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="0ce80-112">Kun ympäristön asetukset on määritetty, valitse **Luo**.</span><span class="sxs-lookup"><span data-stu-id="0ce80-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="0ce80-113">Kirjautuminen tapahtuu, kun ympäristö on luotu.</span><span class="sxs-lookup"><span data-stu-id="0ce80-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="0ce80-114">Ympäristön luominen aiemmin luodussa organisaatiossa</span><span class="sxs-lookup"><span data-stu-id="0ce80-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="0ce80-115">Uusi ympäristö voidaan luoda kahdella tavalla.</span><span class="sxs-lookup"><span data-stu-id="0ce80-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="0ce80-116">Voit joko määrittää kokonaan uuden määrityksen tai voit kopioida joitakin määritysasetuksia aiemmin luodusta ympäristöstä.</span><span class="sxs-lookup"><span data-stu-id="0ce80-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="0ce80-117">Ympäristön luominen:</span><span class="sxs-lookup"><span data-stu-id="0ce80-117">To create an environment:</span></span>

1. <span data-ttu-id="0ce80-118">Valitse sovelluksen otsikossa **Ympäristö**-valitsin.</span><span class="sxs-lookup"><span data-stu-id="0ce80-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="0ce80-119">Valitse **Uusi**.</span><span class="sxs-lookup"><span data-stu-id="0ce80-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0ce80-120">![Ympäristön asetukset](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="0ce80-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="0ce80-121">Valitse **Luo uusi ympäristö** -valintaikkunassa **Uusi ympäristö**.</span><span class="sxs-lookup"><span data-stu-id="0ce80-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="0ce80-122">Jos haluat [kopioida tietoja nykyisestä ympäristöstä](#additional-considerations-for-copy-configuration-preview), valitse **Kopioi aiemmasta ympäristöstä**.</span><span class="sxs-lookup"><span data-stu-id="0ce80-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="0ce80-123">Näkyviin tulee luettelo kaikista organisaation käytettävissä olevista ympäristöistä, joista voit kopioida tietoja.</span><span class="sxs-lookup"><span data-stu-id="0ce80-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="0ce80-124">Anna seuraavat tiedot:</span><span class="sxs-lookup"><span data-stu-id="0ce80-124">Provide the following details:</span></span>
   - <span data-ttu-id="0ce80-125">**Nimi**: Ympäristön nimi.</span><span class="sxs-lookup"><span data-stu-id="0ce80-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="0ce80-126">Tämä kenttä on jo täytetty, jos kopioit tietoja aiemmin luodusta ympäristöstä, mutta voit muuttaa sitä.</span><span class="sxs-lookup"><span data-stu-id="0ce80-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="0ce80-127">**Alue**: Alue, jossa palvelu otetaan käyttöön ja jossa sitä isännöidään.</span><span class="sxs-lookup"><span data-stu-id="0ce80-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="0ce80-128">**Tyyppi**: Määritä, haluatko luoda tuotanto- vai eristysympäristön.</span><span class="sxs-lookup"><span data-stu-id="0ce80-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="0ce80-129">Valinnaisesti voit valita **Lisäasetukset**:</span><span class="sxs-lookup"><span data-stu-id="0ce80-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="0ce80-130">**Tallenna kaikki tiedot kohteeseen**: Määrittää, minne haluat tallentaa Customer Insightsin tulostiedot.</span><span class="sxs-lookup"><span data-stu-id="0ce80-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="0ce80-131">Vaihtoehtoja on kaksi: **Customer Insights -tallennustila** (Customer Insights -ryhmän hallitsema Azure Data Lake) ja **Azure Data Lake Storage Gen2** (oma Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="0ce80-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="0ce80-132">Oletusarvoisesi Customer Insights -tallennustila -vaihtoehto on valittu.</span><span class="sxs-lookup"><span data-stu-id="0ce80-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0ce80-133">Tallentamalla tiedot Azure Data Lake Storageen hyväksyt, että tiedot siirretään ja tallennetaan kyseisen Azure-tallennustilin asianmukaiseen maantieteelliseen sijaintiin. Tämä sijainti voi olla eri kuin sijainti, johon tiedot on tallennettu Dynamics 365 Customer Insightsissa.</span><span class="sxs-lookup"><span data-stu-id="0ce80-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="0ce80-134">Lisätietoja on Microsoftin luottamuskeskuksessa.</span><span class="sxs-lookup"><span data-stu-id="0ce80-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="0ce80-135">Tällä hetkellä käsitellyt entiteetit tallennetaan aina Customer Insightsin hallittuun Data Lake -tallennustilaan.</span><span class="sxs-lookup"><span data-stu-id="0ce80-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="0ce80-136">Vain sellaisia Azure Data Lake Gen2 -tallennustilejä tuetaan, jotka ovat ympäristöä luotaessa valitulla Azure-alueella.</span><span class="sxs-lookup"><span data-stu-id="0ce80-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="0ce80-137">Vain sellaisia tallennustilatilejä tuetaan, joissa on otettu käyttöön Azure Data Lake Gen2:n hierarkkinen nimitila.</span><span class="sxs-lookup"><span data-stu-id="0ce80-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="0ce80-138">Voit valita Azure Data Lake Storage Gen2 -vaihtoehdossa, käytetäänkö todennukseen resurssi- vai tilausperusteista vaihtoehtoa.</span><span class="sxs-lookup"><span data-stu-id="0ce80-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="0ce80-139">Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="0ce80-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="0ce80-140">**Säilön** nimeä ei voi muuttaa, ja se on customerinsights.</span><span class="sxs-lookup"><span data-stu-id="0ce80-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="0ce80-141">Jos haluat käyttää [ennusteita](predictions.md) tai määrittää tietojen jakamisen sovelluksissa ja ratkaisuissa Microsoft Dataversen perusteella, anna Microsoft Dataverse -ympäristön URL-osoite kohdassa **Tietojen jakamisen määrittäminen Microsoft Dataversen kanssa ja lisäominaisuuksien käyttöönotto**.</span><span class="sxs-lookup"><span data-stu-id="0ce80-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="0ce80-142">Valitse **Ota käyttöön tietojen jakaminen**, jos haluat jakaa Customer Insightsin tulostiedot Microsoft Dataversen hallitun Data Laken kanssa.</span><span class="sxs-lookup"><span data-stu-id="0ce80-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="0ce80-143">Tietojen jakamista Microsoft Dataversen hallitun Data Laken kanssa ei tueta tällä hetkellä, jos kaikki tiedot tallennetaan omaan Azure Data Lake Storage -ratkaisuun.</span><span class="sxs-lookup"><span data-stu-id="0ce80-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="0ce80-144">[Entiteetin puuttuvien arvojen ennustetta](predictions.md) ei tueta tällä hetkellä, jos tietojen jakaminen Microsoft Dataversen hallitun Data Laken kanssa otetaan käyttöön.</span><span class="sxs-lookup"><span data-stu-id="0ce80-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="0ce80-145">![Määritysvalinnat tietojen jakamista varten Microsoft Dataversen kanssa](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="0ce80-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="0ce80-146">Kun suoritat prosesseja, kuten tietojen käsittelyä tai segmenttien luontia, vastaavat kansiot luodaan edellä määritettyyn tallennustiliin.</span><span class="sxs-lookup"><span data-stu-id="0ce80-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="0ce80-147">Datatiedostoja ja model.json-tiedostoja luodaan ja lisätään asianmukaisiin alikansioihin suorittamasi prosessin perusteella.</span><span class="sxs-lookup"><span data-stu-id="0ce80-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="0ce80-148">Jos luot useita Customer Insights -ympäristöjä ja valitset kyseisten ympäristöjen tuloste-entiteettien tallentamisen tallennustilille, kullekin ympäristölle luodaan erilliset kansiot siten, että säilössä on ci_<environmentid>.</span><span class="sxs-lookup"><span data-stu-id="0ce80-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="0ce80-149">Muita määrityksen kopioinnissa huomioon otettavia seikkoja (esikatselu)</span><span class="sxs-lookup"><span data-stu-id="0ce80-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="0ce80-150">Seuraavat määritysasetukset kopioidaan:</span><span class="sxs-lookup"><span data-stu-id="0ce80-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="0ce80-151">Toiminnon määritykset</span><span class="sxs-lookup"><span data-stu-id="0ce80-151">Feature configurations</span></span>
- <span data-ttu-id="0ce80-152">Käsitellyt/tuodut tietolähteet</span><span class="sxs-lookup"><span data-stu-id="0ce80-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="0ce80-153">Tietojen yhtenäistämisen (yhdistäminen, vastaavuus) määritys</span><span class="sxs-lookup"><span data-stu-id="0ce80-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="0ce80-154">Segmentit</span><span class="sxs-lookup"><span data-stu-id="0ce80-154">Segments</span></span>
- <span data-ttu-id="0ce80-155">Mittarit</span><span class="sxs-lookup"><span data-stu-id="0ce80-155">Measures</span></span>
- <span data-ttu-id="0ce80-156">Suhteet</span><span class="sxs-lookup"><span data-stu-id="0ce80-156">Relationships</span></span>
- <span data-ttu-id="0ce80-157">Aktiviteetit</span><span class="sxs-lookup"><span data-stu-id="0ce80-157">Activities</span></span>
- <span data-ttu-id="0ce80-158">Haku- ja suodatusindeksi</span><span class="sxs-lookup"><span data-stu-id="0ce80-158">Search & filter Index</span></span>
- <span data-ttu-id="0ce80-159">Vientikohteet</span><span class="sxs-lookup"><span data-stu-id="0ce80-159">Export destinations</span></span>
- <span data-ttu-id="0ce80-160">Ajoitettu päivitys</span><span class="sxs-lookup"><span data-stu-id="0ce80-160">Scheduled refresh</span></span>
- <span data-ttu-id="0ce80-161">Rikastukset</span><span class="sxs-lookup"><span data-stu-id="0ce80-161">Enrichments</span></span>
- <span data-ttu-id="0ce80-162">Mallien hallinta</span><span class="sxs-lookup"><span data-stu-id="0ce80-162">Model management</span></span>
- <span data-ttu-id="0ce80-163">Roolimääritykset</span><span class="sxs-lookup"><span data-stu-id="0ce80-163">Role assignments</span></span>

<span data-ttu-id="0ce80-164">Seuraavia asetuksia *ei* kopioida:</span><span class="sxs-lookup"><span data-stu-id="0ce80-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="0ce80-165">Asiakasprofiilit.</span><span class="sxs-lookup"><span data-stu-id="0ce80-165">Customer profiles.</span></span>
- <span data-ttu-id="0ce80-166">Tietolähteen tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="0ce80-166">Data source credentials.</span></span> <span data-ttu-id="0ce80-167">Sinun on annettava kunkin tietolähteen tunnistetiedot ja päivitettävä tietolähteet manuaalisesti.</span><span class="sxs-lookup"><span data-stu-id="0ce80-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="0ce80-168">Tietolähteet Common Data Model -kansiosta ja Common Data Service -hallitusta tallennustilasta.</span><span class="sxs-lookup"><span data-stu-id="0ce80-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="0ce80-169">Nämä tietolähteet on luotava manuaalisesti samalla nimellä kuin lähdeympäristössä.</span><span class="sxs-lookup"><span data-stu-id="0ce80-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="0ce80-170">Kun kopioit ympäristön, näkyviin tulee vahvistussanoma siitä, että uusi ympäristö on luotu.</span><span class="sxs-lookup"><span data-stu-id="0ce80-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="0ce80-171">Valitse **Siirry tietolähteisiin**, kun haluat nähdä tietolähteiden luettelon.</span><span class="sxs-lookup"><span data-stu-id="0ce80-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="0ce80-172">Kaikkien tietolähteiden tilana näkyy **Vaatii tunnistetietoja**.</span><span class="sxs-lookup"><span data-stu-id="0ce80-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="0ce80-173">Muokkaa tietolähteitä ja päivitä ne syöttämällä tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="0ce80-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0ce80-174">![Kopioidut tietolähteet](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="0ce80-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="0ce80-175">Kun olet päivittänyt tietolähteet, siirry kohtaan **Tiedot** > **Yhtenäistäminen**.</span><span class="sxs-lookup"><span data-stu-id="0ce80-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="0ce80-176">Siellä ovat lähdeympäristön asetukset.</span><span class="sxs-lookup"><span data-stu-id="0ce80-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="0ce80-177">Voit muokata niitä tarpeen mukaan tai valita **Suorita**, jolloin tietojen yhtenäistämisprosessi alkaa ja yhtenäistetty asiakasentiteetti luodaan.</span><span class="sxs-lookup"><span data-stu-id="0ce80-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="0ce80-178">Kun tietojen yhtenäistäminen on valmis, päivitä myös kohdat **Mittarit** ja **Segmentit** siirtymällä niihin.</span><span class="sxs-lookup"><span data-stu-id="0ce80-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="0ce80-179">Aiemmin luodun ympäristön muokkaaminen</span><span class="sxs-lookup"><span data-stu-id="0ce80-179">Edit an existing environment</span></span>

<span data-ttu-id="0ce80-180">Voit muokata joitakin aiemmin luotujen ympäristöjen tietoja.</span><span class="sxs-lookup"><span data-stu-id="0ce80-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="0ce80-181">Valitse sovelluksen otsikossa **Ympäristö**-valitsin.</span><span class="sxs-lookup"><span data-stu-id="0ce80-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="0ce80-182">Valitse **Muokkaa**-kuvake.</span><span class="sxs-lookup"><span data-stu-id="0ce80-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="0ce80-183">**Muokkaa ympäristöä** -ruudussa voit päivittää ympäristön **näyttönimen**, mutta et voi muuttaa **aluetta** tai **tyyppiä**.</span><span class="sxs-lookup"><span data-stu-id="0ce80-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="0ce80-184">Jos ympäristö on määritetty tallentamaan tiedot Azure Data Lake Storage Gen2:ään, voit päivittää **tiliavaimen**.</span><span class="sxs-lookup"><span data-stu-id="0ce80-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="0ce80-185">Et voi kuitenkaan muuttaa **tilin nimeä** tai **säilön** nimeä.</span><span class="sxs-lookup"><span data-stu-id="0ce80-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="0ce80-186">Voit myös tehdä päivityksen käyttöoikeusavaimeen perustuvassa yhteydessä resurssi- tai tilausperusteiseen yhteyteen.</span><span class="sxs-lookup"><span data-stu-id="0ce80-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="0ce80-187">Päivitykseen jälkeen ei ole mahdollista palata käyttöoikeusavaimeen.</span><span class="sxs-lookup"><span data-stu-id="0ce80-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="0ce80-188">Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="0ce80-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="0ce80-189">**Säilö**-tietoja ei voi muuttaa yhteyttä päivitettäessä.</span><span class="sxs-lookup"><span data-stu-id="0ce80-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="0ce80-190">Aiemmin luodun ympäristön palauttaminen</span><span class="sxs-lookup"><span data-stu-id="0ce80-190">Reset an existing environment</span></span>

<span data-ttu-id="0ce80-191">Järjestelmänvalvoja voi palauttaa ympäristön tyhjään tilaan, jos haluat poistaa kaikki määritykset ja käsitellyt tiedot.</span><span class="sxs-lookup"><span data-stu-id="0ce80-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="0ce80-192">Valitse sovelluksen otsikossa **Ympäristö**-valitsin.</span><span class="sxs-lookup"><span data-stu-id="0ce80-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="0ce80-193">Valitse ympäristö, jonka haluat palauttaa, ja valitse sitten kolme pistettä eli **...**.</span><span class="sxs-lookup"><span data-stu-id="0ce80-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="0ce80-194">Valitse **Palauta**-vaihtoehto.</span><span class="sxs-lookup"><span data-stu-id="0ce80-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="0ce80-195">Vahvista poisto antamalla ympäristön nimi ja valitsemalla **Palauta**.</span><span class="sxs-lookup"><span data-stu-id="0ce80-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="0ce80-196">Aiemmin luodun ympäristön poistaminen (käytettävissä vain järjestelmänvalvojille)</span><span class="sxs-lookup"><span data-stu-id="0ce80-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="0ce80-197">Järjestelmänvalvoja voi poistaa myös hallitsemasi ympäristön.</span><span class="sxs-lookup"><span data-stu-id="0ce80-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="0ce80-198">Valitse sovelluksen otsikossa **Ympäristö**-valitsin.</span><span class="sxs-lookup"><span data-stu-id="0ce80-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="0ce80-199">Valitse ympäristö, jonka haluat palauttaa, ja valitse sitten kolme pistettä eli **...**.</span><span class="sxs-lookup"><span data-stu-id="0ce80-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="0ce80-200">Valitse **Poista**-vaihtoehto.</span><span class="sxs-lookup"><span data-stu-id="0ce80-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="0ce80-201">Vahvista poisto antamalla ympäristön nimi ja valitsemalla **Poista**.</span><span class="sxs-lookup"><span data-stu-id="0ce80-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]