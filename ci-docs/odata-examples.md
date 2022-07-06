---
title: Customer Insights -ohjelmointirajapinnan OData-kyselyesimerkit
description: Yleisesti käytettyjä esimerkkejä Open Data Protocol (OData) -protokollasta Customer Insights -ohjelmointirajapintojen kyselyille tietojen tarkistamista varten.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54ba9f4e9baeb4b7021bb8c20a706bbb6eb1529f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081215"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Customer Insights -ohjelmointirajapinnan OData-kyselyesimerkit

OData (Open Data Protocol) on perusprotokollien, kuten HTTP:n, tietojen käyttöprotokolla. Se käyttää verkossa yleisesti hyväksyttyjä menetelmiä, kuten REST-menetelmää. OData-palveluiden käytössä voi käyttää erilaisia kirjastoja ja työkaluja.

Tässä artikkelissa on joitakin usein pyydettyjä esimerkkikyselyitä, joiden avulla voit luoda omia toteutuksia [Customer Insights -ohjelmointirajapintojen perusteella](apis.md).

Kyselynäytteitä on muokattava, jotta ne toimivat kohdeympäristöissä: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}`, jossa {instanceId} on GUID siinä Customer Insights -ympäristössä, jossa haluat suorittaa kyselyjä. [ListAllInstances-toiminnon avulla](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) voit etsiä sen {InstanceId}-tunnuksen, johon sinulla on käyttöoikeus.
- {CID}: yhtenäisen asiakastietueen GUID-tunnus. Esimerkki: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: asiakastietueen perusavaimen tunnus tietolähteessä. Esimerkki: `CNTID_1002`
- {DSname}: Merkkijono, jossa on sen tietolähteen entiteetin nimi, joka tuodaan käytettäväksi Customer Insightsiin. Esimerkki: `Website_contacts`.
- {SegmentName}: Merkkijono, jolla on Customer Insights -segmentin tulosentiteetin nimi. Esimerkki: `Male_under_40`.

## <a name="customer"></a>asiakas

Seuraava taulukko sisältää *Asiakas*-entiteetin näytekyselyiden joukon.

|Kyselyn tyyppi |Esimerkki:  | Muistiinpano  |
|---------|---------|---------|
|Yksittäisen asiakkaan tunnus     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Vaihtoehtoinen avain    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Vaihtoehtoiset avaimet säilyvät yhtenäisessä asiakasentiteetissä       |
|Lisää pisteitä ja merkitse mitattavan tilavuuden kanta valitsemalla Lisää-painike   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Kohteessa    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Vaihtoehtoinen avain + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Haku  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Palauttaa 10 ensimmäistä tulosta hakumerkkijonolle      |
|Segmentin jäsenyys  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Palauttaa segmentointientiteetin rivien esimääritetyn määrän.      |

## <a name="unified-activity"></a>Yhdistetty aktiviteetti

Seuraava taulukko sisältää *UnifiedActivity*-entiteetin näytekyselyiden joukon.

|Kyselyn tyyppi |Esimerkki:  | Muistiinpano  |
|---------|---------|---------|
|CID:in aktiviteetti     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Luettelo tietyn asiakasprofiilin aktiviteeteista |
|Aktiviteetin aikaikkuna    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Asiakasprofiilin aktiviteetit aikavälillä       |
|Aktiviteettityyppi    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Aktiviteetti näyttönimen mukaan     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Aktiviteettien lajittelu    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Aktiviteettien lajittelu nousevassa tai laskevassa järjestyksessä       |
|Aktiviteetti on laajennettu segmentin jäsenyydellä  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Lisää esimerkkejä

Seuraava taulukko sisältää muiden entiteettien näytekyselyiden joukon.

|Kyselyn tyyppi |Esimerkki:  | Muistiinpano  |
|---------|---------|---------|
|CID:in mittarit    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|CID:n rikastetut tuotemerkit    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|CID:in rikastetut kiinnostuksen kohteet    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Clause + Expand     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Ei tuettuja OData-kyselyjä

Customer Insights ei tue seuraavia kyselyjä:

- `$filter` käsitellyissä lähde-entiteeteissä. Voit suorittaa $filter-kyselyt vain Customer Insightsin luomissa järjestelmäentiteeteissä.
- `$expand` `$search` -kyselystä. Esimerkki: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` alkaen kohteesta `$select`, jos vain määritteiden alijoukko on valittu. Esimerkki: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` tietyn asiakkaan rikastettuja brändi- tai kiinnostuksen kohteita. Esimerkki: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Kysely ennustemallin tulostekokonaisuuksista vaihtoehtoisen avaimen avulla. Esimerkki: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
