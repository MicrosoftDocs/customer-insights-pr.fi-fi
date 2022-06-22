---
title: Käytä Customer Insights -tietoja Microsoft Dataversessä
description: Opettele yhdistämään Customer Insights ja Microsoft Dataverse ja ymmärtämään Dataverseen viedyt tulosentiteetit.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 252723b8c174cb1ec488388c26fd2a1d398e9002
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011516"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Käytä Customer Insights -tietoja Microsoft Dataversessä

Customer Insights -vaihtoehdon avulla tulosentiteetit voidaan ottaa käyttöön [Microsoft Dataversessä](/powerapps/maker/data-platform/data-platform-intro). Tämä integrointi mahdollistaa helpon tietojen jakamisen ja mukautetun kehittämisen matalan tason koodin tai koodittoman menetelmän avulla. [Tulosentiteetit](#output-entities) ovat käytettävissä tauluina Dataverse-ympäristössä. Voit käyttää minkä tahansa muun sovelluksen tietoja Dataverse-taulukoiden perusteella. Näiden taulujen avulla voidaan käyttää skenaarioita, kuten automatisoidut työnkulut Power Automatessa tai sovellusten luominen Power Appsissa.

Kun muodostat yhteyden Dataverse-ympäristöön, voit myös [käsitellä tietoja paikallisista tietolähteistä Power Platform -tietovirtojen ja -yhdyskäytävien avulla](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>edellytykset

- Customer Insights- ja Dataverse-ympäristöjä on isännöitävä samalla alueella.
- Dataverse-ympäristössä on oltava yleisen järjestelmänvalvojan rooli. Tarkista, onko tämä [Dataverse-ympäristö liitetty](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) tiettyihin käyttöoikeusryhmiin, ja varmista, että sinut on lisätty näihin käyttöoikeusryhmiin.
- Tähän Dataverse-ympäristöön, johon haluat yhdistää, ei ole aiemmin liitetty Customer Insights -ympäristöä. Opettele poistamaan [aiemmin luotu yhteys Dataverse-ympäristöön](#remove-an-existing-connection-to-a-dataverse-environment).
- Microsoft Dataverse -ympäristö voi muodostaa yhteyden vain yhteen tallennustiliin. Sitä käytetään vain, jos määrität ympäristön käyttämään [Azure Data Lake Storageasi](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Dataverse -ympäristön yhdistäminen Customer Insights -asiakkaaseen

**Microsoft Dataverse** -vaiheen avulla voit yhdistää Customer Insights -tietoja Dataverse-ympäristöön [luodessasi Customer Insights -ympäristöä](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="tietojen jakaminen Microsoft Dataversen kanssa automaattisesti käytössä uusissa verkkoympäristöissä.":::

Järjestelmänvalvojat voivat määrittää Customer Insights -tiedot muodostamaan yhteyden olemassa olevaan Dataverse-ympäristöön. Antamalla URL-osoitteen Dataverse-ympäristöön, se liitetään uuteen Customer Insights -ympäristöön.

Jos et halua käyttää olemassa olevaa Dataverse-ympäristöä, järjestelmä luo vuokraajan Customer Insights -tiedoille uuden ympäristön. [Power Platformin järjestelmänvalvojat voivat hallita, kuka voi luoda ja hallita ympäristöjä](/power-platform/admin/control-environment-creation). Kun määrität uutta Customer Insights -ympäristöä ja järjestelmänvalvoja on poistanut Dataverse-ympäristöjen luomisen käytöstä kaikille järjestelmänvalvojille paitsi järjestelmänvalvojille, et ehkä voi luoda uutta ympäristöä.

**Ota tietojen jakaminen käyttöön** Dataversen kanssa valitsemalla tietojen jakamisen valintaruutu.

Jos käytät omaa Data Lake -tallennustiliä, tarvitset myös **Käyttöoikeudet-tunnisteen**. Lisätietoja käyttöoikeustunnisteen hankkimisesta on seuraavassa osiossa.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Tietojen jakamisen ottaminen käyttöön Dataversen kanssa omasta Azure Data Lake Storagesta (esiversio)

Tietojen jakamisen ottaminen käyttöön Microsoft Dataversen kanssa, kun ympäristö [käyttää omaa Azure Data Lake Storage -tiliäsi](own-data-lake-storage.md), edellyttää lisämäärityksiä. Customer Insights-ympäristön määrittävällä käyttäjällä on oltava vähintään **Säilön BLOB-tietojen lukija** -käyttöoikeudet *CustomerInsights*-säilöön Azure Data Lake Storage -tilissä.

1. Luo Azure-tilaukseen kaksi käyttöoikeusryhmää, yksi **Lukija**-käyttöoikeusryhmä ja yksi **Osallistuja**-käyttöoikeusryhmä ja määritä Microsoft Dataverse -palvelu kummankin käyttöoikeusryhmän omistajaksi.
2. Voit hallita tallennustilatilin CustomerInsights-säilön Access control list (ACL) -luetteloa näiden käyttöoikeusryhmien kautta. Lisää Microsoft Dataverse-palvelu ja muut Dataverse-pohjaiset liiketoimintasovellukset, kuten Dynamics 365 Marketing,**Lukija**-käyttöoikeusryhmään **vain luku** -oikeuksilla. Lisää *vain* Customers Insights -sovellus **Osallistuja**-käyttöoikeusryhmään, jotta voit myöntää sekä profiilien ja tietojen **luku- että kirjoitusoikeudet**.

### <a name="limitations"></a>Rajoitukset

Käyttäessäsi Dataverseä omalla Azure Data Lake Storage -tililläsi käytössä on kaksi rajoitusta:

- Dataverse-organisaation ja Azure Data Lake Storage -tilin välillä on yksi yhteen -yhdistämismääritys . Kun Dataverse-organisaatio on yhdistetty tallennustiliin, se ei voi muodostaa yhteyttä toiseen tallennustiliin. Tämä rajoitus estää sen, että Dataverse ei täytä useita tallennustilejä.
- Tietojen jakaminen ei toimi, jos Azuren yksityinen linkki -määritystä tarvitaan Azure Data Lake Storage -tilin käyttämiseen, koska se on palomuurin takana. Dataverse ei tällä hetkellä tue yksityisten päätepisteiden yhteyttä yksityisen linkin kautta.

### <a name="set-up-powershell"></a>PowerShellin määrittäminen

PowerShell-komentosarjojen suorittamiseksi PowerShell on ensin määritettävä sen mukaan.

1. Asenna [Azure Active Directory PowerShell for Graphin ](/powershell/azure/active-directory/install-adv2)uusin versio.
   1. Valitse tietokoneessa näppäimistön Windows-avain, hae **Windows PowerShell** ja valitse **Suorita Järjestelmänvalvojana**.
   1. Anna avautuvassa PowerShell-ikkunassa `Install-Module AzureAD`.
2. Tuo kolme moduulia.
    1. Kirjoita PowerShell-ikkunaan `Install-Module -Name Az.Accounts` ja seuraa ohjeita.
    1. Toista kohteiden `Install-Module -Name Az.Resources` ja `Install-Module -Name Az.Storage` kohdalla.

### <a name="configuration-steps"></a>Määrityksen vaiheet

1. Lataa kaksi suoritettavaa PowerShell-komentosarjaa insinöörin [GitHub-säilöstä](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Tämän PowerShell-komentosarjan suorittamiseen tarvitaan *vuokraajan järjestelmänvalvojan* käyttöoikeudet.
       - Tämä PowerShell-komentosarja luo kaksi käyttöoikeusryhmää Azure-tilaukseen. Yhden Lukija-ryhmälle ja yhden Osallistuja-ryhmälle ja tekee Microsoft Dataverse-palvelusta näiden käyttöoikeusryhmien omistajan.
       - Suorita tämä PowerShell-komentosarja Windows PowerShellissä antamalla Azure-tilauksen tunnus, joka sisältää Azure Data Lake Storagen. Avaamalla PowerShell-komentosarjan editorissa voit tarkastella lisätietoja ja käyttöön otettua logiikkaa.
       - Tallenna molemmat tämän komentosarjan luomat käyttöoikeusryhmän tunnusarvot, koska niitä käytetään `ByolSetup.ps1`-komentosarjassa.

        > [!NOTE]
        > Käyttöoikeusryhmän luonnin voi poistaa käytöstä vuokraajassa. Tällöin tarvitaan manuaalinen asennus, ja Azure AD-järjestelmänvalvojan on [otettava käyttöön käyttöoikeusryhmän luonti](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Tarvitset *Säilön BLOB-tietojen omistajan* oikeudet tallennustilatili-/säilötasolla komentosarjan suorittamiseen tai tämä komentosarja luo komentosarjan sinulle. Roolimääritys voidaan poistaa manuaalisesti, kun komentosarja on suoritettu.
        - Tämä PowerShell-komentosarja lisää Microsoft Dataverse-palveluun ja mihin tahansa Dataverse-pohjaisiin liiketoimintasovelluksiin tarvittavan roolipohjaisen käyttöoikeuksien hallinnan. Se päivittää myös CustomerInsights-säilön access control list (ACL) -luettelon `CreateSecurityGroups.ps1`-komentosarjalla luoduille käyttöoikeusryhmille. Osallistuja-ryhmällä on *rwx*-käyttöoikeudet ja Lukijat-ryhmällä on vain *r-x*-käyttöoikeudet.
        - Suorita tämä PowerShell-komentosarja Windows PowerShellissä antamalla Azure-tilaustunnus, joka sisältää Azure Data Lake Storagen, tallennustilin nimen, resurssiryhmän nimen sekä Lukija- ja Osallistuja-käyttöoikeusryhmän tunnusarvot. Avaamalla PowerShell-komentosarjan editorissa voit tarkastella lisätietoja ja käyttöön otettua logiikkaa.
        - Kopioi tulosmerkkijono, kun komentosarja on suoritettu. Tulosmerkkijono näyttää tältä: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Kirjoita edellä kopioitu tulosmerkkijono **Oikeuksien tunnus** -kenttään ympäristön määritysvaiheessa Microsoft Dataverselle.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Määritysvaihtoehdot, joilla voit ottaa käyttöön tietojen jakamisen omasta kohteesta Azure Data Lake Storage kohteella Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Poista aiemmin luotu yhteys Dataverse-ympäristöön

Kun muodostat yhteyden Dataverse-ympäristöön, virheilmoitus **Tämä CDS-organisaatio on jo liitetty toiseen Customer Insights -esiintymään** tarkoittaa, että Dataverse-ympäristöä käytetään jo Customer Insights -ympäristössä. Voit poistaa aiemmin luodun yhteyden yleisenä Järjestelmänvalvoja Dataverse-ympäristössä. Muutosten täyttäminen voi kestää muutaman tunnin.

1. Siirry [Power Appsiin](https://make.powerapps.com).
1. Valitse ympäristön valitsimesta ympäristö.
1. Valitse **Ratkaisut**
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
|KeyRing           | Monirivinen teksti        | JSON-arvo  </br> Esimerkki: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"avaimet":[" cntid_1078"]}]       |
|CustomerId         | String        | Yhdistetyn asiakasprofiilin tunnus.         |
|AlternateKeyId     | GUID         |  AlternateKeyn deterministinen GUID-tunnus, joka perustuu msdynci_identifieriin       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Näyte: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Tämä taulukko sisältää käyttäjien aktiviteetit, jotka ovat käytettävissä Customer Insights -kentässä.

| Column            | Laji        | Kuvaus                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Asiakkaan profiilin tunnus                                                                      |
| ActivityId        | String      | Asiakasaktiviteetin sisäinen tunnus (perusavain)                                       |
| SourceEntityName  | String      | Lähde-entiteetin nimi                                                                |
| SourceActivityId  | String      | Lähde-entiteetin perusavain                                                       |
| ActivityType      | String      | Semanttinen aktiviteettityyppi tai mukautetun aktiviteetin nimi                                        |
| ActivityTimeStamp | päivämäärä/aika    | Aktiviteetin aikaleima                                                                      |
| Otsikko             | String      | Aktiviteetin otsikko tai nimi                                                               |
| Kuvaus       | String      | Aktiviteetin kuvaus                                                                     |
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

| Column               | Laji        | Kuvaus                                          |
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

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
