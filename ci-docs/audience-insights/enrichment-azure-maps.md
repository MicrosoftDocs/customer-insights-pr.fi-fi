---
title: Täydennä asiakasprofiileja Azure Mapsin sijaintitietojen avulla
description: Yleisiä tietoja Azure Mapsin ensisijaisesta rikastamisesta.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: cbeac7e25d83df152c38d1c59cc6734a3d1fee97
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618563"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Asiakasprofiilien täydennys Azure Mapsin avulla (esiversio)

Azure Mapsin sijaintikeskeiset tiedot ja palvelut tarjoavat käyttökokemuksia, jotka perustuvat geospatiaalisiin tietoihin ja sisäisiin sijaintitietoihin. Azure Maps -tietojen täydennyspalvelut parantavat asiakkaiden sijaintitietojen tarkkuutta. Se sisältää toimintoja, kuten osoitteen normalisoinnin sekä leveys- ja pituusasteiden purkamisen Dynamics 365 Customer Insightsiin.

## <a name="prerequisites"></a>Edellytykset

Jotta Azure Mapsin tietojen rikastus voidaan määrittää, seuraavien edellytysten on täytyttävä:

- Tarvitset aktiivisen Azure Maps -tilauksen. Jos haluat saada tilauksen, voit [rekisteröityä tai saada ilmaisen kokeiluversion](https://azure.microsoft.com/services/azure-maps/).

- Azure Maps [-yhteys](connections.md) on käytettävissä *tai* sinulla on [järjestelmänvalvojan](permissions.md#administrator) oikeudet ja aktiivinen Azure Mapsin ohjelmointirajapinnan avain.

## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Siirry kohtaan **Tiedot** > **Täydentäminen**. 

1. Valitse **Rikasta omat tiedot** **Sijainti**-ruudussa.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps -ruutu.":::

1. Valitse [yhteys](connections.md) avattavasta luettelosta. Ota yhteyttä järjestelmänvalvojaan, jos Azure Maps -yhteyttä ei ole käytettävissä. Jos olet palvelussa Järjestelmänvalvoja, voit [määrittää yhteyden Azure Mapsiin](#configure-the-connection-for-azure-maps). 

1. Vahvista valinta valitsemalla **Seuraava**.

1. Valitse **asiakas tietojoukko**, jota haluat täydentää Azure Mapsin sijaintitiedoilla. Voit rikastaa kaikkia yhtenäisiä asiakasprofiileja valitsemalla **Asiakas**-entiteetin tai valitsemalla segmenttientiteetin, joka rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Näyttökuva asiakkaan tietojoukon valitsemisesta.":::

1. Valitse, haluatko yhdistää kentät ensisijaiseen ja/tai toissijaiseen osoitteeseen. Voit määrittää kenttien yhdistämismäärityksen sekä osoitteille että täydentää profiileja molemmille osoitteille erikseen&mdash;esimerkiksi koti- ja yritysosoitteelle. Valitse **Seuraava**.

1. Määritä, mitä kenttätyyppejä yhdistetyistä profiileista käytetään etsittäessä vastaavia sijaintitietoja Azure Mapsista. **Katuosoite 1**- ja **Postinumero**-kentät ovat pakollisia valitussa ensisijaisessa tai toissijaisessa osoitteessa. Jotta vastineen tarkkuus olisi suurempi, voit lisätä kenttiä.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Azure Maps -rikastamisen määrityssivu.":::

1. Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**.

1. Tarkista, haluatko muokata **lisäasetuksia**. Niiden avulla voit käsitellä erikoiskäyttötapauksia mahdollisimman joustavasti, mutta oletusarvot ovat useimmissa tapauksissa riittävät:
   - **Osoitteiden tyyppi**: Oletusarvo on se, että rikastus palauttaa parhaan vastineen, vaikka osoite olisi puutteellinen. Jos haluat saada vain täydelliset osoitteet&mdash;esimerkiksi osoitteet, joissa on talonnumero&mdash;poista kaikki valintaruudut paitsi **Pisteosoitteet**. 
   - **Kieli**: Oletusarvon mukaan osoitteet palautetaan sen alueen kielellä, johon osoite on määritetty. Jos haluat käyttää vakiomuotoista osoitekieltä, valitse kieli avattavasta valikosta. Esimerkiksi **englannin** valitseminen palauttaa **København, Danmark** sijasta **Copenhagen, Denmark**.

1. Kirjoita rikastuksen nimi.

1. Tarkista valinnat ja valitse sitten **Tallenna rikastus**.

## <a name="configure-the-connection-for-azure-maps"></a>Azure Maps -yhteyden määrittäminen

Sinun on oltava käyttäjäryhmien merkityksellisten tietojen järjestelmänvalvoja, jotta voit määrittää yhteyksiä. Valitse **Lisää yhteys**, kun rikastamista määritetään, tai siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja valitse **Määritä** Azure Maps -ruudussa.

1. Kirjoita **Näyttönimi**-ruutuun yhteyden nimi.

1. Anna kelvollinen Azure Maps -ohjelmointirajapinnan avain.

1. Tarkista tiedot ja hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu

1. Tarkista määritys valitsemalla **Tarkista**.

1. Kun tarkistus on suoritettu, valitse **Tallenna**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Maps -yhteyden määrityssivu.":::

## <a name="enrichment-results"></a>Rikastamisen tulokset

Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**. Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana. Käsittelyaika määräytyy asiakastietojen koon ja ohjelmointirajapinnan vasteaikojen mukaan.

Kun rikastusprosessi on valmis, voit tarkistaa uudet rikastetun asiakasprofiilin tiedot kohdasta **Omat rikastukset**. Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.

Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.

## <a name="next-steps"></a>Seuraavat vaiheet

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun otat käyttöön Dynamics 365 Customer Insightsin tietojen siirtämiseksi Azure Maps -ratkaisuun, sallit tietojen siirtämisen säännöstenmukaisuuden rajan ulkopuolelle Dynamics 365 Customer Insightsissa, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilökohtaiset tiedot. Microsoft siirtää nämä tiedot pyyntösi mukaisesti, mutta olet vastuussa siitä, että Azure Maps täyttää kaikki liiketoimintaasi koskevat tietosuoja- tai tietoturvavelvoitteet. Lisätietoja on kohdassa [Microsoftin tietosuojakäytäntö](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
