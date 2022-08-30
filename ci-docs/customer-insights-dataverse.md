---
title: Käytä Customer Insights -tietoja Microsoft Dataversessä
description: Opettele yhdistämään Customer Insights ja Microsoft Dataverse ja ymmärtämään Dataverseen viedyt tulosentiteetit.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 0d536259f310b41fe12922baeebdc4569937db08
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303825"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Käytä Customer Insights -tietoja Microsoft Dataversessä

Customer Insights -vaihtoehdossa tulosentiteetit voi ottaa käyttöön [Microsoft Dataversessä](/powerapps/maker/data-platform/data-platform-intro). Tämä integrointi mahdollistaa helpon tietojen jakamisen ja mukautetun kehittämisen matalan tason koodin tai koodittoman menetelmän avulla. [Tulosentiteetit](#output-entities) ovat käytettävissä tauluina Dataverse-ympäristössä. Voit käyttää minkä tahansa muun sovelluksen tietoja Dataverse-taulukoiden perusteella. Näiden taulujen avulla voidaan käyttää skenaarioita, kuten automatisoidut työnkulut Power Automatessa tai sovellusten luominen Power Appsissa.

Kun muodostat yhteyden Dataverse-ympäristöön, voit myös [käsitellä tietoja paikallisista tietolähteistä Power Platform -tietovirtojen ja -yhdyskäytävien avulla](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>edellytykset

- Customer Insights- ja Dataverse-ympäristöjä on isännöitävä samalla alueella.
- Dataverse-ympäristössä määritetty yleisen järjestelmänvalvojan rooli. Tarkista, onko tämä [Dataverse-ympäristö liitetty](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) tiettyihin käyttöoikeusryhmiin, ja varmista, että sinut on lisätty näihin käyttöoikeusryhmiin.
- Tähän Dataverse-ympäristöön, johon haluat yhdistää, ei ole aiemmin liitetty Customer Insights -ympäristöä. Opettele poistamaan [aiemmin luotu yhteys Dataverse-ympäristöön](#remove-an-existing-connection-to-a-dataverse-environment).
- Yhteen tallennustiliin yhdistetty Microsoft Dataverse -ympäristö, jos määrität ympäristön [käyttämään omaa Azure Data Lake Storageasi](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse tallennustilakapasiteettioikeudet

Customer Insights -tilaus oikeuttaa organisaatiosi olemassa olevan [Dataverse-tallennuskapasiteetin lisäämiseen](/power-platform/admin/capacity-storage). Lisäkapasiteetti määräytyy tilauksesi käytössä olevien profiilien määrän mukaan.

**Esimerkki:**

Oletetaan, että saat 15 gigatavun tietokantatallennustilan ja 20 gigatavun tiedostotallennustilan 100 000:ta asiakasprofiilia kohti. Jos tilauksessa on 300 000 asiakasprofiilia, tallennustilan kokonaiskapasiteetti on 45 Gt (3 x 15 Gt) tietokantatallennustilaa ja 60 Gt tiedostotallennustilaa (3 x 20 Gt). Jos sinulla on B2B-tilaus 30 000 tilillä, kokonaistallennustila on 45 Gt (3 x 15 Gt) tietokantatallennustilaa ja 60 Gt tiedostotallennustilaa (3 x 20 Gt).

Lokikapasiteettia ei lisätä vaan se on kiinteä organisaatiolle.

Lisätietoja tarkoista kapasiteettioikeuksista on kohdassa [Dynamics 365:n käyttöoikeusopas](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Dataverse -ympäristön yhdistäminen Customer Insights -asiakkaaseen

**Microsoft Dataverse** -vaiheen avulla voit yhdistää Customer Insights -tietoja Dataverse-ympäristöön [luodessasi Customer Insights -ympäristöä](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="tietojen jakaminen Microsoft Dataversen kanssa automaattisesti käytössä uusissa ympäristöissä.":::

1. Anna Dataverse-ympäristön URL-osoite tai jätä kenttä tyhjäksi, jotta se luodaan sinulle.

   > [!NOTE]
   > Kun olet muodostanut yhteyden Customer Insightsin ja Dataversen välille, älä muuta Dataverse-ympäristön organisaationimeä. Organisaation nimeä käytetään Dataverse-URL-osoitteessa, ja muutettu nimi katkaisee yhteyden Customer Insightsiin.

   [Power Platformin järjestelmänvalvojat voivat hallita, kuka voi luoda uuden Dataverse-ympäristön](/power-platform/admin/control-environment-creation). Jos yrität määrittää uutta Customer Insights -ympäristöä mutta se ei onnistu, järjestelmänvalvoja on ehkä poistanut Dataverse-ympäristöjen luomisen käytöstä kaikilta paitsi järjestelmänvalvojilta.

1. Jos käytät omaa Data Lake Storage -tallennustiliä:
   1. Valitse **Ota tietojen jakaminen käyttöön** Dataversen kanssa.
   1. Anna **Oikeuksien tunnus**. Saat oikeuksien tunnuksen [ottamalla tietojen jakamisen käyttöön Dataversen kanssa omasta Azure Data Lake Storagesta](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Tietojen jakamisen ottaminen käyttöön Dataversen kanssa omasta Azure Data Lake Storagesta (esiversio)

Varmista [omassa Azure Data Lake Storage -tilissä](own-data-lake-storage.md), että Customer Insights-ympäristön määrittävällä käyttäjällä on vähintään **Storage Blob Data Reader** -oikeudet `customerinsights`-säilössä tallennustilissä.

### <a name="limitations"></a>Rajoitukset

- Dataverse-organisaation ja Azure Data Lake Storage -tilin välillä on vain yksi yhteen -yhdistämismääritys. Kun Dataverse-organisaatio on yhdistetty tallennustiliin, se ei voi muodostaa yhteyttä toiseen tallennustiliin. Tämä rajoitus estää Dataversea täyttämästä useita tallennustilejä.
- Tietojen jakaminen ei toimi, jos Azuren yksityinen linkki -määritystä tarvitaan Azure Data Lake Storage -tilin käyttämiseen, koska se on palomuurin takana. Dataverse ei tällä hetkellä tue yksityisten päätepisteiden yhteyttä yksityisen linkin kautta.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Käyttöoikeusryhmien määrittäminen omassa Azure Data Lake Storagessa

1. Luo Azure-tilaukseen kaksi käyttöoikeusryhmää, yksi **Lukija**-käyttöoikeusryhmä ja yksi **Osallistuja**-käyttöoikeusryhmä ja määritä Microsoft Dataverse -palvelu kummankin käyttöoikeusryhmän omistajaksi.

1. Voit hallita tallennustilatilin `customerinsights`-säilön Access control list (ACL) -luetteloa näiden käyttöoikeusryhmien kautta.
   1. Lisää Microsoft Dataverse-palvelu ja muut Dataverse-pohjaiset liiketoimintasovellukset, kuten Dynamics 365 Marketing,**Lukija**-käyttöoikeusryhmään **vain luku** -oikeuksilla.
   1. Lisää *vain* Customers Insights -sovellus **Osallistuja**-käyttöoikeusryhmään, jotta voit myöntää sekä profiilien ja tietojen **luku- että kirjoitusoikeudet**.

### <a name="set-up-powershell"></a>PowerShellin määrittäminen

Määritä PowerShell suorittamaan PowerShell-komentosarjoja.

1. Asenna [Azure Active Directory PowerShell for Graphin ](/powershell/azure/active-directory/install-adv2)uusin versio.
   1. Valitse tietokoneessa näppäimistön Windows-avain, hae **Windows PowerShell** ja valitse **Suorita Järjestelmänvalvojana**.
   1. Anna avautuvassa PowerShell-ikkunassa `Install-Module AzureAD`.

1. Tuo kolme moduulia.
   1. Kirjoita PowerShell-ikkunaan `Install-Module -Name Az.Accounts` ja seuraa ohjeita.
   1. Toista kohteiden `Install-Module -Name Az.Resources` ja `Install-Module -Name Az.Storage` kohdalla.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Suorita PowerShell-komentosarjat ja hanki oikeuksien tunnus

1. Lataa kaksi suoritettavaa PowerShell-komentosarjaa insinöörin [GitHub-säilöstä](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: Edellyttää vuokraajan järjestelmänvalvojan käyttöoikeuksia.
   - `ByolSetup.ps1`: Edellyttää Storage Blob Data Owner -oikeuksia tallennustilatili-/säilötasolla. Tämä komentosarja luo sinulle oikeudet. Roolimääritys voidaan poistaa manuaalisesti, kun komentosarja on suoritettu.

1. Suorita `CreateSecurityGroups.ps1` Windows PowerShellissä antamalla Azure-tilauksen tunnus, joka sisältää Azure Data Lake Storagen. Avaamalla PowerShell-komentosarjan editorissa voit tarkastella lisätietoja ja käyttöön otettua logiikkaa.

   Tämä komentosarja luo Azure-tilaukseen kaksi suojausryhmää: toisen Lukija-ryhmälle ja toisen Osallistuja-ryhmälle. Microsoft Dataverse -palvelu on molempien käyttöoikeusryhmien omistaja.

1. Tallenna molemmat tämän komentosarjan luomat käyttöoikeusryhmän tunnusarvot; niitä käytetään `ByolSetup.ps1`-komentosarjassa.

   > [!NOTE]
   > Käyttöoikeusryhmän luonnin voi poistaa käytöstä vuokraajassa. Tällöin tarvitaan manuaalinen asennus, ja Azure AD-järjestelmänvalvojan on [otettava käyttöön käyttöoikeusryhmän luonti](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Suorita `ByolSetup.ps1` Windows PowerShellissä antamalla Azure-tilaustunnus, joka sisältää Azure Data Lake Storagen, tallennustilin nimen, resurssiryhmän nimen sekä Lukija- ja Osallistuja-käyttöoikeusryhmän tunnusarvot. Avaamalla PowerShell-komentosarjan editorissa voit tarkastella lisätietoja ja käyttöön otettua logiikkaa.

   Tämä komentosarja lisää Microsoft Dataverse-palveluun ja mihin tahansa Dataverse-pohjaisiin liiketoimintasovelluksiin tarvittavan roolipohjaisen käyttöoikeuksien hallinnan. Se päivittää myös `customerinsights`-säilön access control list (ACL) -luettelon `CreateSecurityGroups.ps1`-komentosarjalla luoduille käyttöoikeusryhmille. Osallistuja-ryhmälle on annettu *rwx*-käyttöoikeudet ja Lukijat-ryhmälle on annettu vain *r-x*-käyttöoikeudet.

1. Kopioi tulosmerkkijono, joka näyttää tältä: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Kirjoita kopioitu tulosmerkkijono **Oikeuksien tunnus** -kenttään ympäristön määritysvaiheessa Microsoft Dataverselle.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Määritysvaihtoehdot, joilla voit ottaa käyttöön tietojen jakamisen omasta kohteesta Azure Data Lake Storage kohteella Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Poista aiemmin luotu yhteys Dataverse-ympäristöön

Kun muodostat yhteyden Dataverse-ympäristöön, virheilmoitus **Tämä CDS-organisaatio on jo liitetty toiseen Customer Insights -esiintymään** tarkoittaa, että Dataverse-ympäristöä käytetään jo Customer Insights -ympäristössä. Voit poistaa aiemmin luodun yhteyden yleisenä Järjestelmänvalvoja Dataverse-ympäristössä. Muutosten täyttäminen voi kestää muutaman tunnin.

1. Siirry [Power Appsiin](https://make.powerapps.com).
1. Valitse ympäristön valitsimesta ympäristö.
1. Valitse **Ratkaisut**.
1. Poista **Dynamics 365 Customer Insights -asiakaskortin apuohjelma (esiversio)** -niminen ratkaisu tai sen asennus.

Tai

1. Avaa Dataverse-ympäristösi.
1. Siirry kohtaan **Lisäasetukset** > **Ratkaisut**.
1. Poista **CustomerInsightsCustomerCard**-ratkaisun asennus.

Jos yhteyden poistaminen epäonnistuu riippuvuuksien vuoksi, myös riippuvuudet on poistettava. Lisätietoja on aiheessa [Riippuvuuksien poistaminen](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Tulosentiteetit

Jotkin Customer Insightsin tulosentiteetit ovat käytettävissä taulukoina Dataversessä. Alla olevat osat kuvaavat näiden taulukoiden odotettua rakennetta.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Rikastus](#enrichment)
- [Ennuste](#prediction)
- [Segmentin jäsenyys](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Tämä taulukko sisältää Customer Insightsin yhtenäisen asiakasprofiilin. Unified customer profile -rakenne määräytyy tietojenyhdistämisprosessissa käytettyjen entiteettien ja määritteiden mukaan. Asiakasprofiilirakenne sisältää yleensä [CustomerProfilen Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) -määrityksen määritteiden alijoukon.

### <a name="alternatekey"></a>AlternateKey

AlternateKey-taulukko sisältää prosessiin osallistuneiden entiteettien avaimet.

|Column  |Laji  |Kuvaus  |
|---------|---------|---------|
|DataSourceName    |String         | Tietolähteen nimi. Esimerkki: `datasource5`        |
|EntityName        | String        | Entiteetin nimi Customer Insightsissa. Esimerkki: `contact1`        |
|AlternateValue    |String         |Vaihtoehtoinen tunnus, joka on yhdistetty asiakastunnukseen. Esimerkki: `cntid_1078`         |
|KeyRing           | Monirivinen teksti        | JSON-arvo  </br> Esimerkki: [{”dataSourceName”:” datasource5 ”,</br>”entityName”:” contact1”,</br>”preferredKey”:” cntid_1078”,</br>”avaimet”:[” cntid_1078”]}]       |
|CustomerId         | String        | Yhdistetyn asiakasprofiilin tunnus.         |
|AlternateKeyId     | GUID         |  AlternateKeyn deterministinen GUID-tunnus, joka perustuu msdynci_identifieriin       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Näyte: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Tämä taulukko sisältää käyttäjien aktiviteetit, jotka ovat käytettävissä Customer Insights -kentässä.

| Column            | Type        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Asiakkaan profiilin tunnus                                                                      |
| ActivityId        | String      | Asiakasaktiviteetin sisäinen tunnus (perusavain)                                       |
| SourceEntityName  | String      | Lähde-entiteetin nimi                                                                |
| SourceActivityId  | String      | Lähde-entiteetin perusavain                                                       |
| ActivityType      | String      | Semanttinen aktiviteettityyppi tai mukautetun aktiviteetin nimi                                        |
| ActivityTimeStamp | päivämäärä/aika    | Aktiviteetin aikaleima                                                                      |
| Title             | String      | Aktiviteetin otsikko tai nimi                                                               |
| Description       | String      | Aktiviteetin kuvaus                                                                     |
| URL               | String      | Linkitä aktiviteettia varten tiettyyn ulkoiseen URL-osoitteeseen                                         |
| SemanticData      | JSON-merkkijono | Sisältää luettelon avainarvopareista toiminnan tyypille ominaisten semanttisten kartoituskenttien osalta |
| RangeIndex        | String      | Unix-aikaleima, jota käytetään aktiviteetin aikajanan ja tehokkaiden aluekyselyiden lajittelemiseen |
| mydynci_unifiedactivityid   | GUID | Asiakasaktiviteetin sisäinen tunnus (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Tässä taulukossa on asiakasmääritteeseen perustuvien toimenpiteiden tulostiedot.

| Column             | Laji             | Kuvaus                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | Asiakkaan profiilin tunnus        |
| Mittarit           | JSON-merkkijono      | Sisältää luettelon avainarvojen pareista tietyn asiakkaan mittayksikön nimelle ja arvoille | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | Asiakkaan profiilin tunnus |


### <a name="enrichment"></a>Rikastus

Tämä taulukko sisältää täydennysprosessin tulostiedot.

| Column               | Laji             |  Kuvaus                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | Asiakkaan profiilin tunnus                                 |
| EnrichmentProvider   | String           | Kirjoita rikastuksen antajan nimi                                  |
| EnrichmentType       | String           | Rikastuksen tyyppi                                      |
| Arvot               | JSON-merkkijono      | Täydennysprosessin tuottama lisämääritteiden luettelo |
| msdynci_enrichmentid | GUID             | Msdynci_identifierista luotu deterministinen GUID-tunnus |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Ennuste

Tämä taulukko sisältää malliennusteen tulostiedot.

| Column               | Type        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | Asiakkaan profiilin tunnus                                  |
| ModelProvider        | String      | Kirjoita mallin antajan nimi                                      |
| Malli                | String      | Mallin nimi                                                |
| Arvot               | JSON-merkkijono | Mallin tuottama lisämääritteiden luettelo |
| msdynci_predictionid | GUID        | Msdynci_identifierista luotu deterministinen GUID-tunnus | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmentin jäsenyys

Tämä taulukko sisältää asiakasprofiilien segmenttien jäsenyystiedot.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Asiakkaan profiilin tunnus        |
| SegmentProvider      | String       | Sovellus, joka julkaisee segmentit.      |
| SegmentMembershipType | String       | Tämän segmentin jäsenyystietueen asiakkaan tyyppi. Tukee useita tyyppejä, kuten asiakasta, yhteyshenkilöä tai asiakkuutta. Oletus: Asiakas  |
| Segmentit       | JSON-merkkijono  | Niiden yksilöllisten segmenttien luettelo, joihin asiakasprofiili kuuluu      |
| msdynci_identifier  | String   | Segmentin jäsenyystietueen yksilöllinen tunnus. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministinen GUID, joka on luotu kohteesta `msdynci_identifier`          |


[!INCLUDE [footer-include](includes/footer-banner.md)]
