---
title: Customer Insights -tietojen vieminen SendGridiin
description: Tietoja yhteyden määrittämisestä SendGridiin.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268728"
---
# <a name="connector-for-sendgrid-preview"></a>SendGrid-yhdistin (esiversio)

Vie yhdistettyjen asiakasprofiilien segmentit SendGridin yhteyshenkilöluetteloihin ja käytä niitä SendGridin kampanjoissa ja sähköpostimarkkinoinnissa. 

## <a name="prerequisites"></a>Edellytykset

-   [SendGrid-tili](https://sendgrid.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.
-   SendGridissa on aiemmin luotuja yhteyshenkilöluetteloja ja vastaavia tunnuksia. Lisätietoja on kohdassa [SendGrid - yhteyshenkilöiden hallinta](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="connect-to-sendgrid"></a>Yhteyden muodostaminen SendGridiin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.

1. Valitse **SendGrid**-kohdassa **Määritä**.

1. Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGridin viennin määritysruutu.":::

1. Anna **SendGridin ohjelmointirajapinnan avain** [SendGridin ohjelmointirajapinnan avain](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Anna **[SendGrid-luettelon tunnus](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Käynnistä SendGrid-yhteys valitsemalla **Yhdistä**.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Määritä vienti valitsemalla **Next**.

## <a name="configure-the-connector"></a>Yhdistimen määrittäminen

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa. Toimi samalla tavalla muiden valinnaisten kenttien osalta. Näitä kenttiä ovat esimerkiksi **Etunimi**, **Sukunimi**, **Maa/alue**, **Osavaltio**, **Kaupunki** ja **Postinumero**.

1. Valitse segmentit, jotka haluat viedä. On erittäin **suositeltavaa, että asiakastietueita viedään enintään 100 000** SendGridiin. 

1. Valitse **Tallenna**.

## <a name="export-the-data"></a>Tietojen vieminen

Voit [viedä tietoja tarvittaessa](export-destinations.md). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Yhteensä enintään 100 000 profiilia SendGridiin.
- SendGrid-vienti on rajoitettu segmentteihin.
- 100 000 profiilin vieminen SendGridiin voi kestää muutaman tunnin. 
- SendGridiin vietävien profiilien määrä määräytyy SendGrid-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys SendGridiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että SendGrid noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]