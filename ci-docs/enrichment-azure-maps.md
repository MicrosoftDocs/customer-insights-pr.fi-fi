---
title: Täydennä asiakasprofiileja Azure Mapsin sijaintitietojen avulla
description: Yleisiä tietoja Azure Mapsin ensisijaisesta rikastamisesta.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a806b2d0c791972c967c90694527608b4def9f3f
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953624"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Asiakasprofiilien täydennys Azure Mapsin avulla (esiversio)

Azure-kartat tuottaa sijaintikeskeisiä tietoja ja palveluja, joilla voidaan toteuttaa geospatiaalisiin tietoihin perustuvia, älykkäitä sijaintitietoja sisältäviä kokemuksia. Azure Maps -tietojen täydennyspalvelut parantavat asiakkaiden sijaintitietojen tarkkuutta. Se sisältää toimintoja, kuten osoitteen normalisoinnin sekä leveys- ja pituusasteiden purkamisen Dynamics 365 Customer Insightsiin.

## <a name="prerequisites"></a>edellytykset

- Aktiivinen Azure-karttojen tilaus. Tilauksen voi tehdä [rekisteröitymällä tai hakemalla ilmaisen kokeiluversion](https://azure.microsoft.com/services/azure-maps/).

- Järjestelmänvalvoja on [määrittänyt](#configure-the-connection-for-azure-maps) Azure-karttojen [yhteyden](connections.md).

## <a name="configure-the-connection-for-azure-maps"></a>Azure Maps -yhteyden määrittäminen

Määrittäjän on oltava Customer Insightsin [järjestelmänvalvoja](permissions.md#admin), jolla on aktiivinen Azure-karttojen ohjelmointirajapinnan avain.

1. Valitse **Lisää yhteys**, kun rikastamista määritetään, tai siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja valitse **Määritä** Azure Maps -ruudussa.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Maps -yhteyden määrityssivu.":::

1. Anna yhteydelle nimi ja kelvollisen Azure-karttojen ohjelmointirajapinnan avain.

1. Tarkista [Tietojen yksityisyys ja vaatimustenmukaisuus](#data-privacy-and-compliance) -kohta ja hyväksy se valitsemalla **Hyväksyn**.

1. Tarkista määritys valitsemalla **Vahvista** ja valitse sitten **Tallenna**.

### <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun otat käyttöön Dynamics 365 Customer Insightsin tietojen siirtämiseksi Azure Maps -ratkaisuun, sallit tietojen siirtämisen säännöstenmukaisuuden rajan ulkopuolelle Dynamics 365 Customer Insightsissa, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilökohtaiset tiedot. Microsoft siirtää tällaiset tiedot ohjeittesi mukaisesti, mutta olet vastuussa siitä, että Azure Maps täyttää tietosuoja- ja tietoturvavaatimukset. Lisätietoja on kohdassa [Microsoftin tietosuojakäytäntö](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.

## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.

1. Valitse Microsoft Azure -kartat -ruudun **Sijainti**-kohdassa **Rikasta tiedot**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps -ruutu.":::

1. Tutustu yleiskatsaukseen ja valitse **Seuraava**.

1. Valitse yhteys. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Valitse **Seuraava**.

1. Valitse ensin **Asiakkaan tietojoukko** ja sitten Microsoftin tietojen avulla rikastettava profiili tai segmentti. *Asiakas*-entiteetti rikastaa kaikkia asiakasprofiileja, kun taas segmentti rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

1. Määritä vastaavuuksien etsinnässä käytettävien yhdistettyjen profiilien kenttätyypit: ensisijainen ja/tai toissijainen osoite. Voit määrittää kenttien yhdistämismäärityksen molemmille osoitteille että rikastaa profiileja molemmille osoitteille erikseen. Esimerkissä koti- ja työosoite. Valitse **Seuraava**.

1. Yhdistä kentät Azure-karttojen sijaintitietoihin. **Lähiosoite 1** ja **Postinumero** ovat pakollisia kenttiä valitussa ensi- ja/tai toissijaisen osoitteessa. Vastaavuutta voi parantaa lisäämällä muita kenttiä.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Azure-karttojen määritteen yhdistämismääritys":::

1. Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**.

1. Tutustu **lisäasetuksiin**, joiden avulla voi käsitellä joustavasti haastavia käyttötapauksia. Seuraavia oletusarvoja ei kuitenkaan yleensä tarvitse muuttaa.

   - **Osoitteiden tyypit**: Palautetaan paras osoitevastine, vaikka se ei olisi täydellinen. Jos haluat saada vain täydelliset osoitteet&mdash;esimerkiksi osoitteet, joissa on talonnumero&mdash;poista kaikki valintaruudut paitsi **Pisteosoitteet**.
   - **Kieli**: Osoitteet palautetaan osoitealueeseen perustuvalla kielellä. Jos haluat käyttää vakiomuotoista osoitekieltä, valitse kieli avattavasta valikosta. Jos valinta on esimerkiksi **suomi**, tuloksena on **Kööpenhamina, Tanska** eikä **København, Danmark**.
   - **Tulosten enimmäismäärä**: osoitekohtaisten tulosten määrä.

1. Valitse **Seuraava**.

1. Anna **Nimi** rikastamista varten ja **Tulosentiteetin nimi**.

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.

1. Aloita rikastamisprosessi valitsemalla **Suorita** tai sulje ja palaa **Rikastukset**-sivulle.

## <a name="enrichment-results"></a>Rikastamisen tulokset

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Rikastettujen asiakkaiden määrä kentän mukaan** antaa mahdollisuuden porautua kuhunkin rikastettuun kenttään.

## <a name="next-steps"></a>Seuraavat vaiheet

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
