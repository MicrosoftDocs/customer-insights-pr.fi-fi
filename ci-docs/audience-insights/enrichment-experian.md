---
title: Rikastaminen kolmannen osapuolen Experian-rikastamisella
description: Yleisiä tietoja kolmannen osapuolen Experian-rikastamisesta.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668806"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Asiakasprofiilien rikastaminen Experianin demografiatiedoilla (esiversio)

Experian on maailman johtava kuluttaja- ja yritysluottojen raportointi- ja markkinointipalvelujen toimittaja. Experianin tietojen rikastamispalveluilla voidaan syventää tietoja asiakkaista rikastamalla asiakasprofiileja demografiatiedoilla, kuten sillä, minkä kokoinen talous on kyseessä ja minkälaiset tulot sillä on käytettävissä.

## <a name="prerequisites"></a>Edellytykset

Experianin määrittäminen edellyttää seuraavien edellytysten toteutumista:

- Aktiivinen Experian-tilaus. Tilaus tehdään suoraan [Experianilta](https://www.experian.com/marketing-services/contact). [Lisätietoja Experianin tietojen rikastamisesta](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Sinulla on Experianin luoma SSH-yhteensopivan ST (Secure Transport) -tilin käyttäjätunnus, osapuolen tunnus ja mallinumero.
- Sinulla on käyttäjäryhmän merkityksellisten tietojen [järjestelmänvalvojan](permissions.md#administrator) oikeudet.

## <a name="configuration"></a>Määritys

1. Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.

1. Valitse Experian-ruudussa **Rikasta tietojani**.

   > [!div class="mx-imgBorder"]
   > ![Experian-ruutu](media/experian-tile.png "Experian-ruutu")

1. Valitse **Aloita** ja Experianin ST (Secure Transport) -tilin käyttäjätunnus, osapuolen tunnus ja mallinumero. Tarkista tiedot ja hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu. Vahvista kaikki syötteet valitsemalla **Käytä**:

## <a name="map-your-fields"></a>Yhdistä kenttäsi

1. Valitse **Lisää tiedot** ja valitse **Nimi ja osoite**-, **Sähköposti**- tai **Puhelin**-kohdista avaintunnisteet, jotka lähetetään Experianiin käyttäjätietojen selvitystä varten.

   > [!TIP]
   > Mitä enemmän avaintunnisteiden määritteitä lähetetään Experianiin, sitä korkeampi vastaavuusaste on.

1. Valitse **Seuraava** ja yhdistä vastaavat määritteet valittujen avaintunnistekenttien yhdistetystä asiakasentiteetistä.

1. Valitsemalla **Lisää määrite** voit yhdistää lisämääritteet, jotka halutaan lähettää Experianiin.

1.  Viimeistele kenttien yhdistäminen valitsemalla **Tallenna**.

   > [!div class="mx-imgBorder"]
   > ![Experianin kenttämääritys](media/experian-field-mapping.png "Experianin kenttämääritys")

## <a name="enrichment-results"></a>Rikastamisen tulokset

Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**. Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana. Käsittelyaika määräytyy asiakastietojen koon ja Experianin tilille määrittämän rikastamisprosessin perusteella.

Kun rikastamisprosessi on valmis, voit tarkastella juuri rikastettujen asiakasprofiilien tietoja valitsemalla **Omat rikastukset**. Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.

Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.

## <a name="next-steps"></a>Seuraavat vaiheet

Voit hyödyntää rikastettuja asiakastietoja. Voit antaa asiakkaille mukautettuja kokemuksia luomalla [segmenttejä](segments.md) ja [mittoja](measures.md) sekä [viemällä tietoja](export-destinations.md).

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Experianiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Experian noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.
