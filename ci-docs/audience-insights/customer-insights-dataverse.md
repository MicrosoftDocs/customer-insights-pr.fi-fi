---
title: Customer Insights -tiedot Microsoft Dataversessä
description: Käytä Customer Insights -entiteettejä -taulukoina Microsoft Dataversessä.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: bbbbf2a7f5edb81ee75f6e33988cd4721134b6e7
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547622"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Käytä Customer Insights -tietoja Microsoft Dataversessä

Customer Insights -vaihtoehdossa tulosentiteetit voi ottaa käyttöön [Microsoft Dataversessä](/powerapps/maker/data-platform/data-platform-intro). Tämä integrointi mahdollistaa helpon tietojen jakamisen ja mukautetun kehittämisen matalan tason koodin tai koodittoman menetelmän avulla. [Tulosentiteetit](#output-entities) ovat käytettävissä tauluina Dataverse-ympäristössä. Voit käyttää minkä tahansa muun sovelluksen tietoja Dataverse-taulukoiden perusteella. Näiden taulujen avulla voidaan käyttää skenaarioita, kuten automatisoidut työnkulut Power Automatessa tai sovellusten luominen Power Appsissa. Nykyinen toteutus tukee pääasiassa hakuja, joissa käytettävissä olevien Customer Insights -entiteettien tiedot voidaan hakea annetun asiakastunnuksen avulla.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Dataverse-ympäristön liittäminen Customer Insightsiin

**Olemassa oleva organisaatio**

Järjestelmänvalvojat voivat määrittää Customer Insightsin [käyttämään olemassa olevaa Dataverse-ympäristöä](create-environment.md), kun he luovat Customer Insights -ympäristön. Antamalla URL-osoitteen Dataverse-ympäristöön se liitetään ympäristön uuteen kohdeyleisöön. Customer Insights- ja Dataverse-ympäristöjä on isännöitävä samalla alueella. 

Jos et halua käyttää olemassa olevaa Dataverse-ympäristöä, järjestelmä luo vuokraajan Customer Insights -tiedoille uuden ympäristön. 

> [!NOTE]
> Jos organisaatiossasi on jo käytössä Dataverse vuokraajassa, on tärkeää muistaa, että [Dataverse-ympäristön luontia hallitsee järjestelmänvalvoja](/power-platform/admin/control-environment-creation). Jos esimerkiksi määrität organisaatiotililläsi uutta kohdeyleisötieto-ympäristöä ja järjestelmänvalvoja on poistanut Dataverse-kokeiluympäristöjen luomisen käytöstä kaikille järjestelmänvalvojille, et voi luoda uutta kokeiluympäristöä.
> 
> Customer Insightsissa luoduissa Dataverse-kokeiluympäristöissä on 3 Gt tallennustilaa, jota ei lasketa mukaan vuokraajaan oikeutettuun kapasiteetin kokonaismäärään. Maksetut tilaukset saavat 15 Gt:n Dataverse-oikeuden tietokantaan ja 20 Gt:a tiedostotallennustilaan.

**Uusi organisaatio**

Jos luot uuden organisaation Customer Insightsin määrittämisen yhteydessä, järjestelmä luo automaattisesti uuden Dataverse-ympäristön organisaatiossa.

## <a name="output-entities"></a>Tulosentiteetit

Jotkin tulosentiteetit käyttäjäryhmän merkityksellisistä tiedoista ovat käytettävissä taulukoina Dataversessä. Alla olevat osat kuvaavat näiden taulukoiden odotettua rakennetta.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Rikastus](#enrichment)
- [Ennuste](#prediction)
- [Segmentin jäsenyys](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Tämä taulukko sisältää Customer Insightsin yhtenäisen asiakasprofiilin. Yhtenäisen asiakasprofiilin rakenne määräytyy yhdistämisprosessissa käytettynä käytetyn entiteettien ja määritteiden mukaan. Asiakasprofiilirakenne sisältää yleensä [CustomerProfilen Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) -määrityksen määritteiden alijoukon.

### <a name="alternatekey"></a>AlternateKey

AlternateKey-taulukko sisältää prosessiin osallistuneiden entiteettien avaimet.

|Column  |Laji  |Kuvaus  |
|---------|---------|---------|
|DataSourceName    |String         | Tietolähteen nimi. Esimerkki: `datasource5`        |
|EntityName        | String        | Käyttäjäryhmän merkityksellisten tietojen entiteetin nimi. Esimerkki: `contact1`        |
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

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Asiakkaan profiilin tunnus        |
| SegmentProvider      | String       | Sovellus, joka julkaisee segmentit. Oletus: Käyttäjäryhmien merkitykselliset tiedot         |
| SegmentMembershipType | String       | Tämän segmentin jäsenyystietueen asiakkaan tyyppi. Tukee useita tyyppejä, kuten asiakasta, yhteyshenkilöä tai asiakkuutta. Oletus: Asiakas  |
| Segmentit       | JSON-merkkijono  | Niiden yksilöllisten segmenttien luettelo, joihin asiakasprofiili kuuluu      |
| msdynci_identifier  | String   | Segmentin jäsenyystietueen yksilöllinen tunnus. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministinen GUID, joka on luotu kohteesta `msdynci_identifier`          |
