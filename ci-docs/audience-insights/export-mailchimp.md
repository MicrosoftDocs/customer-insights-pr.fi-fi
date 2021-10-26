---
title: Customer Insightsin tietojen vieminen Mailchimpiin
description: Tietoja yhteyden määrittämisestä ja viennistä Mailchimpiin.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 94a9fead56ce8c40b35d4eb41ebdc0d672798dce
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618609"
---
# <a name="export-segments-to-mailchimp-preview"></a>Segmenttien vieminen Mailchimpiin (esiversio)

Uutiskirjeiden ja sähköpostikampanjoiden luonti viemällä yhtenäistettyjä asiakasprofiilisegmenttejä Mailchimpiin.

## <a name="prerequisites-for-connection"></a>Yhteyden edellytykset

-   [Mailchimp-tili](https://mailchimp.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
-   Mailchimpissa on aiemmin luotuja käyttäjäryhmiä ja vastaavia tunnuksia. Lisätietoja on kohdassa [Mailchimp-käyttäjäryhmät](https://mailchimp.com/help/create-audience/).
-   [Segmentit on määritetty](segments.md)
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään miljoona asiakasprofiilia Mailchimp-vientiä kohden.
- MailChimp-vienti on rajoitettu segmentteihin
- Miljoona asiakasprofiilia sisältävien segmenttien vieminen voi kestää kolme tuntia. 
- Mailchimpiin vietävien asiakasprofiilien määrä riippuu Mailchimp-sopimuksestasi ja sen sisältämistä rajoituksista.

## <a name="set-up-connection-to-mailchimp"></a>Määritä yhteys Mailchimpiin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Määritä yhteys valitsemalla **Lisää yhteys**. Valitse lopuksi **Mailchimp**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Alusta yhteys Mailchimpiin valitsemalla **Yhdistä**.

1. Valitse **Todenna Mailchimpin avulla** ja anna Mailchimp-tunnistetiedot.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**. 

## <a name="configure-the-connector"></a>Yhdistimen määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot**> **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Mailchimp-osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Anna **[Mailchimp-käyttäjäryhmän tunnus](https://mailchimp.com/help/find-audience-id/)**

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta. 

1. Voit myös viedä **etunimen** ja **sukunimen** yksilöllisempien sähköpostiviestien luomiseksi. Yhdistä nämä kenttä valitsemalla **Lisää määrite**.

1. Valitse segmentit, jotka haluat viedä. Voit viedä yhteensä enintään 1 000 000 asiakasprofiilia MailChimpiin.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Mailchimpiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Mailchimp noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
