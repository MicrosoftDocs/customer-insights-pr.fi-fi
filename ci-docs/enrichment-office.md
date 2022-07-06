---
title: Asiakasprofiilien rikastaminen Microsoft Office 365 -tietojen avulla (esiversio)
description: Voit täydentää asiakasprofiilejasi Microsoft Office -sitouttamistietojen avulla.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 75762afb70814c8a81c1574ee7ea1553a2048737
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055670"
---
# <a name="enrich-customer-profiles-with-data-from-microsoft-office-365-preview"></a>Asiakasprofiilien rikastaminen Microsoft Office 365 -tietojen avulla (esiversio)

Microsoft Office 365 -tietojen avulla voit täydentää asiakastiliprofiileja tiedoilla vuorovaikutuksista Office 365 -sovelluksissa. Seurantatiedot muodostuvat sähköposti- ja kokousaktiviteetista, jotka kootaan asiakastasolla. Esimerkiksi yritystilin sähköpostiviestien määrä tai asiakkaan tapaamisten määrän. Yksittäisten käyttäjien tietoja ei ole saatavilla.

## <a name="supported-countries-or-regions"></a>Tuetut maat tai alueet

Tällä hetkellä tuetaan seuraavia alueita: UK, Eurooppa, Pohjois-Amerikka.

## <a name="prerequisites"></a>edellytykset

- Aktiivinen Office 365 -pilvikäyttöoikeus.
- [Yritystileihin](work-with-business-accounts.md) perustuvat [yhdistetyt asiakasprofiilit](customer-profiles.md).
- Customer Insights -ympäristöön liitetty [Microsoft Dataverse -organisaatio](create-environment.md#step-3-connect-to-microsoft-dataverse).
- [Järjestelmänvalvojan](permissions.md#admin) oikeudet.
- Office 365 -vuokraajan järjestelmänvalvoja on hyväksynyt Office 365 -tietojen käyttämisen tuottamaan **organisaation merkityksellisiä tietoja** Dynamics 365 -sovelluksissa.

## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.

1. Valitse **Rikasta tiedot** **Tilin osallistaminen** -ruudussa.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Asiakkaan vuorovaikutus -ruutu.":::

1. Tutustu yleiskatsaukseen ja valitse **Seuraava**.

1. Anna organisaation sähköpostiosoitteet, joista Office-tiedot kootaan. Vain luettelossa mainituista sähköpostiosoitteista peräisin olevan tieto käsitellään. Paras käytäntö on käyttää sähköpostiryhmiä, kuten *Suomen myyntitiimi*, jota voi hallita Office 365:ssä. Ryhmien sähköpostiosoitteiden määrä selvitetään ja näytetään. Sähköpostiosoitteiden kokonaismäärän on oltava vähintään 2 eikä se saa olla suurempi kuin 2 500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Asiakkaan vuorovaikutus -sähköpostiosoitteet.":::

1. Tutustu [Office 365 -vuokraajan järjestelmänvalvojan suostumukseen](#office-365-tenant-administrator-consent) ja hyväksy se valitsemalla **Hyväksyn**.

1. Valitse **Seuraava**.

1. Valitse ensin **Yhteyshenkilön tietojoukko** ja sitten rikastettava profiili. Valitse **Seuraava**.

1. Yhdistä yhteyshenkilön sähköpostiosoitekenttä ja valitse **Seuraava**.

1. Anna **Nimi** rikastusta ja **Tulosentiteettiä** varten.

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.

1. Palaa **Rikastamiset**-sivulle valitsemalla **Sulje**.

### <a name="office-365-tenant-administrator-consent"></a>Office 365 -vuokraajan järjestelmänvalvojan hyväksyntä

Office 365 -vuokraajan järjestelmänvalvojan hyväksyntä vaaditaan, jotta täydennys voidaan aktivoida. Office 365 -vuokraajan järjestelmänvalvojille lähetetään sähköposti, kun täydennys tallennetaan. Sähköposti pyytää heitä tarkistamaan ja sallimaan Dynamics 365 -sovellusten käyttää yrityksen Office 365 -tietoja **organisaationäkemyksien** tarjoamiseen. Office 365 -vuokraajan järjestelmänvalvoja voi hyväksyä myös suoraan Office 365 -hallintakonsolissa valitsemalla **Organisaation tiedot**.

## <a name="running-the-enrichment-for-the-first-time"></a>Rikastuksen suorittaminen ensimmäisen kerran

Kun täydennys käynnistetään ensimmäisen kerran sen jälkeen, kun Office 365 -vuokraajan järjestelmänvalvoja on antanut hyväksynnän, tiedot ladataan Office 365:stä. Tämä voi kestää jonkin aikaa. Ensimmäinen rikastus suoritetaan kuuden tunnin viiveellä. Voit nähdä, kuinka monta päivää tiedot kattavat tilitietojen lisäämisen yleiskuvaussivulla rikastuksen valmistumisen jälkeen. Jos tietomäärä on suuri, suorita rikastus uudelleen muutaman päivän kuluttua. Se varmistaa, että tiedot ovat valmiina koko aikaväliltä, joka on yksi vuosi.

Office-tietojen määrän mukaan rikastuksen suorittaminen voi kestää useita tunteja.

Kun suoritat täydennystä, Microsoft käsittelee tiedot Office 365 -yhteensopivuusrajan sisällä ja luo koostetut oivallukset, jotka lisätään Customer Insights -ympäristöön. Henkilötasolla (esimerkiksi sähköpostiviestien tai kalenterikutsujen teksti) ei ole tietoja, jotka olisivat Customer Insightsin käyttäjien käytettävissä.

Aloita rikastamisprosessi valitsemalla **Suorita**.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Rikastamisen tulosten tarkasteleminen

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Tämä on *Office*-entiteetti. *Office_UserEntity* sisältää rikastuksen määrityksen yhteydessä valittujen sähköpostiosoitteiden Active Directory -tunnukset.

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

## <a name="see-enrichment-data-on-the-customer-card"></a>Rikastamistietojen tarkasteleminen asiakaskortissa

Asiakkaan vuorovaikutusta voidaan tarkastella myös yksittäisissä asiakaskorteissa. Valitse ensin **Asiakkaat** ja sitten asiakasprofiili. Asiakaskortista näet asiakkaan seurantapisteet, sähköpostiviestien kokonaismäärän ja edellisen vuoden aikana järjestettyjen kokousten kokonaismäärän. Löydät myös kaavioita, jotka näyttävät sähköposti- ja kokoushistorian.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Asiakaskortin rikastetut tiedot.":::

## <a name="next-steps"></a>Seuraavat vaiheet

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Esimerkiksi segmentti, joka sisältää kaikki asiakkaat, joilla on yli 60 päivän arvo *edellisen sähköpostin jälkeen* ja *edellisen kokouksen jälkeen*. Tämä segmentti sisältää passiivisia tilejä, joita voit yrittää aktivoida uudelleen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
