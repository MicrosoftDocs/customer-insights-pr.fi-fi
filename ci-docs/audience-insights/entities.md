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
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049390"
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

## <a name="exploring-a-specific-entitys-data"></a>Tutustuminen tietyn entiteetin tietoihin

Valitse entiteetti, jonka kenttiin ja tietueisiin haluat tutustua.

> [!div class="mx-imgBorder"]
> ![Valitse entiteetti](media/data-manager-entities-data.png "Valitse entiteetti")

- **Tiedot**-välilehdessä on taulukko, jossa on tietoja entiteetin yksittäisistä tietueista.

> [!div class="mx-imgBorder"]
> ![Kentät-taulukko](media/data-manager-entities-fields.PNG "Kentät-taulukko")

- **Määritteet**-välilehti on oletusarvoisesti valittuna, ja se näyttää taulukon, jossa tarkastellaan valitun entiteetin tietoja, kuten kenttien nimiä, tietotyyppejä ja tyyppejä. **Tyyppi**-sarakkeessa näkyy liittyviä Common Data Model -tyyppejä, jotka järjestelmä joko tunnistaa automaattisesti tai jotka käyttäjät [yhdistävät manuaalisesti](map-entities.md). Nämä ovat sementtisia tyyppejä, jotka eroavat määritetteiden tietotyypeistä. Esimerkiksi alla olevan *Sähköposti*-kentän tietotyyppi on *Teksti*, mutta sen (semanttinen) Common Data Model -tyyppi voi olla *Sähköposti* tai *EmailAddress*.

> [!NOTE]
> Kummassakin taulukossa näkyy vain osa entiteetin tiedoista. Voit tarkastella koko tietojoukkoa siirtymällä **Tietolähteet**-sivulle, valitsemalla entiteetin, valitsemalla **Muokka** ja tarkastelemalla entiteetin tietoja Power Query -editorissa kohdassa [Tietolähteet](data-sources.md) kuvatulla tavalla.

Lisätietoja entiteetissä käsitellyistä tiedoista on **Yhteenveto**-sarakkeessa, jossa on joitakin tärkeitä tietoja tietojen ominaisuuksista, kuten tyhjäarvot, puuttuvat arvot, yksilöivät arvot, määrät ja jakelut.

Näet tietojen yhteenvedon valitsemalla kaaviokuvakkeen.

> [!div class="mx-imgBorder"]
> ![Yhteenvetosymboli](media/data-manager-entities-summary.png "Tietojen yhteenvetotaulukko")

### <a name="next-step"></a>Seuraava vaihe

Ohjeaiheessa [Yhdistäminen](data-unification.md) on lisätietoja käsiteltyjen tietojen *vastaavuusmäärityksestä*, *täsmäytyksestä* ja *yhdistämisestä*.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
