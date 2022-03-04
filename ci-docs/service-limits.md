---
title: Palvelun rajoitukset Dynamics 365 Customer Insightsissa
description: Tietoja rajoista ja rajoituksista.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350403"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Palvelun rajoitukset Customer Insights -ominaisuuksissa

Tässä artikkelissa on tietoja Customer Insights -palvelun sisältämistä rajoituksista. Niiden avulla varmistetaan palvelun luotettavuus ja vakaus. Muutospyynnöt voi lähettää [ideakeskustelupalstan](https://go.microsoft.com/fwlink/?linkid=2074172) kautta. 

## <a name="audience-insights"></a>Merkityksellisiä tietoja käyttäjäryhmästä

| Area  | Rajoitukset  | Huomautuksia |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentit, mittarit ja ennusteet | 300  | [Segmenttien](audience-insights/segments.md), [mittareiden](audience-insights/measures.md) ja [ennusteiden](audience-insights/predictions.md) yhdistetty kokonaismäärä ei voi olla yli 300.  |
| Suhteet | 20 syvyystasoa suhteiden entiteettipoluilla. | Kun luot [segmenttejä](audience-insights/segments.md) tai [mittareita](audience-insights/measures.md) muodostinkäyttöliittymän avulla, entiteettipoluilla voi olla enintään 20 suhdehyppyä aloitusentiteetin ja kohde-entiteetin välillä.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
