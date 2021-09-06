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
ms.openlocfilehash: 8404515a20529c00708d84813f3a022ad98c45362a2f1e68d7aa890d085071a9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033581"
---
# <a name="work-with-customer-insights-apis"></a>Customer Insights -ohjelmointirajapintojen käyttäminen

Dynamics 365 Customer Insights määrittää ohjelmointirajapinnat, jotta voit luoda omia sovelluksia Customer Insights -sovelluksen tietojen perusteella.

> [!IMPORTANT]
> Kyseisten ohjelmointirajapintojen tiedot ovat [Customer Insightsin ohjelmointirajapintojen viitteessä](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Niissä on lisätietoja toiminnoista, parametreista ja vastauksista.

Tässä artikkelissa kerrotaan Customer Insightsin ohjelmointirajapintojen käyttämisestä, Azure-sovelluksen rekisteröinnin luomisesta ja käytettävissä olevien asiakasohjelmakirjastojen käytön aloittamisesta.

## <a name="get-started-trying-the-customer-insights-apis"></a>Customer Insightsin ohjelmistorajapintojen käytön kokeilemisen aloittaminen

1. [Kirjaudu](https://home.ci.ai.dynamics.com) Customer Insightsiin. Jos et ole vielä tehnyt tilausta, [rekisteröidy Customer Insightsin kokeiluversioon](https://aka.ms/tryci).

1. Ota ohjelmointirajapinnat käyttöön Customer Insights -ympäristössä valitsemalla **Hallinta** > **Käyttöoikeudet**. Sitä varten tarvitaan järjestelmänvalvojan oikeudet.

1. Siirry **Ohjelmointirajapinnat**-välilehteen ja valitse **Ota käyttöön** -painike.    
 
   Ohjelmointirajapintojen ottaminen käyttöön luo sen esiintymän ensisijaisen ja toissijaisen tilausavaimen, jota käytetään ohjelmointirajapintapyynnöissä. Voit luoda avaimet uudelleen valitsemalla **Luo ensisijainen uudelleen** tai **Luo toissijainen uudelleen**, kun olet valinnut ensin **Hallinta** > **Käyttöoikeudet** > **Ohjelmointirajapinnat**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insightsin ohjelmointirajapintojen ottaminen käyttöön.":::

1. **Kokeile ohjelmointirajapintoja** valitsemalla [Tutustu ohjelmointirajapintoihin](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Valitse ohjelmointirajapintatoiminto ja valitse sitten **Kokeile**.

1. Määritä sivupaneelissa avattava **Valtuutus**-valikon arvoksi **Implisiittinen**. Otsikko `Authorization` lisätään haltijatunnukseen. Tilausavain täytetään automaattisesti.
  
1. Vaihtoehtoisesti voit lisätä kaikki tarvittavat kyselyparametrit.

1. Vieritä sivuruudun alareunaan ja valitse **Lähetä**.

HTTP-vastaus tulee pian näkyviin alapuolelle.

   :::image type="content" source="media/try-apis.gif" alt-text="Ohjelmointirajapintojen testaaminen.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Uuden sovellusrekisteröinnin luominen Azure-portaalissa

Näiden vaiheiden avulla voit aloittaa Customer Insightsin ohjelmointirajapintojen käyttämisen Azure-sovelluksessa delegoitujen oikeuksien avulla. Varmista, että [Aloittaminen-osa](#get-started-trying-the-customer-insights-apis) on tehty ensin.

1. Käytä [Azure-portaaliin](https://portal.azure.com) kirjautumiseen tiliä, jolla voi käyttää Customer Insightsin tietoja.

1. Valitse vasemmalla **Sovelluksen rekisteröinnit**.

1. Valitse **Uusi rekisteröinti**, anna sovelluksen nimi ja valitse tilityyppi.
 
   Voit lisätä myös uudelleenohjauksen URL-osoitteen (valinnainen). http://localhost on riittävä sovelluksen kehittämiseen paikallisessa tietokoneessa.

1. Valitse uudessa sovellusrekisteröinnissä **Ohjelmointirajapinnan oikeudet**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Ohjelmointirajapinnan oikeuksien määrittäminen sovelluksen rekisteröinnin yhteydessä.":::

1. Valitse **Lisää käyttöoikeus** ja valitse sitten sivuruudussa **Customer Insights**.

1. Valitse **Oikeustyyppi**-kohdassa **Delegoidut oikeudet**. Valitse lopuksi **user_impersonation**-oikeus.

1. Valitse **Lisää käyttöoikeudet**. Jos tarvitse ohjelmointirajapinnan käyttöoikeuden ilman käyttäjän kirjautumista, lisätietoja on osiossa [Palvelinten väliset sovelluksen käyttöoikeudet](#server-to-server-application-permissions).

1. Viimeistele sovelluksen rekisteröinti valitsemalla **Myönnä järjestelmänvalvojan hyväksyntä kohteelle...**.

Voit käyttää tämän sovelluksen rekisteröinnin sovellus- tai asiakastunnusta MSAL (Microsoft Authentication Library) -kirjastossa. Tällä tavoin saadaan pyynnön kanssa ohjelmointirajapintaan lähetettävä haltijatunnus.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Järjestelmänvalvojan suostumuksen myöntäminen.":::

Lisätietoja MSAL-kirjastosta on kohdassa [MSAL (Microsoft Authentication Library) -kirjaston yleiskatsaus](/azure/active-directory/develop/msal-overview).

Lisätietoja sovelluksen rekisteröimisestä Azuressa on kohdassa [Sovelluksen rekisteröiminen](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).

Lisätietoja ohjelmointirajapintojen käyttämisestä asiakasohjelmakirjastoissa on kohdassa [Customer Insightsin asiakasohjelmakirjastot](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Palvelinten väliset sovelluksen käyttöoikeudet

[Sovelluksen rekisteröintiä käsittelevässä osiossa](#create-a-new-app-registration-in-the-azure-portal) selvitetään sellaisen sovelluksen rekisteröintiä, johon käyttäjän on kirjauduttava todennusta varten. Lisätietoja sellaisen sovelluksen rekisteröinnin luomisesta, jossa ei tarvita käyttäjän toimia ja joka voidaan suorittaa palvelimessa.

1. Valitse Azure-portaalin sovelluksen rekisteröinnissä **Ohjelmointirajapinnan käyttöoikeudet**.

1. Valitse **Lisää oikeus**. 

1. Valitse **API-rajapinnat, joita organisaationi käyttää** -välilehti, ja valitse luettelosta **Dynamics 365 AI for Customer Insights**. 

1. Valitse **Oikeustyyppi**-kohdassa **Sovelluksen oikeudet**. Valitse lopuksi **CustomerInsights.Api.All**-oikeus.

1. Valitse **Lisää käyttöoikeudet**.

1. Palaa sovellusrekisteröinnin **Ohjelmointirajapinnan oikeuksiin**.

1. Viimeistele sovelluksen rekisteröinti valitsemalla **Myönnä järjestelmänvalvojan hyväksyntä kohteelle...**.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Järjestelmänvalvojan suostumuksen myöntäminen.":::

1. Lopuksi on vielä lisättävä sovellusrekisteröinnin nimi Customer Insightsin käyttäjänä.  
   
   Avaa Customer Insights, valitse **Hallinta** > **Käyttöoikeudet** ja valitse lopuksi **Lisää käyttäjä**.

1. Hae sovellusrekisteröinnin nimi, valitse se hakutuloksissa ja valitse **Tallenna**.

## <a name="customer-insights-client-libraries"></a>Customer Insightsin asiakaskirjastot

Tässä osassa on tietoja Customer Insightsin ohjelmointirajapinnoissa käytettävissä olevien asiakaskirjastojen käytön aloittamisesta. Kaikki kirjaston lähdekoodit ja näytesovellukset löytyvät [Customer Insights GitHub -sivulta](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Lisätietoja NuGet.orgin C#-asiakaskirjastojen käytön aloittamisesta. Lisätietoja NuGet-paketista on kohdassa [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Tällä hetkellä nämä paketit on tarkoitettu netstandard 2.0- ja netcoreapp 2.0-kehyksiin.

#### <a name="add-the-c-client-library-to-a-c-project"></a>C#-asiakaskirjaston lisääminen C#-projektiin

1. Avaa Visual Studiossa projektin **NuGet Package Manager**.

1. Tee hakua hakuehdolla **Microsoft.Dynamics.CustomerInsights.Api**.

1. Lisää paketti projektiin valitsemalla **Asenna**.
 
   Vaihtoehtoisesti voit suorittaa seuraavan komennon **NuGet Package Manager Consolessa**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="NuGet-paketin lisääminen Visual Studio projektiin.":::

#### <a name="use-the-c-client-library"></a>C#-asiakaskirjaston käyttäminen

1. Hae `AccessToken` [MSAL (Microsoft Authentication Library) -kirjaston](/azure/active-directory/develop/msal-overview) avulla käyttämällä aiemmin luotua [Azure-sovelluksen rekisteröintiä](#create-a-new-app-registration-in-the-azure-portal).

1. Kun tunnuksen todennus ja hankkiminen on tehty, luo uusi tai ota käyttöön aiemmin luotu `HttpClient` jossa **DefaultRequestHeaders "Authorization"**-lisäasetuksen arvona on **Haltijan <access token>** ja **Ocp-Apim-Subscription-Key**-määrityksenä on [Customer Insights -ympäristön **tilausavain**](#get-started-trying-the-customer-insights-apis).   
 
   Palauta **Valtuutus**-otsikko tarvittaessa. Esimerkki: tunnus on vanhentunut.

1. Välitä tämä `HttpClient` `CustomerInsights`-asiakkaan muodostukseen.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Httpclient-näyte.":::

1. Tee asiakasohjelmasta kutsuja laajennusmenetelmiin, esimerkiksi `GetAllInstancesAsync`. Jos taustalla oleva `Microsoft.Rest.HttpOperationResponse` on ensisijainen vaihtoehto, käytä http-sanomamenetelmiä, esimerkiksi `GetAllInstancesWithHttpMessagesAsync`.

1. Vastauksen tyyppi on todennäköisesti `object`, koska menetelmä voi palauttaa useita tyyppejä (kuten `IList<InstanceInfo>` ja `ApiErrorResult`). Voit tarkistaa palautustyypin tekemällä turvallisesti objektien tyyppimuunnokset kyseisen toiminnon [ohjelmointirajapinnan tietosivulla](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) määritettyihin vastaustyyppeihin.    
   
   Jos pyynnössä tarvitaan enemmän tietoja, käytä raakavastausobjektia **http-sanomamenetelmillä**.

### <a name="nodejs-package"></a>NodeJS-paketti

Käytä NodeJS-asiakaskirjastoja, jotka ovat käytettävissä NPM:n kautta: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python-paketti

Käytä Python-asiakaskirjastoja, jotka ovat käytettävissä PyPi:n kautta: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
