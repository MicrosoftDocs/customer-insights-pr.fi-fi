---
title: Yritystilien käsitteleminen
description: Tietoja yritystileistä ensisijaisena kohdekäyttäjäryhmänä Dynamics 365 Customer Insightsissa.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: abb77a720ab737520a905b0c93b65573e669109f
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303912"
---
# <a name="work-with-business-accounts"></a>Yritystilien käsitteleminen

Dynamics 365 Customer Insights antaa mahdollisuuden määrittää ympäristön erilaisille ensisijaisille kohdekäyttäjäryhmille: yksittäisille kuluttajille (kuluttajakauppa) ja yritystileille (yritystenvälinen). Kuluttajakauppaskenaarioissa tiedot on keskitetty yksittäisten henkilöiden ympärille. Yritystenvälisessä kaupassa ensisijaiset kohdekäyttäjäryhmät ovat tilit – organisaatiot ja yritykset – ja yhteyshenkilöt. Tämän artikkelin avulla voit aloittaa yritystiliympäristön käytön. Siinä luetellaan eri ominaisuusalueiden erot Customer Insightsissa riippuen ympäristösi kohdistuksesta. Lisätietoja eroista on ominaisuusalueiden ohjeissa. 

## <a name="create-an-environment-for-business-accounts"></a>Ympäristön luominen yritystileille

Järjestelmänvalvojat voivat [luoda ympäristön aiemmin luotuun organisaatioon](create-environment.md). Uuden ympäristön luonnin vaihe kysyy järjestelmänvalvojilta ympäristön ensisijaista kohdekäyttäjäryhmää. Jos kyseessä on ensimmäinen asennus lisenssin ostamisen jälkeen, ohjattu kokemus auttaa luomaan ensimmäisen ympäristön.

Voit sitten [käyttää tietoja](data-sources.md) yritystilien ja liittyvien yhteyshenkilöiden tietolähteinä kaikista tuetuista lähteistä.

 Yhdistä yhteyshenkilö - ja tilientiteetit [yhtenäistämällä](data-unification.md) tilitiedot ja yhteyshenkilötiedot.

## <a name="switch-between-primary-target-audience"></a>Vaihtaminen ensisijaisen kohdekäyttäjäryhmän välillä

Jos organisaatiosi ylläpitää yksittäisten asiakkaiden ja yritystilien ympäristöjä, voit vasemmanpuoleisen ruudun valitsimen avulla valita ensisijaisen kohdekäyttäjäryhmän.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Valitsin, joka vaihtaa ensisijaista kohdekäyttäjäryhmää yksittäisten asiakkaiden ja yritystilien välillä.":::

## <a name="supported-feature-areas"></a>Tuetut ominaisuusalueet

- [Aktiviteetit](activities.md): Tuki tileille ja liittyville yhteyshenkilöille aktiviteettien luomista varten ja niiden aikajanalla näyttämistä varten.
- [Suhteet](relationships.md): Aktiviteettien ohjattu toiminto auttaa luomaan suhteita entiteettien välille, jotta tilinäkymässä voidaan näyttää yhteyshenkilöiden kaikki aktiviteetit. Yhteyshenkilöt voivat porautua ylöspäin yhteyshenkilönäkymään, ja hierarkioita voidaan käyttää tilin aktiviteettien koostamista varten.
- [Mittarit](measures.md): Tukee mittareita, jotka on luotu mittarin muodostimella yhdellä laskutoimituksella. Valinnainen asetus sallii alitilien kokoamisen, kun luodaan mittareita.
- [Segmentit](segments.md): Tukee segmenttejä, jotka on luotu alusta asti segmenttien muodostimella. Segmentit voivat perustua tileihin tai yhteyshenkilöihin.
- [Tietojen käsittely](data-sources.md): Tämän alueen kaikki ominaisuudet ovat samat yritystileille ja yksittäisille asiakkaille.
- Tietojen B2B-yhdistäminen muistuttaa hyvin paljon tietojen B2C-yhdistämistä, mutta sillä on lisävaihe yhteyshenkilöiden yhdistämiseksi tilien yhdistämisen jälkeen. Katso [Yritystilit (yritysten väliset)](data-unification.md).
- [Rikastaminen](enrichment-hub.md): Jotkin rikastustyypit ovat käytössä vain yksittäisille asiakkaille, kun taas jotkin ovat käytössä vain yritystileille.
- [Ennusteet ja valmiit mallit](predictions-overview.md): Tapahtumien vaihtuvuuden ennusteet sisältävät lisävaiheita yritystileille. Muut ennusteet ovat käytettävissä vain yksittäisille asiakkaille.
- [Aktivointi ja vienti](export-destinations.md): Vienti on mahdollista yritystileille ja yksittäisille asiakkaille. Jotkin viennit edellyttävät, että taustalla olevien segmenttien lisämääritys- ja yhteyshenkilötiedot ovat voimassa yritystilien osalta.
- [Järjestelmän asetukset](system.md) ja [käyttäjien hallinta](permissions.md): Tämän alueen kaikki ominaisuudet ovat samat yritystileille ja yksittäisille asiakkaille.

[!INCLUDE [footer-include](includes/footer-banner.md)]
