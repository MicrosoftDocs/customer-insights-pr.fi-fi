---
title: Ympäristöjen luominen Customer Insightsissa
description: Ympäristöjen luomisen vaiheet lisensoidulla Dynamics 365 Customer Insights -tilauksella.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 914af46d2d82f3556d149f2836680c902f826d50
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673387"
---
# <a name="create-an-environment-in-audience-insights"></a>Ympäristöjen luominen käyttäjäryhmän merkityksellisissä tiedoissa

Tässä artikkelissa kerrotaan, miten luodaan uusi ympäristö sen jälkeen, kun organisaatio on ostanut Dynamics 365 Customer Insights -tilauksen. 

Organisaatiot voivat luoda *kaksi* ympäristöä jokaista Customer Insights -käyttöoikeutta varten. Jos organisaatiosi ostaa enemmän kuin yhden lisenssin, [ota yhteyttä tukihenkilöstöömme](https://go.microsoft.com/fwlink/?linkid=2079641), jotta käytössä olevien ympäristöjen määrää voidaan lisätä. Saat lisätietoja kapasiteetista ja lisäkapasiteetista lataamalla [Dynamics 365 -käyttöoikeusoppaan](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Jos haluat kokeilla palvelua, katso kohta [Kokeiluympäristön määrittäminen](../trial-signup.md).

## <a name="create-a-new-environment"></a>Luo uusi ympäristö

Kun asiakas on hankkinut tilauslisenssin Customer Insightsiin, Microsoft 365 -vuokraajan yleinen järjestelmänvalvoja saa sähköpostiviestin, jossa häntä kehotetaan luomaan ympäristö. Mene osoitteeseen [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) aloittaaksesi. 

Ohjatun käyttökokemuksen avulla voit kerätä kaikki uuteen ympäristöön tarvittavat tiedot. Tarvitset [järjestelmänvalvojan oikeudet](permissions.md) käyttäjäryhmän merkityksellisissä tiedoissa, jotta voit luoda ja hallita ympäristöjä.

1. Avaa käyttäjäryhmän merkityksellisissä tiedoissa ympäristön valitsin ja valitse **+ Uusi**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Valitse ympäristön valitsin.":::

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

Valitse **Tietojen tallennustila** -vaiheessa, mihin tiedot käyttäjäryhmän merkityksellisistä tiedoista tallennetaan.

Käytettävissä on kaksi vaihtoehtoa: **Customer Insights -tallennustila** (Customer Insights -ryhmän hallitsema Azure Data Lake -ratkaisu) ja **Azure Data Lake Storage** (oma Azure Data Lake Storage). Oletusarvoisesi Customer Insights -tallennustila -vaihtoehto on valittu.

:::image type="content" source="media/data-storage-environment.png" alt-text="Valitse se Azure Data Lake Storage, johon tiedot käyttäjäryhmän merkityksellisistä tiedoista tallennetaan.":::

Kun tiedot tallennetaan Azure Data Lake Storageen, hyväksyt, että tiedot siirretään ja tiedot tallennetaan tämän Azure-tallennustilin maantieteellisen sijainnin mukaisesti. Sijainti voi olla eri kuin se, mihin tiedot tallennetaan Dynamics 365 Customer Insightsissa. Lisätietoja löytyy [Microsoftin luottamuskeskuksesta](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights tukee tällä hetkellä seuraavia:
> - Käytetyt entiteetit Power BI -tiedonkuluista, jotka tallennetaan Microsoft Dataversen hallinnoimaan Data Lakeen.  
> - Azure Data Lake Storage -tilit samasta Azure-alueesta, jonka valitsit ympäristöä luotaessa.
> - Azure Data Lake Storage -tilit, joissa *hierarkkinen nimitila* on otettu käyttöön.

Voit valita Azure Data Lake Storage -asetukselle resurssi- tai tilausperustaisen asetuksen todentamista varten. Lisätietoja on kohdassa [Yhteyden muodostaminen Azure Data Lake Storage -tiliin Azure-palvelun päänimen avulla](connect-service-principal.md). **Säilön** nimi on `customerinsights`, eikä sitä voi muuttaa.

Kun järjestelmäprosessit, kuten tietojen käsittely, ovat valmiit, järjestelmä luo vastaavat kansiot määrittämällesi tallennustilille. Datatiedostot ja *model.json*-tiedostot luodaan ja lisätään kansioihin prosessin nimen perusteella.

Jos luot useita Customer Insights -ympäristöjä ja päätät tallentaa näiden ympäristöjen tuloste-entiteetit tallennustilillesi, Customer Insights luo erilliset kansiot kullekin ympäristölle ja `ci_environmentID`-tunnuksen säilöön.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Vaihe 3: Muodosta yhteys Microsoft Dataverseen
   
Tässä **Microsoft Dataverse** -vaiheessa voit yhdistää Customer Insightsin Dataverse-ympäristöösi.

Jos haluat käyttää [valmiita ennustemalleja](predictions-overview.md#out-of-box-models), määritä tietojen jakaminen Dataversen kanssa. Voit myös ottaa käyttöön tietojen käsittelyn paikallisista tietolähteistä antamalla organisaatiosi hallinnoiman Microsoft Dataverse -ympäristön URL-osoitteen. Valitse **Ota käyttöön tietojen jakaminen**, jos haluat jakaa Customer Insightsin tulostiedot Dataversen hallitun Data Laken kanssa.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Määritysvalinnat tietojen jakamista varten Microsoft Dataversen kanssa.":::

> [!NOTE]
> Customer Insights ei tue seuraavia tietojen jakamisen skenaarioita:
> - Jos tallennat kaikki tiedot omaan Azure Data Lake Storageen, et voi ottaa käyttöön tietojen jakamista Dataversen hallitun Data Laken kanssa.
> - Jos otat käyttöön tietojen jakamisen Dataversen kanssa, et voi [luoda ennustettuja tai puuttuvia arvoja entiteetissä](predictions.md).

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
