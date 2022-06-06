---
title: Customer Insights -tietojen vieminen SendGridiin
description: Tietoja yhteyden määrittämisestä ja viennistä SendGridiin.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 38dd782fdf06d5970e79e6deb6e8fc94252da585
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646334"
---
# <a name="export-segments-to-sendgrid-preview"></a>Segmenttien vieminen SendGridiin (esiversio)

Vie yhdistettyjen asiakasprofiilien segmentit SendGridin yhteyshenkilöluetteloihin ja käytä niitä SendGridin kampanjoissa ja sähköpostimarkkinoinnissa. 

## <a name="prerequisites-for-a-connection"></a>Yhteyden edellytykset

-   [SendGrid-tili](https://sendgrid.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
-   SendGridissa on aiemmin luotuja yhteyshenkilöluetteloja ja vastaavia tunnuksia. Lisätietoja on kohdassa [SendGrid - yhteyshenkilöiden hallinta](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Olet [määrittänyt segmenttejä](segments.md) Customer Insightsissa.
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään 100 000 asiakasprofiilia SendGridiin.
- SendGrid-vienti on rajoitettu segmentteihin.
- Enintään 100 000 asiakasprofiilin vieminen SendGridiin voi kestää muutaman tunnin. 
- SendGridiin vietävien asiakasprofiilien määrä riippuu SendGrid-sopimuksestasi ja sen sisältämistä rajoituksista.

## <a name="set-up-connection-to-sendgrid"></a>Määritä yhteys SendGridiin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **SendGrid**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna **SendGridin ohjelmointirajapinnan avain** [SendGridin ohjelmointirajapinnan avain](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Käynnistä SendGrid-yhteys valitsemalla **Yhdistä**.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys SendGrid-osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Anna **[SendGrid-luettelon tunnus](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta. Toimi samalla tavalla muiden valinnaisten kenttien osalta. Näitä kenttiä ovat esimerkiksi **Etunimi**, **Sukunimi**, **Maa/alue**, **Osavaltio**, **Kaupunki** ja **Postinumero**.

1. Valitse segmentit, jotka haluat viedä. On erittäin **suositeltavaa, että asiakastietueita viedään enintään 100 000** SendGridiin. 

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys SendGridiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että SendGrid noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.


[!INCLUDE [footer-include](includes/footer-banner.md)]