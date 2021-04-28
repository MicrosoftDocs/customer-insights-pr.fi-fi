---
title: Yritysprofiilien rikastaminen kolmannen osapuolen Leadspace-rikastamisella
description: Yleisiä tietoja kolmannen osapuolen Leadspace-rikastamisesta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895909"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Yritysprofiilien täydentäminen Leadspacen avulla (esikatselu)

Leadspace on tietotekniikkayritys, joka tarjoaa yritysten välisten asiakastietojen ympäristön. Sen avulla voidaan täydentää niiden asiakkaiden tietoja, joilla on yhtenäiset asiakasprofiilit yrityksissä. Rikastuksissa on enemmän määritteitä, kuten esim. yrityksen koko, sijainti ja toimiala.

## <a name="prerequisites"></a>Edellytykset

Voit määrittää Leadspacen, jos seuraavat edellytykset täyttyvät:

- Sinulla on aktiivinen Leadspace-käyttöoikeus.
- Sinulla on [yhtenäiset asiakasprofiilit](customer-profiles.md) yrityksiä varten.
- Leadspace-yhteys on jo määritetty järjestelmänvalvojan toimesta tai sinulla on [järjestelmänvalvojan](permissions.md#administrator) oikeudet ja "pysyvä avain" (**Leadspace-tunnus**). Jos haluat lisätietoja tuotteesta, ota suoraan yhteyttä [Leadspaceen](https://www.leadspace.com/products/leadspace-on-demand/).

## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Rikastaminen**.

1. Valitse Leadspace-ruudussa **Rikasta tietojani** ja valitse **Aloita**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Näyttökuvassa Leadspace-ruutu":::

1. Valitse [yhteys](connections.md) avattavasta luettelosta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä. Jos olet järjestelmänvalvoja, voit luoda yhteyden valitsemalla **Lisää yhteys** ja sitten **Leadspace**. 

1. Vahvista yhteys valitsemalla **Yhdistä Leadspaceen**.

1. Valitse **Seuraava** ja valitse **Asiakastietojoukko**, jonka haluat rikastaa Leadspacen yritystiedoilla. Voit valita **asiakasentiteetin**, joka rikastaa kaikkia asiakasprofiileja, tai segmenttientiteetin, joka rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Näyttökuva asiakastietojoukon valitsemisesta.":::

1. Valitse **Seuraava** ja määritä, mitä yhtenäisten profiilien kenttiä käytetään Leadspacen vastaavien yritystietojen etsimiseen. **Yrityksen nimi** on pakollinen kenttä. Tarkkuutta voi parantaa lisäämällä enintään kaksi muuta kenttää: **Yrityksen verkkosivusto** ja **Yrityksen sijainti**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace-kentän yhdistämismääritysruutu":::

1. Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**.

1. Anna rikastusta varten nimi ja valitse vaihtoehtojen tarkistamisen jälkeen **Tallenna rikastus**.


## <a name="configure-the-connection-for-leadspace"></a>Leadspace-yhteyden määrittäminen 

Yhteyksien määrittämiseen tarvitaan järjestelmänvalvojan oikeudet. Valitse rikastusta määritettäessä **Lisää yhteys** *tai* siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja valitse Leadspace-ruudussa **Määritä**.

1. Valitse **Aloita** 

1. Kirjoita yhteyden nimi **Näyttönimi**-ruutuun.

1. Anna voimassa oleva Leadspace-tunnus.

1. Tarkista tiedot ja hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu

1. Tarkista määritys valitsemalla **Tarkista**.

1. Kun tarkistus on suoritettu, valitse **Tallenna**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace-yhteyden määrityssivu.":::

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
