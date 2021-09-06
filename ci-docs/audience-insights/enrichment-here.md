---
title: Rikastaminen kolmannen osapuolen rikastamisen HERE Technologies -ratkaisun avulla
description: Yleisiä tietoja HERE Technologiesin kolmannen osapuolen rikastamisesta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: be0ac9fa29ce1569d06e4e539e95824c0a3ada4dcf49802c2b574e9d91730630
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032570"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Asiakasprofiilien rikastaminen HERE Technologiesin avulla (esiversio)

HERE Technologies on sijaintitietoyritys, joka toimittaa sijaintitietoja ja -palveluja. HERE Technologiesin tietojen rikastamispalveluilla voi muodostaa tarkemman asiakkaiden sijaintitietoisuuden esimerkiksi osoitteen normalisoinnin sekä leveys- ja pituusastetietojen poiminnan avulla.

## <a name="prerequisites"></a>Edellytykset

HERE Technologiesin rikastamisen määrittämiselle on seuraavat edellytykset:

- Aktiviinen HERE Technologies -tilaus. Voit tehdä tilauksen [rekisteröitymällä täällä](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) tai ottamalla suoraan [yhteyttä HERE Technologiesiin](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Lisätietoja HERE Technologiesin sijaintitietojen rikastamisesta.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- [HERE-yhteys](connections.md) on käytettävissä *tai* sinulla on [järjestelmänvalvojan](permissions.md#administrator) oikeudet ja HERE Technologies -ohjelmointirajapinnan avain.

## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Siirry kohtaan **Tiedot** > **Täydentäminen**. 

1. Valitse HERE Technologies -ruudussa **Rikasta tietojani** ja valitse **Aloita**.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies -ruutu.](media/HERE-tile.png "HERE Technologies -ruutu")

1. Valitse [yhteys](connections.md) avattavasta luettelosta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä. Jos olet järjestelmänvalvoja, voit luoda yhteyden valitsemalla **Lisää yhteys**. Valitse avattavasta luettelosta **HERE Technologies**. 

1. Vahvista valinta valitsemalla **Yhdistä HERE Technologiesiin**.

1.  Valitse **Seuraava** ja valitse **Asiakastietojoukko**, jonka haluat rikastaa HERE Technologiesin sijaintitiedoilla. Voit valita **asiakasentiteetin**, joka rikastaa kaikkia asiakasprofiileja, tai segmenttientiteetin, joka rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Näyttökuva asiakastietojoukon valitsemisesta.":::

1. Määritä, yhdistetäänkö kentät ensi- ja/tai toissijaiseen osoitteeseen. Voit määrittää kenttien yhdistämismäärityksen molemmille osoitteille että rikastaa profiileja molemmille osoitteille erikseen. Jos esimerkiksi on koti- ja yritysosoite. Valitse **Seuraava**.

1. Määritä, mitä yhtenäistettyjen profiilien kenttiä käytetään hakemaan vastaavia sijaintitietoja HERE Technologies -palvelusta. **Lähiosoite 1** ja **Postinumero** ovat pakollisia kenttiä valitussa ensi- ja/tai toissijaisen osoitteessa. Vastaavuuden tarkkuutta voi parantaa lisäämällä kenttiä.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies -rikastamisen määrityssivu.](media/enrichment-HERE-configuration.png "HERE Technologies -rikastamisen määrityssivu")

1. Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**.

1. Kirjoita rikastuksen nimi. 

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.

## <a name="configure-the-connection-for-here-technologies"></a>HERE Technologies -yhteyden määrittäminen 

Yhteyksien määrittämiseen tarvitaan järjestelmänvalvojan oikeudet. Valitse rikastusta määritettäessä **Lisää yhteys** *tai* siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja valitse HERE Technologies -ruudussa **Määritä**.

1. Kirjoita yhteyden nimi **Näyttönimi**-ruutuun.

1. Anna kelvollinen HERE Technologiesin API-avain.

1. Tarkista **Tietojen yksityisyys ja vaatimustenmukaisuus** -kohta ja hyväksy se valitsemalla **Hyväksyn**.

1. Tarkista määritys valitsemalla **Tarkista**.

1. Kun tarkistus on suoritettu, valitse **Tallenna**.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies -yhteyden määrityssivu.](media/enrichment-HERE-connection.png "HERE Technologies -yhteyden määrityssivu")

## <a name="enrichment-results"></a>Rikastamisen tulokset

Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**. Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana. Käsittelyaika määräytyy asiakastietojen koon ja ohjelmointirajapinnan HERE Technologies -vasteajan mukaan.

Kun rikastamisprosessi on valmis, voit tarkastella juuri rikastettujen asiakasprofiilien tietoja valitsemalla **Omat rikastukset**. Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.

Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.

## <a name="next-steps"></a>Seuraavat vaiheet

Voit hyödyntää rikastettuja asiakastietoja. Voit luoda [segmenttejä](segments.md) ja [mittareita](measures.md) ja jopa [viedä tietoja](export-destinations.md), jos haluat tarjota asiakkaille mukautettuja käyttökokemuksia.

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys HERE Technologiesiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että HERE Technologies noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
