---
title: Entiteetit ja tietojoukot
description: Tietojen näyttäminen Entiteetit-sivulla.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: ac8b0671b20123091bef64e672fc53398fe8955a
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2021
ms.locfileid: "6553971"
---
# <a name="entities-in-audience-insights"></a>Käyttäjäryhmän merkityksellisten tietojen entiteetit

Kun [tietolähteet on määritetty](data-sources.md), siirry **Entiteetit**-sivulle arvioimaan käsiteltyjen tietojen laatua. Entiteettejä pidetään tietojoukkoina. Monet Dynamics 365 Customer Insights -ominaisuudet perustuvat näihin entiteetteihin. Niiden huolellinen tarkastelu voi auttaa tarkistamaan kyseisten ominaisuuksien tuloksia.

**Entiteetit**-sivulla on luettelo entiteeteistä, ja siinä on useita sarakkeita:

- **Nimi**: Tietoentiteetin nimi. Jos entiteetin nimen vieressä on varoitussymboli, kyseisen entiteetin tietojen lataus ei onnistunut.
- **Lähde**: entiteetin käsitelleen tietolähteen tyyppi.
- **Luonut**: entiteetin luoneen henkilön nimi.
- **Luotu**: entiteetin luontipäivä ja -aika.
- **Päivittäjä**: entiteetin päivittäneen henkilön nimi.
- **Viimeksi päivitetty**: entiteetin viimeisin päivityspäivä ja -aika.
- **Päivitetty viimeksi**: tietojen viimeisin päivityspäivä ja -aika.

## <a name="explore-a-specific-entitys-data"></a>Tutustu tietyn entiteetin tietoihin

Valitse entiteetti, jonka kenttiin ja tietueisiin haluat tutustua.

> [!div class="mx-imgBorder"]
> ![Valitse entiteetti.](media/data-manager-entities-data.png "Valitse entiteetti")

- **Tiedot**-välilehdessä on taulukko, jossa on tietoja entiteetin yksittäisistä tietueista.

> [!div class="mx-imgBorder"]
> ![Kentät-taulukko.](media/data-manager-entities-fields.PNG "Kentät-taulukko")

- **Määritteet**-välilehti on oletusarvoisesti valittuna, ja se näyttää taulukon, jossa tarkastellaan valitun entiteetin tietoja, kuten kenttien nimiä, tietotyyppejä ja tyyppejä. **Tyyppi**-sarakkeessa näkyy liittyviä Common Data Model -tyyppejä, jotka järjestelmä joko tunnistaa automaattisesti tai jotka käyttäjät [yhdistävät manuaalisesti](map-entities.md). Nämä tyypit ovat semanttisia tyyppejä, jotka voivat poiketa määritteiden tietotyypeistä. Esimerkiksi alla olevassa *Sähköposti*-kentässä on tietotyyppi *Teksti*, mutta sen (semanttisen) Common Data Model -tyyppi voi olla *Email* tai *EmailAddress*.

> [!NOTE]
> Kummassakin taulukossa näkyy vain osa entiteetin tiedoista. Voit tarkastella koko tietojoukkoa siirtymällä **Tietolähteet**-sivulle, valitsemalla entiteetin, valitsemalla **Muokka** ja tarkastelemalla entiteetin tietoja Power Query -editorissa kohdassa [Tietolähteet](data-sources.md) kuvatulla tavalla.

Lisätietoja entiteetissä käsitellyistä tiedoista on **Yhteenveto**-sarakkeessa, jossa on joitakin tärkeitä tietoja tietojen ominaisuuksista, kuten tyhjäarvot, puuttuvat arvot, yksilöivät arvot, määrät ja jakelut.

Näet tietojen yhteenvedon valitsemalla kaaviokuvakkeen.

> [!div class="mx-imgBorder"]
> ![Yhteenvetosymboli.](media/data-manager-entities-summary.png "Tietojen yhteenvetotaulukko")

## <a name="entity-specific-information"></a>Entiteettikohtainen tieto

Seuraavassa osassa on tietoja joistakin järjestelmän luomista entiteeteistä.

### <a name="corrupted-data-sources"></a>Vioittuneet tietolähteet

Käsiteltyjen tietolähteiden kentät voivat sisältää vioittuneita tietoja. Tietueet, joissa on vioittuneita kenttiä, paljastetaan järjestelmän luomissa entiteeteissä. Vioittuneista tietueista tietäminen auttaa sinua tunnistamaan lähdejärjestelmän tarkistettavat ja päivitettävät tiedot. Tietolähteen seuraavan päivityksen yhteydessä korjatut tietueet päivitetään Customer Insightsiin ja välitetään jatkoprosesseihin. 

Esimerkiksi syntymäpäiväsarakkeen tietotyypiksi on määritetty päivämäärä. Asiakasrekisterin syntymäpäiväksi on merkitty "1.1.19777". Järjestelmä merkitsee tämän tietueen vioittuneeksi. Joku voi nyt muuttaa lähdejärjestelmän syntymäpäiväksi '1977'. Tietolähteiden automaattisen päivityksen jälkeen kentän muoto on nyt kelvollinen ja tietue poistetaan vioittuneesta entiteetistä. 

Siirry kohtaan **Tieto** > **Entiteetit** ja etsi vioittuneet entiteetit **Järjestelmä**-osasta. Vioittuneiden entiteettien rakenteen nimeäminen: "DataSourceName_EntityName_corrupt".

Customer Insights käsittelee edelleen vioittuneita tietueita. Ne saattavat kuitenkin aiheuttaa ongelmia yhtenäisten tietojen kanssa toimittaessa.

Seuraavat tarkistukset suoritetaan, jotta näytetyt tiedot voidaan paljastaa vioittuneille tietueille: 

- Kentän arvo ei vastaa sen sarakkeen tietotyyppiä.
- Kentissä on merkkejä, joiden vuoksi sarakkeet eivät vastaa odotettua rakennetta. Esimerkiksi: väärin muotoiltuja lainausmerkkejä, virheellisiä lainausmerkkejä tai uuden linjan merkkejä.
- Jos datetime-, date/date/datetimeoffset-sarakkeita on, niiden muoto on määritettävä mallissa, jos se ei noudata ISO-vakiomuotoa.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
