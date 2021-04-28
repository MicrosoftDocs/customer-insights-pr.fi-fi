---
title: Rikastaminen kolmannen osapuolen Experian-rikastamisella
description: Yleisiä tietoja kolmannen osapuolen Experian-rikastamisesta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896369"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Asiakasprofiilien rikastaminen Experianin demografiatiedoilla (esiversio)

Experian on maailman johtava kuluttaja- ja yritysluottojen raportointi- ja markkinointipalvelujen toimittaja. Experianin tietojen rikastamispalveluilla voidaan syventää tietoja asiakkaista rikastamalla asiakasprofiileja demografiatiedoilla, kuten sillä, minkä kokoinen talous on kyseessä ja minkälaiset tulot sillä on käytettävissä.

## <a name="prerequisites"></a>Edellytykset

Experianin määrittäminen edellyttää seuraavien edellytysten toteutumista:

- Aktiivinen Experian-tilaus. Tilaus tehdään suoraan [Experianilta](https://www.experian.com/marketing-services/contact). [Lisätietoja Experianin tietojen rikastamisesta](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Järjestelmänvalvoja on jo määrittänyt Experian-yhteyden *tai* sinulla on [järjestelmänvalvojan](permissions.md#administrator) käyttöoikeudet. Tarvitset myös käyttäjätunnuksen, osapuolen tunnuksen ja mallinumeron sinulle luomallesi SSH-yhteensopivalle Secure Transport (ST) -tilille, jonka Experian loi.

## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.

1. Valitse Experian-ruudussa **Rikasta tietojani**.

   > [!div class="mx-imgBorder"]
   > ![Experian-ruutu](media/experian-tile.png "Experian-ruutu")
   > 

1. Valitse [yhteys](connections.md) avattavasta luettelosta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä. Jos olet järjestelmänvalvoja, voit luoda yhteyden valitsemalla **Lisää yhteys** ja valitsemalla avattavasta valikosta Experian. 

1. Vahvista valinta valitsemalla **Yhdistä Experianiin**.

1.  Valitse **Seuraava** ja valitse **Asiakastietojoukko**, jonka haluat rikastaa Experianin demografiatiedoilla. Voit valita **asiakasentiteetin**, joka rikastaa kaikkia asiakasprofiileja, tai segmenttientiteetin, joka rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Näyttökuva asiakastietojoukon valitsemisesta.":::

1. Valitse **Seuraava** ja määritä, mitä yhtenäisten profiilien kenttätyyppejä pitäisi käyttää Experianin vastaavien demografiatietojen etsimiseen. Vähintään yksi kenttä seuraavista vaaditaan: **Nimi ja osoite**, **Puhelin** tai **Sähköposti**. Jotta vastineen tarkkuus olisi suurempi, voit lisätä enintään kaksi muuta kenttää. Valinta vaikuttaa seuraavassa vaiheessa käytettävissä oleviin yhdistämiskenttiin.

    > [!TIP]
    > Mitä enemmän avaintunnisteiden määritteitä lähetetään Experianiin, sitä korkeampi vastaavuusaste on.

1. Aloita kentän vastaavuusmääritys valitsemalla **Seuraava**.

1. Määritä, mitä yhtenäisten profiilien kenttiä pitäisi käyttää Experianin vastaavien demografiatietojen etsimiseen. Pakolliset kentät on merkitty.

1. Anna rikastuksen ja tulosentiteetin nimi.

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.

## <a name="configure-the-connection-for-experian"></a>Experian-yhteyden määrittäminen 

Yhteyksien määrittämiseen tarvitaan järjestelmänvalvojan oikeudet. Valitse rikastusta määritettäessä **Lisää yhteys** *tai* siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja valitse Experian-ruudussa **Määritä**.

1. Valitse **Aloita**.

1. Kirjoita yhteyden nimi **Näyttönimi**-ruutuun.

1. Anna Experianin Secure Transport -tilisi voimassa oleva käyttäjätunnus, osapuolitunnus ja mallinumero.

1. Tarkista tiedot ja hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu

1. Tarkista määritys valitsemalla **Tarkista**.

1. Kun tarkistus on suoritettu, valitse **Tallenna**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian-yhteyden määritysruutu.":::

## <a name="enrichment-results"></a>Rikastamisen tulokset

Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**. Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana. Käsittelyaika määräytyy asiakastietojen koon ja Experianin tilille määrittämän rikastamisprosessin perusteella.

Kun rikastamisprosessi on valmis, voit tarkastella juuri rikastettujen asiakasprofiilien tietoja valitsemalla **Omat rikastukset**. Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.

Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.

## <a name="next-steps"></a>Seuraavat vaiheet

Voit hyödyntää rikastettuja asiakastietoja. Voit antaa asiakkaille mukautettuja kokemuksia luomalla [segmenttejä](segments.md) ja [mittoja](measures.md) sekä [viemällä tietoja](export-destinations.md).

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Experianiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Experian noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
