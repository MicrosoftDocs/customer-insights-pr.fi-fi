---
title: Customer Insightsin entiteetit
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
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183542"
---
# <a name="entities-in-customer-insights"></a>Customer Insightsin entiteetit

Kun [tietolähteet on määritetty](data-sources.md), siirry **Entiteetit**-sivulle arvioimaan käsiteltyjen tietojen laatua. Entiteettejä pidetään tietojoukkoina. Monet Dynamics 365 Customer Insights -ominaisuudet perustuvat näihin entiteetteihin. Niiden huolellinen tarkastelu voi auttaa tarkistamaan kyseisten ominaisuuksien tuloksia.

Kun työskentelet Customer Insightsissa rikastamassa tietoja tai luomassa segmenttejä, mittareita ja aktiviteetteja, näistä toiminnoista luodut entiteetit näkyvät **Entiteetit**-sivulla.

## <a name="view-a-list-of-entities"></a>Tarkastele entiteettiluetteloa

Siirry kohtaan **Tieto** > **Entiteetit**, kun haluat tarkastella entiteettiluetteloa. Seuraavat tiedot näkyvät kunkin entiteetin yhteydessä.

- **Nimi**: Tietoentiteetin nimi. Jos entiteetin nimen vieressä on varoitussymboli, kyseisen entiteetin tietojen lataus ei onnistunut.
- **Lähde**: Entiteetin keränneen tietolähteen tyyppi.
- **Päivitetty**: Entiteetin edellinen päivitysaika.
- **Tila**: entiteetin viimeisen päivityksen tiedot.

## <a name="explore-a-specific-entitys-data"></a>Tutustu tietyn entiteetin tietoihin

1. Siirry kohtaan **Tiedot** > **Entiteetit**.
1. Avaa entiteetin tietosivu valitsemalla entiteetti.  
1. Tutustu tämän entiteetin kenttiin ja tietueisiin.

- **Määritteet**-välilehti on oletusarvoisesti valittuna, ja se näyttää valitun entiteetin tietoja, kuten kenttien nimiä, tietotyyppejä ja tyyppejä. **Tyyppi**-sarakkeessa näkyy liittyviä Common Data Model -tyyppejä, jotka järjestelmä joko tunnistaa automaattisesti tai jotka käyttäjät [yhdistävät manuaalisesti](map-entities.md). Nämä tyypit ovat semanttisia tyyppejä, jotka voivat poiketa määritteiden tietotyypeistä. Esimerkiksi alla olevassa *Sähköposti*-kentässä on tietotyyppi *Merkkijono*, mutta sen (semanttisen) Common Data Model -tyyppi voi olla *Email*, *EmailAddress* tai *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Kentät-taulukko.":::

   > [!NOTE]
   > Tässä sivussa näkyy vain esimerkki entiteetin tiedoista. Voit tarkastella koko tietojoukkoa siirtymällä **Tietolähteet**-sivulle, valitsemalla entiteetin, valitsemalla **Muokkaa** ja tarkastelemalla entiteetin tietoja Power Query -editorissa kohdassa [Tietolähteet](data-sources.md) kuvatulla tavalla.

   Lisätietoja entiteetissä käsitellyistä tiedoista on **Yhteenveto**-sarakkeessa, jossa on joitakin tärkeitä tietoja tietojen ominaisuuksista, kuten tyhjäarvot, puuttuvat arvot, yksilöivät arvot, määrät ja jakelut. Näet tietojen yhteenvedon valitsemalla kaaviokuvakkeen.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Tietojen yhteenvetotaulukko.":::

- **Tiedot**-välilehdessä on tietoja entiteetin yksittäisistä tietueista. Luettelossa näkyvät tiedot määräytyvät entiteetin tietotyypin mukaan.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Valitse entiteetti.":::

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

   :::image type="content" source="media/corruption-reason.png" alt-text="Vioittumisen syy.":::

Customer Insights käsittelee edelleen vioittuneita tietueita. Ne saattavat kuitenkin aiheuttaa ongelmia yhtenäisten tietojen kanssa toimittaessa.

Seuraavat tarkistukset suoritetaan, jotta näytetyt tiedot voidaan paljastaa vioittuneille tietueille:

- Kentän arvo ei vastaa sen sarakkeen tietotyyppiä.
- Kentissä on merkkejä, joiden vuoksi sarakkeet eivät vastaa odotettua rakennetta. Esimerkiksi: väärin muotoiltuja lainausmerkkejä, virheellisiä lainausmerkkejä tai uuden linjan merkkejä.
- Jos on päivämäärä ja aika / päivämäärä / päivämääräsiirtymä-sarakkeita, niiden muoto on määritettävä mallissa, jos se ei noudata ISO-vakiomuotoa.

[!INCLUDE [footer-include](includes/footer-banner.md)]
