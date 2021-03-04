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
ms.openlocfilehash: 966db1a22e7dece1bcd89733880bce059151157f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267520"
---
# <a name="work-with-customer-insights-apis"></a>Customer Insights -ohjelmointirajapintojen käyttäminen

Dynamics 365 Customer Insightsissa on ohjelmointirajapintoja, joilla voi muodostaa omia Customer Insightsissa oleviin tietoihin perustuvia sovelluksia.

> [!IMPORTANT]
> Kyseisten ohjelmointirajapintojen tiedot ovat [Customer Insightsin ohjelmointirajapintojen viitteessä](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Niissä on lisätietoja toiminnoista, parametreista ja vastauksista.

Tässä artikkelissa on ohjeita Customer Insightsin ohjelmointirajapintojen käytöstä ja Azure-sovelluksen rekisteröinnin luonnista. Lisäksi siinä opastetaan käytettävissä olevien asiakasohjelmakirjastojen käytön aloittamisessa.

## <a name="get-started-trying-the-customer-insights-apis"></a>Customer Insightsin ohjelmistorajapintojen käytön kokeilemisen aloittaminen

1. [Kirjaudu](https://home.ci.ai.dynamics.com) Customer Insightsiin. Jos et ole vielä tehnyt tilausta, [rekisteröidy Customer Insightsin kokeiluversioon](https://aka.ms/tryci).

1. Ota ohjelmointirajapinnat käyttöön Customer Insights -ympäristössä valitsemalla **Hallinta** > **Käyttöoikeudet**. Sitä varten tarvitaan järjestelmänvalvojan oikeudet.

1. Siirry **Ohjelmointirajapinnat**-välilehteen ja valitse **Ota käyttöön** -painike.    
   Ohjelmointirajapintojen ottaminen käyttöön luo sen esiintymän ensisijaisen ja toissijaisen tilausavaimen, jota käytetään ohjelmointirajapintapyynnöissä. Voit luoda avaimet uudelleen valitsemalla **Luo ensisijainen uudelleen** tai **Luo toissijainen uudelleen**, kun olet valinnut ensin **Hallinta** > **Käyttöoikeudet** > **Ohjelmointirajapinnat**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insightsin ohjelmointirajapintojen ottaminen käyttöön":::

1. Kokeile ohjelmointirajapintoja valitsemalla **Tutustu ohjelmointirajapintoihin**.

1. Valitse ohjelmointirajapintatoiminto ja valitse sitten **Kokeile**.

1. Määritä sivuruudussa avattavan **Valtuutus**-valikon arvoksi **implisiittinen**. `Authorization`-otsikkoon lisätään haltijatunnus. Tilausavain täytetään automaattisesti.
  
1. Vaihtoehtoisesti voit lisätä kaikki tarvittavat kyselyparametrit.

1. Vieritä sivuruudun alareunaan ja valitse **Lähetä**.

HTTP-vastaus tulee pian näkyviin alapuolelle.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Uuden sovellusrekisteröinnin luominen Azure-portaalissa

Näiden ohjeiden avulla aloitetaan Customer Insightsin ohjelmointirajapintojen käyttö Azure-sovelluksessa delegoituja oikeuksia käyttämällä. Varmista, että olet suorittanut ensin [Aloittaminen-osan](#get-started-trying-the-customer-insights-apis) toimet.

1. Käytä [Azure-portaaliin](https://portal.azure.com) kirjautumiseen tiliä, jolla voi käyttää Customer Insightsin tietoja.

1. Valitse vasemmalla **Sovelluksen rekisteröinnit**.

1. Valitse **Uusi rekisteröinti**, anna sovelluksen nimi ja valitse tilityyppi.
   Voit lisätä myös uudelleenohjauksen URL-osoitteen (valinnainen). http://localhost on riittävä sovelluksen kehittämiseen paikallisessa tietokoneessa.

1. Valitse uudessa sovellusrekisteröinnissä **Ohjelmointirajapinnan oikeudet**.

1. Valitse **Lisää käyttöoikeus** ja valitse sitten sivuruudussa **Customer Insights**.

1. Valitse **Käyttöoikeustyyppi**-kohdassa **Delegoidut käyttöoikeudet** ja valitse sitten **user_impersonation**-oikeus.

1. Valitse **Lisää käyttöoikeudet**. Jos tarvitse ohjelmointirajapinnan käyttöoikeuden ilman käyttäjän kirjautumista, lisätietoja on osiossa [Palvelinten väliset sovelluksen käyttöoikeudet](#server-to-server-application-permissions).

1. Viimeistele sovelluksen rekisteröinti valitsemalla **Myönnä järjestelmänvalvojan hyväksyntä kohteelle...**.

Voit käyttää tämän sovelluksen rekisteröinnin sovellus- tai asiakastunnusta MSAL (Microsoft Authentication Library) -kirjastossa. Tällä tavoin saadaan pyynnön kanssa ohjelmointirajapintaan lähetettävä haltijatunnus.

Lisätietoja MSAL-kirjastosta on kohdassa [MSAL (Microsoft Authentication Library) -kirjaston yleiskatsaus](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

Lisätietoja sovelluksen rekisteröinnistä Azuressa on kohdassa [Azure-portaalin uusi sovelluksen rekisteröintikokemus](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).

Lisätietoja ohjelmointirajapintojen käyttämisestä asiakaskirjastojen kanssa on kohdassa [Customer Insightsin asiakaskirjastot](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Palvelinten väliset sovelluksen käyttöoikeudet

[Sovelluksen rekisteröintiä käsittelevässä osiossa](#create-a-new-app-registration-in-the-azure-portal) selvitetään sellaisen sovelluksen rekisteröintiä, johon käyttäjän on kirjauduttava todennusta varten. Lisätietoja sellaisen sovelluksen rekisteröinnin luomisesta, jossa ei tarvita käyttäjän toimia ja joka voidaan suorittaa palvelimessa.

1. Valitse Azure-portaalin sovelluksen rekisteröinnissä **Ohjelmointirajapinnan käyttöoikeudet**.

1. Valitse **Lisää käyttöoikeus** ja valitse sitten sivuruudussa **Customer Insights**.

1. Valitse **Käyttöoikeustyyppi**-kohdassa **Sovelluksen käyttöoikeudet** ja valitse sitten **CustomerInsights.Api.All**-oikeus.

1. Valitse **Lisää käyttöoikeudet**.

1. Järjestelmänvalvojan hyväksynnän antaminen tässä sovelluksen käyttöoikeudessa edellyttää palveluobjektin lisäämistä.

   1. Asenna Azure Active Directoryn (AD) PowerShell-moduuli: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Muodosta yhteys AD-tiliin: `Connect-AzureAD -TenantId <your tenant id>`. Voit etsiä vuokraajan tunnuksen valitsemalla **Yleiskuvaus** > **Azure Active Directory**.
   1. Lisää Azure AD -palveluobjekti suorittamalla seuraavan komento: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` AppId-parametri viittaa Customer Insightsin ohjelmointirajapintasovellukseen.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Palveluobjektinäyte":::

1. Palaa sovellusrekisteröinnin **Ohjelmointirajapinnan oikeuksiin**.

1. Viimeistele sovelluksen rekisteröinti valitsemalla **Myönnä järjestelmänvalvojan hyväksyntä kohteelle...**.

1. Lopuksi on vielä lisättävä sovellusrekisteröinnin nimi Customer Insightsin käyttäjänä.    
   Avaa Customer Insights, valitse **Hallinta** > **Käyttöoikeudet** ja valitse lopuksi **Lisää käyttäjä**.

1. Hae sovellusrekisteröinnin nimi, valitse se hakutuloksissa ja valitse **Tallenna**.

## <a name="customer-insights-client-libraries"></a>Customer Insightsin asiakaskirjastot

Tässä osassa on tietoja Customer Insightsin ohjelmointirajapinnoissa käytettävissä olevien asiakaskirjastojen käytön aloittamisesta.

### <a name="c-nuget"></a>C# NuGet

Lisätietoja NuGet.orgin C#-asiakaskirjastojen käytön aloittamisesta. Lisätietoja NuGet-paketista on kohdassa [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Tällä hetkellä nämä paketit on tarkoitettu netstandard 2.0- ja netcoreapp 2.0-kehyksiin.

#### <a name="add-the-c-client-library-to-a-c-project"></a>C#-asiakaskirjaston lisääminen C#-projektiin

1. Avaa Visual Studiossa projektin **NuGet Package Manager**.

1. Tee hakua hakuehdolla **Microsoft.Dynamics.CustomerInsights.Api**.

1. Lisää paketti projektiin valitsemalla **Asenna**.
   Vaihtoehtoisesti voit suorittaa seuraavan komennon **NuGet Package Manager Consolessa**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="NuGet-paketin lisääminen Visual Studio projektiin":::

#### <a name="use-the-c-client-library"></a>C#-asiakaskirjaston käyttäminen

1. Hae `AccessToken` [MSAL (Microsoft Authentication Library) -kirjaston](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) avulla käyttämällä aiemmin luotua [Azure-sovelluksen rekisteröintiä](#create-a-new-app-registration-in-the-azure-portal).

1. Kun tunnuksen todennus ja hankkiminen on tehty, luo uusi tai ota käyttöön aiemmin luotu `HttpClient` jossa **DefaultRequestHeaders "Authorization"**-lisäasetuksen arvona on **Haltijan <access token>** ja **Ocp-Apim-Subscription-Key**-määrityksenä on [Customer Insights -ympäristön **tilausavain**](#get-started-trying-the-customer-insights-apis).    
   Palauta **Valtuutus**-otsikko tarvittaessa. Esimerkki: tunnus on vanhentunut.

1. Välitä tämä `HttpClient` `CustomerInsights`-asiakkaan muodostukseen.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Httpclient-näyte":::

1. Tee asiakasohjelmasta kutsuja laajennusmenetelmiin, kuten `GetAllInstancesAsync`. Jos taustalla olevaa `Microsoft.Rest.HttpOperationResponse`-käyttöä suositeen, käytä http-sanomamenetelmiä, kuten `GetAllInstancesWithHttpMessagesAsync`.

1. Vastauksen tyyppi on todennäköisesti `object`, koska menetelmä voi palauttaa useita tyyppejä (kuten `IList<InstanceInfo>` ja `ApiErrorResult`). Voit tarkistaa palautustyypin tekemällä turvallisesti objektien tyyppimuunnokset kyseisen toiminnon [ohjelmointirajapinnan tietosivulla](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) määritettyihin vastaustyyppeihin.    
   Jos pyynnössä tarvitaan enemmän tietoja, käytä raakavastausobjektia **http-sanomamenetelmillä**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]