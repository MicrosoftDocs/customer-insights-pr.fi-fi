---
title: Yhteyden muodostaminen Azure Data Lake Storage Gen2 -tiliin palveluobjektia käyttämällä
description: Käyttäjäryhmän merkityksellisten tietojen Azure-palveluobjektin käyttäminen muodostamaan yhteys omaan Data Lake -tallennustilaan, kun se liitetään käyttäjäryhmän merkityksellisiin tietoihin.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644084"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="a860d-103">Yhteyden muodostaminen Azure Data Lake Storage Gen2 -tiliin käyttäjäryhmän merkityksellisten tietojen Azure-palveluobjektilla</span><span class="sxs-lookup"><span data-stu-id="a860d-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="a860d-104">Azure-palveluja käyttävillä automaattisilla työkaluilla on oltava aina rajoitetut käyttöoikeudet.</span><span class="sxs-lookup"><span data-stu-id="a860d-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="a860d-105">Sen sijaan että sovellukset kirjautusivat sisään käyttäjänä, jolla on kaikki oikeudet, Azure antaa mahdollisuuden käyttää palveluobjekteja.</span><span class="sxs-lookup"><span data-stu-id="a860d-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="a860d-106">Aiheessa käsitellään käyttäjäryhmän merkityksellisten tietojen yhdistämisestä Azure Data Lake Storage Gen2 -tiliin käyttämällä Azure-palveluobjektia eikä tallennustilan tiliavaimia.</span><span class="sxs-lookup"><span data-stu-id="a860d-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="a860d-107">Palveluobjektin avulla voi turvallisesti [lisätä Common Data Model -kansion tietolähteenä tai muokata sitä](connect-common-data-model.md) tai [luoda uuden ympäristön tai päivittää aiemmin luotua ympäristöä](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="a860d-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="a860d-108">Palveluobjektin luontiin tarvitaan Azure-tilauksen järjestelmänvalvojan oikeudet.</span><span class="sxs-lookup"><span data-stu-id="a860d-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="a860d-109">Käyttäjäryhmän merkityksellisten tietojen Azure-palveluobjektin luominen</span><span class="sxs-lookup"><span data-stu-id="a860d-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="a860d-110">Tarkista ennen uuden käyttäjäryhmän merkityksellisten tietojen palveluobjektin luontia, onko sellainen jo luotu organisaatioon.</span><span class="sxs-lookup"><span data-stu-id="a860d-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="a860d-111">Aiemmin luodun palveluobjektin etsiminen</span><span class="sxs-lookup"><span data-stu-id="a860d-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="a860d-112">Siirry [Azure-hallintaportaaliin](https://portal.azure.com) ja kirjaudu organisaatioon.</span><span class="sxs-lookup"><span data-stu-id="a860d-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="a860d-113">Valitse **Azure Active Directory** Azure-palveluissa.</span><span class="sxs-lookup"><span data-stu-id="a860d-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="a860d-114">Valitse **Hallinta**-kohdassa **Enterprise-sovellukset**.</span><span class="sxs-lookup"><span data-stu-id="a860d-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="a860d-115">Käytä hakusanana käyttäjäryhmän merkityksellisten tietojen ensimmäisen osapuolen sovellustunnusta `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` tai nimeä `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="a860d-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="a860d-116">Jos löydät vastaavan tietueen, käyttäjäryhmän merkityksellisillä tiedoilla on palveluobjekti.</span><span class="sxs-lookup"><span data-stu-id="a860d-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="a860d-117">Sitä ei tarvitse luoda uudelleen.</span><span class="sxs-lookup"><span data-stu-id="a860d-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Näyttökuva, jossa on aiemmin luotu palveluobjekti":::
   
6. <span data-ttu-id="a860d-119">Jos tuloksia ei ole, luo uusi palveluobjekti.</span><span class="sxs-lookup"><span data-stu-id="a860d-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="a860d-120">Uuden palveluobjektin luominen</span><span class="sxs-lookup"><span data-stu-id="a860d-120">Create a new service principal</span></span>

1. <span data-ttu-id="a860d-121">Asenna uusin **Azure Active Directory PowerShell for Graph** -versio.</span><span class="sxs-lookup"><span data-stu-id="a860d-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="a860d-122">Lisätietoja on kohdassa [Azure Active Directory PowerShell for Graphin asentaminen](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="a860d-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="a860d-123">Valitse tietokoneessa näppäimistön Windows-avain, tee haku hakusanalla **Windows PowerShell** ja **suorita järjestelmänvalvojana**.</span><span class="sxs-lookup"><span data-stu-id="a860d-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="a860d-124">Anna avautuvassa PowerShell-ikkunassa `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="a860d-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="a860d-125">Luo käyttäjäryhmän merkityksellisten tietojen palveluobjekti Azure AD PowerShell -moduulissa.</span><span class="sxs-lookup"><span data-stu-id="a860d-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="a860d-126">Anna PowerShell-ikkunassa `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="a860d-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="a860d-127">Vaihda vuokraajan tunnuksen paikkamerkin paikalle sen vuokraajan tunnus, jossa haluat luoda palveluobjektin.</span><span class="sxs-lookup"><span data-stu-id="a860d-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="a860d-128">Ympäristön nimiparametri `AzureEnvironmentName` on valinnainen.</span><span class="sxs-lookup"><span data-stu-id="a860d-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="a860d-129">Anna `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="a860d-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="a860d-130">Tämä komento luo käyttäjäryhmän merkityksellisten tietojen palveluobjektin valitussa vuokraajassa.</span><span class="sxs-lookup"><span data-stu-id="a860d-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="a860d-131">Tallennustilin käyttöön tarvittavien oikeuksien myöntäminen palveluobjektille</span><span class="sxs-lookup"><span data-stu-id="a860d-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="a860d-132">Siirry Azure-portaaliin myöntämään palveluobjektille sen tallennustilin oikeudet, jota haluat käyttää käyttäjäryhmän merkityksellisissä tiedoissa.</span><span class="sxs-lookup"><span data-stu-id="a860d-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="a860d-133">Siirry [Azure-hallintaportaaliin](https://portal.azure.com) ja kirjaudu organisaatioon.</span><span class="sxs-lookup"><span data-stu-id="a860d-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="a860d-134">Avaa se tallennustili, jota haluat käyttäjäryhmän merkityksellisten tietojen palveluobjektin voivan käyttää.</span><span class="sxs-lookup"><span data-stu-id="a860d-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="a860d-135">Valitse siirtymisruudussa **Käyttöoikeuksien hallinta (IAM)** ja valitse sitten **Lisää** > **Lisää roolimääritys**.</span><span class="sxs-lookup"><span data-stu-id="a860d-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Näyttökuvassa Azure-portaali roolimääritystä lisättäessä":::
   
1. <span data-ttu-id="a860d-137">Määritä seuraavat ominaisuudet **Lisää roolimääritys** -ruudussa:</span><span class="sxs-lookup"><span data-stu-id="a860d-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="a860d-138">Rooli: *Tallennustilan BLOB-tietojen osallistuja*</span><span class="sxs-lookup"><span data-stu-id="a860d-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="a860d-139">Käyttöoikeuden delegointi: *Käyttäjä, ryhmä tai palveluobjekti*</span><span class="sxs-lookup"><span data-stu-id="a860d-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="a860d-140">Valitse: *Dynamics 365 AI for Customer Insights* ([luotu palveluobjekti](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="a860d-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="a860d-141">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="a860d-141">Select **Save**.</span></span>

<span data-ttu-id="a860d-142">Muutosten päivittyminen voi kestää 15 minuuttia.</span><span class="sxs-lookup"><span data-stu-id="a860d-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="a860d-143">Anna Azure-resurssitunnus tai Azure-tilauksen tiedot käyttäjäryhmän merkityksellisten tietojen tallennustililiitteessä.</span><span class="sxs-lookup"><span data-stu-id="a860d-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="a860d-144">Liitä käyttäjäryhmän merkityksellisten tietojen Azure Data Lake -tallennustili [säilön tulostetietoihin](manage-environments.md) tai [käytä sitä tietolähteenä](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="a860d-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="a860d-145">Azure Data Lake -vaihtoehdon valinta antaa mahdollisuuden valita, käytetäänkö resurssi- tai tilauspohjaista menettelytapaa.</span><span class="sxs-lookup"><span data-stu-id="a860d-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="a860d-146">Anna valitussa menettelytavassa tarvittavat tiedot seuraavien ohjeiden mukaisesti.</span><span class="sxs-lookup"><span data-stu-id="a860d-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="a860d-147">Resurssipohjainen tallennustiliyhteys</span><span class="sxs-lookup"><span data-stu-id="a860d-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="a860d-148">Siirry [Azure-hallintaportaaliin](https://portal.azure.com), kirjaudu tilaukseen ja avaa tallennustili.</span><span class="sxs-lookup"><span data-stu-id="a860d-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="a860d-149">Valitse siirtymisruudussa **Asetukset** > **Ominaisuudet**.</span><span class="sxs-lookup"><span data-stu-id="a860d-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="a860d-150">Kopioi tallennustilin resurssitunnuksen arvo.</span><span class="sxs-lookup"><span data-stu-id="a860d-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Tallennustilin resurssitunnuksen arvon kopiointi":::

1. <span data-ttu-id="a860d-152">Lisää käyttäjäryhmän merkityksellisissä tiedoissa resurssitunnus resurssikenttään, joka näkyy tallennustilin yhteysnäytössä.</span><span class="sxs-lookup"><span data-stu-id="a860d-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Tallennustilin resurssitunnuksen tietojen antaminen":::   
   
1. <span data-ttu-id="a860d-154">Liitä tallennustili suorittamalla jäljellä olevat vaiheet käyttäjäryhmän merkityksellisissä tiedoissa.</span><span class="sxs-lookup"><span data-stu-id="a860d-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="a860d-155">Tilauspohjainen tallennustiliyhteys</span><span class="sxs-lookup"><span data-stu-id="a860d-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="a860d-156">Siirry [Azure-hallintaportaaliin](https://portal.azure.com), kirjaudu tilaukseen ja avaa tallennustili.</span><span class="sxs-lookup"><span data-stu-id="a860d-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="a860d-157">Valitse siirtymisruudussa **Asetukset** > **Ominaisuudet**.</span><span class="sxs-lookup"><span data-stu-id="a860d-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="a860d-158">Varmista, että valitset oikeat tiedot käyttäjäryhmän merkityksellisissä tiedoissa tarkista tallennustilin **Tilaus**-, **Resurssiryhmä**- ja **Nimi**-kohtien tiedot.</span><span class="sxs-lookup"><span data-stu-id="a860d-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="a860d-159">Valitse käyttäjäryhmän merkityksellisissä tiedoissa arvot tai vastaavat kentät tallennustiliä liitettäessä.</span><span class="sxs-lookup"><span data-stu-id="a860d-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Tallennustilin resurssitunnuksen tietojen antaminen":::
   
1. <span data-ttu-id="a860d-161">Liitä tallennustili suorittamalla jäljellä olevat vaiheet käyttäjäryhmän merkityksellisissä tiedoissa.</span><span class="sxs-lookup"><span data-stu-id="a860d-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
