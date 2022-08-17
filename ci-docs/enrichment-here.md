---
title: Asiakasprofiilien rikastaminen HERE Technologiesin avulla (esiversio)
description: Yleisiä tietoja HERE Technologiesin kolmannen osapuolen rikastamisesta.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237854"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Asiakasprofiilien rikastaminen HERE Technologiesin avulla (esiversio)

HERE Technologies on sijaintitietoyritys, joka toimittaa sijaintitietoja ja -palveluja. HERE Technologiesin tietojen rikastamispalvelut parantavat asiakkaita koskevien sijaintitietojen tarkkuutta. Se mahdollistaa esimerkiksi osoitteiden normalisoinnin sekä pituus- ja leveysastetietojen poimimisen.

## <a name="prerequisites"></a>edellytykset

- Aktiivinen HERE Technologies -tilaus. Tilauksen voi hankkia [rekisteröitymällä täällä](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) tai [ottamalla yhteyttä HERE Technologiesiin](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) suoraan. [Lisätietoja HERE Technologiesin sijaintitietojen rikastamisesta.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Järjestelmänvalvoja on [määrittänyt](#configure-the-connection-for-here-technologies) HERE-[yhteyden](connections.md).

## <a name="configure-the-connection-for-here-technologies"></a>HERE Technologies -yhteyden määrittäminen

Määrittäjän on oltava Customer Insightsin [järjestelmänvalvoja](permissions.md#admin), jolla on aktiivinen HERE Technologiesin ohjelmointirajapinnan avain.

1. Valitse rikastusta määritettäessä **Lisää yhteys** tai valitse ensin **Järjestelmänvalvoja** > **Yhteydet** ja sitten HERE Technologies -ruudussa **Määritä**.

1. Anna yhteydelle nimi ja kelvollisen HERE Technologiesin ohjelmointirajapinnan avain.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Tarkista määritys valitsemalla **Vahvista** ja valitse sitten **Tallenna**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="HERE Technologies -yhteyden määrityssivu.":::

## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.

1. Valitse HERE Technologies -ruudun **Sijainti**-kohdassa **Rikasta tiedot**.

   :::image type="content" source="media/HERE-tile.png" alt-text="HERE Technologies -ruutu.":::

1. Tutustu yleiskatsaukseen ja valitse **Seuraava**.

1. Valitse yhteys. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Valitse **Seuraava**.

1. Valitse ensin **Asiakkaan tietojoukko** ja sitten HERE Technologiesin tietojen avulla rikastettava profiili tai segmentti. *Asiakas*-entiteetti rikastaa kaikkia asiakasprofiileja, kun taas segmentti rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

1. Määritä vastaavuuksien etsinnässä käytettävien yhdistettyjen profiilien kenttätyypit: ensisijainen ja/tai toissijainen osoite. Voit määrittää kenttien yhdistämismäärityksen molemmille osoitteille että rikastaa profiileja molemmille osoitteille erikseen. Esimerkissä koti- ja työosoite. Valitse **Seuraava**.

1. Yhdistä kentät HERE Technologiesin tietoihin. **Lähiosoite 1** ja **Postinumero** ovat pakollisia kenttiä valitussa ensi- ja/tai toissijaisen osoitteessa. Vastaavuutta voi parantaa lisäämällä muita kenttiä.

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
