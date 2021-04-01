---
title: Customer Insightsin entiteettirakenteet Common Data Modelissa
description: Common Data Modelin entiteettien käyttäminen.
ms.date: 04/17/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6667e411a1b56e13105a6b59b7b5d249bc8141ea
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596357"
---
# <a name="entity-schemas-in-common-data-model"></a>Entiteettirakenteet Common Data Modelissa

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](/common-data-model/) on sääntöpohjainen eritelmä ja määritelmä vakioentiteeteille, jotka edustavat yleisiä liiketoiminta- ja tuottavuussovelluksissa käytettyjä käsitteitä ja toimintoja. Tätä mallia laajennetaan myös havainnollisiin ja analyyttisiin tietoihin. Common Data Model tarjoaa selkeästi määriteltyjä, modulaarisia ja laajennettavia liiketoimintaentiteettejä, kuten Tili, Liiketoimintayksikkö, Tapaus, Yhteyshenkilö, Liidi, Mahdollisuus ja Tuote, sekä vuorovaikutusta myyjien, työntekijöiden ja asiakkaiden välille, kuten toimintoja ja palvelutasosopimuksia. Kuka tahansa voi käyttää ja laajentaa Common Data Model -määritelmiä tallentamaan lisää liiketoimintakohtaisia ideoita.

Tämä on jaettu tietomalli, joka helpottaa sovellusten ja tietointegraattorien välistä yhteistyötä tuottamalla yhtenäisen tietomääritelmän. Common Data model sisältää monipuolisen metatietojärjestelmän, jossa on vakio-entiteettejä, suhteita, hierarkioita, ominaisuuksia ja muuta. Se on peräisin Dynamics 365 -sovelluksista ja se on saatavana avoimena lähdekoodina GitHubissa yli 260 vakioentiteetissä. Suuri sisäisten ja ulkoisten kumppanien järjestelmä tuottaa toimialakohtaisia käsitteitä Common Data Modeliin.

Monet järjestelmät ja ympäristöt soveltavat nykyään Common Data Modelia. Näitä ovat esimerkiksi Power BI -tietovuot ja Azure Data Services. Sitä tuetaan jo Common Data Servicessä, Dynamics 365:ssä, Power Appsissa, Power BI:ssä ja tulevissa Azuren tietopalveluissa, jossa ne keräävät suoraan arvoa [Open Data Initiativeen](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Customer Insightsin entiteettirakenteet

Jos haluat luoda asiakkaasta 360:n asteen näkymän ja ottaa Customer Insights -mallit käyttöön Common Data Modelissa laajennettavuutta varten, voit käyttää seuraavia julkaisemiamme entiteettirakenteita:

| Entiteetti | Kuvaus |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Käyttäjän suorittama aktiviteetti, jolla on havaintoarvoa liiketoiminnalle. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Henkilö tai organisaatio, joka on suorittanut ja joka voi mahdollisesti suorittaa aktiviteetit. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Nollan tai sitä useamman dimension osioiman tunnusluvun määritelmä (kuten kuukausittain aktiivinen käyttäjä, asiakkaan kokonaiskulutus, asiakkaan keskimääräinen hankintakustannus) |
|[Segmentti ](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Määrittää yhteisiä ominaisuuksia omaavien jäsenten ryhmän. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Tiettyyn segmenttiin osallistuvat jäsenet. |

Lisätietoja on ohjeistuksessa, jossa käsitellään [Customer Insightsin entiteettirakenteita Common Data Modelissa](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Entiteettien näyttäminen Common Data Model -taulukossa

Entiteettejä voi tarkastella [Common Data Modelin taulukossa](https://microsoft.github.io/CDM/). Valitse **Lataa GitHubista** -painike ja valitse **foundationCommon** > **crmCommon** > **solutions** > **customerInsights**, jossa on luettelo Customer Insights -entiteeteistä ja niiden määritelmistä.
> [!div class="mx-imgBorder"]
> ![CDM-taulukossa näkyy CustomerActivity-entiteetti](media/CDM-entity-navigator.png "CDM-taulukossa näkyy CustomerActivity-entiteetti")


[!INCLUDE[footer-include](../includes/footer-banner.md)]