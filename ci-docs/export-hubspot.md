---
title: Customer Insights -tietojen vieminen HubSpotiin
description: Opettele määrittämään yhteys ja viemään tietoja HubSpotiin.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588903"
---
# <a name="export-segments-to-hubspot-preview"></a>Segmenttien vieminen HubSpotiin (esiversio)

Vie yhtenäisten asiakasprofiilien segmenttejä HubSpotiin ja käytä niitä sähköpostimarkkinoinnissa.

## <a name="prerequisites-for-a-connection"></a>Yhteyden edellytykset

- [HubSpot-tili](https://www.hubspot.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
- HubSpotista saatu [API-avain](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key).
- [Määritetyt segmentit](segments.md) Customer Insightsissa.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään 100 000 asiakasprofiilia per vienti HubSpotiin, mikä voi kestää 15 minuuttia. HubSpotiin vietävien asiakasprofiilien määrä riippuu HubSpot-sopimuksestasi ja sen sisältämistä rajoituksista.
- Vain segmentit.

## <a name="set-up-connection-to-hubspot"></a>HubSpot-yhteyden määrittäminen

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **HubSpot**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Syötä HubSpot-tunnistetietosi pyydettäessä.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Alusta HubSpot-yhteys valitsemalla **Yhdistä**.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentästä yhteys HubSpot-osiosta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta. Toista samat vaiheet muille valinnaisille kentille.

1. Valitse segmentit, jotka haluat viedä.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
