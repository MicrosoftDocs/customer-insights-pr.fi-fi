---
title: Asiakasprofiilien rikastaminen LiveRamp-tunnistetietojen avulla (esiversio)
description: Täydennä asiakasprofiileja LiveRamp-tietojen avulla.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 49bf558209ca91ab9d8db945862a57adccee1f6b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196344"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Asiakasprofiilien rikastaminen LiveRamp-tunnistetietojen avulla (esiversio)

LiveRamp mahdollistaa offline-tunnistetietojen deterministisen ratkaisun ja asiakastietojen yhdistämisen. Voit liittää asiakastiedoissa olevia henkilökohtaisia tunnisteita AbiliTec-tunnistetietokaavioon ja vastaanottaa AbiliTec-tunnuksia. Sen jälkeen kyseisiä tunnuksia voi käyttää asiakastietojen aiempaa parempaa yhdistämistä varten.

## <a name="supported-countriesregions"></a>Tuetut maat ja alueet

Tällä hetkellä tuemme asiakasprofiilien rikastamista LiveRamp-tietojen avulla vain Yhdysvalloissa.

## <a name="prerequisites"></a>edellytykset

- Aktiivinen LiveRamp-tilaus. Hanki tilaus ottamalla yhteyttä LiveRamp-asiakasryhmään tai lähetä sähköpostia osoitteeseen [dynamics@liveramp.com](mailto:dynamics@liveramp.com), niin saat lisätietoja.

- Aktiivinen AbiliTec-tilaus, asiakastunnus ja salainen koodi, jonka avulla voi käyttää ohjelmointirajapintaa. Lisätietoja: [AbiliTec-ohjelmointirajapintakehittäjäkeskus](https://developers.liveramp.com/abilitec-api/).

- Järjestelmänvalvoja on [määrittänyt](#configure-the-connection-for-liveramp) LiveRamp-[yhteyden](connections.md).

## <a name="configure-the-connection-for-liveramp"></a>LiveRamp-yhteyden määrittäminen

Määrittäjän on oltava Customer Insightsin [järjestelmänvalvoja](permissions.md#admin), jolla on aktiivinen LiveRamp-asiakastunnus ja salainen koodi.

1. Valitse **Lisää yhteys** rikastuksen määrityksen yhteydessä tai valitse **Järjestelmänvalvoja** > **Yhteydet** ja valitse sitten **Määritä** LiveRamp-ruudussa.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Määritysruutu, jota käytetään määritettäessä yhteyttä LiveRamp AbiliTec -palveluun. ":::

1. Anna yhteyden nimi sekä kelvollinen LiveRamp-asiakastunnus ja salainen koodi.

1. Tarkista [Tietojen yksityisyys ja vaatimustenmukaisuus](#data-privacy-and-compliance) -kohta ja hyväksy se valitsemalla **Hyväksyn**.

1. Tarkista määritys valitsemalla **Vahvista** ja valitse sitten **Tallenna**.

### <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys LiveRampiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää tällaiset tiedot ohjeittesi mukaisesti, mutta olet vastuussa siitä, että LiveRamp täyttää tietosuoja- ja tietoturvavaatimukset. Lisätietoja: [Microsoft-tietosuojatiedot](https://go.microsoft.com/fwlink/?linkid=396732). Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.

## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.

1. Valitse LiveRamp-ruudun **Tunnistetiedot**-kohdassa **Rikasta tiedot**.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Tunnistetietoruutu rikastamisen yleiskuvaussivulla. ":::

1. Tutustu yleiskatsaukseen ja valitse **Seuraava**.

1. Valitse yhteys. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Valitse **Seuraava**.

1. Valitse ensin **Asiakkaan tietojoukko** ja sitten LiveRamp-tunnistetietojen avulla rikastettava profiili tai segmentti. *Asiakas*-entiteetti rikastaa kaikkia asiakasprofiileja, kun taas segmentti rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

1. Määritä, mitä yhdistettyjen profiilien kenttätyyppejä käytetään vastaavien LiveRamp-tunnistetietojen etsimiseen. Vähintään jokin kentistä **Nimi ja osoite**, **Sähköposti** tai **Puhelin** on pakollinen. Vastaavuutta voi parantaa lisäämällä muita kenttiä. Valitse **Seuraava**.

1. Yhdistä kentät LiveRamp-tunnistetietoihin.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Tietojen yhdistämisen asetukset LiveRamp-rikastusta varten.":::

1. Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**.

1. Anna **Nimi** rikastamista varten ja **Tulosentiteetin nimi**.

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.

1. Aloita rikastamisprosessi valitsemalla **Suorita** tai sulje ja palaa **Rikastukset**-sivulle.

## <a name="view-enrichment-results"></a>Rikastamisen tulosten tarkasteleminen

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Rikastettujen asiakkaiden määrä kentän mukaan** antaa mahdollisuuden porautua kuhunkin rikastettuun kenttään.

## <a name="next-steps"></a>Seuraavat vaiheet

Voit hyödyntää rikastettuja asiakastietoja. Käyitä AbiliTec-tunnuksia asiakasprofiilien yhdistämiseksi henkilöpohjaiseen näkymään.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
