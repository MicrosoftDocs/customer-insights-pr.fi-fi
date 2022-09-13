---
title: Palvelun rajoitukset Customer Insightsissa
description: Tietoja Customer Insights SaaS -palvelun rajoituksista.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f38b7d9985368fc38107f1f360f0603a7fcc8e6
ms.sourcegitcommit: 3c7cdfc8bd83ca236e4777240e08a541dc955d34
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/07/2022
ms.locfileid: "9411736"
---
# <a name="service-limits-in-customer-insights"></a>Palvelun rajoitukset Customer Insightsissa

 Customer Insightsissa on sisäisiä rajoituksia. Ne on suunniteltu varmistamaan palvelun luotettavuus ja vakaus. Muutospyynnöt voi lähettää [ideakeskustelupalstan](https://go.microsoft.com/fwlink/?linkid=2074172) kautta.

## <a name="customer-insights"></a>Customer Insights

| Area  | Rajoitukset  | Huomautuksia |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentit, mittarit ja ennusteet | 300  | [Segmenttien](segments.md), [mittareiden](measures.md) ja [ennusteiden](predictions-overview.md) yhdistetty kokonaismäärä ei voi olla yli 300.  |
| Suhteet | 20 syvyystasoa suhteiden entiteettipoluilla. | Kun luot [segmenttejä](segments.md) tai [mittareita](measures.md) muodostinkäyttöliittymän avulla, entiteettipoluilla voi olla enintään 20 suhdehyppyä aloitusentiteetin ja kohde-entiteetin välillä.  |

## <a name="fair-scheduling-of-jobs"></a>Töiden oikeudenmukainen aikatauluttaminen

Customer Insights on jaettuja Azure-resursseja käyttävä SaaS-palvelu. Asiakkaiden työmäärät ja aikataulut yleensä vaihtelevat. Taustaresurssien oikeudenmukainen käyttö varmistetaan siten, että järjestelmäprosessit suoritetaan oikeudenmukaisessa järjestyksessä. Järjestelmäprosesseja ovat esimerkiksi tietojen yhdistämiseen, segmenttipäivityksiin tai mittarien laskemiseen liittyvät työt. Oikeudenmukainen aikataulutus tarkoittaa, että resursseja ei tarvitse jonottaa, jos työpyyntöjen määrä kasvaa suureksi. Customer Insights ei kuitenkaan takaa, että kaikki käyttäjän jonossa olevat käsitellään rinnakkain.

[!INCLUDE [footer-include](includes/footer-banner.md)]
