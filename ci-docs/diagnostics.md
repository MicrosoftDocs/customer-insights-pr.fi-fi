---
title: Dynamics 365 Customer Insightsin tarkistus Azure Monitorin avulla
description: Tietoja lokien lähettämisestä Microsoft Azure Monitoriin.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 03169f0218dfad55cf20ecaf1c1596c652e5f601
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755258"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Lokien edelleenlähetys Dynamics 365 Customer Insightsissa Azure Monitorin avulla (esiversio)

Dynamics 365 Customer Insights tarjoaa suoran integroinnin Azure Monitorin kanssa. Azure Monitorin resurssilokien avulla voit valvoa ja lähettää lokeja [Azure Storageen](https://azure.microsoft.com/services/storage/), [Azure Log Analyticsiin](/azure/azure-monitor/logs/log-analytics-overview) tai virtauttaa se [Azure-tapahtumakeskukseen](https://azure.microsoft.com/services/event-hubs/).

Customer Insights lähettää seuraavat tapahtumalokit:

- **Tarkistustapahtumat**
  - **APIEvent** – ottaa käyttöön Dynamics 365 Customer Insights -käyttöliittymän kautta tehtyjen muutosten seurannan.
- **Operatiiviset tapahtumat**
  - **WorkflowEvent** – Työnkulun avulla voi määrittää [tietolähteitä](data-sources.md), [yhdistää](data-unification.md), [rikastaa](enrichment-hub.md) sekä lopuksi [viedä](export-destinations.md) tietoja muihin järjestelmiin. Kaikki nämä vaiheet voidaan tehdä yksitellen (esimerkiksi käynnistää yksittäinen vienti). Voi suorittaa niitä myös orkestroituina (esimerkiksi päivittää tiedot tietolähteistä, mikä käynnistää yhdistäminenprosessin, joka hakee rikastukset ja vie tiedot toiseen järjestelmään valmistuttuaan). Katso lisätietoja [WorkflowEvent-rakenteesta](#workflow-event-schema).
  - **APIEvent** – kaikki ohjelmointirajapinnan kutsut asiakkaiden ilmentymään Dynamics 365 Customer Insightsiin. Katso lisätietoja [APIEvent-rakenteesta](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Diagnostiikka-asetusten määrittäminen

### <a name="prerequisites"></a>edellytykset

Jotta diagnostiikka voidaan määrittää Customer Insightsissa, seuraavien edellytysten on täytyttävä:

- Sinulla on aktiivinen [Azure-tilaus](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Sinulla on [järjestelmänvalvojan](permissions.md#admin) oikeudet Customer Insightsissa.
- Sinulla on **Osallistuja**- ja **Käyttäjän käyttöoikeuksien järjestelmänvalvoja** -rooli Azuren kohderesurssissa. Resurssi voi olla Azure Storage account, Azure-tapahtumakeskus tai Azure Log Analytics -työtila. Jos haluat lisätietoja, siirry kohtaan [Lisää tai poista Azure-roolimäärityksiä käyttäen Azure-portaalia](/azure/role-based-access-control/role-assignments-portal).
- Azure Storagen, Azure-tapahtumakeskuksen tai Azure Log Analyticsin [kohdevaatimukset](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) pitää olla täytettynä.
- Sinulla on vähintään **Lukija**-rooli resurssiryhmässä, johon resurssi kuuluu.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Diagnostiikan määritykset Azure Monitorin avulla

1. Valitse Customer Insightsissa **Järjestelmä** > **Diagnostiikka**, kun haluat nähdä tämän ilmentymän määritetyt diagnostiikkakohteet.

1. Valitse **Lisää kohde**.

   > [!div class="mx-imgBorder"]
   > ![Diagnostiikkayhteys](media/diagnostics-pane.png "Diagnostiikkayhteys")

1. Kirjoita nimi **Diagnostiikkakohteen nimi** -kenttään.

1. Valitse kohderesurssin sisältävän Azure-tilauksen **Vuokraaja** ja valitse sitten **Kirjaudu sisään**.

1. Valitse **Resurssityyppi** (tallennustilan tili, tapahtumakeskus tai Log Analytics).

1. Valitse kohderesurssin **Tilaus**.

1. Valitse kohderesurssin **Resurssiryhmä**.

1. Valitse **Resurssi**.

1. Vahvista **Tietosuoja ja vaatimustenmukaisuus** -lauseke.

1. Muodosta yhteys kohderesurssiin valitsemalla **Yhdistä järjestelmään**. Lokit alkavat näkyä kohteessa 15 minuutin kuluttua, jos ohjelmointirajapinta on käytössä ja luo tapahtumia.

### <a name="remove-a-destination"></a>Kohteen poistaminen

1. Siirry kohtaan **Järjestelmä** > **Diagnostiikka**.

1. Valitse diagnostiikkakohde luettelosta.

1. Valitse **Toiminnot**-sarakkeen **Poista**-kuvake.

1. Vahvista poisto, jotta lokin edelleenlähetys voidaan pysäyttää. Azure-tilauksen resurssia ei poisteta. Voit valita **Toiminnot**-sarakkeen linkin, kun haluat avata valitun resurssin Azure-portaalissa ja poistaa resurssin siellä.

## <a name="log-categories-and-event-schemas"></a>Lokien luokat ja tapahtumarakenteet

[API-tapahtumia](apis.md) ja työnkulkutapahtumia tuetaan tällä hetkellä, ja seuraavat luokat ja rakenteet ovat käytössä.
Lokirakenne noudattaa [Azure Monitorin yleistä rakennetta](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Luokat

Customer Insights sisältää kaksi luokkaa:

- **Tarkistustapahtumat**: [API-tapahtumat](#api-event-schema), jotka seuraavat palvelun määritysmuutoksia. `POST|PUT|DELETE|PATCH`-toiminnot kuuluvat tähän luokkaan.
- **Operatiiviset tapahtumat**: [API-tapahtumat](#api-event-schema) tai [työnkulun tapahtumat](#workflow-event-schema), jotka luodaan palvelua käytettäessä.  Esimerkiksi työnkulun `GET`-pyynnöt tai suoritustapahtumat.

## <a name="configuration-on-the-destination-resource"></a>Kohderesurssin määritys

Seuraavat vaiheet tulevat automaattisesti käyttöön resurssityypin valinnan mukaan:

### <a name="storage-account"></a>Storage account

Customer Insights -palvelun päänimi saa **Tallennustilatilin osallistuja** -oikeuden valittuun resurssiin ja luo kaksi säilöä valitun nimitilan alle:

- `insight-logs-audit`, joka sisältää **tarkistustapahtumat**
- `insight-logs-operational`, joka sisältää **operationaaliset tapahtumat**

### <a name="event-hub"></a>Tapahtumakeskus

Customer Insights -palvelun päänimi saa **Azure-tapahtumakeskuksen tietojen omistaja** -oikeuden valittuun resurssiin ja luo kaksi tapahtumakeskusta valitun nimitilan alle:

- `insight-logs-audit`, joka sisältää **tarkistustapahtumat**
- `insight-logs-operational`, joka sisältää **operationaaliset tapahtumat**

### <a name="log-analytics"></a>Log Analytics

Customer Insights -palvelun päänimi saa **Log Analytics -osallistuja** -oikeuden resurssiin. Lokit ovat käytettävissä kohdassa **Lokit** > **Taulukot** > **Lokien hallinta** valitussa Log Analytics -työtilassa. Laajenna **Lokin hallinta** -ratkaisu ja etsi `CIEventsAudit`- ja `CIEventsOperational`-taulukot.

- `CIEventsAudit`, joka sisältää **tarkistustapahtumat**
- `CIEventsOperational`, joka sisältää **operationaaliset tapahtumat**

Laajenna **Kyselyt**-ikkunan **Seuranta**-ratkaisu ja etsi `CIEvents`-haun avulla löytäneet esimerkkikyselyt.

## <a name="event-schemas"></a>Tapahtumarakenteet

API-tapahtumilla ja työnkulun tapahtumilla on yhteinen rakenne. Eriävät tiedot löytyvät kohdista [API-tapahtumarakenne](#api-event-schema) tai [Työnkulku-tapahtumarakennetta](#workflow-event-schema).

### <a name="api-event-schema"></a>API-tapahtumarakenne

| Field             | DataType  | Pakollinen/valinnainen | Description       | Esimerkki:        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Aikaleima | Pakollinen          | Tapahtuman aikaleima (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Pakollinen          | Tapahtuman lähettäneen ilmentymän ResourceId-tunnus         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Pakollinen          | Tapahtuman edustaman toiminnon nimi.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Pakollinen          | Tapahtuman lokiluokka. Joko `Operational` tai `Audit`. Kaikkiin POST/PUT/PATCH/DELETE-tyyppisiin HTTP-pyyntöihin merkitään `Audit`, muihin merkitään `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Pakollinen          | Tapahtuman tila. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Valinnainen          | Tapahtuman tulostila. Jos toiminto vastaa REST API -kutsua, se on HTTP-tilakoodi.        | `200`             |
| `durationMs`      | Long      | Valinnainen          | Toiminnon kesto millisekunteina.     | `133`     |
| `callerIpAddress` | String    | Valinnainen          | Kutsujan IP-osoite, jos toiminto vastaa API-kutsua, joka tulee julkisesta IP-osoitteesta.                                                 | `144.318.99.233`         |
| `identity`        | String    | Valinnainen          | Käyttäjän tai sovelluksen identiteettiä kuvaava JSON-objekti, joka on tehnyt toiminnon.       | Katso [Käyttäjätiedot](#identity-schema)-osa.     |  
| `properties`      | String    | Valinnainen          | JSON-objekti, jossa on enemmän ominaisuuksia tiettyyn tapahtumaluokkaan.      | Katso [Ominaisuudet](#api-properties-schema)-osa.    |
| `level`           | String    | Pakollinen          | Tapahtuman suojaustaso.    | `Informational`, `Warning`, `Error` tai `Critical`.           |
| `uri`             | String    | Valinnainen          | Pyynnön absoluuttinen URI.    |               |

#### <a name="identity-schema"></a>Tunnistetietorakenne

JSON-objektin `identity` rakenne on seuraavanlainen

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Field                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Käyttäjän tai sovelluksen delegoitu rooli. Lisätietoja on kohdassa [käyttäjän oikeudet](permissions.md).                                     |
| `Authorization.RequiredRoles` | Toiminnon edellyttämät roolit. `Admin`-roolilla on oikeus tehdä kaikki toiminnot.                                                    |
| `Claims`                      | Käyttäjän tai sovelluksen JSON-verkkotunnuksen (JWT) väite (claim). Väitteen ominaisuudet vaihtelevat organisaation ja Azure Active Directory -määritysten mukaan. |

#### <a name="api-properties-schema"></a>API-ominaisuuksien rakenne

[API-tapahtumilla](apis.md) on seuraavat ominaisuudet.

| Field                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Aina `ApiEvent`, joka merkitsee lokitapahtuman API-tapahtumaksi.                                                                 |
| `properties.userAgent`       | Selainagentti, joka lähettää pyynnön tai `unknown`.                                                                        |
| `properties.method`          | HTTP-menetelmä: `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Pyynnön suhteellinen polku.                                                                                          |
| `properties.origin`          | URI, joka ilmaisee, mistä nouto on peräisin tai `unknown`.                                                                  |
| `properties.operationStatus` | `Success` HTTP-tilakoodille < 400 <br> `ClientError` HTTP-tilakoodille < 500 <br> `Error` HTTP-tilakoodille >= 500 |
| `properties.tenantId`        | Organisaation tunnus                                                                                                        |
| `properties.tenantName`      | Organisaation nimi.                                                                                              |
| `properties.callerObjectId`  | Kutsujan Azure Active Directory ObjectId -tunnus.                                                                         |
| `properties.instanceId`      | Customer Insightsin `instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Työnkulun tapahtumarakenne

Työnkulku sisältää useita vaiheita. [Kerää tietolähteet](data-sources.md), [yhdistä](data-unification.md), [rikasta](enrichment-hub.md) ja [vie](export-destinations.md) tiedot. Kaikki nämä vaiheet voidaan suorittaa yksitellen tai järjestää seuraavilla prosesseilla.

#### <a name="operation-types"></a>Toimintotyypit

| OperationType     | Ryhmittele                                     |
| ----------------- | ----------------------------------------- |
| Kerääminen         | [Tietolähteet](data-sources.md)           |
| DataPreparation   | [Tietolähteet](data-sources.md)           |
| Liitä               | [Tietojen yhdistäminen](data-unification.md)   |
| Match             | [Tietojen yhdistäminen](data-unification.md)   |
| Yhdistä             | [Tietojen yhdistäminen](data-unification.md)   |
| ProfileStore      | [Asiakasprofiilit](customer-profiles.md) |
| Haku            | [Asiakasprofiilit](customer-profiles.md) |
| Toiminta          | [Aktiviteetit](activities.md)                  |
| AttributeMeasures | [Segmentit ja mittarit](segments.md)      |
| EntityMeasures    | [Segmentit ja mittarit](segments.md)      |
| Mittarit          | [Segmentit ja mittarit](segments.md)      |
| Segmentointi      | [Segmentit ja mittarit](segments.md)      |
| Rikastus        | [Rikastus](enrichment-hub.md)                                          |
| Analytiikka      | [Ennusteet](predictions-overview.md)                                          |
| AiBuilder         | [Ennusteet](predictions-overview.md)                                          |
| Näkemykset          | [Ennusteet](predictions-overview.md)                                          |
| Export            | [Viennit](export-destinations.md)                                          |
| ModelManagement   | [Ennusteet](custom-models.md)                                           |
| Suhde      | [Tietojen yhdistäminen](relationships.md)                                           |

#### <a name="field-description"></a>Kentän kuvaus

| Field           | DataType  | Pakollinen/valinnainen | Description                                                                                                                                                   | Esimerkki:                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Aikaleima | Pakollinen          | Tapahtuman aikaleima (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Pakollinen          | Tapahtuman lähettäneen ilmentymän ResourceId-tunnus.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Pakollinen          | Tapahtuman edustaman toiminnon nimi. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Lisätietoja on ohjeaiheessa [Toimintotyypit](#operation-types). | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Pakollinen          | Tapahtuman lokiluokka. Aina `Operational` työnkulkutapahtumille                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Pakollinen          | Tapahtuman tila. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Long      | Valinnainen          | Toiminnon kesto millisekunteina.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Valinnainen          | JSON-objekti, jossa on enemmän ominaisuuksia tiettyyn tapahtumaluokkaan.                                                                                        | Katso aliosa [Työnkulun ominaisuudet](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Pakollinen          | Tapahtuman suojaustaso.                                                                                                                                  | `Informational`, `Warning` tai `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Työnkulun ominaisuusrakenne

Työnkulkutapahtumilla on seuraavat ominaisuudet.

| Field              | Workflow | Tehtävä | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Kyllä      | Kyllä  | Aina `WorkflowEvent`, joka merkitsee lokitapahtuman työnkulkutapahtumaksi.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Kyllä      | Kyllä  | Työnkulun suorituksen tunnus. Kaikilla työnkulku- ja tehtävätapahtumilla työnkulun suorittamisessa on sama `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Kyllä      | Kyllä  | Toiminnon tunnus, katso [Toimintotyypit](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Kyllä      | No   | Vain työnkulku. Työnkulun käynnistämien tehtävien määrä.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Kyllä      | No   | Valinnainen. Vain työnkulkutapahtumat. Azure Active Directory [objectId käyttäjälle](/azure/marketplace/find-tenant-object-id#find-user-object-id), joka käynnisti työnkulun. Katso myös `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Kyllä      | No   | `full`- tai `incremental`-päivitys.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Kyllä      | No   | `OnDemand` tai `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Kyllä      | No   | `Running` tai `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Kyllä      | Kyllä  | UTC-aikaleima `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Kyllä      | Kyllä  | UTC-aikaleima `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Kyllä      | Kyllä  | UTC-aikaleima `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Kyllä      | Kyllä  | Customer Insightsin `instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Kyllä  | - Jos käytössä on OperationType = `Export`, tunnus on vientimäärityksen GUID-tunnus. <br> - Jos OperationType = `Enrichment`, tunnus on rikastustoiminnon GUID-tunnus. <br> - OperationType-tyypeille `Measures` ja `Segmentation` tunnus on entiteetin nimi. |
| `properties.friendlyName`                    | No       | Kyllä  | Viennin tai käsiteltävän entiteetin helppokäyttöinen nimi.                                                                                                                                                                                           |
| `properties.error`                           | No       | Kyllä  | Valinnainen. Virhesanoma, jossa on lisätietoja.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Kyllä  | Valinnainen. Vain OperationType-tyyppiä `Export` varten. Määrittää viennin tyypin. Lisätietoja on [vientikohteiden yleiskuvauksessa](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Kyllä  | Valinnainen. Vain OperationType-tyyppiä `Export` varten. Sisältää viennin määritettyjen entiteettien luettelon.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Kyllä  | Valinnainen. Vain OperationType-tyyppiä `Export` varten. Viennin yksityiskohtainen sanoma.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Kyllä  | Valinnainen. Vain OperationType-tyyppiä `Segmentation` varten. Osoittaa segmentin jäsenten kokonaismäärän.                                                                                                                                                    |
