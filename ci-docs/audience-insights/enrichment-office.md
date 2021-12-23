---
title: Täydennä asiakasprofiileja Microsoft Office 365 -tietojen avulla
description: Voit täydentää asiakasprofiilejasi Microsoft Office -sitouttamistietojen avulla.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a30e09b5ed491c8d36019b5f0d35e0a2f7a0199c
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/03/2021
ms.locfileid: "7889750"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Täydennä asiakasprofiileja vuorovaikutustietojen avulla (esiversio)

Microsoft Office 365 -tietojen avulla voit täydentää asiakastiliprofiileja tiedoilla vuorovaikutuksista Office 365 -sovelluksissa. Seurantatiedot muodostuvat sähköposti- ja kokousaktiviteetista, jotka kootaan asiakastasolla. Esimerkiksi yritystilin sähköpostiviestien määrä tai asiakkaan tapaamisten määrän. Yksittäisten käyttäjien tietoja ei ole saatavilla. 

Tämä toiminto on saatavana seuraavilla alueilla: Yhdistynyt kuningaskunta, Eurooppa, Pohjois-Amerikka.

## <a name="prerequisites"></a>edellytykset

Jotta voit määrittää rikastuksen, seuraavien edellytysten on täytyttävä:

- Tarvitset aktiivisen Office 365 -pilvikäyttöoikeuden.
- Sinulla on [yhtenäiset asiakasprofiilit](customer-profiles.md), jotka perustuvat [yritysasiakkuuksiin](work-with-business-accounts.md).
- Customer Insights -ympäristöön on liitettävä [Microsoft Dataverse -organisaatio](create-environment.md#step-3-connect-to-microsoft-dataverse).
- [Järjestelmänvalvojan](permissions.md#administrator) käyttöoikeudet.
- Sinulla on tai voit saada Office 365 -vuokraajasi järjestelmänvalvojalta luvan käyttää Office 365 -tietoja **organisaation tietojen** tarjoamiseen Dynamics 365 -sovelluksissa.

## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Rikastaminen**.

1. Siirry **Etsi**-välilehteen ja valitse **Asiakaan vuorovaikutus** -ruudussa **Tietojen rikastaminen**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Asiakkaan vuorovaikutus -ruutu.":::
   
1. Valitse **Yleiskatsaus**-vaiheessa **Seuraava** ja kirjoita organisaation sähköpostiosoitteet, joista Office-tiedot kootaan. Vain luettelossa mainituista sähköpostiosoitteista peräisin olevan tieto käsitellään. Paras käytäntö on käyttää sähköpostiryhmiä, kuten *Suomen myyntitiimi*, jota on helppo hallita Office 365:ssä. Ryhmien sähköpostiosoitteiden määrä selvitetään ja näytetään. Sähköpostiosoitteiden kokonaismäärän on oltava vähintään 2 eikä se saa olla suurempi kuin 2 500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Asiakkaan vuorovaikutus -sähköpostiosoitteet.":::

1. Tarkista hyväksyntälauseke, valitse **Hyväksyn**-valintaruutu ja valitse sitten **Seuraava**.

1. Valitse asiakastietojoukko ja valitse **Seuraava**.

1. Yhdistä yhteyshenkilön sähköpostiosoitekenttä ja valitse **Seuraava**.

1. Tarkista täydennysmääritys, anna täydennystä varten nimi ja tallenna täydennys valitsemalla **Tallenna rikastus**.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 -vuokraajan järjestelmänvalvojan hyväksyntä

Office 365 -vuokraajan järjestelmänvalvojan hyväksyntä vaaditaan, jotta täydennys voidaan aktivoida. Office 365 -vuokraajan järjestelmänvalvojille lähetetään sähköposti, kun täydennys tallennetaan. Sähköposti pyytää heitä tarkistamaan ja sallimaan Dynamics 365 -sovellusten käyttää yrityksen Office 365 -tietoja **organisaationäkemyksien** tarjoamiseen. Office 365 -vuokraajan järjestelmänvalvoja voi hyväksyä myös suoraan Office 365 -hallintakonsolissa valitsemalla **Organisaation tiedot**.

## <a name="running-the-enrichment-for-the-first-time"></a>Rikastuksen suorittaminen ensimmäisen kerran

Kun täydennys käynnistetään ensimmäisen kerran sen jälkeen, kun Office 365 -vuokraajan järjestelmänvalvoja on antanut hyväksynnän, tiedot ladataan Office 365:stä. Tämä voi kestää jonkin aikaa. Ensimmäinen rikastus suoritetaan kuuden tunnin viiveellä. Voit nähdä, kuinka monta päivää tiedot kattavat tilitietojen lisäämisen yleiskuvaussivulla rikastuksen valmistumisen jälkeen. Jos tietomäärä on suuri, suorita rikastus uudelleen muutaman päivän kuluttua. Se varmistaa, että tiedot ovat valmiina koko aikaväliltä, joka on yksi vuosi.

Aloita prosessi valitsemalla Asiakkaan vuorovaikutus -määrityssivulla **Suorita**. Voit lisäksi jättää rikastamisen suoritettavaksi automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana. Täydennys suoritetaan oletusarvoisesti kerran viikossa.

Office-tietojen määrän mukaan rikastuksen suorittaminen voi kestää useita tunteja.

Kun suoritat täydennystä, Microsoft käsittelee tiedot Office 365 -yhteensopivuusrajan sisällä ja luo koostetut oivallukset, jotka lisätään Customer Insights -ympäristöön. Henkilötasolla (esimerkiksi sähköpostiviestien tai kalenterikutsujen teksti) ei ole tietoja, jotka olisivat Customer Insightsin käyttäjien käytettävissä. 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Rikastamisen tulokset

Kun täydennysprosessi on käynnissä, tarkista täydennystulokset **Omat rikastukset** -kohdassa. Näet rikastettujen asiakkaiden kokonaismäärän ja yleiskatsauksen rikastustuloksista. Se sisältää käsiteltyjen sähköpostiviestien ja kokousten määrän, tietojen koontipäivien määrän ja paljon muuta.

Näet myös kaavion, jossa on rikastettujen asiakkaiden määrä ajan kuluessa sekä rikastustietojen esikatselu.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Tulosten esikatselu rikastamisprosessin suorittamisen jälkeen.":::

Kaikki tiedot kootaan asiakastasolla. Järjestelmä laskee kunkin tilin seurantapisteet välillä 0–100. Seurantapisteet mittaavat tilin vuorovaikutusta sähköpostiviestien ja kokousten suhteen suhteessa muihin tileihin. Seuraavassa luettelossa on koostettu tiedot, jotka asiakkaan vuorovaikutuksen rikastus tarjoaa:



| Tiedot                                                                              | Sarakkeen nimi                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Seurantapisteet                                                                  |  EngagementScore                         |
| Asiakkaalle lähetettyjen sähköpostiviestien määrä                                                       |  NoOfEmails_ToAccount                    |
| Asiakkaalta lähetettyjen sähköpostiviestien määrä                                                     |  NoOfEmails_FromAccount                  | 
| Asiakkaan käynnistämien kokousten määrä                                           |  NoOfMeetings_FromAccount                | 
| Organisaatiosi käynnistämien kokousten määrä                                 |  NoOfMeetings_ToAccount                  | 
| Organisaatiosi henkilöiden määrä kokouksissa asiakkaan kanssa                  |  NoOfContactsInvolved_Meetings           | 
| Organisaatiosi henkilöiden määrä sähköpostikeskusteluissa asiakkaan kanssa       |  NoOfContactsInvolved_Emails             | 
| Asiakkaan henkilöiden määrä kokouksissa organisaatiosi kanssa                  |  NoOfAccountContactsInvolved_Meetings    | 
| Asiakkaan henkilöiden määrä sähköpostikeskusteluissa organisaatiosi kanssa       |  NoOfAccountContactsInvolved_Emails      | 
| Vuorovaikutuksen alkamispäivä (ensimmäinen sähköpostiviesti tai kokous datassa)                        |  EngagementStartDate                     | 
| Päivää viimeisestä sähköpostiviestistä                                                             |  DaysSinceLastEmail                      | 
| Päivää viimeisestä kokouksesta                                                           |  DaysSinceLastMeeting                    | 
| Kokousten keskimääräinen kesto                                                      |  AverageDuration_Of_Meetings             | 
| Asiakkaan sähköpostivastauksen keskimääräinen kesto                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Koostamisen aloituspäivämäärä                                                            |  AggregationStartDate                    | 
| Koostamistaso (vuosi, kuukausi tai viikko)                                          |  AggregationLevel                        | 


Tarkista rikastetut tiedot valitsemalla esikatseluosasta **Näytä lisää**. Se avaa *Office*-kohteen. Voit myös löytää entiteetin **Tiedot** > **Entiteetit** --kohdan **Rikastus**-ryhmän luettelosta. Löydät myös *Office_UserEntity*-kohteen, joka sisältää rikastuksen määrityksen yhteydessä valittujen sähköpostiosoitteiden Active Directory -tunnukset 

## <a name="see-enrichment-data-on-the-customer-card"></a>Rikastamistietojen tarkasteleminen asiakaskortissa

Asiakkaan vuorovaikutusta voidaan tarkastella myös yksittäisissä asiakaskorteissa. Valitse ensin **Asiakkaat** ja sitten asiakasprofiili. Asiakaskortista näet asiakkaan seurantapisteet, sähköpostiviestien kokonaismäärän ja edellisen vuoden aikana järjestettyjen kokousten kokonaismäärän. Löydät myös kaavioita, jotka näyttävät sähköposti- ja kokoushistorian.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Asiakaskortin rikastetut tiedot.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Segmenttien ja toimenpiteiden luominen rikastettujen tietojen perusteella

Rikastettujen tietojen avulla voidaan luoda segmenttejä ja mittareita alla kuvatuilla tavalla. Esimerkiksi segmentti, joka sisältää kaikki asiakkaat, joilla on yli 60 päivän arvo *edellisen sähköpostin jälkeen* ja *edellisen kokouksen jälkeen*. Tämä segmentti sisältää passiivisia tilejä, joita voit yrittää aktivoida uudelleen. 

## <a name="next-steps"></a>Seuraavat vaiheet

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
