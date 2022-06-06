---
title: Käyttöoikeuksien hallinta
description: Tietoja käyttöoikeuksista ja käyttäjärooleista.
ms.date: 02/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: 8022563f8994400b88389c20d7d661d9ea82bab1
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833718"
---
# <a name="user-permissions"></a>Käyttäjien käyttöoikeudet

**Oikeudet**-sivulla voit määrittää rooleja ja oikeuksia Customer Insights -tietojen käyttöön.

Sivun näyttämiseen tarvitaan järjestelmänvalvojan käyttöoikeudet. Jos haluat käyttää käyttöoikeussivua, siirry sivulle **Järjestelmänhallinta** > **Tietoturva** > **Käyttäjät**.

Roolityyppejä on kolme:

## <a name="viewer"></a>Katselija

- **Aloitus**- ja **Segmentit**-sivuilla voi tutustua merkityksellisiin tietoihin ja segmentteihin.
- Hae ja suodata asiakasprofiileja **Asiakkaat**-sivun avulla. Kentistä on voitava tehdä hakuja.
- Tutustu **Rikastaminen**-sivuun.
- Tuutustu entiteetteihin ja vie niitä **Entiteetit**-sivun avulla.
- Näytä järjestelmän käsittelyn tila **Järjestelmä**-sivun avulla.
- Vientien tarkasteleminen **Viennit**-sivulla.
- Asenna **Power BI Customer Insights** -koontinäyttö ja käytä sitä.

## <a name="contributor"></a>Osallistuja

- Kaikki katselijan oikeudet.
- Lataa ja muunna tietoja **Tietolähteet**-sivun avulla.
- Täytä **Tietojen yhdistäminen**, joka johtaa unified customer profile -profiilientiteettiin.
- Määritä **suhteet** ja **aktiviteetit**.
- Luo segmenttejä **Segmentit**-sivun avulla.
- Luo mittareita **Mittarit**-sivun avulla.
- Hallitse määrityksiä ja täydennä asiakasprofiilit **Täydennä**-sivulla (vain ensimmäisen osapuolen täydennykset).
- Hallitse ja luo vientejä osallistujien kanssa jaettujen yhteyksien perusteella. [Lisätietoja siitä, miten järjestelmänvalvojat voivat sallia osallistujien käyttää yhteyttä vienneissä.](connections.md#allow-contributors-to-use-a-connection-for-exports)

## <a name="admin"></a>Järjestelmänvalvoja

- Kaikki osallistujan oikeudet.
- Muuta asetuksia **Järjestelmä**-sivulla, myös työskentelykieli, ja päivitä järjestelmäprosessien aikataulut.
- Tarkastele ja lisää oikeuksia **Käyttöoikeudet**-sivulla.
- Määritä Asiakkaat-sivun haku- ja suodatusmääritelmät **Hae ja suodata indeksi** -sivulla (käytettävissä **Asiakkaat**-sivulla).
- Voit hallita yhteyksiä ja sallia niitä muille käyttäjärooleille **Yhteydet**-sivulla.
- Hallitse määrityksiä ja täydennä asiakasprofiilit **Täydennä**-sivulla (kaikki täydennykset).
- Hallitse ja luo vientejä **Viennit**-sivulla.
- Asenna **asiakaskortin apuohjelma** ja käytä sitä.
- Lisää **Power Apps -yhdistin** ja käytä sitä.
- Ota [Customer Insights -ohjelmointirajapinnat](apis.md) käyttöön.
- [Delegoi ympäristön omistus](manage-environments.md#change-the-owner-of-an-environment) toiselle järjestelmänvalvojalle.

## <a name="admin-owner"></a>Järjestelmänvalvoja (omistaja)

- Kaikki järjestelmänvalvojan käytettävissä olevat oikeudet.
- [Nollaa ja poista](manage-environments.md#reset-an-existing-environment-preview) ympäristö.

## <a name="assign-roles-and-permissions"></a>Delegoi roolit ja oikeudet

1. Valitse **Järjestelmänhallinta** > **Tietoturva** > **Käyttäjät**.

1. Avaa **Lisää tai muokkaa oikeuksia** -ruutu valitsemalla **Lisää käyttäjiä**.

1. Etsi **Hae**-kentän avulla Azure Active Directoryn käyttäjä tai ryhmä, jonka käyttöoikeuksia haluat muokata. Valitse **Rooli**, joka liitetään käyttäjälle tai ryhmälle.

1. Valitse **Tallenna**. Nykyinen ympäristö jaetaan automaattisen sen käyttäjän tai niiden ryhmän jäsenten kanssa, joiden käyttöoikeuksia on muutettu. Käyttäjät voivat käyttää Customer Insights -sovellusta ja käyttää sitä määritetyn roolinsa mukaisesti.

## <a name="view-current-permissions"></a>Tarkastele nykyisiä oikeuksia

Siirry kohtaan **Järjestelmänvalvoja** > **Tietoturva** > **Käyttäjät** ja katso, mitkä roolimääritykset ovat tällä hetkellä aktiivisia.

- **Tyyppi**-sarake määrittää yhden käyttäjän, ryhmän tai sovelluksen. Järjestelmä tukee yksittäisiä käyttäjiä ja ryhmiä.
- Roolit määritetään **Rooli**-sarakkeessa.
- Valitse sarakkeen otsikko, jos haluat lajitella tulokset kyseisen sarakkeen arvon mukaan.
- Etsi tietyt käyttäjät sivun yläosassa olevan **Hae**-kentän avulla.


[!INCLUDE [footer-include](includes/footer-banner.md)]
