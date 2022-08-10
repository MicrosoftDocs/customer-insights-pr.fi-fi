---
title: Segmenttien vieminen Campaign Monitoriin (esiversio)
description: Tietoja yhteyden määrittämisestä ja viennistä Campaign Monitoriin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196298"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Segmenttien vieminen Campaign Monitoriin (esiversio)

Vie yhtenäisten asiakasprofiilien segmentit Campaign Monitoriin ja käytä niitä markkinointiaktiviteetteihin.

## <a name="prerequisites"></a>edellytykset

- [Campaign Monitor -tili](https://www.campaignmonitor.com/) ja sitä vastaavat järjestelmänvalvojan tunnistetiedot.
- [Campaign Monitorin luettelotunnus](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- [Luotu API-avain](https://www.campaignmonitor.com/api/getting-started/) Campaign Monitorin **tiliasetuksista**, jotta näet ohjelmointirajapinnan luettelotunnuksen.
- [Määritetyt segmentit](segments.md) Customer Insightsissa.
- Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään yhden miljoonan asiakasprofiilin vieminen kerrallaan Campaign Monitoriin, mikä voi kestää 20 minuuttia. Campaign Monitoriin vietävien asiakasprofiilien määrä riippuu Campaign Monitor -sopimuksestasi.
- Vain segmentit.

## <a name="set-up-connection-to-campaign-monitor"></a>Määritä yhteys Campaign Monitoriin

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **Campaign Monitor**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Alusta yhteys Campaign Monitoriin valitsemalla **Yhdistä**.

1. Valitse **Todenna Campaign Monitorin avulla** ja anna Campaign Monitorin järjestelmänvalvojan tunnistetiedot.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Campaign Monitor -osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Anna **Campaign Monitor -luettelon tunnus**.

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta. Campaign Monitoriin pitää viedä segmenttejä.

1. Valitse segmentit, jotka haluat viedä.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
