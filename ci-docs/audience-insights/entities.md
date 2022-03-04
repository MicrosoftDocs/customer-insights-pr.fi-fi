---
title: Entiteetit ja tietojoukot
description: Tietojen näyttäminen Entiteetit-sivulla.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 1e1abdf49a3c1fe6f9fdd2cf5353a7723454f47b
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355294"
---
# <a name="entities-in-audience-insights"></a>Käyttäjäryhmän merkityksellisten tietojen entiteetit

Kun [tietolähteet on määritetty](data-sources.md), siirry **Entiteetit**-sivulle arvioimaan käsiteltyjen tietojen laatua. Entiteettejä pidetään tietojoukkoina. Monet Dynamics 365 Customer Insights -ominaisuudet perustuvat näihin entiteetteihin. Niiden huolellinen tarkastelu voi auttaa tarkistamaan kyseisten ominaisuuksien tuloksia.

**Entiteetit**-sivulla on entiteettejä, ja siinä on seuraavat sarakkeet:

- **Nimi**: Tietoentiteetin nimi. Jos entiteetin nimen vieressä on varoitussymboli, kyseisen entiteetin tietojen lataus ei onnistunut.
- **Lähde**: Entiteetin keränneen tietolähteen tyyppi.
- **Päivitetty**: Entiteetin edellinen päivitysaika.
- **Tila**: entiteetin viimeisen päivityksen tiedot.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Tutustu tietyn entiteetin tietoihin

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Entiteetit**.
1. Valitse **Entiteetit**-sivulta entiteetti, jonka tietosivu avautuu.  
1. Tutustu tämän entiteetin kenttiin ja tietueisiin.

- **Määritteet**-välilehti on oletusarvoisesti valittuna, ja se näyttää taulukon, jossa tarkastellaan valitun entiteetin tietoja, kuten kenttien nimiä, tietotyyppejä ja tyyppejä. **Tyyppi**-sarakkeessa näkyy liittyviä Common Data Model -tyyppejä, jotka järjestelmä joko tunnistaa automaattisesti tai jotka käyttäjät [yhdistävät manuaalisesti](map-entities.md). Nämä tyypit ovat semanttisia tyyppejä, jotka voivat poiketa määritteiden tietotyypeistä. Esimerkiksi alla olevassa *Sähköposti*-kentässä on tietotyyppi *Teksti*, mutta sen (semanttisen) Common Data Model -tyyppi voi olla *Email* tai *EmailAddress*.

> [!div class="mx-imgBorder"]
> ![Kentät-taulukko.](media/data-manager-entities-fields.PNG "Kentät-taulukko")

> [!NOTE]
> Tässä sivussa näkyy vain esimerkki entiteetin tiedoista. Voit tarkastella koko tietojoukkoa siirtymällä **Tietolähteet**-sivulle, valitsemalla entiteetin, valitsemalla **Muokkaa** ja tarkastelemalla entiteetin tietoja Power Query -editorissa kohdassa [Tietolähteet](data-sources.md) kuvatulla tavalla.

Lisätietoja entiteetissä käsitellyistä tiedoista on **Yhteenveto**-sarakkeessa, jossa on joitakin tärkeitä tietoja tietojen ominaisuuksista, kuten tyhjäarvot, puuttuvat arvot, yksilöivät arvot, määrät ja jakelut. Näet tietojen yhteenvedon valitsemalla kaaviokuvakkeen.

> [!div class="mx-imgBorder"]
> ![Yhteenvetosymboli.](media/data-manager-entities-summary.png "Tietojen yhteenvetotaulukko")

- **Tiedot**-välilehdessä on taulukko, jossa on tietoja entiteetin yksittäisistä tietueista. Luettelossa näkyvät tiedot määräytyvät entiteetin tietotyypin mukaan.

> [!div class="mx-imgBorder"]
> ![Valitse entiteetti.](media/data-manager-entities-data.png "Valitse entiteetti")

- **Raportit**-välilehden (joidenkin entiteettien käytettävissä) avulla voit visualisoida tiedot luomalla raportin ja se sisältää seuraavat sarakkeet:

  - **Raportin nimi**: raportin nimi.
  - **Luonut**: entiteetin luoneen henkilön nimi.
  - **Luotu**: entiteetin luontipäivä ja -aika.
  - **Muokannut**: entiteettiä muokanneen henkilön nimi.
  - **Muokattu**: entiteetin muokkauspäivä ja -aika. 

## <a name="entity-specific-information"></a>Entiteettikohtainen tieto

Seuraavassa osassa on tietoja joistakin järjestelmän luomista entiteeteistä.

### <a name="corrupted-data-sources"></a>Vioittuneet tietolähteet

Käsiteltyjen tietolähteiden kentät voivat sisältää vioittuneita tietoja. Tietueet, joissa on vioittuneita kenttiä, paljastetaan järjestelmän luomissa entiteeteissä. Vioittuneista tietueista tietäminen auttaa sinua tunnistamaan lähdejärjestelmän tarkistettavat ja päivitettävät tiedot. Tietolähteen seuraavan päivityksen yhteydessä korjatut tietueet päivitetään Customer Insightsiin ja välitetään jatkoprosesseihin. 

Esimerkiksi syntymäpäiväsarakkeen tietotyypiksi on määritetty päivämäärä. Asiakasrekisterin syntymäpäiväksi on merkitty "1.1.19777". Järjestelmä merkitsee tämän tietueen vioittuneeksi. Joku voi nyt muuttaa lähdejärjestelmän syntymäpäiväksi '1977'. Tietolähteiden automaattisen päivityksen jälkeen kentän muoto on nyt kelvollinen ja tietue poistetaan vioittuneesta entiteetistä. 

Siirry kohtaan **Tieto** > **Entiteetit** ja etsi vioittuneet entiteetit **Järjestelmä**-osasta. Vioittuneiden entiteettien rakenteen nimeäminen: "DataSourceName_EntityName_corrupt". Valitse vioittunut entiteetti tunnistaaksesi kaikki vialliset kentät ja syyn yksittäisen tietueen tasolla.
> [!div class="mx-imgBorder"]
> ![Vioittumisen syy.](media/corruption-reason.png "Vioittumisen syy")

Customer Insights käsittelee edelleen vioittuneita tietueita. Ne saattavat kuitenkin aiheuttaa ongelmia yhtenäisten tietojen kanssa toimittaessa.

Seuraavat tarkistukset suoritetaan, jotta näytetyt tiedot voidaan paljastaa vioittuneille tietueille: 

- Kentän arvo ei vastaa sen sarakkeen tietotyyppiä.
- Kentissä on merkkejä, joiden vuoksi sarakkeet eivät vastaa odotettua rakennetta. Esimerkiksi: väärin muotoiltuja lainausmerkkejä, virheellisiä lainausmerkkejä tai uuden linjan merkkejä.
- Jos on päivämäärä ja aika / päivämäärä / päivämääräsiirtymä-sarakkeita, niiden muoto on määritettävä mallissa, jos se ei noudata ISO-vakiomuotoa.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
