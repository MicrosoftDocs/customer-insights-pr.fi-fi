---
title: Customer Insightsin entiteettirakenteet Common Data Modelissa
description: Common Data Modelin entiteettien käyttäminen.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 33a0562854e97b9ac5218e060f965996305627fd
ms.sourcegitcommit: d45c00a5f6cb106714366af81e8070e7f53654b3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/15/2022
ms.locfileid: "8757428"
---
# <a name="entity-schemas-in-common-data-model"></a>Entiteettirakenteet Common Data Modelissa



[Common Data Model](/common-data-model/) on sääntöpohjainen eritelmä ja määritelmä vakioentiteeteille, jotka edustavat yleisiä liiketoiminta- ja tuottavuussovelluksissa käytettyjä käsitteitä ja toimintoja. Tätä mallia laajennetaan myös havainnollisiin ja analyyttisiin tietoihin. Common Data Model tarjoaa selkeästi määriteltyjä, modulaarisia ja laajennettavia liiketoimintaentiteettejä, kuten Tili, Liiketoimintayksikkö, Tapaus, Yhteyshenkilö, Liidi, Mahdollisuus ja Tuote, sekä vuorovaikutusta myyjien, työntekijöiden ja asiakkaiden välille, kuten toimintoja ja palvelutasosopimuksia. Kuka tahansa voi käyttää ja laajentaa Common Data Model -määritelmiä tallentamaan lisää liiketoimintakohtaisia ideoita.

Tämä on jaettu tietomalli, joka helpottaa sovellusten ja tietointegraattorien välistä yhteistyötä tuottamalla yhtenäisen tietomääritelmän. Common Data model sisältää monipuolisen metatietojärjestelmän, jossa on vakio-entiteettejä, suhteita, hierarkioita, ominaisuuksia ja muuta. Se on peräisin Dynamics 365 -sovelluksista ja se on saatavana avoimena lähdekoodina GitHubissa yli 260 vakioentiteetissä. Suuri sisäisten ja ulkoisten kumppanien järjestelmä tuottaa toimialakohtaisia käsitteitä Common Data Modeliin.

Monet järjestelmät ja ympäristöt käyttävät nykyisin Common Data Modelia. Niitä ovat esimerkiksi Power BI:n tiedonkulut ja Azuren tietopalvelut. Sitä tuetaan jo Microsoft Dataversessä, Dynamics 365:ssä, Power Appsissa ja Power BIssä, sekä tulevissa Azure-tietopalveluissa, jotka kerryttävät arvoa suoraan [avointa dataa koskeviin aloitteisiin](https://dynamics.microsoft.com/en-us/open-data-initiative/).

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

Entiteettejä voi tarkastella [Common Data Modelin taulukossa](https://microsoft.github.io/CDM/). Valitsemalla kohteen Tiedot-sovellusosasta saat luettelon Customer Insights -entiteeteistä ja niiden määrityksistä.
> [!div class="mx-imgBorder"]
> ![CDM-taulukossa näkyy CustomerActivity-entiteetti.](media/CDM-entity-navigator.png "CDM-taulukossa näkyy CustomerActivity-entiteetti")


[!INCLUDE [footer-include](includes/footer-banner.md)]
