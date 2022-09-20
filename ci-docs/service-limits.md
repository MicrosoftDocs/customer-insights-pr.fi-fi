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
ms.openlocfilehash: c3863b1a72fd92ddc87755699feda11371ec9214
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463215"
---
# <a name="service-limits-in-customer-insights"></a>Palvelun rajoitukset Customer Insightsissa

 Customer Insightsissa on sisäisiä rajoituksia. Ne on suunniteltu varmistamaan palvelun luotettavuus ja vakaus. Muutospyynnöt voi lähettää [ideakeskustelupalstan](https://go.microsoft.com/fwlink/?linkid=2074172) kautta.

## <a name="customer-insights"></a>Customer Insights

| Area  | Rajoitukset  | Huomautuksia |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentit, mittarit ja ennusteet | 300  | [Segmenttien](segments.md), [mittareiden](measures.md) ja [ennusteiden](predictions-overview.md) yhdistetty kokonaismäärä ei voi olla yli 300.  |
| Suhteet | 20 syvyystasoa suhteiden entiteettipoluilla. | Kun luot [segmenttejä](segments.md) tai [mittareita](measures.md) muodostinkäyttöliittymän avulla, entiteettipoluilla voi olla enintään 20 suhdehyppyä aloitusentiteetin ja kohde-entiteetin välillä.  |
|Tietojen käsittely| Power Query -tietolähteiden samanaikaisia arviointeja on rajoitettu. | Customer Insights sisältää samat [päivitysrajoitukset kuin tietovuot PowerBI.comissa](/power-query/power-query-online-limits#refresh-limits). |

## <a name="fair-scheduling-of-jobs"></a>Töiden oikeudenmukainen aikatauluttaminen

Customer Insights on jaettuja Azure-resursseja käyttävä SaaS-palvelu. Asiakkaiden työmäärät ja aikataulut yleensä vaihtelevat. Taustaresurssien oikeudenmukainen käyttö varmistetaan siten, että järjestelmäprosessit suoritetaan oikeudenmukaisessa järjestyksessä. Järjestelmäprosesseja ovat esimerkiksi tietojen yhdistämiseen, segmenttipäivityksiin tai mittarien laskemiseen liittyvät työt. Oikeudenmukainen aikataulutus tarkoittaa, että resursseja ei tarvitse jonottaa, jos työpyyntöjen määrä kasvaa suureksi. Customer Insights ei kuitenkaan takaa, että kaikki käyttäjän jonossa olevat käsitellään rinnakkain.

[!INCLUDE [footer-include](includes/footer-banner.md)]
