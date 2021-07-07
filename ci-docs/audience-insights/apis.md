---
title: Ohjelmointirajapintojen käsitteleminen
description: Ohjelmointirajapintojen käyttäminen ja tietoja niiden rajoituksista.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304738"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="b67c9-103">Customer Insights -ohjelmointirajapintojen käyttäminen</span><span class="sxs-lookup"><span data-stu-id="b67c9-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="b67c9-104">Dynamics 365 Customer Insights määrittää ohjelmointirajapinnat, jotta voit luoda omia sovelluksia Customer Insights -sovelluksen tietojen perusteella.</span><span class="sxs-lookup"><span data-stu-id="b67c9-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b67c9-105">Kyseisten ohjelmointirajapintojen tiedot ovat [Customer Insightsin ohjelmointirajapintojen viitteessä](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="b67c9-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="b67c9-106">Niissä on lisätietoja toiminnoista, parametreista ja vastauksista.</span><span class="sxs-lookup"><span data-stu-id="b67c9-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="b67c9-107">Tässä artikkelissa kerrotaan Customer Insightsin ohjelmointirajapintojen käyttämisestä, Azure-sovelluksen rekisteröinnin luomisesta ja käytettävissä olevien asiakasohjelmakirjastojen käytön aloittamisesta.</span><span class="sxs-lookup"><span data-stu-id="b67c9-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="b67c9-108">Customer Insightsin ohjelmistorajapintojen käytön kokeilemisen aloittaminen</span><span class="sxs-lookup"><span data-stu-id="b67c9-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="b67c9-109">[Kirjaudu](https://home.ci.ai.dynamics.com) Customer Insightsiin.</span><span class="sxs-lookup"><span data-stu-id="b67c9-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="b67c9-110">Jos et ole vielä tehnyt tilausta, [rekisteröidy Customer Insightsin kokeiluversioon](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="b67c9-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="b67c9-111">Ota ohjelmointirajapinnat käyttöön Customer Insights -ympäristössä valitsemalla **Hallinta** > **Käyttöoikeudet**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="b67c9-112">Sitä varten tarvitaan järjestelmänvalvojan oikeudet.</span><span class="sxs-lookup"><span data-stu-id="b67c9-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="b67c9-113">Siirry **Ohjelmointirajapinnat**-välilehteen ja valitse **Ota käyttöön** -painike.</span><span class="sxs-lookup"><span data-stu-id="b67c9-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="b67c9-114">Ohjelmointirajapintojen ottaminen käyttöön luo sen esiintymän ensisijaisen ja toissijaisen tilausavaimen, jota käytetään ohjelmointirajapintapyynnöissä.</span><span class="sxs-lookup"><span data-stu-id="b67c9-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="b67c9-115">Voit luoda avaimet uudelleen valitsemalla **Luo ensisijainen uudelleen** tai **Luo toissijainen uudelleen**, kun olet valinnut ensin **Hallinta** > **Käyttöoikeudet** > **Ohjelmointirajapinnat**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insightsin ohjelmointirajapintojen ottaminen käyttöön":::

1. <span data-ttu-id="b67c9-117">**Kokeile ohjelmointirajapintoja** valitsemalla [Tutustu ohjelmointirajapintoihin](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="b67c9-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="b67c9-118">Valitse ohjelmointirajapintatoiminto ja valitse sitten **Kokeile**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="b67c9-119">Määritä sivupaneelissa avattava **Valtuutus**-valikon arvoksi **Implisiittinen**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="b67c9-120">Otsikko `Authorization` lisätään haltijatunnukseen.</span><span class="sxs-lookup"><span data-stu-id="b67c9-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="b67c9-121">Tilausavain täytetään automaattisesti.</span><span class="sxs-lookup"><span data-stu-id="b67c9-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="b67c9-122">Vaihtoehtoisesti voit lisätä kaikki tarvittavat kyselyparametrit.</span><span class="sxs-lookup"><span data-stu-id="b67c9-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="b67c9-123">Vieritä sivuruudun alareunaan ja valitse **Lähetä**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="b67c9-124">HTTP-vastaus tulee pian näkyviin alapuolelle.</span><span class="sxs-lookup"><span data-stu-id="b67c9-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="Ohjelmointirajapintojen testaaminen.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="b67c9-126">Uuden sovellusrekisteröinnin luominen Azure-portaalissa</span><span class="sxs-lookup"><span data-stu-id="b67c9-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="b67c9-127">Näiden vaiheiden avulla voit aloittaa Customer Insightsin ohjelmointirajapintojen käyttämisen Azure-sovelluksessa delegoitujen oikeuksien avulla.</span><span class="sxs-lookup"><span data-stu-id="b67c9-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="b67c9-128">Varmista, että [Aloittaminen-osa](#get-started-trying-the-customer-insights-apis) on tehty ensin.</span><span class="sxs-lookup"><span data-stu-id="b67c9-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="b67c9-129">Käytä [Azure-portaaliin](https://portal.azure.com) kirjautumiseen tiliä, jolla voi käyttää Customer Insightsin tietoja.</span><span class="sxs-lookup"><span data-stu-id="b67c9-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="b67c9-130">Valitse vasemmalla **Sovelluksen rekisteröinnit**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="b67c9-131">Valitse **Uusi rekisteröinti**, anna sovelluksen nimi ja valitse tilityyppi.</span><span class="sxs-lookup"><span data-stu-id="b67c9-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="b67c9-132">Voit lisätä myös uudelleenohjauksen URL-osoitteen (valinnainen).</span><span class="sxs-lookup"><span data-stu-id="b67c9-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="b67c9-133">http://localhost on riittävä sovelluksen kehittämiseen paikallisessa tietokoneessa.</span><span class="sxs-lookup"><span data-stu-id="b67c9-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="b67c9-134">Valitse uudessa sovellusrekisteröinnissä **Ohjelmointirajapinnan oikeudet**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Ohjelmointirajapinnan oikeuksien määrittäminen sovelluksen rekisteröinnin yhteydessä.":::

1. <span data-ttu-id="b67c9-136">Valitse **Lisää käyttöoikeus** ja valitse sitten sivuruudussa **Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="b67c9-137">Valitse **Oikeustyyppi**-kohdassa **Delegoidut oikeudet**. Valitse lopuksi **user_impersonation**-oikeus.</span><span class="sxs-lookup"><span data-stu-id="b67c9-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="b67c9-138">Valitse **Lisää käyttöoikeudet**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-138">Select **Add permissions**.</span></span> <span data-ttu-id="b67c9-139">Jos tarvitse ohjelmointirajapinnan käyttöoikeuden ilman käyttäjän kirjautumista, lisätietoja on osiossa [Palvelinten väliset sovelluksen käyttöoikeudet](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="b67c9-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="b67c9-140">Viimeistele sovelluksen rekisteröinti valitsemalla **Myönnä järjestelmänvalvojan hyväksyntä kohteelle...**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="b67c9-141">Voit käyttää tämän sovelluksen rekisteröinnin sovellus- tai asiakastunnusta MSAL (Microsoft Authentication Library) -kirjastossa. Tällä tavoin saadaan pyynnön kanssa ohjelmointirajapintaan lähetettävä haltijatunnus.</span><span class="sxs-lookup"><span data-stu-id="b67c9-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Järjestelmänvalvojan suostumuksen myöntäminen.":::

<span data-ttu-id="b67c9-143">Lisätietoja MSAL-kirjastosta on kohdassa [MSAL (Microsoft Authentication Library) -kirjaston yleiskatsaus](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="b67c9-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="b67c9-144">Lisätietoja sovelluksen rekisteröimisestä Azuressa on kohdassa [Sovelluksen rekisteröiminen](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span><span class="sxs-lookup"><span data-stu-id="b67c9-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="b67c9-145">Lisätietoja ohjelmointirajapintojen käyttämisestä asiakasohjelmakirjastoissa on kohdassa [Customer Insightsin asiakasohjelmakirjastot](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="b67c9-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="b67c9-146">Palvelinten väliset sovelluksen käyttöoikeudet</span><span class="sxs-lookup"><span data-stu-id="b67c9-146">Server-to-server application permissions</span></span>

<span data-ttu-id="b67c9-147">[Sovelluksen rekisteröintiä käsittelevässä osiossa](#create-a-new-app-registration-in-the-azure-portal) selvitetään sellaisen sovelluksen rekisteröintiä, johon käyttäjän on kirjauduttava todennusta varten.</span><span class="sxs-lookup"><span data-stu-id="b67c9-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="b67c9-148">Lisätietoja sellaisen sovelluksen rekisteröinnin luomisesta, jossa ei tarvita käyttäjän toimia ja joka voidaan suorittaa palvelimessa.</span><span class="sxs-lookup"><span data-stu-id="b67c9-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="b67c9-149">Valitse Azure-portaalin sovelluksen rekisteröinnissä **Ohjelmointirajapinnan käyttöoikeudet**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="b67c9-150">Valitse **Lisää oikeus**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="b67c9-151">Valitse **API-rajapinnat, joita organisaationi käyttää** -välilehti, ja valitse luettelosta **Dynamics 365 AI for Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="b67c9-152">Valitse **Oikeustyyppi**-kohdassa **Sovelluksen oikeudet**. Valitse lopuksi **CustomerInsights.Api.All**-oikeus.</span><span class="sxs-lookup"><span data-stu-id="b67c9-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="b67c9-153">Valitse **Lisää käyttöoikeudet**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="b67c9-154">Palaa sovellusrekisteröinnin **Ohjelmointirajapinnan oikeuksiin**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="b67c9-155">Viimeistele sovelluksen rekisteröinti valitsemalla **Myönnä järjestelmänvalvojan hyväksyntä kohteelle...**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Järjestelmänvalvojan suostumuksen myöntäminen.":::

1. <span data-ttu-id="b67c9-157">Lopuksi on vielä lisättävä sovellusrekisteröinnin nimi Customer Insightsin käyttäjänä.</span><span class="sxs-lookup"><span data-stu-id="b67c9-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="b67c9-158">Avaa Customer Insights, valitse **Hallinta** > **Käyttöoikeudet** ja valitse lopuksi **Lisää käyttäjä**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="b67c9-159">Hae sovellusrekisteröinnin nimi, valitse se hakutuloksissa ja valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="b67c9-160">Customer Insightsin asiakaskirjastot</span><span class="sxs-lookup"><span data-stu-id="b67c9-160">Customer Insights client libraries</span></span>

<span data-ttu-id="b67c9-161">Tässä osassa on tietoja Customer Insightsin ohjelmointirajapinnoissa käytettävissä olevien asiakaskirjastojen käytön aloittamisesta.</span><span class="sxs-lookup"><span data-stu-id="b67c9-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="b67c9-162">Kaikki kirjaston lähdekoodit ja näytesovellukset löytyvät [Customer Insights GitHub -sivulta](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="b67c9-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="b67c9-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="b67c9-163">C# NuGet</span></span>

<span data-ttu-id="b67c9-164">Lisätietoja NuGet.orgin C#-asiakaskirjastojen käytön aloittamisesta. Lisätietoja NuGet-paketista on kohdassa [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="b67c9-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="b67c9-165">Tällä hetkellä nämä paketit on tarkoitettu netstandard 2.0- ja netcoreapp 2.0-kehyksiin.</span><span class="sxs-lookup"><span data-stu-id="b67c9-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="b67c9-166">C#-asiakaskirjaston lisääminen C#-projektiin</span><span class="sxs-lookup"><span data-stu-id="b67c9-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="b67c9-167">Avaa Visual Studiossa projektin **NuGet Package Manager**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="b67c9-168">Tee hakua hakuehdolla **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="b67c9-169">Lisää paketti projektiin valitsemalla **Asenna**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="b67c9-170">Vaihtoehtoisesti voit suorittaa seuraavan komennon **NuGet Package Manager Consolessa**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="b67c9-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="NuGet-paketin lisääminen Visual Studio projektiin":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="b67c9-172">C#-asiakaskirjaston käyttäminen</span><span class="sxs-lookup"><span data-stu-id="b67c9-172">Use the C# client library</span></span>

1. <span data-ttu-id="b67c9-173">Hae `AccessToken` [MSAL (Microsoft Authentication Library) -kirjaston](/azure/active-directory/develop/msal-overview) avulla käyttämällä aiemmin luotua [Azure-sovelluksen rekisteröintiä](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="b67c9-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="b67c9-174">Kun tunnuksen todennus ja hankkiminen on tehty, luo uusi tai ota käyttöön aiemmin luotu `HttpClient` jossa **DefaultRequestHeaders "Authorization"**-lisäasetuksen arvona on **Haltijan <access token>** ja **Ocp-Apim-Subscription-Key**-määrityksenä on [Customer Insights -ympäristön **tilausavain**](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="b67c9-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="b67c9-175">Palauta **Valtuutus**-otsikko tarvittaessa.</span><span class="sxs-lookup"><span data-stu-id="b67c9-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="b67c9-176">Esimerkki: tunnus on vanhentunut.</span><span class="sxs-lookup"><span data-stu-id="b67c9-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="b67c9-177">Välitä tämä `HttpClient` `CustomerInsights`-asiakkaan muodostukseen.</span><span class="sxs-lookup"><span data-stu-id="b67c9-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Httpclient-näyte":::

1. <span data-ttu-id="b67c9-179">Tee asiakasohjelmasta kutsuja laajennusmenetelmiin, esimerkiksi `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="b67c9-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="b67c9-180">Jos taustalla oleva `Microsoft.Rest.HttpOperationResponse` on ensisijainen vaihtoehto, käytä http-sanomamenetelmiä, esimerkiksi `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="b67c9-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="b67c9-181">Vastauksen tyyppi on todennäköisesti `object`, koska menetelmä voi palauttaa useita tyyppejä (kuten `IList<InstanceInfo>` ja `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="b67c9-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="b67c9-182">Voit tarkistaa palautustyypin tekemällä turvallisesti objektien tyyppimuunnokset kyseisen toiminnon [ohjelmointirajapinnan tietosivulla](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) määritettyihin vastaustyyppeihin.</span><span class="sxs-lookup"><span data-stu-id="b67c9-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="b67c9-183">Jos pyynnössä tarvitaan enemmän tietoja, käytä raakavastausobjektia **http-sanomamenetelmillä**.</span><span class="sxs-lookup"><span data-stu-id="b67c9-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="b67c9-184">NodeJS-paketti</span><span class="sxs-lookup"><span data-stu-id="b67c9-184">NodeJS package</span></span>

<span data-ttu-id="b67c9-185">Käytä NodeJS-asiakaskirjastoja, jotka ovat käytettävissä NPM:n kautta: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="b67c9-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="b67c9-186">Python-paketti</span><span class="sxs-lookup"><span data-stu-id="b67c9-186">Python package</span></span>

<span data-ttu-id="b67c9-187">Käytä Python-asiakaskirjastoja, jotka ovat käytettävissä PyPi:n kautta: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="b67c9-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
