---
title: Segmenttien vieminen Brazeen (esiversio)
description: Tietoja Braze-yhteyden määrittämisestä ja viennistä siihen.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 2f52eb8196e057f934c8d2b5ac0518ce121606b6
ms.sourcegitcommit: 003c1929f730d7d505c108aba84f6269f4c98978
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2022
ms.locfileid: "9655271"
---
# <a name="export-segments-to-braze-preview"></a>Segmenttien vieminen Brazeen (esiversio)

Vie unified customer profile -profiilien segmentit Brazeen ja käytä niitä markkinointiaktiviteetteihin.

## <a name="prerequisites"></a>edellytykset

- Käytössä on [Braze-tili](https://www.braze.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
- [Braze-ohjelmointirajapinta-avain](https://www.braze.com/docs/api/basics/)
- [Braze REST -päätepiste](https://www.braze.com/docs/api/basics/#api-definitions) 
- [Määritetyt segmentit](segments.md) Customer Insightsissa.
- Viedyissä segmenteissä Unified Customer Profile -profiilit sisältävät kentän, joka vastaa sähköpostiosoitetta ja Braze-asiakastunnusta.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään yhden miljoonan asiakasprofiilin vieminen Brazeen voi kestää 40 minuuttia. Omnisendiin vietävien asiakasprofiilien määrä määräytyy Brazen kanssa tekemäsi sopimuksen mukaan.
- Vain segmentit.
- Braze-vienti ei tue Azure Private Link -linkkiä.

## <a name="set-up-connection-to-braze"></a>Määritä yhteys Brazeen

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **Braze**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Jatka kirjautumista antamalla Braze-ohjelmointirajapinnan avain.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Käynnistä yhteys valitsemalla **Yhdistä**.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Braze-osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Kirjoita REST-päätepiste **Hostname**-kenttään seuraavassa muodossa: `rest.iad-03.braze.com`.

1. Anna viennin nimi.

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta. Valitse **Asiakastunnus**-kentässä kenttä, joka ilmaisee asiakkaan Braze-tunnuksen. Brazen segmentit luodaan samalla nimellä kuin kohteen Dynamics 365 Customer Insights segmenttikin. Voit valita muita valinnaisia kenttiä vastaavia tietoja varten.

1. Valitse vietävät entiteetit, esimerkiksi segmentit.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
