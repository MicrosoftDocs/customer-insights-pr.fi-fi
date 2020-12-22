---
title: Luo ja hallitse ympäristöjä
description: Tietoja palveluun rekisteröitymisestä ja ympäristöjen hallinnasta.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644129"
---
# <a name="manage-environments"></a><span data-ttu-id="c9236-103">Ympäristöjen hallinta</span><span class="sxs-lookup"><span data-stu-id="c9236-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c9236-104">Tässä artikkelissa käsitellään uuden organisaation luontia ja ympäristön valmistelua.</span><span class="sxs-lookup"><span data-stu-id="c9236-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="c9236-105">Rekisteröityminen ja organisaation luominen</span><span class="sxs-lookup"><span data-stu-id="c9236-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="c9236-106">Siirry [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) -sivustoon.</span><span class="sxs-lookup"><span data-stu-id="c9236-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="c9236-107">Valitse **Aloita**.</span><span class="sxs-lookup"><span data-stu-id="c9236-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="c9236-108">Valitse ensin sopiva kirjautumisskenaario ja sitten vastaava linkki.</span><span class="sxs-lookup"><span data-stu-id="c9236-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="c9236-109">Aloita organisaation luonti hyväksymällä ehdot ja valitsemalla **Jatka**.</span><span class="sxs-lookup"><span data-stu-id="c9236-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="c9236-110">Kun ympäristö on luotu, sinut ohjataan [Customer Insightsiin](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="c9236-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="c9236-111">Tutustu sovellukseen esittely-ympäristön avulla tai luo uusi ympäristö seuraavan osan vaiheiden avulla.</span><span class="sxs-lookup"><span data-stu-id="c9236-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="c9236-112">Kun ympäristön asetukset on määritetty, valitse **Luo**.</span><span class="sxs-lookup"><span data-stu-id="c9236-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="c9236-113">Kirjautuminen tapahtuu, kun ympäristö on luotu.</span><span class="sxs-lookup"><span data-stu-id="c9236-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="c9236-114">Ympäristön luominen aiemmin luodussa organisaatiossa</span><span class="sxs-lookup"><span data-stu-id="c9236-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="c9236-115">Uusi ympäristö voidaan luoda kahdella tavalla.</span><span class="sxs-lookup"><span data-stu-id="c9236-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="c9236-116">Voit joko määrittää kokonaan uuden määrityksen tai voit kopioida joitakin määritysasetuksia aiemmin luodusta ympäristöstä.</span><span class="sxs-lookup"><span data-stu-id="c9236-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="c9236-117">Ympäristön luominen:</span><span class="sxs-lookup"><span data-stu-id="c9236-117">To create an environment:</span></span>

1. <span data-ttu-id="c9236-118">Valitse sovelluksen otsikossa **Asetukset**-kuvake.</span><span class="sxs-lookup"><span data-stu-id="c9236-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="c9236-119">Valitse **Uusi ympäristö**.</span><span class="sxs-lookup"><span data-stu-id="c9236-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c9236-120">![Ympäristön asetukset](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="c9236-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="c9236-121">Valitse **Luo uusi ympäristö** -valintaikkunassa **Uusi ympäristö**.</span><span class="sxs-lookup"><span data-stu-id="c9236-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="c9236-122">Jos haluat [kopioida tietoja nykyisestä ympäristöstä](#additional-considerations-for-copy-configuration-preview), valitse **Kopioi aiemmasta ympäristöstä**.</span><span class="sxs-lookup"><span data-stu-id="c9236-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="c9236-123">Näkyviin tulee luettelo kaikista organisaation käytettävissä olevista ympäristöistä, joista voit kopioida tietoja.</span><span class="sxs-lookup"><span data-stu-id="c9236-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="c9236-124">Anna seuraavat tiedot:</span><span class="sxs-lookup"><span data-stu-id="c9236-124">Provide the following details:</span></span>
   - <span data-ttu-id="c9236-125">**Nimi**: Ympäristön nimi.</span><span class="sxs-lookup"><span data-stu-id="c9236-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="c9236-126">Tämä kenttä on jo täytetty, jos kopioit tietoja aiemmin luodusta ympäristöstä, mutta voit muuttaa sitä.</span><span class="sxs-lookup"><span data-stu-id="c9236-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="c9236-127">**Alue**: Alue, jossa palvelu otetaan käyttöön ja jossa sitä isännöidään.</span><span class="sxs-lookup"><span data-stu-id="c9236-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="c9236-128">**Tyyppi**: Määritä, haluatko luoda tuotanto- vai eristysympäristön.</span><span class="sxs-lookup"><span data-stu-id="c9236-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="c9236-129">Valinnaisesti voit valita **Lisäasetukset**:</span><span class="sxs-lookup"><span data-stu-id="c9236-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="c9236-130">**Tallenna kaikki tiedot kohteeseen**: Määrittää, minne haluat tallentaa Customer Insightsin tulostiedot.</span><span class="sxs-lookup"><span data-stu-id="c9236-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="c9236-131">Vaihtoehtoja on kaksi: **Customer Insights -tallennustila** (Customer Insights -ryhmän hallitsema Azure Data Lake) ja **Azure Data Lake Storage Gen2** (oma Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="c9236-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="c9236-132">Oletusarvoisesi Customer Insights -tallennustila -vaihtoehto on valittu.</span><span class="sxs-lookup"><span data-stu-id="c9236-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c9236-133">Tallentamalla tiedot Azure Data Lake Storageen hyväksyt, että tiedot siirretään ja tallennetaan kyseisen Azure-tallennustilin asianmukaiseen maantieteelliseen sijaintiin. Tämä sijainti voi olla eri kuin sijainti, johon tiedot on tallennettu Dynamics 365 Customer Insightsissa.</span><span class="sxs-lookup"><span data-stu-id="c9236-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="c9236-134">Lisätietoja on Microsoftin luottamuskeskuksessa.</span><span class="sxs-lookup"><span data-stu-id="c9236-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="c9236-135">Tällä hetkellä käsitellyt entiteetit tallennetaan aina Customer Insightsin hallittuun Data Lake -tallennustilaan.</span><span class="sxs-lookup"><span data-stu-id="c9236-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="c9236-136">Vain sellaisia Azure Data Lake Gen2 -tallennustilejä tuetaan, jotka ovat ympäristöä luotaessa valitulla Azure-alueella.</span><span class="sxs-lookup"><span data-stu-id="c9236-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="c9236-137">Vain sellaisia tallennustilatilejä tuetaan, joissa on otettu käyttöön Azure Data Lake Gen2:n hierarkkinen nimitila.</span><span class="sxs-lookup"><span data-stu-id="c9236-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="c9236-138">Voit valita Azure Data Lake Storage Gen2 -vaihtoehdossa, käytetäänkö todennukseen resurssi- vai tilausperusteista vaihtoehtoa.</span><span class="sxs-lookup"><span data-stu-id="c9236-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="c9236-139">Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="c9236-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="c9236-140">**Säilön** nimeä ei voi muuttaa, ja se on customerinsights.</span><span class="sxs-lookup"><span data-stu-id="c9236-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="c9236-141">Jos haluat käyttää [ennusteita](predictions.md), anna Common Data Service -esiintymän URL-osoite **Käytä ennusteita** -kohdan **Palvelimen osoite** -kentässä.</span><span class="sxs-lookup"><span data-stu-id="c9236-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="c9236-142">Kun suoritat prosesseja, kuten tietojen käsittelyä tai segmenttien luontia, vastaavat kansiot luodaan edellä määritettyyn tallennustiliin.</span><span class="sxs-lookup"><span data-stu-id="c9236-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="c9236-143">Datatiedostoja ja model.json-tiedostoja luodaan ja lisätään asianmukaisiin alikansioihin suorittamasi prosessin perusteella.</span><span class="sxs-lookup"><span data-stu-id="c9236-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="c9236-144">Jos luot useita Customer Insights -ympäristöjä ja valitset kyseisten ympäristöjen tuloste-entiteettien tallentamisen tallennustilille, kullekin ympäristölle luodaan erilliset kansiot siten, että säilössä on ci_<environmentid>.</span><span class="sxs-lookup"><span data-stu-id="c9236-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="c9236-145">Muita määrityksen kopioinnissa huomioon otettavia seikkoja (esikatselu)</span><span class="sxs-lookup"><span data-stu-id="c9236-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="c9236-146">Seuraavat määritysasetukset kopioidaan:</span><span class="sxs-lookup"><span data-stu-id="c9236-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="c9236-147">Toiminnon määritykset</span><span class="sxs-lookup"><span data-stu-id="c9236-147">Feature configurations</span></span>
- <span data-ttu-id="c9236-148">Tuodut tietolähteet</span><span class="sxs-lookup"><span data-stu-id="c9236-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="c9236-149">Tietojen yhtenäistämisen (yhdistäminen, vastaavuus) määritys</span><span class="sxs-lookup"><span data-stu-id="c9236-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="c9236-150">Segmentit</span><span class="sxs-lookup"><span data-stu-id="c9236-150">Segments</span></span>
- <span data-ttu-id="c9236-151">Mittarit</span><span class="sxs-lookup"><span data-stu-id="c9236-151">Measures</span></span>
- <span data-ttu-id="c9236-152">Suhteet</span><span class="sxs-lookup"><span data-stu-id="c9236-152">Relationships</span></span>
- <span data-ttu-id="c9236-153">Aktiviteetit</span><span class="sxs-lookup"><span data-stu-id="c9236-153">Activities</span></span>
- <span data-ttu-id="c9236-154">Haku- ja suodatusindeksi</span><span class="sxs-lookup"><span data-stu-id="c9236-154">Search & filter Index</span></span>
- <span data-ttu-id="c9236-155">Vientikohteet</span><span class="sxs-lookup"><span data-stu-id="c9236-155">Export destinations</span></span>
- <span data-ttu-id="c9236-156">Ajoitettu päivitys</span><span class="sxs-lookup"><span data-stu-id="c9236-156">Scheduled refresh</span></span>
- <span data-ttu-id="c9236-157">Rikastukset</span><span class="sxs-lookup"><span data-stu-id="c9236-157">Enrichments</span></span>
- <span data-ttu-id="c9236-158">Mallien hallinta</span><span class="sxs-lookup"><span data-stu-id="c9236-158">Model management</span></span>
- <span data-ttu-id="c9236-159">Roolimääritykset</span><span class="sxs-lookup"><span data-stu-id="c9236-159">Role assignments</span></span>

<span data-ttu-id="c9236-160">Seuraavia asetuksia *ei* kopioida:</span><span class="sxs-lookup"><span data-stu-id="c9236-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="c9236-161">Asiakasprofiilit.</span><span class="sxs-lookup"><span data-stu-id="c9236-161">Customer profiles.</span></span>
- <span data-ttu-id="c9236-162">Tietolähteen tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="c9236-162">Data source credentials.</span></span> <span data-ttu-id="c9236-163">Sinun on annettava kunkin tietolähteen tunnistetiedot ja päivitettävä tietolähteet manuaalisesti.</span><span class="sxs-lookup"><span data-stu-id="c9236-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="c9236-164">Tietolähteet Common Data Model -kansiosta ja Common Data Service -hallitusta tallennustilasta.</span><span class="sxs-lookup"><span data-stu-id="c9236-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="c9236-165">Nämä tietolähteet on luotava manuaalisesti samalla nimellä kuin lähdeympäristössä.</span><span class="sxs-lookup"><span data-stu-id="c9236-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="c9236-166">Kun kopioit ympäristön, näkyviin tulee vahvistussanoma siitä, että uusi ympäristö on luotu.</span><span class="sxs-lookup"><span data-stu-id="c9236-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="c9236-167">Valitse **Siirry tietolähteisiin**, kun haluat nähdä tietolähteiden luettelon.</span><span class="sxs-lookup"><span data-stu-id="c9236-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="c9236-168">Kaikkien tietolähteiden tilana näkyy **Vaatii tunnistetietoja**.</span><span class="sxs-lookup"><span data-stu-id="c9236-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="c9236-169">Muokkaa tietolähteitä ja päivitä ne syöttämällä tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="c9236-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c9236-170">![Kopioidut tietolähteet](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="c9236-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="c9236-171">Kun olet päivittänyt tietolähteet, siirry kohtaan **Tiedot** > **Yhtenäistäminen**.</span><span class="sxs-lookup"><span data-stu-id="c9236-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="c9236-172">Siellä ovat lähdeympäristön asetukset.</span><span class="sxs-lookup"><span data-stu-id="c9236-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="c9236-173">Voit muokata niitä tarpeen mukaan tai valita **Suorita**, jolloin tietojen yhtenäistämisprosessi alkaa ja yhtenäistetty asiakasentiteetti luodaan.</span><span class="sxs-lookup"><span data-stu-id="c9236-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="c9236-174">Kun tietojen yhtenäistäminen on valmis, päivitä myös kohdat **Mittarit** ja **Segmentit** siirtymällä niihin.</span><span class="sxs-lookup"><span data-stu-id="c9236-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="c9236-175">Aiemmin luodun ympäristön muokkaaminen</span><span class="sxs-lookup"><span data-stu-id="c9236-175">Edit an existing environment</span></span>

<span data-ttu-id="c9236-176">Voit muokata joitakin aiemmin luotujen ympäristöjen tietoja.</span><span class="sxs-lookup"><span data-stu-id="c9236-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="c9236-177">Valitse **Hallinta** > **Järjestelmä** > **Tietoja**.</span><span class="sxs-lookup"><span data-stu-id="c9236-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="c9236-178">Valitse **muokkaa**.</span><span class="sxs-lookup"><span data-stu-id="c9236-178">Select **Edit**.</span></span>

3. <span data-ttu-id="c9236-179">Voit päivittää ympäristön **näyttönimen**, mutta et voi päivittää **aluetta** tai **tyyppiä**.</span><span class="sxs-lookup"><span data-stu-id="c9236-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="c9236-180">Jos ympäristö on määritetty tallentamaan tiedot Azure Data Lake Storage Gen2:ään, voit päivittää **tiliavaimen**.</span><span class="sxs-lookup"><span data-stu-id="c9236-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="c9236-181">Et voi kuitenkaan muuttaa **tilin nimeä** tai **säilön** nimeä.</span><span class="sxs-lookup"><span data-stu-id="c9236-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="c9236-182">Voit myös tehdä päivityksen käyttöoikeusavaimeen perustuvassa yhteydessä resurssi- tai tilausperusteiseen yhteyteen.</span><span class="sxs-lookup"><span data-stu-id="c9236-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="c9236-183">Päivitykseen jälkeen ei ole mahdollista palata käyttöoikeusavaimeen.</span><span class="sxs-lookup"><span data-stu-id="c9236-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="c9236-184">Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="c9236-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="c9236-185">**Säilö**-tietoja ei voi muuttaa yhteyttä päivitettäessä.</span><span class="sxs-lookup"><span data-stu-id="c9236-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="c9236-186">Aiemmin luodun ympäristön palauttaminen</span><span class="sxs-lookup"><span data-stu-id="c9236-186">Reset an existing environment</span></span>

<span data-ttu-id="c9236-187">Ympäristö voidaan palauttaa tyhjään tilaan, jos haluat poistaa kaikki määritykset ja käsitellyt tiedot.</span><span class="sxs-lookup"><span data-stu-id="c9236-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="c9236-188">Valitse **Hallinta** > **Järjestelmä** > **Tietoja**.</span><span class="sxs-lookup"><span data-stu-id="c9236-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="c9236-189">Valitse **Palauta**.</span><span class="sxs-lookup"><span data-stu-id="c9236-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="c9236-190">Vahvista poisto antamalla ympäristön nimi ja valitsemalla **Palauta**.</span><span class="sxs-lookup"><span data-stu-id="c9236-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="c9236-191">Olemassa olevan ympäristön poistaminen</span><span class="sxs-lookup"><span data-stu-id="c9236-191">Delete an existing environment</span></span>

1. <span data-ttu-id="c9236-192">Valitse **Hallinta** > **Järjestelmä** > **Tietoja**.</span><span class="sxs-lookup"><span data-stu-id="c9236-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="c9236-193">Valitse **Poista**.</span><span class="sxs-lookup"><span data-stu-id="c9236-193">Select **Delete**.</span></span>

1. <span data-ttu-id="c9236-194">Vahvista poisto antamalla ympäristön nimi ja valitsemalla **Poista**.</span><span class="sxs-lookup"><span data-stu-id="c9236-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
