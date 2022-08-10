---
title: Segmenttien vieminen Snapchatiin (esiversio)
description: Tietoja yhteyden määrittämisestä ja viennistä Snapchatiin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195378"
---
# <a name="export-segments-to-snapchat-preview"></a>Segmenttien vieminen Snapchatiin (esiversio)

Vie yhtenäisten asiakasprofiilien segmentit Snapchatiin ja käytä niitä mainontaan.

## <a name="prerequisites"></a>edellytykset

- [Snapchat-yritystili](https://business.snapchat.com/), [Snapchat-mainostili](https://ads.snapchat.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot. Tarvitse ainakin yhden organisaatiotilin jäsenyyden ja tietyn mainostilin tietojen hallinnan.
- Vähintään yksi käyttäjäryhmä Snapchatin käyttäjäryhmän hallinnassa, ja sen tyypin on oltava SAM (Snap Audience Match).
- [Anna Snapchat-segmentin tai käyttäjäryhmän tunnus](https://businesshelp.snapchat.com/s/article/custom-audiences). Käyttäjäryhmän tunnus löytyy URL-osoitteesta sen jälkeen, kun käyttäjäryhmä on valittu Snapchatin käyttäjäryhmän hallinnassa.
- [Määritetyt segmentit](segments.md) Customer Insightsissa.
- Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään yhden miljoonan asiakasprofiilin vieminen, mikä voi kestää 15 minuuttia.
- Vain segmentit.

## <a name="set-up-connection-to-snapchat"></a>Määritä yhteys Snapchatiin

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **Snapchat**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Käynnistä yhteys valitsemalla **Yhdistä**.

1. Valitse **Todenna Snapchatin avulla** ja anna Snapchatin järjestelmänvalvojan tunnistetiedot.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Snapchat-osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Anna **Snapchat-segmentin tai käyttäjäryhmän tunnus**.

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta.

1. Valitse segmentit, jotka haluat viedä.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
