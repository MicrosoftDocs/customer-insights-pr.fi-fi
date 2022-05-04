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
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641758"
---
# <a name="service-limits-in-customer-insights"></a>Palvelun rajoitukset Customer Insightsissa

Tässä artikkelissa on tietoja Customer Insights -palvelun sisältämistä rajoituksista. Niiden avulla varmistetaan palvelun luotettavuus ja vakaus. Muutospyynnöt voi lähettää [ideakeskustelupalstan](https://go.microsoft.com/fwlink/?linkid=2074172) kautta. 

## <a name="customer-insights"></a>Customer Insights

| Area  | Rajoitukset  | Huomautuksia |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentit, mittarit ja ennusteet | 300  | [Segmenttien](segments.md), [mittareiden](measures.md) ja [ennusteiden](predictions.md) yhdistetty kokonaismäärä ei voi olla yli 300.  |
| Suhteet | 20 syvyystasoa suhteiden entiteettipoluilla. | Kun luot [segmenttejä](segments.md) tai [mittareita](measures.md) muodostinkäyttöliittymän avulla, entiteettipoluilla voi olla enintään 20 suhdehyppyä aloitusentiteetin ja kohde-entiteetin välillä.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
