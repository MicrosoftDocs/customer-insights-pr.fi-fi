---
title: Customer Insightsin entiteettirakenteet Common Data Modelissa
description: Common Data Modelin entiteettien käyttäminen.
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2cf01029ef6b64fe566022d09ce65bca3603189c
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643904"
---
# <a name="entity-schemas-in-common-data-model"></a>Entiteettirakenteet Common Data Modelissa

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](https://docs.microsoft.com/common-data-model/) on sääntöpohjainen eritelmä ja määritelmä vakioentiteeteille, jotka edustavat yleisiä liiketoiminta- ja tuottavuussovelluksissa käytettyjä käsitteitä ja toimintoja. Tätä mallia laajennetaan myös havainnollisiin ja analyyttisiin tietoihin. Common Data Model tarjoaa selkeästi määriteltyjä, modulaarisia ja laajennettavia liiketoimintaentiteettejä, kuten Tili, Liiketoimintayksikkö, Tapaus, Yhteyshenkilö, Liidi, Mahdollisuus ja Tuote, sekä vuorovaikutusta myyjien, työntekijöiden ja asiakkaiden välille, kuten toimintoja ja palvelutasosopimuksia. Kuka tahansa voi käyttää ja laajentaa Common Data Model -määritelmiä tallentamaan lisää liiketoimintakohtaisia ideoita.

Tämä on jaettu tietomalli, joka helpottaa sovellusten ja tietointegraattorien välistä yhteistyötä tuottamalla yhtenäisen tietomääritelmän. Common Data model sisältää monipuolisen metatietojärjestelmän, jossa on vakio-entiteettejä, suhteita, hierarkioita, ominaisuuksia ja muuta. Se on peräisin Dynamics 365 -sovelluksista ja se on saatavana avoimena lähdekoodina GitHubissa yli 260 vakioentiteetissä. Suuri sisäisten ja ulkoisten kumppanien järjestelmä tuottaa toimialakohtaisia käsitteitä Common Data Modeliin.

Monet järjestelmät ja ympäristöt soveltavat nykyään Common Data Modelia. Näitä ovat esimerkiksi Power BI -tietovuot ja Azure Data Services. Sitä tuetaan jo Common Data Servicessä, Dynamics 365:ssä, Power Appsissa, Power BI:ssä ja tulevissa Azuren tietopalveluissa, jossa ne keräävät suoraan arvoa [Open Data Initiativeen](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Customer Insightsin entiteettirakenteet

Jos haluat luoda asiakkaasta 360:n asteen näkymän ja ottaa Customer Insights -mallit käyttöön Common Data Modelissa laajennettavuutta varten, voit käyttää seuraavia julkaisemiamme entiteettirakenteita:

| Entiteetti | Kuvaus |
|---------|---------|
|[CustomerActivity](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Käyttäjän suorittama aktiviteetti, jolla on havaintoarvoa liiketoiminnalle. |
|[CustomerProfile](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Henkilö tai organisaatio, joka on suorittanut ja joka voi mahdollisesti suorittaa aktiviteetit. |
|[MeasureDefinition](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Nollan tai sitä useamman dimension osioiman tunnusluvun määritelmä (kuten kuukausittain aktiivinen käyttäjä, asiakkaan kokonaiskulutus, asiakkaan keskimääräinen hankintakustannus) |
|[Segmentti ](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Määrittää yhteisiä ominaisuuksia omaavien jäsenten ryhmän. |
|[SegmentMembership](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Tiettyyn segmenttiin osallistuvat jäsenet. |

Lisätietoja on ohjeistuksessa, jossa käsitellään [Customer Insightsin entiteettirakenteita Common Data Modelissa](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Entiteettien näyttäminen Common Data Model -taulukossa

Entiteettejä voi tarkastella [Common Data Modelin taulukossa](https://microsoft.github.io/CDM/). Valitse **Lataa GitHubista** -painike ja valitse **foundationCommon** > **crmCommon** > **solutions** > **customerInsights**, jossa on luettelo Customer Insights -entiteeteistä ja niiden määritelmistä.
> [!div class="mx-imgBorder"]
> ![CDM-taulukossa näkyy CustomerActivity-entiteetti](media/CDM-entity-navigator.png "CDM-taulukossa näkyy CustomerActivity-entiteetti")
