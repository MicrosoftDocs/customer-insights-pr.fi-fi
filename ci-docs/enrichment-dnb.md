---
title: Yritysprofiilien rikastaminen Dun & Bradstreetin avulla (esiversio)
description: Yleisiä tietoja Dun & Bradstreetin kolmannen osapuolen rikastamisesta.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 71b35e4295e19c13edadc6548ac79715555e8183
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196022"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Yritysprofiilien rikastaminen Dun & Bradstreetin avulla (esiversio)

Dun & Bradstreet tarjoaa liikeyrityksille merkityksellisiä kaupallisia tietoja, analyyseja ja oivalluksia. Sen avulla voidaan täydentää niiden asiakkaiden tietoja, joilla on yhtenäiset asiakasprofiilit yrityksissä. Rikastamiseen sisältyy määritteitä, kuten DUNS-numerolla, yrityksen koolla, sijainnilla, toimialalla ja muilla tiedoilla.

## <a name="prerequisites"></a>edellytykset

- Aktiivinen [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) -käyttöoikeus.
- Yritysten [Unified customer profile](customer-profiles.md) -profiilit.
- Määritetty Dun & Bradstreet [-projekti](#set-up-your-dun--bradstreet-project).
- Järjestelmänvalvoja on [määrittänyt](#configure-a-connection-for-dun--bradstreet) Dun & Bradstreet -[yhteyden](connections.md).

## <a name="set-up-your-dun--bradstreet-project"></a>Dun & Bradstreet -projektin määrittäminen

Voit määrittää projektin Dun & Bradstreetin käyttöoikeuden omistavana käyttäjänä [Dun & Bradstreet Connectissa](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Kirjaudu [Dun & Bradstreet Connectiin](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Jos haluat hakea tunnistetiedot, [palauta salasanasi](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Lataa [CSV-mallitiedosto](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv), jonka avulla Customer Insights -kentät yhdistetään vastaaviin Dun & Bradstreet -kenttiin.

1. Lataa tiedosto Dun & Bradstreet -projektin luontikokemuksen **Lataa tiedot** -vaiheessa.

1. Näet käytettävissä olevat vaihtoehdot valitsemalla vaakapisteet sopivan **lähteen** alla juuri luodussa Dun & Bradstreet -projektissa.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Näyttökuva Dun & Bradstreet -projektin pisteistä.":::

1. Valitse **Hae S3-tiedot**. Tallenna nämä tiedot turvalliseen paikkaan. Tarvitset sen, jotta voit [määrittää yhteyden rikastusta varten](#configure-a-connection-for-dun--bradstreet) Customer Insightsissa.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Näyttökuva Dun & Bradstreet -projektin s3-tietojen valinnasta.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Yhteyden määrittäminen Dun & Bradstreetia varten

Määrittäjän on oltava Customer Insightsin [järjestelmänvalvoja](permissions.md#admin), jolla on Dun & Bradstreet Connectin tunnistetiedot.

1. Valitse **Lisää yhteys** rikastusta määrittäessä tai valitse ensin **Järjestelmänvalvoja** > **Yhteydet** ja sitten **Määritä** Dun & Bradstreet -ruudussa.

1. Anna yhteyden nimi.

1. Anna kelvolliset Dun & Bradstreet -tunnukset sekä Dun & Bradstreet -projektin tiedot *Alue, pudotuskansiopolku ja pudotuskansion nimi*. [Saat nämä tiedot](#set-up-your-dun--bradstreet-project) Dun & Bradstreet -projektista.

1. Tarkista [Tietojen yksityisyys ja vaatimustenmukaisuus](#data-privacy-and-compliance) -kohta ja hyväksy se valitsemalla **Hyväksyn**.

1. Tarkista määritys valitsemalla **Vahvista** ja valitse sitten **Tallenna**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet -yhteyden määrittämissivu.":::

### <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Dun & Bradstreetiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää tällaiset tiedot ohjeittesi mukaisesti, mutta olet vastuussa siitä, että Dun & Bradstreet täyttää tietosuoja- ja tietoturvavaatimukset. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.

## <a name="supported-countries-or-regions"></a>Tuetut maat tai alueet

Tällä hetkellä tuetaan seuraavia maita tai alueita: Kanada (englanti) tai Yhdysvallat (englanti).

## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.

1. Valitse **Rikasta tiedot** Dun & Bradstreet -ruudun **Yrityksen tiedot** -kohdassa.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Näyttökuva Dun & Bradstreet -ruudusta.":::

1. Tutustu yleiskatsaukseen ja valitse **Seuraava**.

1. Valitse yhteys ja vahvista valinta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Valitse **Seuraava**.

1. Valitse ensin **Asiakkaan tietojoukko** ja sitten Dun & Bradstreet -yritystietojen avulla rikastettava profiili tai segmentti. *Asiakas*-entiteetti rikastaa kaikkia asiakasprofiileja, kun taas segmentti rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

1. Määritä, mitä yhdistettyjen profiilien kenttätyyppejä käytetään vastaavien Dun & Bradstreet -yritystietojen etsimiseen. Vähintään yksi kenttä seuraavista vaaditaan: **Nimi ja osoite**, **Puhelin** tai **Sähköposti**.

1. Valitse **Seuraava**

1. Yhdistä kentät Dun & Bradstreet -yritystietoihin. Joko **DUNS-numero** tai **Yrityksen nimi**- ja **Maa**-kentät ovat pakollisia.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet -kentänyhdistämismääritysruutu.":::

1. Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**.

1. Anna **Nimi** rikastamista varten ja **Tulosentiteetin nimi**.

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.

1. Aloita rikastamisprosessi valitsemalla **Suorita** tai sulje ja palaa **Rikastukset**-sivulle.

## <a name="view-enrichment-results"></a>Rikastamisen tulosten tarkasteleminen

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Seuraavat vaiheet

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
