---
title: Ohjelmointirajapintojen käsitteleminen
description: Ohjelmointirajapintojen käyttäminen ja tietoja niiden rajoituksista.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 011fa700563c53534554a6b73e87c2391bfdf714
ms.sourcegitcommit: a872f59e6febe4d4bd678ddd0b60a1660acca0f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/24/2021
ms.locfileid: "5710456"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="294a9-103">Customer Insights -ohjelmointirajapintojen käyttäminen</span><span class="sxs-lookup"><span data-stu-id="294a9-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="294a9-104">Dynamics 365 Customer Insightsissa on ohjelmointirajapintoja, joilla voi muodostaa omia Customer Insightsissa oleviin tietoihin perustuvia sovelluksia.</span><span class="sxs-lookup"><span data-stu-id="294a9-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="294a9-105">Kyseisten ohjelmointirajapintojen tiedot ovat [Customer Insightsin ohjelmointirajapintojen viitteessä](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="294a9-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="294a9-106">Niissä on lisätietoja toiminnoista, parametreista ja vastauksista.</span><span class="sxs-lookup"><span data-stu-id="294a9-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="294a9-107">Tässä artikkelissa on ohjeita Customer Insightsin ohjelmointirajapintojen käytöstä ja Azure-sovelluksen rekisteröinnin luonnista. Lisäksi siinä opastetaan käytettävissä olevien asiakasohjelmakirjastojen käytön aloittamisessa.</span><span class="sxs-lookup"><span data-stu-id="294a9-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="294a9-108">Customer Insightsin ohjelmistorajapintojen käytön kokeilemisen aloittaminen</span><span class="sxs-lookup"><span data-stu-id="294a9-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="294a9-109">[Kirjaudu](https://home.ci.ai.dynamics.com) Customer Insightsiin.</span><span class="sxs-lookup"><span data-stu-id="294a9-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="294a9-110">Jos et ole vielä tehnyt tilausta, [rekisteröidy Customer Insightsin kokeiluversioon](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="294a9-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="294a9-111">Ota ohjelmointirajapinnat käyttöön Customer Insights -ympäristössä valitsemalla **Hallinta** > **Käyttöoikeudet**.</span><span class="sxs-lookup"><span data-stu-id="294a9-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="294a9-112">Sitä varten tarvitaan järjestelmänvalvojan oikeudet.</span><span class="sxs-lookup"><span data-stu-id="294a9-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="294a9-113">Siirry **Ohjelmointirajapinnat**-välilehteen ja valitse **Ota käyttöön** -painike.</span><span class="sxs-lookup"><span data-stu-id="294a9-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="294a9-114">Ohjelmointirajapintojen ottaminen käyttöön luo sen esiintymän ensisijaisen ja toissijaisen tilausavaimen, jota käytetään ohjelmointirajapintapyynnöissä.</span><span class="sxs-lookup"><span data-stu-id="294a9-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="294a9-115">Voit luoda avaimet uudelleen valitsemalla **Luo ensisijainen uudelleen** tai **Luo toissijainen uudelleen**, kun olet valinnut ensin **Hallinta** > **Käyttöoikeudet** > **Ohjelmointirajapinnat**.</span><span class="sxs-lookup"><span data-stu-id="294a9-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insightsin ohjelmointirajapintojen ottaminen käyttöön":::

1. <span data-ttu-id="294a9-117">**Kokeile ohjelmointirajapintoja** valitsemalla [Tutustu ohjelmointirajapintoihin](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="294a9-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="294a9-118">Valitse ohjelmointirajapintatoiminto ja valitse sitten **Kokeile**.</span><span class="sxs-lookup"><span data-stu-id="294a9-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="294a9-119">Määritä sivuruudussa avattavan **Valtuutus**-valikon arvoksi **implisiittinen**.</span><span class="sxs-lookup"><span data-stu-id="294a9-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="294a9-120">`Authorization`-otsikkoon lisätään haltijatunnus.</span><span class="sxs-lookup"><span data-stu-id="294a9-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="294a9-121">Tilausavain täytetään automaattisesti.</span><span class="sxs-lookup"><span data-stu-id="294a9-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="294a9-122">Vaihtoehtoisesti voit lisätä kaikki tarvittavat kyselyparametrit.</span><span class="sxs-lookup"><span data-stu-id="294a9-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="294a9-123">Vieritä sivuruudun alareunaan ja valitse **Lähetä**.</span><span class="sxs-lookup"><span data-stu-id="294a9-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="294a9-124">HTTP-vastaus tulee pian näkyviin alapuolelle.</span><span class="sxs-lookup"><span data-stu-id="294a9-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="Animoitu gif, joka näyttää, miten ohjelmointirajapintojen testaaminen valitaan.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="294a9-126">Uuden sovellusrekisteröinnin luominen Azure-portaalissa</span><span class="sxs-lookup"><span data-stu-id="294a9-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="294a9-127">Näiden ohjeiden avulla aloitetaan Customer Insightsin ohjelmointirajapintojen käyttö Azure-sovelluksessa delegoituja oikeuksia käyttämällä.</span><span class="sxs-lookup"><span data-stu-id="294a9-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="294a9-128">Varmista, että olet suorittanut ensin [Aloittaminen-osan](#get-started-trying-the-customer-insights-apis) toimet.</span><span class="sxs-lookup"><span data-stu-id="294a9-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="294a9-129">Käytä [Azure-portaaliin](https://portal.azure.com) kirjautumiseen tiliä, jolla voi käyttää Customer Insightsin tietoja.</span><span class="sxs-lookup"><span data-stu-id="294a9-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="294a9-130">Valitse vasemmalla **Sovelluksen rekisteröinnit**.</span><span class="sxs-lookup"><span data-stu-id="294a9-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="294a9-131">Valitse **Uusi rekisteröinti**, anna sovelluksen nimi ja valitse tilityyppi.</span><span class="sxs-lookup"><span data-stu-id="294a9-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="294a9-132">Voit lisätä myös uudelleenohjauksen URL-osoitteen (valinnainen).</span><span class="sxs-lookup"><span data-stu-id="294a9-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="294a9-133">http://localhost on riittävä sovelluksen kehittämiseen paikallisessa tietokoneessa.</span><span class="sxs-lookup"><span data-stu-id="294a9-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="294a9-134">Valitse uudessa sovellusrekisteröinnissä **Ohjelmointirajapinnan oikeudet**.</span><span class="sxs-lookup"><span data-stu-id="294a9-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Animoitu gif, joka määrittää ohjelmointirajapinnan oikeudet sovelluksen rekisteröinnissä.":::

1. <span data-ttu-id="294a9-136">Valitse **Lisää käyttöoikeus** ja valitse sitten sivuruudussa **Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="294a9-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="294a9-137">Valitse **Käyttöoikeustyyppi**-kohdassa **Delegoidut käyttöoikeudet** ja valitse sitten **user_impersonation**-oikeus.</span><span class="sxs-lookup"><span data-stu-id="294a9-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="294a9-138">Valitse **Lisää käyttöoikeudet**.</span><span class="sxs-lookup"><span data-stu-id="294a9-138">Select **Add permissions**.</span></span> <span data-ttu-id="294a9-139">Jos tarvitse ohjelmointirajapinnan käyttöoikeuden ilman käyttäjän kirjautumista, lisätietoja on osiossa [Palvelinten väliset sovelluksen käyttöoikeudet](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="294a9-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="294a9-140">Viimeistele sovelluksen rekisteröinti valitsemalla **Myönnä järjestelmänvalvojan hyväksyntä kohteelle...**.</span><span class="sxs-lookup"><span data-stu-id="294a9-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="294a9-141">Voit käyttää tämän sovelluksen rekisteröinnin sovellus- tai asiakastunnusta MSAL (Microsoft Authentication Library) -kirjastossa. Tällä tavoin saadaan pyynnön kanssa ohjelmointirajapintaan lähetettävä haltijatunnus.</span><span class="sxs-lookup"><span data-stu-id="294a9-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Animoitu gif järjestelmänvalvojan hyväksynnän myöntämiseksi.":::

<span data-ttu-id="294a9-143">Lisätietoja MSAL-kirjastosta on kohdassa [MSAL (Microsoft Authentication Library) -kirjaston yleiskatsaus](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="294a9-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="294a9-144">Lisätietoja sovelluksen rekisteröinnistä Azuressa on kohdassa [Azure-portaalin uusi sovelluksen rekisteröintikokemus](/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="294a9-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="294a9-145">Lisätietoja ohjelmointirajapintojen käyttämisestä asiakaskirjastojen kanssa on kohdassa [Customer Insightsin asiakaskirjastot](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="294a9-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="294a9-146">Palvelinten väliset sovelluksen käyttöoikeudet</span><span class="sxs-lookup"><span data-stu-id="294a9-146">Server-to-server application permissions</span></span>

<span data-ttu-id="294a9-147">[Sovelluksen rekisteröintiä käsittelevässä osiossa](#create-a-new-app-registration-in-the-azure-portal) selvitetään sellaisen sovelluksen rekisteröintiä, johon käyttäjän on kirjauduttava todennusta varten.</span><span class="sxs-lookup"><span data-stu-id="294a9-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="294a9-148">Lisätietoja sellaisen sovelluksen rekisteröinnin luomisesta, jossa ei tarvita käyttäjän toimia ja joka voidaan suorittaa palvelimessa.</span><span class="sxs-lookup"><span data-stu-id="294a9-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="294a9-149">Valitse Azure-portaalin sovelluksen rekisteröinnissä **Ohjelmointirajapinnan käyttöoikeudet**.</span><span class="sxs-lookup"><span data-stu-id="294a9-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="294a9-150">Valitse **Lisää käyttöoikeus** ja valitse sitten sivuruudussa **Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="294a9-150">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="294a9-151">Valitse **Käyttöoikeustyyppi**-kohdassa **Sovelluksen käyttöoikeudet** ja valitse sitten **CustomerInsights.Api.All**-oikeus.</span><span class="sxs-lookup"><span data-stu-id="294a9-151">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="294a9-152">Valitse **Lisää käyttöoikeudet**.</span><span class="sxs-lookup"><span data-stu-id="294a9-152">Select **Add permissions**.</span></span>

1. <span data-ttu-id="294a9-153">Järjestelmänvalvojan hyväksynnän antaminen tässä sovelluksen käyttöoikeudessa edellyttää palveluobjektin lisäämistä.</span><span class="sxs-lookup"><span data-stu-id="294a9-153">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="294a9-154">Asenna Azure Active Directoryn (AD) PowerShell-moduuli: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="294a9-154">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="294a9-155">Muodosta yhteys AD-tiliin: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="294a9-155">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="294a9-156">Voit etsiä vuokraajan tunnuksen valitsemalla **Yleiskuvaus** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="294a9-156">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="294a9-157">Lisää Azure AD -palveluobjekti suorittamalla seuraavan komento: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` AppId-parametri viittaa Customer Insightsin ohjelmointirajapintasovellukseen.</span><span class="sxs-lookup"><span data-stu-id="294a9-157">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Palveluobjektinäyte":::

1. <span data-ttu-id="294a9-159">Palaa sovellusrekisteröinnin **Ohjelmointirajapinnan oikeuksiin**.</span><span class="sxs-lookup"><span data-stu-id="294a9-159">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="294a9-160">Viimeistele sovelluksen rekisteröinti valitsemalla **Myönnä järjestelmänvalvojan hyväksyntä kohteelle...**.</span><span class="sxs-lookup"><span data-stu-id="294a9-160">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Animoitu gif järjestelmänvalvojan hyväksynnän myöntämiseksi.":::

1. <span data-ttu-id="294a9-162">Lopuksi on vielä lisättävä sovellusrekisteröinnin nimi Customer Insightsin käyttäjänä.</span><span class="sxs-lookup"><span data-stu-id="294a9-162">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="294a9-163">Avaa Customer Insights, valitse **Hallinta** > **Käyttöoikeudet** ja valitse lopuksi **Lisää käyttäjä**.</span><span class="sxs-lookup"><span data-stu-id="294a9-163">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="294a9-164">Hae sovellusrekisteröinnin nimi, valitse se hakutuloksissa ja valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="294a9-164">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="294a9-165">Customer Insightsin asiakaskirjastot</span><span class="sxs-lookup"><span data-stu-id="294a9-165">Customer Insights client libraries</span></span>

<span data-ttu-id="294a9-166">Tässä osassa on tietoja Customer Insightsin ohjelmointirajapinnoissa käytettävissä olevien asiakaskirjastojen käytön aloittamisesta.</span><span class="sxs-lookup"><span data-stu-id="294a9-166">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="294a9-167">Kaikki kirjaston lähdekoodit ja näytesovellukset löytyvät [Customer Insights GitHub -sivulta](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="294a9-167">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="294a9-168">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="294a9-168">C# NuGet</span></span>

<span data-ttu-id="294a9-169">Lisätietoja NuGet.orgin C#-asiakaskirjastojen käytön aloittamisesta. Lisätietoja NuGet-paketista on kohdassa [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="294a9-169">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="294a9-170">Tällä hetkellä nämä paketit on tarkoitettu netstandard 2.0- ja netcoreapp 2.0-kehyksiin.</span><span class="sxs-lookup"><span data-stu-id="294a9-170">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="294a9-171">C#-asiakaskirjaston lisääminen C#-projektiin</span><span class="sxs-lookup"><span data-stu-id="294a9-171">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="294a9-172">Avaa Visual Studiossa projektin **NuGet Package Manager**.</span><span class="sxs-lookup"><span data-stu-id="294a9-172">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="294a9-173">Tee hakua hakuehdolla **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="294a9-173">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="294a9-174">Lisää paketti projektiin valitsemalla **Asenna**.</span><span class="sxs-lookup"><span data-stu-id="294a9-174">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="294a9-175">Vaihtoehtoisesti voit suorittaa seuraavan komennon **NuGet Package Manager Consolessa**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="294a9-175">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="NuGet-paketin lisääminen Visual Studio projektiin":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="294a9-177">C#-asiakaskirjaston käyttäminen</span><span class="sxs-lookup"><span data-stu-id="294a9-177">Use the C# client library</span></span>

1. <span data-ttu-id="294a9-178">Hae `AccessToken` [MSAL (Microsoft Authentication Library) -kirjaston](/azure/active-directory/develop/msal-overview) avulla käyttämällä aiemmin luotua [Azure-sovelluksen rekisteröintiä](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="294a9-178">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="294a9-179">Kun tunnuksen todennus ja hankkiminen on tehty, luo uusi tai ota käyttöön aiemmin luotu `HttpClient` jossa **DefaultRequestHeaders "Authorization"**-lisäasetuksen arvona on **Haltijan <access token>** ja **Ocp-Apim-Subscription-Key**-määrityksenä on [Customer Insights -ympäristön **tilausavain**](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="294a9-179">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="294a9-180">Palauta **Valtuutus**-otsikko tarvittaessa.</span><span class="sxs-lookup"><span data-stu-id="294a9-180">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="294a9-181">Esimerkki: tunnus on vanhentunut.</span><span class="sxs-lookup"><span data-stu-id="294a9-181">For example, when the token expired.</span></span>

1. <span data-ttu-id="294a9-182">Välitä tämä `HttpClient` `CustomerInsights`-asiakkaan muodostukseen.</span><span class="sxs-lookup"><span data-stu-id="294a9-182">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Httpclient-näyte":::

1. <span data-ttu-id="294a9-184">Tee asiakasohjelmasta kutsuja laajennusmenetelmiin, kuten `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="294a9-184">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="294a9-185">Jos taustalla olevaa `Microsoft.Rest.HttpOperationResponse`-käyttöä suositeen, käytä http-sanomamenetelmiä, kuten `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="294a9-185">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="294a9-186">Vastauksen tyyppi on todennäköisesti `object`, koska menetelmä voi palauttaa useita tyyppejä (kuten `IList<InstanceInfo>` ja `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="294a9-186">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="294a9-187">Voit tarkistaa palautustyypin tekemällä turvallisesti objektien tyyppimuunnokset kyseisen toiminnon [ohjelmointirajapinnan tietosivulla](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) määritettyihin vastaustyyppeihin.</span><span class="sxs-lookup"><span data-stu-id="294a9-187">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="294a9-188">Jos pyynnössä tarvitaan enemmän tietoja, käytä raakavastausobjektia **http-sanomamenetelmillä**.</span><span class="sxs-lookup"><span data-stu-id="294a9-188">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="294a9-189">NodeJS-paketti</span><span class="sxs-lookup"><span data-stu-id="294a9-189">NodeJS package</span></span>

<span data-ttu-id="294a9-190">Käytä NodeJS-asiakaskirjastoja, jotka ovat käytettävissä NPM:n kautta: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="294a9-190">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="294a9-191">Python-paketti</span><span class="sxs-lookup"><span data-stu-id="294a9-191">Python package</span></span>

<span data-ttu-id="294a9-192">Käytä Python-asiakaskirjastoja, jotka ovat käytettävissä PyPi:n kautta: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="294a9-192">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
