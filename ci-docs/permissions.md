---
title: Delegoidaan käyttöoikeuksia
description: Tietoja käyttöoikeuksista ja käyttäjärooleista.
ms.date: 08/08/2022
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
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245415"
---
# <a name="assign-user-permissions"></a>Delegoidaan käyttöoikeuksia

Customer Insights -tietojen käyttöoikeus rajoittuu organisaatiosi käyttäjiin, jotka järjestelmänvalvoja on lisännyt sovellukseen. Järjestelmänvalvoja voi lisätä, muokata tai poistaa käyttäjiä. Käyttäjä voi olla yksittäinen käyttäjä, ryhmä tai sovellus. Käyttäjällä voi olla kolmentyyppisiä rooleja:

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
- Täysi **Tietojen yhdistäminen**, joka johtaa yhtenäiseen profiilientiteettiin.
- Määritä **suhteet** ja **aktiviteetit**.
- Luo segmenttejä **Segmentit**-sivun avulla.
- Luo mittareita **Mittarit**-sivun avulla.
- Hallitse määrityksiä ja täydennä asiakasprofiilit **Täydennä**-sivulla (vain ensimmäisen osapuolen täydennykset).
- Hallitse ja luo vientejä [osallistujien kanssa jaettujen yhteyksien perusteella](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Järjestelmänvalvoja

- Kaikki osallistujan oikeudet.
- Muuta asetuksia **Järjestelmä**-sivulla, myös työskentelykieli, järjestelmäprosessien päivitysaikataulut ja diagnostiikkalokien vienti.
- Muuta **Suojaus**-sivun asetuksia, kuten käyttäjiä, ohjelmointirajapinnan avaimia, yksityislinkkejä ja avainsäilöä.
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

## <a name="add-users"></a>Lisää käyttäjiä

1. Siirry kohtaan **Järjestelmänvalvoja** > **Suojaus** ja valitse **Käyttäjät**-välilehti.

1. Avaa **Lisää tai muokkaa oikeuksia** -ruutu valitsemalla **Lisää käyttäjiä**.

1. Etsi **Hae**-kentän avulla Azure Active Directoryn käyttäjä tai ryhmä, jonka käyttöoikeudet haluat lisätä. Valitse **Rooli**, joka liitetään käyttäjälle tai ryhmälle.

1. Valitse **Tallenna**. Nykyinen ympäristö jaetaan automaattisesti käyttäjän tai ryhmän jäsenten kanssa. Käyttäjät voivat käyttää Customer Insights -sovellusta ja käyttää sitä määritetyn roolinsa mukaisesti.

## <a name="view-current-permissions"></a>Tarkastele nykyisiä oikeuksia

Siirry kohtaan **Järjestelmänvalvoja** > **Suojaus** ja valitse **Käyttäjät**-välilehti, kun haluat tarkastella aktiivisten käyttäjien luetteloa ja heidän roolimäärityksiään. Voit lajitella käyttäjäluettelon minkä tahansa sarakkeen mukaan tai etsiä tietyn käyttäjän hakukentän avulla.

## <a name="manage-current-users"></a>Nykyisten käyttäjien hallinta

Siirry kohtaan **Järjestelmänvalvoja** > **Suojaus** ja valitse **Käyttäjät**-välilehti. Voit lajitella käyttäjäluettelon minkä tahansa sarakkeen mukaan tai etsiä hallinnoitavan käyttäjän hakukentän avulla.

Voit tarkastella käytettävissä olevia toimintoja valitsemalla käyttäjän.

- **Muokkaa**, jos haluat muokata käyttäjän roolia Customer Insightsissa. Vahvista muutos valitsemalla **Tallenna**.
- **Poista**, jos haluat poistaa käyttäjältä Customer Insightsin käytön. Vahvista poisto valitsemalla **Poista**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
