---
title: Käyttöoikeuksien hallinta
description: Tietoja käyttöoikeuksista ja käyttäjärooleista.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760369"
---
# <a name="user-permissions"></a>Käyttäjien käyttöoikeudet

**Käyttöoikeudet**-sivulla määritetään käyttäjäryhmän merkityksellisten tietojen rooli ja käyttöoikeudet.

Sivun näyttämiseen tarvitaan järjestelmänvalvojan käyttöoikeudet. Voit siirtyä käyttäjäryhmän merkityksellisten tietojen käyttöoikeussivulle valitsemalla **Hallinta** > **Käyttöoikeudet**.

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
- Täydennä *Tietojen yhdistäminen*-osat (**Vastaavuus**, **Täsmäyttäminen** ja **Yhdistäminen**). joiden tuloksena saadaan yhdistetty asiakasprofiilientiteetti.
- Määritä **suhteet** ja **aktiviteetit**.
- Luo segmenttejä **Segmentit**-sivun avulla.
- Luo mittareita **Mittarit**-sivun avulla.
- Hallitse määrityksiä ja täydennä asiakasprofiilit **Täydennä**-sivulla (vain ensimmäisen osapuolen täydennykset).
- Hallitse ja luo vientejä osallistujien kanssa jaettujen yhteyksien perusteella. [Lisätietoja siitä, miten järjestelmänvalvojat voivat sallia osallistujien käyttää yhteyttä vienneissä.](connections.md#allow-contributors-to-use-a-connection-for-exports)

## <a name="administrator"></a>Järjestelmänvalvoja

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

## <a name="assign-roles-and-permissions"></a>Delegoi roolit ja oikeudet

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Käyttöoikeudet**

1. Avaa **Lisää tai muokkaa oikeuksia** -ruutu valitsemalla **Lisää käyttäjiä**.

1. Etsi **Hae**-kentän avulla Azure Active Directoryn käyttäjä tai ryhmä, jonka käyttöoikeuksia haluat muokata. Valitse **Rooli**, joka liitetään käyttäjälle tai ryhmälle.

1. Valitse **Tallenna**. Nykyinen ympäristö jaetaan automaattisen sen käyttäjän tai niiden ryhmän jäsenten kanssa, joiden käyttöoikeuksia on muutettu. Käyttäjät voivat käyttää Customer Insights -sovellusta ja käyttää sitä määritetyn roolinsa mukaisesti.

## <a name="view-current-permissions"></a>Tarkastele nykyisiä oikeuksia

Valitsemalla käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Käyttöoikeudet** näet, mitkä roolimääritykset ovat aktiivisia.

- **Tyyppi**-sarake määrittää yhden käyttäjän, ryhmän tai sovelluksen. Järjestelmä tukee yksittäisiä käyttäjiä ja ryhmiä.
- Roolit määritetään **Rooli**-sarakkeessa.
- Valitse sarakkeen otsikko, jos haluat lajitella tulokset kyseisen sarakkeen arvon mukaan.
- Etsi tietyt käyttäjät sivun yläosassa olevan **Hae**-kentän avulla.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
