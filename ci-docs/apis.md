---
title: Customer Insights -ohjelmointirajapintojen käyttäminen
description: Ohjelmointirajapintojen käyttäminen ja tietoja niiden rajoituksista.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387336"
---
# <a name="work-with-customer-insights-apis"></a>Customer Insights -ohjelmointirajapintojen käyttäminen

Dynamics 365 Customer Insights määrittää ohjelmointirajapinnat, jotta voit luoda omia sovelluksia Customer Insights -sovelluksen tietojen perusteella.

> [!IMPORTANT]
> Kyseisten ohjelmointirajapintojen tiedot ovat [Customer Insightsin ohjelmointirajapintojen viitteessä](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Niissä on lisätietoja toiminnoista, parametreista ja vastauksista.

Kokeile Customer Insightsin ohjelmointirajapintoja, luo Azure-sovelluksen rekisteröinti ja aloita asiakaskirjastojen käyttö.

## <a name="get-started-trying-the-customer-insights-apis"></a>Customer Insightsin ohjelmistorajapintojen käytön kokeilemisen aloittaminen

Ota Customer Insights -ohjelmointirajapinnat käyttöön ja kokeile niitä. Customer Insights -järjestelmänvalvojan on otettava käyttöön Customer Insightsissa ohjelmointirajapinnan käyttöoikeus. Kun käyttöoikeus on otettu käyttöön, kuka tahansa käyttäjä voi käyttää ohjelmointirajapintaa tilausavaimen kanssa.

1. [Kirjaudu](https://home.ci.ai.dynamics.com) Customer Insightsiin. Jos et ole vielä tehnyt tilausta, [rekisteröidy Customer Insightsin kokeiluversioon](https://aka.ms/tryci).

1. Siirry kohtaan **Järjestelmänvalvoja** > **Suojaus** ja valitse **Ohjelmointirajapinnat**-välilehti.

1. Jos ympäristön ohjelmointirajapintaa ei ole määritetty, valitse **Ota käyttöön**.

   Ohjelmointirajapintojen ottaminen käyttöön luo sen esiintymän ensisijaisen ja toissijaisen tilausavaimen, jota käytetään ohjelmointirajapintapyynnöissä. Voit luoda avaimet uudelleen valitsemalla **Luo uudelleen ensisijainen** tai **Luo uudelleen toissijainen** **Ohjelmointirajapinnat**-välilehdessä.

1. Kokeile ohjelmointirajapintoja valitsemalla [**Tutustu ohjelmointirajapintoihin**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Hae ja valitse ohjelmointirajapintatoiminto ja valitse **Kokeile sitä**.

   :::image type="content" source="media/try-api.png" alt-text="Ohjelmointirajapintojen testaaminen.":::

1. Määritä sivupaneelissa avattava **Valtuutus**-valikon arvoksi **Implisiittinen**. Otsikko `Authorization` lisätään haltijatunnukseen. Tilausavain täytetään automaattisesti.
  
1. Vaihtoehtoisesti voit lisätä kaikki tarvittavat kyselyparametrit.

1. Vieritä sivuruudun alareunaan ja valitse **Lähetä**.

   HTTP-vastaus näkyy ruudun alareunassa.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Uuden sovellusrekisteröinnin luominen Azure-portaalissa

Luo uusi [sovellusrekisteröinti](/graph/auth-register-app-v2) käyttääksesi Customer Insightsin ohjelmointirajapintoja Azure-sovelluksessa delegoituja oikeuksia käyttämällä.

1. Suorita [Aloittaminen-osa](#get-started-trying-the-customer-insights-apis).

1. Käytä [Azure-portaaliin](https://portal.azure.com) kirjautumiseen tiliä, jolla voi käyttää Customer Insightsin tietoja.

1. Etsi ja valitse sitten **Sovellusrekisteröinnit**.

1. Valitse **Uusi rekisteröinti**, anna sovelluksen nimi ja valitse tilityyppi.

   Voit lisätä myös uudelleenohjauksen URL-osoitteen (valinnainen). http://localhost on riittävä sovelluksen kehittämiseen paikallisessa tietokoneessa.

1. Valitse **Rekisteröi**.

1. Valitse uudessa sovellusrekisteröinnissä **Ohjelmointirajapinnan oikeudet**.

1. Valitse sivuruudusta **Lisää oikeus** ja valitse sitten **Dynamics 365 AI for Customer Insights** .

1. Valitse **Oikeustyyppi**-kohdassa **Delegoidut oikeudet**. Valitse lopuksi **user_impersonation**-oikeus.

1. Valitse **Lisää käyttöoikeudet**.

1. Viimeistele sovelluksen rekisteröinti valitsemalla **Myönnä järjestelmänvalvojan hyväksyntä kohteelle...**.

1. Jos tarvitset ohjelmointirajapinnan käyttöoikeuden ilman käyttäjän kirjautumista, siirry osioon [Palvelinten väliset sovelluksen käyttöoikeudet](#server-to-server-application-permissions).

Voit käyttää tämän sovelluksen rekisteröinnin sovellus- tai asiakastunnusta [MSAL (Microsoft Authentication Library) -kirjastossa](/azure/active-directory/develop/msal-overview). Tällä tavoin saadaan pyynnön kanssa ohjelmointirajapintaan lähetettävä haltijatunnus.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Lisätietoja ohjelmointirajapintojen käyttämisestä asiakasohjelmakirjastoissa on kohdassa [Customer Insightsin asiakasohjelmakirjastot](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Palvelinten väliset sovelluksen käyttöoikeudet

Luo sovelluksen rekisteröinti, joka ei tarvitse käyttäjän vuorovaikutusta ja joka voidaan suorittaa palvelimessa.

1. Valitse Azure-portaalin sovelluksen rekisteröinnissä **Ohjelmointirajapinnan käyttöoikeudet**.

1. Valitse **Lisää oikeus**.

1. Valitse **API-rajapinnat, joita organisaationi käyttää** -välilehti, ja valitse luettelosta **Dynamics 365 AI for Customer Insights**.

1. Valitse **Oikeustyyppi**-kohdassa **Sovelluksen oikeudet**. Valitse lopuksi **CustomerInsights.Api.All**-oikeus.

1. Valitse **Lisää käyttöoikeudet**.

1. Palaa sovellusrekisteröinnin **Ohjelmointirajapinnan oikeuksiin**.

1. Viimeistele sovelluksen rekisteröinti valitsemalla **Myönnä järjestelmänvalvojan hyväksyntä kohteelle...**.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Lisää sovellusrekisteröinnin nimi Customer Insightsin käyttäjänä.

   1. Avaa Customer Insights, valitse **Järjestelmänvalvoja** > **suojaus** ja valitse **Lisää käyttäjiä**.

   1. Hae sovellusrekisteröinnin nimi, valitse se hakutuloksissa ja valitse **Tallenna**.

## <a name="sample-queries"></a>Näytekyselyt

Lyhyt OData-näytekyselyiden luettelo ohjelmointirajapinnan kanssa toimimiseksi: [OData-kyselyesimerkit](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Customer Insightsin asiakaskirjastot

Tietoja Customer Insightsin ohjelmointirajapinnoissa käytettävissä olevien asiakaskirjastojen käytön aloittamisesta. Kaikki kirjaston lähdekoodit ja näytesovellukset löytyvät [Customer Insights GitHub -sivulta](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Käytä C#-asiakaskirjastoja osoitteesta NuGet.org. Tällä hetkellä nämä paketit on tarkoitettu netstandard 2.0- ja netcoreapp 2.0-kehyksiin. Lisätietoja NuGet-paketista on kohdassa [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>C#-asiakaskirjaston lisääminen C#-projektiin

1. Avaa Visual Studiossa projektin **NuGet Package Manager**.

1. Tee hakua hakuehdolla **Microsoft.Dynamics.CustomerInsights.Api**.

1. Lisää paketti projektiin valitsemalla **Asenna**.

   Vaihtoehtoisesti voit suorittaa seuraavan komennon **NuGet Package Manager Consolessa**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>C#-asiakaskirjaston käyttäminen

1. Hae `AccessToken` [MSAL (Microsoft Authentication Library) -kirjaston](/azure/active-directory/develop/msal-overview) avulla käyttämällä aiemmin luotua [Azure-sovelluksen rekisteröintiä](#create-a-new-app-registration-in-the-azure-portal).

1. Kun todennus on tehty ja tunnus hankittu onnistuneesti, muodosta uusi tai käytä aiemmin luotua `HttpClient`-asiakasta, jossa on lisäksi **DefaultRequestHeaders "Authorization"** -arvoksi asetettu **Bearer "access token"** ja **Ocp-Apim-Subscription-Key** -arvoksi asetettu [**tilaustunnus** Customer Insights -ympäristöstäsi](#get-started-trying-the-customer-insights-apis).   

   Palauta **Valtuutus**-otsikko tarvittaessa. Esimerkki: tunnus on vanhentunut.

1. Välitä tämä `HttpClient` `CustomerInsights`-asiakkaan muodostukseen.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Tee asiakasohjelmasta kutsuja laajennusmenetelmiin, kuten `GetAllInstancesAsync`. Jos taustalla oleva `Microsoft.Rest.HttpOperationResponse` on ensisijainen vaihtoehto, käytä http-sanomamenetelmiä, esimerkiksi `GetAllInstancesWithHttpMessagesAsync`.

1. Vastauksen tyyppi on todennäköisesti `object`, koska menetelmä voi palauttaa useita tyyppejä (kuten `IList<InstanceInfo>` ja `ApiErrorResult`). Voit tarkistaa palautustyypin käyttämällä objekteja toiminnon [ohjelmointirajapinnan tietosivulla](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) määritetyissä vastaustyypeissä.

   Jos pyynnössä tarvitaan enemmän tietoja, käytä raakavastausobjektia **http-sanomamenetelmillä**.

### <a name="nodejs-package"></a>NodeJS-paketti

Käytä NodeJS-asiakaskirjastoja, jotka ovat käytettävissä NPM:n kautta: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python-paketti

Käytä Python-asiakaskirjastoja, jotka ovat käytettävissä PyPi:n kautta: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
