---
title: Tietojen käsitteleminen tietolähteiden avulla
description: Tietoja tietojen tuomisesta eri lähteistä.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 0a017a37777adaaf7de079cf481ec10c70c7adba
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692431"
---
# <a name="data-sources-overview"></a>Tietolähteiden yleiskatsaus

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuus yhdistää tietoihin monenlaisista lähteistä. Tietolähteen yhdistämistä kutsutaan usein *tietojen käsittelyprosessiksi*. Kun tiedot on käsitelty, ne voidaan [yhdistää](data-unification.md) ja niissä voidaan tehdä toimintoja.

## <a name="add-a-data-source"></a>Lisää tietolähde

Lisätietoja tietolähteen lisäämisestä on artikkeleissa, joissa käsitellään valittua vaihtoehtoa.

Tietolähde voidaan lisätä pääasiassa kolmella tavalla:

- [Käyttämällä kymmeniä Power Query -yhdistimiä](connect-power-query.md)
- [Common Data Model -kansiosta](connect-common-data-model.md)
- [Omasta Microsoft Dataversen Data Lake -tallennustilasta](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Tietojen lisääminen paikallisista tietolähteistä

Käyttäjäryhmän merkityksellisten tietojen paikallisten tietolähteiden tietojen käsittelemistä tuetaan Microsoft Power Platform -tietotyönkulkujen perusteella. Tietovirtaukset voidaan ottaa käyttöön Customer Insightsissa [antamalla Microsoft Dataverse -ympäristön URL-osoite](get-started-paid.md) ympäristöä määritettäessä.

Kun Dataverse-ympäristö on liitetty Customer Insights -tietoihin, luodut tietolähteet käyttävät oletusarvoisesti [Power Platform -tietovirtoja](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Tietovuot tukevat paikallisia yhteyksiä tietoyhdyskäytävän avulla. Poista ja luo uudelleen tietolähteet, jotka olivat olemassa ennen Dataverse-ympäristön liittämistä [paikallisten tietoyhdyskäytävien käyttöön](/data-integration/gateway/service-gateway-app).

Aiemmin luodun Power BI- tai Power Apps -ympäristön tietoyhdyskäytävät ovat näkyvissä, ja voit käyttää niitä uudelleen Customer Insightsissa. Tietolähteiden sivulla on linkki, jonka avulla voi siirtyä Microsoft Power Platform -ympäristöön paikallisten tietoyhdyskäytävien tarkastelemista ja määrittämistä varten.

## <a name="review-ingested-data"></a>Käsiteltyjen tietojen tarkistaminen

Näkyvissä on kunkin käsitellyn tietolähteen nimi, sen tilan ja kyseisen tietolähteen tietojen viimeisimmän päivityskerran. Tietolähdeluettelon voi lajitella kunkin sarakkeen mukaan.

> [!div class="mx-imgBorder"]
> ![Tietolähde lisättiin.](media/configure-data-datasource-added.png "Tietolähde lisättiin")

|Tila  |Kuvaus  |
|---------|---------|
|Onnistui   |Tietolähde on käsitelty, jos **Päivitetty**-sarakkeessa on aika.
|Ei aloitettu   |Tietolähteessä ei ole vielä käsiteltyjä tietoja tai se on edelleen luonnostilassa.         |
|Päivittää    |Tietoja käsittely on meneillään. Voit peruuttaa tämän toiminnon valitsemalla **Pysäytä päivittäminen** **Toiminnot**-sarakkeessa. Tietolähteen päivittämisen pysäyttäminen palauttaa sen tilaan, jossa se on viimeksi päivitetty.       |
|Epäonnistunut     |Tietojen käsittelyssä havaittiin virheitä.         |

Valitse jonkin tietolähteen **Tila**-sarakkeen arvo, jos haluat tarkastella lisätietoja. Laajenna **Edistymisen tiedot** -ruudussa **Tietolähteet**-kohta. Valitsemalla **Katso tiedot** -kohdan voit tarkastella lisätietoja päivityksen tilasta, kuten virhetiedot ja jäljempänä tapahtuvat prosessipäivitykset.

Tietojen lataaminen voi viedä aikaa. Kun päivitys on onnistunut, käsiteltyjä tietoja voi tarkastella **Entiteetit**-sivulla. Lisätietoja on kohdassa [Entiteetit](entities.md).

## <a name="refresh-a-data-source"></a>Tietolähteen päivittäminen

Tietolähteet voidaan päivittää automaattisen aikataulun mukaan tai manuaalisesti tarvittaessa. 

Määritä kaikkien käsiteltyjen tietolähteiden ajoitetut päivitykset valitsemalla **Hallinta** > **Järjestelmä** > [**Ajoitus**](system.md#schedule-tab).

Tietolähde päivitetään tarvittaessa seuraavasti:

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.

2. Valitse tietolähteen vieressä olevat kolme pystysuuntaista pistettä, jos haluat päivittää. Valitse avattavasta luettelosta **Päivitä**.

3. Tietolähde on nyt valmis manuaaliseen päivitykseen. Jos päivität tietolähteen, päivitetään tietolähteessä määritettyjen entiteettien sekä tiedot että entiteettirakenne.

4. Valitse **Pysäytä päivittäminen**, jos haluat peruuttaa nykyisen päivityksen, jolloin tietolähde palautuu viimeksi päivitettyyn tilaan.

## <a name="delete-a-data-source"></a>Tietolähteen poistaminen

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.

2. Valitse tietolähteen vieressä olevat kolme pystysuuntaista pistettä, jos haluat poistaa kohteen. Valitse avattavasta valikosta **Poista**.

3. Vahvista poisto.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
