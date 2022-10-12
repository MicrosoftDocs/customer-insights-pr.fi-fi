---
title: Customer Insightsin entiteetit
description: Tietojen näyttäminen Entiteetit-sivulla.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610094"
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

[!INCLUDE [footer-include](includes/footer-banner.md)]
