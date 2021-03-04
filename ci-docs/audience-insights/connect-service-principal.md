---
title: Yhteyden muodostaminen Azure Data Lake Storage Gen2 -tiliin palveluobjektia käyttämällä
description: Käytä käyttäjäryhmän tietojen Azure-palveluobjektia muodostamaan yhteys omaan Data Lake -tallennustilaan, kun se liitetään käyttäjäryhmän tietoihin.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267718"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="56f46-103">Yhteyden muodostaminen Azure Data Lake Storage Gen2 -tiliin käyttäjäryhmän merkityksellisten tietojen Azure-palveluobjektilla</span><span class="sxs-lookup"><span data-stu-id="56f46-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="56f46-104">Azure-palveluja käyttävillä automaattisilla työkaluilla on oltava aina rajoitetut käyttöoikeudet.</span><span class="sxs-lookup"><span data-stu-id="56f46-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="56f46-105">Sen sijaan että sovellukset kirjautusivat sisään käyttäjänä, jolla on kaikki oikeudet, Azure antaa mahdollisuuden käyttää palveluobjekteja.</span><span class="sxs-lookup"><span data-stu-id="56f46-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="56f46-106">Aiheessa käsitellään käyttäjäryhmän merkityksellisten tietojen yhdistämisestä Azure Data Lake Storage Gen2 -tiliin käyttämällä Azure-palveluobjektia eikä tallennustilan tiliavaimia.</span><span class="sxs-lookup"><span data-stu-id="56f46-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="56f46-107">Palveluobjektin avulla voi turvallisesti [lisätä Common Data Model -kansion tietolähteenä tai muokata sitä](connect-common-data-model.md) tai [luoda uuden ympäristön tai päivittää aiemmin luotua ympäristöä](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="56f46-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="56f46-108">Azure Data Lake Gen2 -tallennustilillä, joka yrittää käyttää palveluobjektia, on [oltava käytössä hierarkkinen nimitila (HNS)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="56f46-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="56f46-109">Palveluobjektin luontiin tarvitaan Azure-tilauksen järjestelmänvalvojan oikeudet.</span><span class="sxs-lookup"><span data-stu-id="56f46-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="56f46-110">Käyttäjäryhmän merkityksellisten tietojen Azure-palveluobjektin luominen</span><span class="sxs-lookup"><span data-stu-id="56f46-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="56f46-111">Tarkista ennen uuden käyttäjäryhmän merkityksellisten tietojen palveluobjektin luontia, onko sellainen jo luotu organisaatioon.</span><span class="sxs-lookup"><span data-stu-id="56f46-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="56f46-112">Aiemmin luodun palveluobjektin etsiminen</span><span class="sxs-lookup"><span data-stu-id="56f46-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="56f46-113">Siirry [Azure-hallintaportaaliin](https://portal.azure.com) ja kirjaudu organisaatioon.</span><span class="sxs-lookup"><span data-stu-id="56f46-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="56f46-114">Valitse **Azure Active Directory** Azure-palveluissa.</span><span class="sxs-lookup"><span data-stu-id="56f46-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="56f46-115">Valitse **Hallinta**-kohdassa **Enterprise-sovellukset**.</span><span class="sxs-lookup"><span data-stu-id="56f46-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="56f46-116">Käytä hakusanana käyttäjäryhmän merkityksellisten tietojen ensimmäisen osapuolen sovellustunnusta `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` tai nimeä `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="56f46-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="56f46-117">Jos löydät vastaavan tietueen, käyttäjäryhmän merkityksellisillä tiedoilla on palveluobjekti.</span><span class="sxs-lookup"><span data-stu-id="56f46-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="56f46-118">Sitä ei tarvitse luoda uudelleen.</span><span class="sxs-lookup"><span data-stu-id="56f46-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Näyttökuva, jossa on aiemmin luotu palveluobjekti":::
   
6. <span data-ttu-id="56f46-120">Jos tuloksia ei ole, luo uusi palveluobjekti.</span><span class="sxs-lookup"><span data-stu-id="56f46-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="56f46-121">Uuden palveluobjektin luominen</span><span class="sxs-lookup"><span data-stu-id="56f46-121">Create a new service principal</span></span>

1. <span data-ttu-id="56f46-122">Asenna uusin **Azure Active Directory PowerShell for Graph** -versio.</span><span class="sxs-lookup"><span data-stu-id="56f46-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="56f46-123">Lisätietoja on kohdassa [Azure Active Directory PowerShell for Graphin asentaminen](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="56f46-123">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="56f46-124">Valitse tietokoneessa näppäimistön Windows-avain, tee haku hakusanalla **Windows PowerShell** ja **suorita järjestelmänvalvojana**.</span><span class="sxs-lookup"><span data-stu-id="56f46-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="56f46-125">Anna avautuvassa PowerShell-ikkunassa `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="56f46-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="56f46-126">Luo käyttäjäryhmän merkityksellisten tietojen palveluobjekti Azure AD PowerShell -moduulissa.</span><span class="sxs-lookup"><span data-stu-id="56f46-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="56f46-127">Anna PowerShell-ikkunassa `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="56f46-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="56f46-128">Vaihda vuokraajan tunnuksen paikkamerkin paikalle sen vuokraajan tunnus, jossa haluat luoda palveluobjektin.</span><span class="sxs-lookup"><span data-stu-id="56f46-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="56f46-129">Ympäristön nimiparametri `AzureEnvironmentName` on valinnainen.</span><span class="sxs-lookup"><span data-stu-id="56f46-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="56f46-130">Anna `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="56f46-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="56f46-131">Tämä komento luo käyttäjäryhmän merkityksellisten tietojen palveluobjektin valitussa vuokraajassa.</span><span class="sxs-lookup"><span data-stu-id="56f46-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="56f46-132">Tallennustilin käyttöön tarvittavien oikeuksien myöntäminen palveluobjektille</span><span class="sxs-lookup"><span data-stu-id="56f46-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="56f46-133">Siirry Azure-portaaliin myöntämään palveluobjektille sen tallennustilin oikeudet, jota haluat käyttää käyttäjäryhmän merkityksellisissä tiedoissa.</span><span class="sxs-lookup"><span data-stu-id="56f46-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="56f46-134">Siirry [Azure-hallintaportaaliin](https://portal.azure.com) ja kirjaudu organisaatioon.</span><span class="sxs-lookup"><span data-stu-id="56f46-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="56f46-135">Avaa se tallennustili, jota haluat käyttäjäryhmän merkityksellisten tietojen palveluobjektin voivan käyttää.</span><span class="sxs-lookup"><span data-stu-id="56f46-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="56f46-136">Valitse siirtymisruudussa **Käyttöoikeuksien hallinta (IAM)** ja valitse sitten **Lisää** > **Lisää roolimääritys**.</span><span class="sxs-lookup"><span data-stu-id="56f46-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Näyttökuvassa Azure-portaali roolimääritystä lisättäessä":::
   
1. <span data-ttu-id="56f46-138">Määritä seuraavat ominaisuudet **Lisää roolimääritys** -ruudussa:</span><span class="sxs-lookup"><span data-stu-id="56f46-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="56f46-139">Rooli: *Tallennustilan BLOB-tietojen osallistuja*</span><span class="sxs-lookup"><span data-stu-id="56f46-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="56f46-140">Käyttöoikeuden delegointi: *Käyttäjä, ryhmä tai palveluobjekti*</span><span class="sxs-lookup"><span data-stu-id="56f46-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="56f46-141">Valitse: *Dynamics 365 AI for Customer Insights* ([luotu palveluobjekti](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="56f46-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="56f46-142">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="56f46-142">Select **Save**.</span></span>

<span data-ttu-id="56f46-143">Muutosten päivittyminen voi kestää 15 minuuttia.</span><span class="sxs-lookup"><span data-stu-id="56f46-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="56f46-144">Anna Azure-resurssitunnus tai Azure-tilauksen tiedot käyttäjäryhmän merkityksellisten tietojen tallennustililiitteessä.</span><span class="sxs-lookup"><span data-stu-id="56f46-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="56f46-145">Liitä käyttäjäryhmän merkityksellisten tietojen Azure Data Lake -tallennustili [säilön tulostetietoihin](manage-environments.md) tai [käytä sitä tietolähteenä](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="56f46-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="56f46-146">Azure Data Lake -vaihtoehdon valinta antaa mahdollisuuden valita, käytetäänkö resurssi- tai tilauspohjaista menettelytapaa.</span><span class="sxs-lookup"><span data-stu-id="56f46-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="56f46-147">Anna valitussa menettelytavassa tarvittavat tiedot seuraavien ohjeiden mukaisesti.</span><span class="sxs-lookup"><span data-stu-id="56f46-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="56f46-148">Resurssipohjainen tallennustiliyhteys</span><span class="sxs-lookup"><span data-stu-id="56f46-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="56f46-149">Siirry [Azure-hallintaportaaliin](https://portal.azure.com), kirjaudu tilaukseen ja avaa tallennustili.</span><span class="sxs-lookup"><span data-stu-id="56f46-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="56f46-150">Valitse siirtymisruudussa **Asetukset** > **Ominaisuudet**.</span><span class="sxs-lookup"><span data-stu-id="56f46-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="56f46-151">Kopioi tallennustilin resurssitunnuksen arvo.</span><span class="sxs-lookup"><span data-stu-id="56f46-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Tallennustilin resurssitunnuksen arvon kopiointi":::

1. <span data-ttu-id="56f46-153">Lisää käyttäjäryhmän merkityksellisissä tiedoissa resurssitunnus resurssikenttään, joka näkyy tallennustilin yhteysnäytössä.</span><span class="sxs-lookup"><span data-stu-id="56f46-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Tallennustilin resurssitunnuksen tietojen antaminen":::   
   
1. <span data-ttu-id="56f46-155">Liitä tallennustili suorittamalla jäljellä olevat vaiheet käyttäjäryhmän merkityksellisissä tiedoissa.</span><span class="sxs-lookup"><span data-stu-id="56f46-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="56f46-156">Tilauspohjainen tallennustiliyhteys</span><span class="sxs-lookup"><span data-stu-id="56f46-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="56f46-157">Siirry [Azure-hallintaportaaliin](https://portal.azure.com), kirjaudu tilaukseen ja avaa tallennustili.</span><span class="sxs-lookup"><span data-stu-id="56f46-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="56f46-158">Valitse siirtymisruudussa **Asetukset** > **Ominaisuudet**.</span><span class="sxs-lookup"><span data-stu-id="56f46-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="56f46-159">Varmista, että valitset oikeat tiedot käyttäjäryhmän merkityksellisissä tiedoissa tarkista tallennustilin **Tilaus**-, **Resurssiryhmä**- ja **Nimi**-kohtien tiedot.</span><span class="sxs-lookup"><span data-stu-id="56f46-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="56f46-160">Valitse käyttäjäryhmän merkityksellisissä tiedoissa arvot tai vastaavat kentät tallennustiliä liitettäessä.</span><span class="sxs-lookup"><span data-stu-id="56f46-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="56f46-161">Liitä tallennustili suorittamalla jäljellä olevat vaiheet käyttäjäryhmän merkityksellisissä tiedoissa.</span><span class="sxs-lookup"><span data-stu-id="56f46-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]