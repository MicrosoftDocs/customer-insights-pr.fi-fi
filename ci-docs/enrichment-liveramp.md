---
title: LiveRamp-tunnistetietojen rikastus
description: Täydennä asiakasprofiileja LiveRamp-tietojen avulla.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0727818f6df565d9a031966a68d521ae7167e484
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646088"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Täydennä asiakasprofiileja LiveRamp-tunnistetietojen avulla (esiversio) 

LiveRamp mahdollistaa offline-tunnistetietojen deterministisen ratkaisun ja asiakastietojen yhdistämisen. Voit liittää asiakastiedoissa olevia henkilökohtaisia tunnisteita AbiliTec-tunnistetietokaavioon ja vastaanottaa AbiliTec-tunnuksia. Sen jälkeen kyseisiä tunnuksia voi käyttää asiakastietojen aiempaa parempaa yhdistämistä varten. 

## <a name="prerequisites"></a>edellytykset 

Jotta voit määrittää rikastuksen, seuraavien edellytysten on täytyttävä: 

- Sinulla on aktiivinen LiveRamp-tilaus. Hanki tilaus ottamalla yhteyttä LiveRamp-asiakasryhmään tai lähetä sähköpostia osoitteeseen [dynamics@liveramp.com](mailto:dynamics@liveramp.com), niin saat lisätietoja.   

- Aktiivinen AbiliTec-tilaus, asiakastunnus ja salainen koodi, jonka avulla voi käyttää ohjelmointirajapintaa. Lisätietoja: [AbiliTec-ohjelmointirajapintakehittäjäkeskus](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Tuetut maat ja alueet 

Tällä hetkellä tuemme asiakasprofiilien rikastamista LiveRamp-tietojen avulla vain Yhdysvalloissa. 

## <a name="configure-the-enrichment"></a>Määritä rikastus 

1. Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti. 

1. Valitse **Rikasta tiedot** **Tunnistetiedot**-ruudussa. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Tunnistetietoruutu rikastamisen yleiskuvaussivulla. ":::

1. Valitse [yhteys](connections.md) avattavasta luettelosta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä. Jos olet järjestelmänvalvoja, voit luoda yhteyden valitsemalla **Lisää yhteys**. Valitse **LiveRamp** avattavasta luettelosta. 

1. Valitse **Seuraava** ja valitse **Asiakkaan tietojoukko**, jota haluat rikastaa LiveRamp-tunnistetietojen avulla. Voit valita *asiakasentiteetin*, joka rikastaa kaikkia asiakasprofiileja, tai *segmenttientiteetin*, joka rikastaa vain segmenttiin sisältyviä asiakasprofiileja. 

1. Valitse **Seuraava** ja määritä, minkätyyppisiä yhdistettyjen profiilien kenttiä käytetään vastaavien LiveRamp-tunnistetietojen etsimiseen. Vähintään yksi kentistä **Nimi ja osoite**, **Puhelinnumero** tai **Sähköposti** on pakollinen. 

   > [!TIP]
   > Mitä enemmän avaintunnuksia ja kenttiä yhdistät, sitä todennäköisempää on, että vastineiden määrä on parempi 

1. Liitä kentät yhdistetystä *Asiakas*-entiteetistä, jota käytetään vastaavuuteen LiveRampin AbiliTec-tunnuskaavion kanssa. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Tietojen yhdistämisen asetukset LiveRamp-rikastusta varten.":::

1. Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**. 

1. Anna **Nimi** rikastusta ja **Tulosentiteettiä** varten. 

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot. 

## <a name="configure-the-connection-for-liveramp"></a>LiveRamp-yhteyden määrittäminen 

Sinun on oltava järjestelmänvalvoja, jotta voit [määrittää yhteydet](connections.md). Valitse **Lisää yhteys** määrittäessäsi rikastusta tai siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja valitse **Määritä** **LiveRamp**-ruudussa. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Määritysruutu, jota käytetään määritettäessä yhteyttä LiveRamp AbiliTec -palveluun. ":::

1. Syötä **Näyttönimi**-kohtaan yhteyden nimi. 

1. Anna kelvollinen LiveRamp-asiakastunnus ja salainen koodi. 

1. Tarkista tiedot ja hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu. 

1. Tarkista määritys valitsemalla **Tarkista**. 

1. Viimeistele yhteys valitsemalla **Tallenna**. 

## <a name="enrichment-results"></a>Rikastamisen tulokset 

Aloita rikastamisprosessi valitsemalla komentopalkissa Suorita. Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana. Käsittelyaika riippuu asiakastietojen koosta. 

Kun rikastusprosessi on valmis, voit tarkastaa rikastetut asiakasprofiilit kohdassa **Omat rikastukset**. Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä. 

Voit tarkastella kunkin rikastetun profiilin yksityiskohtaista näkymää valitsemalla **Näytä rikastetut** tiedot. 

## <a name="next-steps"></a>Seuraavat vaiheet

Voit hyödyntää rikastettuja asiakastietoja. Käyitä AbiliTec-tunnuksia asiakasprofiilien yhdistämiseksi henkilöpohjaiseen näkymään. 
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus 

Kun tietojen lähetys LiveRampiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää tällaiset tiedot ohjeittesi mukaisesti, mutta olet vastuussa siitä, että LiveRamp täyttää tietosuoja- ja tietoturvavaatimukset. Lisätietoja: [Microsoft-tietosuojatiedot](https://go.microsoft.com/fwlink/?linkid=396732). Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä. 


[!INCLUDE [footer-include](includes/footer-banner.md)]
