---
title: Käytä Customer Insights -tietoja Microsoft Dataversessä
description: Opettele yhdistämään Customer Insights ja Microsoft Dataverse ja ymmärtämään Dataverseen viedyt tulosentiteetit.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: dfa63110fc5291f2b63aebf588d6fdd20ed4ab67
ms.sourcegitcommit: 134aac66e3e0b77b2e96a595d6acbb91bf9afda2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/07/2022
ms.locfileid: "9424305"
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
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Rikastus](#enrichment)
- [Ennuste](#prediction)
- [Segmentin jäsenyys](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Tämä taulukko sisältää Customer Insightsin yhtenäisen asiakasprofiilin. Unified customer profile -rakenne määräytyy tietojenyhdistämisprosessissa käytettyjen entiteettien ja määritteiden mukaan. Asiakasprofiilirakenne sisältää yleensä [CustomerProfilen Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) -määrityksen määritteiden alijoukon. B2B-skenaariossa asiakasprofiili sisältää yhtenäisiä tilejä, ja rakenne sisältää yleensä [Asiakkaan Common Data Model -määrityksen](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account) määritteiden alijoukon.

### <a name="contactprofile"></a>ContactProfile

ContactProfile sisältää yhteyshenkilöä koskevat yhtenäiset tiedot. Yhteyshenkilöt ovat [yksityishenkilöitä, jotka on yhdistetty tiliin](data-unification-contacts.md) B2B-skenaariossa.

| Column                       | Type                | Description     |
| ---------------------------- | ------------------- | --------------- |
|  BirthDate            | DateTime       |  Yhteyshenkilön syntymäaika               |
|  City                 | Viesti |  Yhteyshenkilön osoitteen paikkakunta               |
|  ContactId            | Viesti |  Yhteyshenkilöprofiilin tunnus               |
|  ContactProfileId     | Yksilöivä tunniste   |  Yhteyshenkilön GUID               |
|  CountryOrRegion      | Viesti |  Yhteyshenkilön osoitteen maa/alue               |
|  CustomerId           | Viesti |  Sen tilin tunnus, johon yhteyshenkilö on yhdistetty               |
|  EntityName           | Viesti |  Entiteetti, josta tiedot ovat peräisin                |
|  FirstName            | Viesti |  Yhteyshenkilön etunimi               |
|  Sukupuoli               | Viesti |  Yhteyshenkilön sukupuoli               |
|  Id                   | Viesti |  Deterministinen GUID-tunnus, joka perustuu `Identifier`-tunnukseen               |
|  Identifier           | Viesti |  Yhteyshenkilöprofiilin sisäinen tunnus: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | Viesti |  Yhteyshenkilön työnimike               |
|  LastName             | Viesti |  Yhteyshenkilön sukunimi               |
|  PostalCode           | Viesti |  Yhteyshenkilön osoitteen postinumero               |
|  PrimaryEmail         | Viesti |  Yhteyshenkilön sähköpostiosoite               |
|  PrimaryPhone         | Viesti |  Yhteyshenkilön puhelinnumero               |
|  StateOrProvince      | Viesti |  Yhteyshenkilön osoitteen osavaltio tai provinssi               |
|  StreetAddress        | Viesti |  Yhteyshenkilön osoitteen katuosoite               |

### <a name="alternatekey"></a>AlternateKey

AlternateKey-taulukko sisältää prosessiin osallistuneiden entiteettien avaimet.

|Column  |Type  |Description  |
|---------|---------|---------|
|DataSourceName    |Viesti         | Tietolähteen nimi. Esimerkki: `datasource5`        |
|EntityName        | Viesti        | Entiteetin nimi Customer Insightsissa. Esimerkki: `contact1`        |
|AlternateValue    |Viesti         |Vaihtoehtoinen tunnus, joka on yhdistetty asiakastunnukseen. Esimerkki: `cntid_1078`         |
|KeyRing           | Viesti        | JSON-arvo  </br> Esimerkki: [{”dataSourceName”:” datasource5 ”,</br>”entityName”:” contact1”,</br>”preferredKey”:” cntid_1078”,</br>”avaimet”:[” cntid_1078”]}]       |
|CustomerId         | Viesti        | Yhdistetyn asiakasprofiilin tunnus.         |
|AlternateKeyId     | Yksilöivä tunniste        |  Deterministinen (AlternateKey) GUID-tunnus, joka perustuu `Identifier`-tunnukseen      |
|Identifier |   Viesti      |   `DataSourceName|EntityName|AlternateValue`  </br> Näyte: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Tämä taulukko sisältää käyttäjien aktiviteetit, jotka ovat käytettävissä Customer Insights -kentässä.

| Column            | Type        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Viesti      | Asiakkaan profiilin tunnus                                                                      |
| ActivityId        | Viesti      | Asiakasaktiviteetin sisäinen tunnus (perusavain)                                       |
| SourceEntityName  | Viesti      | Lähde-entiteetin nimi                                                                |
| SourceActivityId  | Viesti      | Lähde-entiteetin perusavain                                                       |
| ActivityType      | Viesti      | Semanttinen aktiviteettityyppi tai mukautetun aktiviteetin nimi                                        |
| ActivityTimeStamp | DateTime    | Aktiviteetin aikaleima                                                                      |
| Title             | Viesti      | Aktiviteetin otsikko tai nimi                                                               |
| Description       | Viesti      | Aktiviteetin kuvaus                                                                     |
| URL               | Viesti      | Linkitä aktiviteettia varten tiettyyn ulkoiseen URL-osoitteeseen                                         |
| SemanticData      | Viesti | Sisältää luettelon avainarvopareista toiminnan tyypille ominaisten semanttisten kartoituskenttien osalta |
| RangeIndex        | Viesti      | Unix-aikaleima, jota käytetään aktiviteetin aikajanan ja tehokkaiden aluekyselyiden lajittelemiseen |
| UnifiedActivityId   | Yksilöivä tunniste | Asiakasaktiviteetin sisäinen tunnus (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Tässä taulukossa on asiakasmääritteeseen perustuvien toimenpiteiden tulostiedot.

| Column             | Type             | Description                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Viesti           | Asiakkaan profiilin tunnus        |
| Mittarit           | Viesti      | Sisältää luettelon avainarvojen pareista tietyn asiakkaan mittayksikön nimelle ja arvoille |
| Identifier | Viesti           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Yksilöivä tunniste     | Asiakkaan profiilin tunnus |

### <a name="enrichment"></a>Rikastus

Tämä taulukko sisältää täydennysprosessin tulostiedot.

| Column               | Type             |  Description                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Viesti           | Asiakkaan profiilin tunnus                                 |
| EnrichmentProvider   | Viesti           | Kirjoita rikastuksen antajan nimi                                  |
| EnrichmentType       | Viesti           | Rikastuksen tyyppi                                      |
| Arvot               | Viesti      | Täydennysprosessin tuottama lisämääritteiden luettelo |
| EnrichmentId | Yksilöivä tunniste            | Deterministinen GUID, joka on luotu kohteesta `Identifier` |
| Identifier   | Viesti           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Ennuste

Tämä taulukko sisältää malliennusteen tulostiedot.

| Column               | Type        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Viesti      | Asiakkaan profiilin tunnus                                  |
| ModelProvider        | Viesti      | Kirjoita mallin antajan nimi                                      |
| Malli                | Viesti      | Mallin nimi                                                |
| Arvot               | Viesti | Mallin tuottama lisämääritteiden luettelo |
| PredictionId | Yksilöivä tunniste       | Deterministinen GUID, joka on luotu kohteesta `Identifier` |
| Identifier   | Viesti      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmentin jäsenyys

Tämä taulukko sisältää asiakasprofiilien segmenttien jäsenyystiedot.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | Viesti       | Asiakkaan profiilin tunnus        |
| SegmentProvider      | Viesti       | Sovellus, joka julkaisee segmentit.      |
| SegmentMembershipType | Viesti       | Tämän segmentin jäsenyystietueen asiakkaan tyyppi. Tukee useita tyyppejä, kuten asiakasta, yhteyshenkilöä tai asiakkuutta. Oletus: Asiakas  |
| Segments       | Viesti  | Niiden yksilöllisten segmenttien luettelo, joihin asiakasprofiili kuuluu      |
| Identifier  | Viesti   | Segmentin jäsenyystietueen yksilöllinen tunnus. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Yksilöivä tunniste      | Deterministinen GUID, joka on luotu kohteesta `Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
