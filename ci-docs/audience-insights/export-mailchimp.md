---
title: Customer Insightsin tietojen vieminen Mailchimpiin
description: Tietoja yhteyden määrittämisestä MailChimpiin.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598197"
---
# <a name="connector-for-mailchimp-preview"></a>Mailchimp-yhdistin (esiversio)

Uutiskirjeiden ja sähköpostikampanjoiden luonti viemällä yhtenäistettyjä asiakasprofiilisegmenttejä Mailchimpiin.

## <a name="prerequisites"></a>Edellytykset

-   [Mailchimp-tili](https://mailchimp.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
-   Mailchimpissa on aiemmin luotuja käyttäjäryhmiä ja vastaavia tunnuksia. Lisätietoja on kohdassa [Mailchimp-käyttäjäryhmät](https://mailchimp.com/help/create-audience/).
-   [Segmentit on määritetty](segments.md)
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="connect-to-mailchimp"></a>Yhdistä Mailchimpiin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.

1. Valitse **Mailchimp**-kohdassa **Määritä**.

1. Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Käynnistä yhteys Mailchimpiin antamalla **[Mailchimp-käyttäjäryhmän tunnus](https://mailchimp.com/help/find-audience-id/)** ja valitsemalla **Yhdistä**.

1. Valitse **Todenna Mailchimpin avulla** ja anna Mailchimp-tunnistetiedot.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Näyttökuva viennin MailChimp-yhteydestä":::

1. Määritä vienti valitsemalla **Next**.

## <a name="configure-the-connector"></a>Yhdistimen määrittäminen

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa. 

1. Vaihtoehtoisesti voit viedä **Etunimi**- ja **Sukunimi**-kentät lisäkenttinä, joiden avulla sähköposteja voidaan mukauttaa. Yhdistä nämä kenttä valitsemalla **Lisää määrite**.

1. Valitse segmentit, jotka haluat viedä. Voit viedä yhteensä enintään 1 000 000 asiakasprofiilia MailChimpiin.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Mailchimpiin vietävien kenttien ja segmenttien valitseminen":::

1. Valitse **Tallenna**.

## <a name="export-the-data"></a>Tietojen vieminen

Voit [viedä tietoja tarvittaessa](export-destinations.md). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä. Mailchimpin segmentit ovat nyt [Mailchimp-käyttäjäryhmissä](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään 1 miljoona profiilia kussakin Mailchimp-viennissä.
- MailChimp-vienti on rajoitettu segmentteihin
- Yhteensä 1 miljoonan profiilin segmenttien vienti voi kestää kolme tuntia palveluntoimittajan rajoitusten vuoksi. 
- Mailchimpiin vietävien profiilien määrä määräytyy Mailchimp-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Mailchimpiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Mailchimp noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]