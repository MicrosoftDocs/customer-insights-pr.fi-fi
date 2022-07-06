---
title: Yritysprofiilien rikastaminen Leadspacen avulla (esiversio)
description: Yleisiä tietoja kolmannen osapuolen Leadspace-rikastamisesta.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b58532a541ee22a5e34d0af1a3334ccbd53627b2
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081039"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Yritysprofiilien rikastaminen Leadspacen avulla (esiversio)

Leadspace on datatiedeyritys, joka tarjoaa yritystenvälisen asiakastietoympäristön. Sen avulla ympäristöt, joilla on asiakkaisiin perustuvat yhtenäiset asiakasprofiilit, voivat rikastaa tietojaan. Rikasta *Asiakasprofiilit* määritteillä kuten yrityksen koko, sijainti tai toimiala. Rikasta *Yhteishenkilöprofiilit* määritteillä kuten titteli, henkilötyyppi tai sähköpostin vahvistus.

## <a name="prerequisites"></a>edellytykset

- Aktiivinen Leadspace-käyttöoikeus.
- Tileihin perustuvat [Unified customer profile](customer-profiles.md) -profiilit.
- Järjestelmänvalvoja on [määrittänyt](#configure-the-connection-for-leadspace) Leadspace-[yhteyden](connections.md). Jos haluat lisätietoja tuotteesta, ota suoraan yhteyttä [Leadspaceen](https://www.leadspace.com/leadspace-microsoft-dynamics-365/).

## <a name="configure-the-connection-for-leadspace"></a>Leadspace-yhteyden määrittäminen

Määrittäjän on oltava Customer Insightsin [järjestelmänvalvoja](permissions.md#admin), jolla on jatkuva avain (jota kutsutaan **Leadspace-tunnukseksi**).

1. Valitse rikastusta määritettäessä **Lisää yhteys** tai valitse ensin **Järjestelmänvalvoja** > **Yhteydet** ja sitten Leadspace-ruudussa **Määritä**.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace-yhteyden määrityssivu.":::

1. Anna yhteydelle nimi ja kelvollinen Leadspace-tunnus.

1. Tarkista [Tietojen yksityisyys ja vaatimustenmukaisuus](#data-privacy-and-compliance) -kohta ja hyväksy se valitsemalla **Hyväksyn**.

1. Tarkista määritys valitsemalla **Vahvista** ja valitse sitten **Tallenna**.

### <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Leadspaceen otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Leadspace noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.

## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.

1. Valitse **Rikasta tiedot** Leadspace-ruudun **Yrityksen tiedot** -kohdassa.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Näyttökuvassa Leadspace-ruutu":::

1. Tutustu yleiskatsaukseen ja valitse **Seuraava**.

1. Valitse yhteys. Jos yhteyttä ei ole, ota yhteys järjestelmänvalvojaan.

1. Valitse **Seuraava**.

1. Valitse ensin **Asiakkaan tietojoukko** ja sitten Leadspacen yrityksen tietojen avulla rikastettava profiili tai segmentti. *Asiakas*-entiteetti rikastaa kaikkia asiakasprofiileja, kun taas segmentti rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Näyttökuva asiakastietojoukon valitsemisesta.":::

1. Määritä vastaavuuksien etsinnässä käytettävien yhdistettyjen profiilien kenttätyypit: ensisijainen ja/tai toissijainen osoite. Voit määrittää kenttien yhdistämismäärityksen molemmille osoitteille että rikastaa profiileja molemmille osoitteille erikseen. Esimerkissä koti- ja työosoite. Valitse **Seuraava**.

1. Yhdistä kentät Leadspacen yritystietoihin. **Yrityksen nimi** on pakollinen kenttä. Tarkkuutta voi parantaa lisäämällä enintään kaksi muuta kenttää: **Yrityksen verkkosivusto** ja **Yrityksen sijainti**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace-kentän yhdistämismääritysruutu.":::

1. Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**.

1. Valitse valintaruutu, jos sinulla on *yhteyshenkilöprofiileja*, jotka haluat rikastaa. Customer Insights yhdistää pakolliset kentät automaattisesti.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Leadspace-yhteyshenkilötietueen rikastaminen.":::

1. Valitse **Seuraava**.

1. Anna **Nimi** rikastamista varten ja **Tulosentiteetin nimi**.

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.

1. Aloita rikastamisprosessi valitsemalla **Suorita** tai sulje ja palaa **Rikastukset**-sivulle.

## <a name="view-enrichment-results"></a>Rikastamisen tulosten tarkasteleminen

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Lisätietoja on kohdassa [Leadspacen ohjelmointirajapinnat](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Seuraavat vaiheet

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
