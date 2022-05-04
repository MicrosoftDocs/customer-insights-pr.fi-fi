---
title: Ympäristöjen luominen Customer Insightsissa
description: Ympäristöjen luomisen vaiheet lisensoidulla Dynamics 365 Customer Insights -tilauksella.
ms.date: 04/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0efda9d2997bcfd069b6d2445b69d159d7d3e59b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646038"
---
# <a name="create-an-environment-in-customer-insights"></a>Ympäristöjen luominen Customer Insightsissa

Tässä artikkelissa kerrotaan, miten luodaan uusi ympäristö sen jälkeen, kun organisaatio on ostanut Dynamics 365 Customer Insights -tilauksen. 

Organisaatiot voivat luoda useita ympäristöjä jokaiselle Customer Insights -käyttöoikeudelle. Jos organisaatiosi ostaa enemmän kuin yhden lisenssin, [ota yhteyttä tukihenkilöstöömme](https://go.microsoft.com/fwlink/?linkid=2079641), jotta käytössä olevien ympäristöjen määrää voidaan lisätä. Lisätietoja kapasiteetista ja lisäkapasiteetista on [Dynamics 365:n käyttöoikeusoppaassa](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Jos haluat kokeilla palvelua, katso kohta [Kokeiluympäristön määrittäminen](trial-signup.md).

## <a name="create-a-new-environment"></a>Luo uusi ympäristö

Kun olet ostanut Customer Insights -tilauksen käyttöoikeuden, Microsoft 365 -vuokraajan Järjestelmänvalvoja saa sähköpostiviestin, joka kutsuu hänet luomaan ympäristön. Mene osoitteeseen [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) aloittaaksesi. 

Ohjatun käyttökokemuksen avulla voit kerätä kaikki uuteen ympäristöön tarvittavat tiedot. Tarvitset [järjestelmänvalvojan oikeudet](permissions.md) Customer Insightsissa, jotta voit luoda ja hallita ympäristöjä.

1. Avaa ympäristönvalitsin ja valitse **+ Uusi**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Valitse ympäristön valitsin.":::

1. Noudata seuraavissa osissa kuvattua ohjattua kokemusta.

### <a name="step-1-provide-environment-information"></a>Vaihe 1: Anna ympäristön tiedot

Valitse **Perustiedot**-vaiheessa, haluatko luoda ympäristön alusta asti vai [kopioida tiedot toisesta ympäristöstä](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Valintaikkuna uuden ympäristön luomisesta Customer Insightsiin.":::

Anna seuraavat tiedot:
   - **Nimi**: Ympäristön nimi. Tämä kenttä on jo täytetty, jos kopioit tietoja aiemmin luodusta ympäristöstä, mutta voit muuttaa sitä.
   - **Valitse yritys**: Valitse uuden ympäristön ensisijainen käyttäjäryhmä. Kyse voi yksittäistä kuluttajista (kuluttajakauppa) tai [yritystilistä](work-with-business-accounts.md) (yritystenvälinen kauppa).
   - **Tyyppi**: Määritä, haluatko luoda tuotanto- vai eristysympäristön. Eristysympäristöt eivät salli ajoitettua tietojen päivittämistä, ja ne on tarkoitettu esikäyttöä ja testausta varten. Eristysympäristöt käyttävät samaa ensisijaista käyttäjäryhmää kuin valittu tuotantoympäristö.
   - **Alue**: Alue, jossa palvelu otetaan käyttöön ja jossa sitä isännöidään.

### <a name="step-2-configure-data-storage"></a>Vaihe 2: Määritä tietojen tallennustila

Valitse **Tietojen tallennustila** -vaiheessa, mihin tiedot Customer Insightsin tiedot tallennetaan.

Käytettävissä on kaksi vaihtoehtoa: **Customer Insights -tallennustila** (Customer Insights -ryhmän hallitsema Azure Data Lake -ratkaisu) ja **Azure Data Lake Storage** (oma Azure Data Lake Storage). Oletusarvoisesi Customer Insights -tallennustila -vaihtoehto on valittu.

:::image type="content" source="media/data-storage-environment.png" alt-text="Valitse Azure Data Lake Storage tietojen tallentamiseksi.":::

Kun tiedot tallennetaan Azure Data Lake Storageen, hyväksyt, että tiedot siirretään ja tiedot tallennetaan tämän Azure-tallennustilin maantieteellisen sijainnin mukaisesti. Sijainti voi olla eri kuin se, mihin tiedot tallennetaan Dynamics 365 Customer Insightsissa. Lisätietoja löytyy [Microsoftin luottamuskeskuksesta](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights tukee tällä hetkellä seuraavia:
> - Käytetyt entiteetit Power BI -tiedonkuluista, jotka tallennetaan Microsoft Dataversen hallinnoimaan Data Lakeen.  
> - Azure Data Lake Storage -tilit samasta Azure-alueesta, jonka valitsit ympäristöä luotaessa.
> - Azure Data Lake Storage -tilit, jotka ovat Gen2 ja joissa *hierarkkinen nimitila* on otettu käyttöön. Azure Data Lake Gen1 -tallennustilejä ei tueta.

Voit valita Azure Data Lake Storage -asetukselle resurssi- tai tilausperustaisen asetuksen todentamista varten. Lisätietoja on kohdassa [Yhteyden muodostaminen Azure Data Lake Storage -tiliin Azure-palvelun päänimen avulla](connect-service-principal.md). Säilöllä, jonka nimi on `customerinsights`, on oltava tallennustili.

Kun järjestelmäprosessit, kuten tietojen käsittely, ovat valmiit, järjestelmä luo vastaavat kansiot määrittämällesi tallennustilille. Datatiedostot ja *model.json*-tiedostot luodaan ja lisätään kansioihin prosessin nimen perusteella.

Jos luot useita Customer Insights -ympäristöjä ja päätät tallentaa näiden ympäristöjen tuloste-entiteetit tallennustilillesi, Customer Insights luo erilliset kansiot kullekin ympäristölle ja `ci_environmentID`-tunnuksen säilöön.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Vaihe 3: Muodosta yhteys Microsoft Dataverseen
   
Tässä **Microsoft Dataverse** -vaiheessa voit yhdistää Customer Insightsin Dataverse-ympäristöösi.

Tarjoa oma Microsoft Dataverse -ympäristösi tietojen (profiilien ja tietojen) jakamiseksi Dataverseen perustuviin liiketoimintasovelluksiin, kuten Dynamics 365 Marketingiin tai mallipohjaisiin sovelluksiin Power Appsissa. Jätä tämä kenttä tyhjäksi, jos sinulla ei ole omaa Dataverse -ympäristöä, jolloin valmistelemme sellaisen sinulle.

Kun muodostat yhteyden Dataverse-ympäristöön, voit myös [käsitellä tietoja paikallisista tietolähteistä Power Platform -tietovirtojen ja -yhdyskäytävien avulla](data-sources.md#add-data-from-on-premises-data-sources). Voit myös käyttää [käyttövalmiita ennustemalleja](predictions-overview.md?tabs=b2c#out-of-box-models) muodostamalla yhteyden Dataverse-ympäristöön.

> [!IMPORTANT]
> 1. Customer Insightsin ja Dataversen on oltava samalla alueella, jotta tietojen jakaminen voidaan ottaa käyttöön.
> 1. Dataverse-ympäristössä on oltava yleisen järjestelmänvalvojan rooli. Tarkista, onko tämä [Dataverse-ympäristö liitetty](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) tiettyihin käyttöoikeusryhmiin, ja varmista, että sinut on lisätty näihin käyttöoikeusryhmiin.
> 1. Tähän Dataverse-ympäristöön ei ole jo aiemmin liitetty Customer Insights -ympäristöä. Opettele poistamaan [aiemmin luotu yhteys Dataverse-ympäristöön](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="tietojen jakaminen Microsoft Dataversen kanssa automaattisesti käytössä uusille esiintymille.":::

Lisätietoja tietojen jakamisen ottamisesta käyttöön Microsoft Dataversen kanssa omasta Azure Data Lake Storagesta on ohjeaiheessa [Yhteyden muodostaminen Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse).

Customer Insights ei tue seuraavia tietojen jakamisen skenaarioita:
- Jos otat käyttöön tietojen jakamisen Dataversen kanssa, et voi [luoda ennustettuja tai puuttuvia arvoja entiteetissä](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Vaihe 4: Viimeistele asetukset

Käy **Tarkista**-vaiheessa läpi kaikki määritetyt asetukset. Kun kaikki näyttää valmiilta, valitse **Luo** asentaaksesi ympäristön. 

Voit myös muuttaa useimpia asetuksia myöhemmin. Lisätietoja on kohdassa [Ympäristöjen hallinta](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Käytä uutta ympäristöäsi

Seuraaviin artikkeleihin tutustuminen auttaa aloittamaan Customer Insightsin määrittämisen: 

- [Lisää käyttäjiä ja määritä käyttöoikeuksia](permissions.md).
- [Käytä tietolähteitäsi](data-sources.md) ja suorita ne [tietojen yhdistämisprosessin](data-unification.md) avulla [yhtenäisten asiakasprofiilien](customer-profiles.md) aikaansaamiseksi.
- [Rikastuta yhtenäisiä asiakasprofiileja](enrichment-hub.md) tai [suorita ennustavia malleja](predictions-overview.md).
- [Segmenttien](segments.md) luominen asiakkaiden ryhmittelyä varten ja [mittojen](measures.md) luominen tunnuslukujen arviointia varten.
- Määritä [yhteydet](connections.md) ja [vienti](export-destinations.md), jotta voit käsitellä tietojen alijoukkoja muissa sovelluksissa.
