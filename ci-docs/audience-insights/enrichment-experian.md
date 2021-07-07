---
title: Rikastaminen kolmannen osapuolen Experian-rikastamisen avulla
description: Yleisiä tietoja kolmannen osapuolen Experian-rikastamisesta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309816"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Rikasta asiakasprofiileja Experian-ratkaisun demografisten tietojen avulla (esiversio)

Experian on maailmanlaajuinen johtaja asiakas- ja yritysluottojen raportointi- ja markkinointipalveluiden tarjoamisessa. Experian-ratkaisun tietojen rikastamisen palvelujen avulla voit parantaa tietämystä asiakkaista rikastamalla asiakasprofiileja käyttämällä demografisia tietoja, kuten talouden kokoa ja tuloja.

## <a name="prerequisites"></a>Edellytykset

Jotta voit määrittää Experian-ratkaisun, seuraavien edellytysten on täytyttävä:

- Tarvitset aktiivisen Experian-tilauksen. Jos haluat tehdä tilauksen, [ota yhteyttä suoraan Experian-ratkaisuun](https://www.experian.com/marketing-services/contact). [Lisätietoja Experian-ratkaisun tietojen rikastamisesta](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Järjestelmänvalvoja on jo määrittänyt Experian-yhteyden *tai* sinulla on [järjestelmänvalvojan](permissions.md#administrator) oikeudet. Experian-ratkaisun luomaa SSH:ta käyttävää Secure Transport (ST) -tiliä varten tarvitaan käyttäjätunnus, osapuolen tunnus ja mallinumero.

## <a name="supported-countriesregions"></a>Tuetut maat ja alueet

Tällä hetkellä tuemme asiakasprofiilien rikastamista vain Yhdysvalloissa.

## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.

1. Valitse **Rikasta omat tiedot** Experian-ruudussa.

   > [!div class="mx-imgBorder"]
   > ![Experian muokkausta](media/experian-tile.png "Experian tile")
   > 

1. Valitse [yhteys](connections.md) avattavasta luettelosta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä. Jos olet järjestelmänvalvoja, voit luoda yhteyden valitsemalla **Lisää yhteys** ja valitsemalla sitten avattavasta luettelosta Experian-kohdan. 

1. Valitse **Muodosta yhteys Experianiin**, jos haluat vahvistaa yhteyden valinnan.

1.  Valitse **Seuraava** ja valitse sitten **Asiakkaan tietojoukko**, jos haluat rikastaa Experianin demografisia tietoja. Voit valita **asiakasentiteetin**, joka rikastaa kaikkia asiakasprofiileja, tai segmenttientiteetin, joka rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Näyttökuva asiakastietojoukon valitsemisesta.":::

1. Valitse **Seuraava** ja määritä, mitkä kenttätyyppejä yhdistetyistä profiileista käytetään etsittäessä vastaavia demografisia tietoja Experianista. Vähintään yksi kenttä seuraavista vaaditaan: **Nimi ja osoite**, **Puhelin** tai **Sähköposti**. Jotta vastineen tarkkuus olisi suurempi, voit lisätä enintään kaksi muuta kenttää. Valinta vaikuttaa seuraavassa vaiheessa käytettävissä oleviin yhdistämiskenttiin.

    > [!TIP]
    > Lisää Experianiin lähetetyt avaimen tunnisteen määritteet, jotka todennäköisesti tuottavat parhaan tuloksen.

1. Aloita kentän vastaavuusmääritys valitsemalla **Seuraava**.

1. Määritä, mitkä kenttätyyppejä yhdistetyistä profiileista käytetään etsittäessä vastaavia demografisia tietoja Experianista. Pakolliset kentät on merkitty.

1. Anna rikastuksen ja tulosentiteetin nimi.

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.

## <a name="configure-the-connection-for-experian"></a>Yhteyden määrittäminen Experianiin 

Yhteyksien määrittämiseen tarvitaan järjestelmänvalvojan oikeudet. Valitse **Lisää yhteys**, kun rikastamista määritetään, *tai* siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja valitse **Määritä** Experian-ruudussa.

1. Valitse **Aloita**.

1. Kirjoita yhteyden nimi **Näyttönimi**-ruutuun.

1. Anna sallittu käyttäjätunnus, osapuolen tunnus ja mallinumero Experianin Secure Transport -tiliä varten.

1. Tarkista **Tietojen yksityisyys ja vaatimustenmukaisuus** -kohta ja hyväksy se valitsemalla **Hyväksyn**.

1. Tarkista määritys valitsemalla **Tarkista**.

1. Kun tarkistus on suoritettu, valitse **Tallenna**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian-yhteyden määritysruutu.":::

## <a name="enrichment-results"></a>Rikastamisen tulokset

Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**. Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana. Käsittelyaika riippuu asiakastietojen koosta ja Experianin tilille määrittämistä rikastusprosesseista.

Kun rikastamisprosessi on valmis, voit tarkastella juuri rikastettujen asiakasprofiilien tietoja valitsemalla **Omat rikastukset**. Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.

Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.

## <a name="next-steps"></a>Seuraavat vaiheet

Voit hyödyntää rikastettuja asiakastietoja. Voit luoda [segmenttejä](segments.md) ja [mittareita](measures.md) ja jopa [viedä tietoja](export-destinations.md), jos haluat tarjota asiakkaille mukautettuja käyttökokemuksia.

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun otat käyttöön Dynamics 365 Customer Insightsin tietojen siirtämiseksi Experianiin, sallit tietojen siirtämisen säännöstenmukaisuuden rajan ulkopuolelle Dynamics 365 Customer Insightsissa, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilökohtaiset tiedot. Microsoft siirtää nämä tiedot pyyntösi mukaisesti, mutta olet vastuussa siitä, että Experian täyttää kaikki liiketoimintaasi koskevat tietosuoja- tai tietoturvavelvoitteet. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
