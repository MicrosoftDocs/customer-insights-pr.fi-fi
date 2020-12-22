---
title: Ohjelmointirajapintojen käsitteleminen
description: Ohjelmointirajapintojen käyttäminen ja tietoja niiden rajoituksista.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689126"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="77cc5-103">Customer Insights -ohjelmointirajapintojen käyttäminen</span><span class="sxs-lookup"><span data-stu-id="77cc5-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="77cc5-104">Dynamics 365 Customer Insightsissa on ohjelmointirajapintoja, joilla voi muodostaa omia Customer Insightsissa oleviin tietoihin perustuvia sovelluksia.</span><span class="sxs-lookup"><span data-stu-id="77cc5-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77cc5-105">Kyseisten ohjelmointirajapintojen tiedot ovat [Customer Insightsin ohjelmointirajapintojen viitteessä](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="77cc5-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="77cc5-106">Niissä on lisätietoja toiminnoista, parametreista ja vastauksista.</span><span class="sxs-lookup"><span data-stu-id="77cc5-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="77cc5-107">Tässä artikkelissa on ohjeita Customer Insightsin ohjelmointirajapintojen käytöstä ja Azure-sovelluksen rekisteröinnin luonnista. Lisäksi siinä opastetaan käytettävissä olevien asiakasohjelmakirjastojen käytön aloittamisessa.</span><span class="sxs-lookup"><span data-stu-id="77cc5-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="77cc5-108">Customer Insightsin ohjelmistorajapintojen käytön kokeilemisen aloittaminen</span><span class="sxs-lookup"><span data-stu-id="77cc5-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="77cc5-109">[Kirjaudu](https://home.ci.ai.dynamics.com) Customer Insightsiin.</span><span class="sxs-lookup"><span data-stu-id="77cc5-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="77cc5-110">Jos et ole vielä tehnyt tilausta, [rekisteröidy Customer Insightsin kokeiluversioon](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="77cc5-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="77cc5-111">Ota ohjelmointirajapinnat käyttöön Customer Insights -ympäristössä valitsemalla **Hallinta** > **Käyttöoikeudet**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="77cc5-112">Sitä varten tarvitaan järjestelmänvalvojan oikeudet.</span><span class="sxs-lookup"><span data-stu-id="77cc5-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="77cc5-113">Siirry **Ohjelmointirajapinnat**-välilehteen ja valitse **Ota käyttöön** -painike.</span><span class="sxs-lookup"><span data-stu-id="77cc5-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="77cc5-114">Ohjelmointirajapintojen ottaminen käyttöön luo sen esiintymän ensisijaisen ja toissijaisen tilausavaimen, jota käytetään ohjelmointirajapintapyynnöissä.</span><span class="sxs-lookup"><span data-stu-id="77cc5-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="77cc5-115">Voit luoda avaimet uudelleen valitsemalla **Luo ensisijainen uudelleen** tai **Luo toissijainen uudelleen**, kun olet valinnut ensin **Hallinta** > **Käyttöoikeudet** > **Ohjelmointirajapinnat**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insightsin ohjelmointirajapintojen ottaminen käyttöön":::

1. <span data-ttu-id="77cc5-117">Kokeile ohjelmointirajapintoja valitsemalla **Tutustu ohjelmointirajapintoihin**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="77cc5-118">Valitse ohjelmointirajapintatoiminto ja valitse sitten **Kokeile**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="77cc5-119">Määritä sivuruudussa avattavan **Valtuutus**-valikon arvoksi **implisiittinen**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="77cc5-120">`Authorization`-otsikkoon lisätään haltijatunnus.</span><span class="sxs-lookup"><span data-stu-id="77cc5-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="77cc5-121">Tilausavain täytetään automaattisesti.</span><span class="sxs-lookup"><span data-stu-id="77cc5-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="77cc5-122">Vaihtoehtoisesti voit lisätä kaikki tarvittavat kyselyparametrit.</span><span class="sxs-lookup"><span data-stu-id="77cc5-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="77cc5-123">Vieritä sivuruudun alareunaan ja valitse **Lähetä**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="77cc5-124">HTTP-vastaus tulee pian näkyviin alapuolelle.</span><span class="sxs-lookup"><span data-stu-id="77cc5-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="77cc5-125">Uuden sovellusrekisteröinnin luominen Azure-portaalissa</span><span class="sxs-lookup"><span data-stu-id="77cc5-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="77cc5-126">Näiden ohjeiden avulla aloitetaan Customer Insightsin ohjelmointirajapintojen käyttö Azure-sovelluksessa delegoituja oikeuksia käyttämällä.</span><span class="sxs-lookup"><span data-stu-id="77cc5-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="77cc5-127">Varmista, että olet suorittanut ensin [Aloittaminen-osan](#get-started-trying-the-customer-insights-apis) toimet.</span><span class="sxs-lookup"><span data-stu-id="77cc5-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="77cc5-128">Käytä [Azure-portaaliin](https://portal.azure.com) kirjautumiseen tiliä, jolla voi käyttää Customer Insightsin tietoja.</span><span class="sxs-lookup"><span data-stu-id="77cc5-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="77cc5-129">Valitse vasemmalla **Sovelluksen rekisteröinnit**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="77cc5-130">Valitse **Uusi rekisteröinti**, anna sovelluksen nimi ja valitse tilityyppi.</span><span class="sxs-lookup"><span data-stu-id="77cc5-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="77cc5-131">Voit lisätä myös uudelleenohjauksen URL-osoitteen (valinnainen).</span><span class="sxs-lookup"><span data-stu-id="77cc5-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="77cc5-132">http://localhost on riittävä sovelluksen kehittämiseen paikallisessa tietokoneessa.</span><span class="sxs-lookup"><span data-stu-id="77cc5-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="77cc5-133">Valitse uudessa sovellusrekisteröinnissä **Ohjelmointirajapinnan oikeudet**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="77cc5-134">Valitse **Lisää käyttöoikeus** ja valitse sitten sivuruudussa **Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="77cc5-135">Valitse **Käyttöoikeustyyppi**-kohdassa **Delegoidut käyttöoikeudet** ja valitse sitten **user_impersonation**-oikeus.</span><span class="sxs-lookup"><span data-stu-id="77cc5-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="77cc5-136">Valitse **Lisää käyttöoikeudet**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-136">Select **Add permissions**.</span></span> <span data-ttu-id="77cc5-137">Jos tarvitse ohjelmointirajapinnan käyttöoikeuden ilman käyttäjän kirjautumista, lisätietoja on osiossa [Palvelinten väliset sovelluksen käyttöoikeudet](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="77cc5-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="77cc5-138">Viimeistele sovelluksen rekisteröinti valitsemalla **Myönnä järjestelmänvalvojan hyväksyntä kohteelle...**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="77cc5-139">Voit käyttää tämän sovelluksen rekisteröinnin sovellus- tai asiakastunnusta MSAL (Microsoft Authentication Library) -kirjastossa. Tällä tavoin saadaan pyynnön kanssa ohjelmointirajapintaan lähetettävä haltijatunnus.</span><span class="sxs-lookup"><span data-stu-id="77cc5-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="77cc5-140">Lisätietoja MSAL-kirjastosta on kohdassa [MSAL (Microsoft Authentication Library) -kirjaston yleiskatsaus](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="77cc5-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="77cc5-141">Lisätietoja sovelluksen rekisteröinnistä Azuressa on kohdassa [Azure-portaalin uusi sovelluksen rekisteröintikokemus](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="77cc5-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="77cc5-142">Lisätietoja ohjelmointirajapintojen käyttämisestä asiakaskirjastojen kanssa on kohdassa [Customer Insightsin asiakaskirjastot](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="77cc5-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="77cc5-143">Palvelinten väliset sovelluksen käyttöoikeudet</span><span class="sxs-lookup"><span data-stu-id="77cc5-143">Server-to-server application permissions</span></span>

<span data-ttu-id="77cc5-144">[Sovelluksen rekisteröintiä käsittelevässä osiossa](#create-a-new-app-registration-in-the-azure-portal) selvitetään sellaisen sovelluksen rekisteröintiä, johon käyttäjän on kirjauduttava todennusta varten.</span><span class="sxs-lookup"><span data-stu-id="77cc5-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="77cc5-145">Lisätietoja sellaisen sovelluksen rekisteröinnin luomisesta, jossa ei tarvita käyttäjän toimia ja joka voidaan suorittaa palvelimessa.</span><span class="sxs-lookup"><span data-stu-id="77cc5-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="77cc5-146">Valitse Azure-portaalin sovelluksen rekisteröinnissä **Ohjelmointirajapinnan käyttöoikeudet**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="77cc5-147">Valitse **Lisää käyttöoikeus** ja valitse sitten sivuruudussa **Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="77cc5-148">Valitse **Käyttöoikeustyyppi**-kohdassa **Sovelluksen käyttöoikeudet** ja valitse sitten **CustomerInsights.Api.All**-oikeus.</span><span class="sxs-lookup"><span data-stu-id="77cc5-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="77cc5-149">Valitse **Lisää käyttöoikeudet**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="77cc5-150">Järjestelmänvalvojan hyväksynnän antaminen tässä sovelluksen käyttöoikeudessa edellyttää palveluobjektin lisäämistä.</span><span class="sxs-lookup"><span data-stu-id="77cc5-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="77cc5-151">Asenna Azure Active Directoryn (AD) PowerShell-moduuli: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="77cc5-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="77cc5-152">Muodosta yhteys AD-tiliin: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="77cc5-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="77cc5-153">Voit etsiä vuokraajan tunnuksen valitsemalla **Yleiskuvaus** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="77cc5-154">Lisää Azure AD -palveluobjekti suorittamalla seuraavan komento: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` AppId-parametri viittaa Customer Insightsin ohjelmointirajapintasovellukseen.</span><span class="sxs-lookup"><span data-stu-id="77cc5-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Palveluobjektinäyte":::

1. <span data-ttu-id="77cc5-156">Palaa sovellusrekisteröinnin **Ohjelmointirajapinnan oikeuksiin**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="77cc5-157">Viimeistele sovelluksen rekisteröinti valitsemalla **Myönnä järjestelmänvalvojan hyväksyntä kohteelle...**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="77cc5-158">Lopuksi on vielä lisättävä sovellusrekisteröinnin nimi Customer Insightsin käyttäjänä.</span><span class="sxs-lookup"><span data-stu-id="77cc5-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="77cc5-159">Avaa Customer Insights, valitse **Hallinta** > **Käyttöoikeudet** ja valitse lopuksi **Lisää käyttäjä**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="77cc5-160">Hae sovellusrekisteröinnin nimi, valitse se hakutuloksissa ja valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="77cc5-161">Customer Insightsin asiakaskirjastot</span><span class="sxs-lookup"><span data-stu-id="77cc5-161">Customer Insights client libraries</span></span>

<span data-ttu-id="77cc5-162">Tässä osassa on tietoja Customer Insightsin ohjelmointirajapinnoissa käytettävissä olevien asiakaskirjastojen käytön aloittamisesta.</span><span class="sxs-lookup"><span data-stu-id="77cc5-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="77cc5-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="77cc5-163">C# NuGet</span></span>

<span data-ttu-id="77cc5-164">Lisätietoja NuGet.orgin C#-asiakaskirjastojen käytön aloittamisesta. Lisätietoja NuGet-paketista on kohdassa [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="77cc5-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="77cc5-165">Tällä hetkellä nämä paketit on tarkoitettu netstandard 2.0- ja netcoreapp 2.0-kehyksiin.</span><span class="sxs-lookup"><span data-stu-id="77cc5-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="77cc5-166">C#-asiakaskirjaston lisääminen C#-projektiin</span><span class="sxs-lookup"><span data-stu-id="77cc5-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="77cc5-167">Avaa Visual Studiossa projektin **NuGet Package Manager**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="77cc5-168">Tee hakua hakuehdolla **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="77cc5-169">Lisää paketti projektiin valitsemalla **Asenna**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="77cc5-170">Vaihtoehtoisesti voit suorittaa seuraavan komennon **NuGet Package Manager Consolessa**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="77cc5-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="NuGet-paketin lisääminen Visual Studio projektiin":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="77cc5-172">C#-asiakaskirjaston käyttäminen</span><span class="sxs-lookup"><span data-stu-id="77cc5-172">Use the C# client library</span></span>

1. <span data-ttu-id="77cc5-173">Hae `AccessToken` [MSAL (Microsoft Authentication Library) -kirjaston](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) avulla käyttämällä aiemmin luotua [Azure-sovelluksen rekisteröintiä](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="77cc5-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="77cc5-174">Kun tunnuksen todennus ja hankkiminen on tehty, luo uusi tai ota käyttöön aiemmin luotu `HttpClient` jossa **DefaultRequestHeaders "Authorization"**-lisäasetuksen arvona on **Haltijan <access token>** ja **Ocp-Apim-Subscription-Key**-määrityksenä on [Customer Insights -ympäristön **tilausavain**](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="77cc5-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="77cc5-175">Palauta **Valtuutus**-otsikko tarvittaessa.</span><span class="sxs-lookup"><span data-stu-id="77cc5-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="77cc5-176">Esimerkki: tunnus on vanhentunut.</span><span class="sxs-lookup"><span data-stu-id="77cc5-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="77cc5-177">Välitä tämä `HttpClient` `CustomerInsights`-asiakkaan muodostukseen.</span><span class="sxs-lookup"><span data-stu-id="77cc5-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Httpclient-näyte":::

1. <span data-ttu-id="77cc5-179">Tee asiakasohjelmasta kutsuja laajennusmenetelmiin, kuten `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="77cc5-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="77cc5-180">Jos taustalla olevaa `Microsoft.Rest.HttpOperationResponse`-käyttöä suositeen, käytä http-sanomamenetelmiä, kuten `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="77cc5-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="77cc5-181">Vastauksen tyyppi on todennäköisesti `object`, koska menetelmä voi palauttaa useita tyyppejä (kuten `IList<InstanceInfo>` ja `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="77cc5-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="77cc5-182">Voit tarkistaa palautustyypin tekemällä turvallisesti objektien tyyppimuunnokset kyseisen toiminnon [ohjelmointirajapinnan tietosivulla](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) määritettyihin vastaustyyppeihin.</span><span class="sxs-lookup"><span data-stu-id="77cc5-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="77cc5-183">Jos pyynnössä tarvitaan enemmän tietoja, käytä raakavastausobjektia **http-sanomamenetelmillä**.</span><span class="sxs-lookup"><span data-stu-id="77cc5-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>
