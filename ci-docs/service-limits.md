---
title: Palvelun rajoitukset Dynamics 365 Customer Insightsissa
description: Tietoja rajoista ja rajoituksista.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791977"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Palvelun rajoitukset Customer Insights -ominaisuuksissa

Tässä artikkelissa on tietoja Customer Insights -palvelun sisältämistä rajoituksista. Niiden avulla varmistetaan palvelun luotettavuus ja vakaus. Muutospyynnöt voi lähettää [ideakeskustelupalstan](https://go.microsoft.com/fwlink/?linkid=2074172) kautta. 

## <a name="audience-insights"></a>Merkityksellisiä tietoja käyttäjäryhmästä

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insightsin käyttäjäryhmäominaisuuden palvelurajat

| Alue  | Rajoitukset  | Huomautuksia |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentit, mittarit ja ennusteet | 300  | [Segmenttien](audience-insights/segments.md), [mittareiden](audience-insights/measures.md) ja [ennusteiden](audience-insights/predictions.md) yhdistetty kokonaismäärä ei voi olla yli 300.  |
| Suhteet | 20 syvyystasoa suhteiden entiteettipoluilla. | Kun luot [segmenttejä](audience-insights/segments.md) tai [mittareita](audience-insights/measures.md) muodostinkäyttöliittymän avulla, entiteettipoluilla voi olla enintään 20 suhdehyppyä aloitusentiteetin ja kohde-entiteetin välillä.  |


## <a name="engagement-insights"></a>Seurannan merkitykselliset tiedot

### <a name="workspace-and-event-quotas"></a>Työtila- ja tapahtumakiintiöt

Vuorovaikutuksen merkitykselliset tiedot on erittäin hyvin skaalautuva sovellus, joka voi tukee miljoonia tapahtumia sekunnissa. Julkisessa esiversiossa tapahtumien määrällä on yläraja. Myös organisaatiokohtainen työtilojen määrä on rajoitettu.

### <a name="engagement-insights-limits"></a>Vuorovaikutuksen merkityksellisten tietojen rajoitukset

- Tapahtumien enimmäismäärä työtilaa kohden = 100 tapahtumaa sekunnissa

- Työtilojen organisaatiokohtainen enimmäismäärä = 100

Kun tapahtumat ylittävät ylärajan, se voi johtaa tietojen menettämiseen kyseisiin tapahtumiin perustuvissa raporteissa. Voit [ottaa yhteyttä tukeen](https://go.microsoft.com/fwlink/?linkid=2145734) ja pyytää määrän lisäämistä, ennen kuin ylität rajoja. Määritämme tarpeesi määrän lisäämiseksi yhdessä kanssasi ja tuemme pyyntöäsi.


[!INCLUDE[footer-include](includes/footer-banner.md)]
