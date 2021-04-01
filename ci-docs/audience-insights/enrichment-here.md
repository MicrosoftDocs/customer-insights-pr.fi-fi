---
title: Rikastaminen kolmannen osapuolen HERE Technologies -rikastamisella
description: Yleisiä tietoja HERE Technologiesin kolmannen osapuolen rikastamisesta.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597737"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Asiakasprofiilien rikastaminen HERE Technologiesin avulla (esiversio)

HERE Technologies on sijaintitietoyritys, joka toimittaa sijaintitietoja ja -palveluja. HERE Technologiesin tietojen rikastamispalveluilla voi muodostaa tarkemman asiakkaiden sijaintitietoisuuden esimerkiksi osoitteen normalisoinnin sekä leveys- ja pituusastetietojen poiminnan avulla.

## <a name="prerequisites"></a>Edellytykset

HERE Technologiesin rikastamisen määrittämiselle on seuraavat edellytykset:

- Aktiviinen HERE Technologies -tilaus. Voit tehdä tilauksen [rekisteröitymällä täällä](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) tai ottamalla suoraan [yhteyttä HERE Technologiesiin](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Lisätietoja HERE Technologiesin sijaintitietojen rikastamisesta.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE Technologies -ohjelmointirajapinnan avain.

- [Järjestelmänvalvojan](permissions.md#administrator) käyttöoikeudet.

## <a name="configuration"></a>Määritys

1. Siirry kohtaan **Tiedot** > **Täydentäminen**.

1. Valitse **Rikasta tietojani** HERE Technologies -ruudussa.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies -ruutu](media/HERE-tile.png "HERE Technologies -ruutu")

1. Anna aktiivinen **HERE Technologies -ohjelmointirajapinnan avain**. Tarkista tiedot ja hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu. 

1. Vahvista molemmat syötteet valitsemalla **Yhdistä HERE-palveluun**.

1.  Valitse **Lisää tiedot** ja valitse sitten **Asiakastietojoukko**, jota haluat rikastaa HERE Technologies -ratkaisun sijaintitiedoilla. Voit valita **asiakasentiteetin**, joka rikastaa kaikkia asiakasprofiileja, tai segmenttientiteetin, joka rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Näyttökuva asiakastietojoukon valitsemisesta.":::

1. Määritä, yhdistetäänkö kentät ensi- ja/tai toissijaiseen osoitteeseen. Voit määrittää kummankin osoitteen (kuten koti- ja työosoitteen) kentän yhdistämismäärityksen ja rikastaa profiileja molemmilla osoitteilla erikseen. Valitse **Seuraava**.

1. Määritä, mitä yhtenäistettyjen profiilien kenttiä käytetään hakemaan vastaavia sijaintitietoja HERE Technologies -palvelusta. **Lähiosoite 1** ja **Postinumero** ovat pakollisia kenttiä valitussa ensi- ja/tai toissijaisen osoitteessa. Vastaavuuden tarkkuutta voi parantaa lisäämällä kenttiä.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies -rikastamisen määrityssivu](media/enrichment-HERE-configuration.png "HERE Technologies -rikastamisen määrityssivu")

1. Viimeistele kentän yhdistämismääritys valitsemalla **Käytä**.

## <a name="enrichment-results"></a>Rikastamisen tulokset

Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**. Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana. Käsittelyaika määräytyy asiakastietojen koon ja ohjelmointirajapinnan HERE Technologies -vasteajan mukaan.

Kun rikastamisprosessi on valmis, voit tarkastella juuri rikastettujen asiakasprofiilien tietoja valitsemalla **Omat rikastukset**. Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.

Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.

## <a name="next-steps"></a>Seuraavat vaiheet

Voit hyödyntää rikastettuja asiakastietoja. Voit antaa asiakkaille mukautettuja kokemuksia luomalla [segmenttejä](segments.md) ja [mittoja](measures.md) sekä [viemällä tietoja](export-destinations.md).

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys HERE Technologiesiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että HERE Technologies noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.


[!INCLUDE[footer-include](../includes/footer-banner.md)]