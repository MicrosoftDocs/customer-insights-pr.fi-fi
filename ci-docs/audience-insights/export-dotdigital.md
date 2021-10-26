---
title: Customer Insightsin tietojen vieminen DotDigitaliin
description: Tietoja yhteyden määrittämisestä ja viennistä DotDigitaliin.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e3a79603f9f5746ee176d3d4299a30510c7459e
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618379"
---
# <a name="export-segments-to-dotdigital-preview"></a>Segmenttien vieminen DotDigitaliin (esiversio)

Vie yhtenäistettyjen asiakasprofiilien segmentit DotDigital-osoitekirjoihin ja käytä niitä kampanjoissa, sähköpostimarkkinoinnissa ja asiakassegmenttien muodostamisessa DotDigitalin kanssa. 

## <a name="prerequisites-for-a-connection"></a>Yhteyden edellytykset

-   Sinulla on [DotDigital-tili](https://dotdigital.com/) ja olet luonut [ohjelmointirajapintakäyttäjän](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user). Yhteyden luomiseksi tarvitset ohjelmointirajapintakäyttäjän valtuustiedot
-   DotDigitalissa on aiemmin luotuja osoitekirjoja ja vastaavia tunnuksia. Tunnus saadaan URL-osoitteesta, kun valitset ja avaat osoitekirjan. Lisätietoja on kohdassa [DotDigital-osoitekirjat](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään miljoona asiakasprofiilia DotDigital-vientiä kohden.
- DotDigital-vienti on rajoitettu segmentteihin.
- Miljoona asiakasprofiilia sisältävä segmenttien vienti voi kestää kolme tuntia palveluntarjoajan päässä olevien rajoitusten vuoksi. 
- DotDigitaliin vietävien asiakasprofiilien määrä riippuu DotDigital-sopimuksestasi ja sen sisältämistä rajoituksista.

## <a name="set-up-connection-to-dotdigital"></a>Määritä yhteys DotDigitaliin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **DotDigital**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna **DotDigitalin ohjelmointirajapinnan käyttäjänimi ja salasana**. 

1. Anna **[DotDigital-osoitekirjan tunnus](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Käynnistä DotDigital-yhteys valitsemalla **Yhdistä**.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**. 

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys DotDigital-osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.


1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta. Toimi samalla tavalla muiden valinnaisten kenttien osalta. Näitä kenttiä ovat esimerkiksi **Etunimi**, **Sukunimi**, **Koko nimi**, **Sukupuoli** ja **Postinumero**.

1. Valitse segmentit, jotka haluat viedä. Voit viedä yhteensä enintään 1 000 000 asiakasprofiilia DotDigitaliin.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 
 
DotDigitalissa voi etsiä nyt segmenttejä [DotDigital-osoitekirjoissa](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys DotDigitaliin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että DotDigital noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
