---
title: Rikasta asiakasprofiileja Experian-ratkaisun demografisten tietojen avulla (esiversio)
description: Yleisiä tietoja kolmannen osapuolen Experian-rikastamisesta.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fccb37cde3f05a70009c18b6c52db01a5ede094d
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237992"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Rikasta asiakasprofiileja Experian-ratkaisun demografisten tietojen avulla (esiversio)

Experian on maailmanlaajuinen johtaja asiakas- ja yritysluottojen raportointi- ja markkinointipalveluiden tarjoamisessa. Experian-ratkaisun tietojen rikastamisen palvelujen avulla voit parantaa tietämystä asiakkaista rikastamalla asiakasprofiileja käyttämällä demografisia tietoja, kuten talouden kokoa ja tuloja.

## <a name="supported-countriesregions"></a>Tuetut maat ja alueet

Tällä hetkellä tuemme asiakasprofiilien rikastamista vain Yhdysvalloissa.

## <a name="prerequisites"></a>edellytykset

- Aktiivinen Experian-tilaus. Jos haluat tehdä tilauksen, [ota yhteyttä suoraan Experian-ratkaisuun](https://www.experian.com/marketing-services/contact). [Lisätietoja Experian-ratkaisun tietojen rikastamisesta](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Järjestelmänvalvoja on [määrittänyt](#configure-the-connection-for-experian) Experian-[yhteyden](connections.md).

- Experianin luoman SSH-valmiin ST (suojattu siirto) -tilin Experian-käyttäjätunnus, -osapuolitunnus ja -mallinumero.

## <a name="configure-the-connection-for-experian"></a>Yhteyden määrittäminen Experianiin

Määrittäjän on oltava Customer Insightsin [järjestelmänvalvoja](permissions.md#admin), jolla on Experianin käyttäjätunnus, osapuolitunnus ja mallinumero.

1. Valitse **Lisää yhteys**, kun rikastamista määritetään, tai valitse ensin **Järjestelmänvalvoja** > **Yhteydet** ja valitse **Määritä** Experian-ruudussa.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian-yhteyden määritysruutu.":::

1. Anna yhteyden nimi sekä Experianin ST-tilin käyttäjätunnus, osapuolitunnus ja mallinumero.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Tarkista määritys valitsemalla **Vahvista** ja valitse sitten **Tallenna**.

## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.

1. Valitse Experian-ruudun **Demografiatiedot**-kohdassa **Rikasta tiedot**.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian-ruutu rikastamisen yleiskatsaussivulla":::

1. Tutustu yleiskatsaukseen ja valitse **Seuraava**.

1. Valitse yhteys. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Valitse **Seuraava**.

1. Valitse ensin **Asiakkaan tietojoukko** ja sitten Experianin demografiatietojen avulla rikastettava profiili tai segmentti. *Asiakas*-entiteetti rikastaa kaikkia asiakasprofiileja, kun taas segmentti rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Näyttökuva asiakastietojoukon valitsemisesta.":::

1. Määritä, mitä yhdistettyjen profiilien kenttätyyppejä käytetään vastaavien Experianin demografiatietojen etsimiseen. Vähintään yksi kenttä seuraavista vaaditaan: **Nimi ja osoite**, **Puhelin** tai **Sähköposti**. Vastaavuutta voi parantaa lisäämällä muita kenttiä. Valitse **Seuraava**.

1. Yhdistä kentät Experianin demografiatietoihin.

1. Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**.

1. Anna **Nimi** rikastamista varten ja **Tulosentiteetin nimi**.

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.

1. Aloita rikastamisprosessi valitsemalla **Suorita** tai sulje ja palaa **Rikastukset**-sivulle.

## <a name="view-enrichment-results"></a>Rikastamisen tulosten tarkasteleminen

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Rikastettujen asiakkaiden määrä kentän mukaan** antaa mahdollisuuden porautua kuhunkin rikastettuun kenttään.

## <a name="next-steps"></a>Seuraavat vaiheet

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
