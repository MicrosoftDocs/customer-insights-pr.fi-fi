---
title: Segmenttien vieminen Marketoon (esiversio)
description: Tietoja yhteyden määrittämisestä ja viennistä Marketoon.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f57cdfbb24df8a8ffa1670b426d50dbba2c5f40f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195240"
---
# <a name="export-segments-to-marketo-preview"></a>Segmenttien vieminen Marketoon (esiversio)

Viemällä yhtenäisten asiakasprofiilien segmenttejä voit luoda kampanjoita, tuottaa sähköpostimarkkinointia ja käyttää tiettyjä asiakasryhmiä Marketon avulla.

## <a name="prerequisites"></a>edellytykset

- [Marketo-tili](https://login.marketo.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
- [Marketon asiakastunnus, asiakasohjelman salasana ja REST-päätepisteen isäntänimi](https://developers.marketo.com/rest-api/authentication/).
- [Marketon](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) aiemmin luodut luettelot ja vastaavat tunnukset.
- [Määritetyt segmentit](segments.md).
- Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Vientiä kohden voi viedä enintään miljoona asiakasprofiilia Marketoon, mikä voi kestää 3 tuntia. Marketon vietävien asiakasprofiilien määrä riippuu sopimuksestasi Marketon kanssa.
- Vain segmentit.

## <a name="set-up-connection-to-marketo"></a>Määritä yhteys Marketoon

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **Marketo**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna **Marketon asiakastunnus, asiakasohjelman salasana ja REST-päätepisteen isäntänimi**. REST-päätepisteen hostname on vain isäntänimi ilman https://. Esimerkki: xyz-abc-123.mktorest.com.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Käynnistä yhteys valitsemalla **Yhdistä**.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Marketo-osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Syötä **Marketo-luettelon tunnus**. Luettelon tunnus on pelkästään numeerinen arvo. Jos esimerkiksi Marketo-luettelon tunnus on ST12345A7, poista merkki numeroiden edestä ja jäljestä ja kirjoita *12345*.

1. Valitse **Tietojen vastaavuus** -osassa vähintään yksi kenttä, joka edustaa asiakkaan sähköpostiosoitetta tai asiakkaan Marketo-tunnusta.

1. Voit myös viedä **etunimen**, **sukunimen**, **paikkakunnan**, **osavaltion** ja **maan/alueen** yksilöllisempien sähköpostiviestien luomiseksi. Yhdistä nämä kenttä valitsemalla **Lisää määrite**.

1. Valitse segmentit, jotka haluat viedä.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Marketon segmentit ovat nyt [Marketo-luetteloissa](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
