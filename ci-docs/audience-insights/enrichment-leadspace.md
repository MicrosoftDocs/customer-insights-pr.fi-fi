---
title: Yritysprofiilien rikastaminen kolmannen osapuolen Leadspace-rikastamisella
description: Yleisiä tietoja kolmannen osapuolen Leadspace-rikastamisesta.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269418"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Yritysprofiilien täydentäminen Leadspacen avulla (esikatselu)

Leadspace on tietotekniikkayritys, joka tarjoaa yritysten välisten asiakastietojen ympäristön. Sen avulla voidaan täydentää niiden asiakkaiden tietoja, joilla on yhtenäiset asiakasprofiilit yrityksissä. Rikastamiset sisältävät lisämääritteitä, kuten yrityksen koko, sijainti ja toimiala.

## <a name="prerequisites"></a>Edellytykset

Voit määrittää Leadspacen, jos seuraavat edellytykset täyttyvät:

- Aktiivinen Leadspace-käyttöoikeus ja pysyvä avain (johon viitataan **Leadspace-tunnuksena**). Saat lisätietoja tuotteesta ottamalla yhteyttä suoraan [Leadspaceen](https://www.leadspace.com/products/leadspace-on-demand/).
- [Järjestelmänvalvojan](permissions.md#administrator) käyttöoikeudet.
- Sinulla on [yhtenäiset asiakasprofiilit](customer-profiles.md) yrityksiä varten.

## <a name="configuration"></a>Määritys

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Rikastaminen**.

1. Valitse **Rikasta tietojani** Leadspace-ruudussa.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Näyttökuvassa Leadspace-ruutu":::

1. Valitse **Aloita** ja anna sitten aktiivinen **Leadspace-tunnus** (pysyvä avain). Tarkista tiedot ja hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu. Vahvista molemmat syötteet valitsemalla **Yhdistä Leadspaceen**.

1. Valitse **Yhdistä tiedot** ja valitse sitten tietojoukko, jota haluat rikastaa Leadspacen yritystiedoilla. Voit valita *asiakasentiteetin*, joka rikastaa kaikkia asiakasprofiileja, tai segmenttientiteetin, joka rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Valitse asiakasprofiilin tai segmentin rikastaminen.":::

1. Valitse **Seuraava** ja määritä, mitä yhtenäisten profiilien kenttiä käytetään vastaavien yritystietojen hakemiseen Leadspacesta. **Yrityksen nimi** on pakollinen kenttä. Tarkkuutta voi parantaa lisäämällä enintään kaksi muuta kenttää: **Yrityksen verkkosivusto** ja **Yrityksen sijainti**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace-kentän yhdistämismääritysruutu":::
   
1. Viimeistele kentän yhdistämismääritys valitsemalla **Käytä**.

1. Valitse **Suorita**, jos haluat täydentää yritysprofiileja. Rikastamisen kesto määräytyy yhtenäisten asiakasprofiilien määrän mukaan.

## <a name="enrichment-results"></a>Rikastamisen tulokset

Kun rikastaminen on päivitetty, voit tarkastella uusia rikastettuja yritystietoja [Omat rikastukset](enrichment-hub.md) -kohdassa. Voit etsiä viimeisimmän päivityksen ajankohdan ja täydennettyjen profiilien määrän.

Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.

Lisätietoja on kohdassa [Leadspacen ohjelmointirajapinnat](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Seuraavat vaiheet

Voit hyödyntää rikastettuja asiakastietoja. Voit antaa asiakkaille mukautettuja kokemuksia luomalla [segmenttejä](segments.md) ja [mittoja](measures.md) sekä [viemällä tietoja](export-destinations.md).

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Leadspaceen otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Leadspace noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.


[!INCLUDE[footer-include](../includes/footer-banner.md)]