---
title: Tietojen käsitteleminen tietolähteiden avulla
description: Tietoja tietojen tuomisesta eri lähteistä.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 68aa1b56fb634da80a0c64db72f778d57507104d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269694"
---
# <a name="data-sources-overview"></a>Tietolähteiden yleiskatsaus

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuus yhdistää tietoihin monenlaisista lähteistä. Tietolähteen yhdistämistä kutsutaan usein *tietojen käsittelyprosessiksi*. Kun tiedot on käsitelty, ne voidaan [yhdistää](data-unification.md) ja niissä voidaan tehdä toimintoja.

## <a name="add-a-data-source"></a>Lisää tietolähde

Lisätietoja tietolähteen lisäämisestä on artikkeleissa, joissa käsitellään valittua vaihtoehtoa.

Tietolähde voidaan lisätä pääasiassa kolmella tavalla:

- [Käyttämällä kymmeniä Power Query -yhdistimiä](connect-power-query.md)
- [Common Data Model -kansiosta](connect-common-data-model.md)
- [Omasta Common Data Servicen Data Lake -tallennustilasta](connect-common-data-service-lake.md)

> [!NOTE]
> Tietoja ei voi vielä listä paikallisista tietolähteistä.

## <a name="review-ingested-data"></a>Käsiteltyjen tietojen tarkistaminen

Näkyvissä on kunkin käsitellyn tietolähteen nimi, sen tilan ja kyseisen tietolähteen tietojen viimeisimmän päivityskerran. Tietolähdeluettelon voi lajitella kunkin sarakkeen mukaan.

> [!div class="mx-imgBorder"]
> ![Tietolähde lisättiin](media/configure-data-datasource-added.png "Tietolähde lisättiin")

|Tila  |Kuvaus  |
|---------|---------|
|Onnistui   |Tietolähde on käsitelty, jos **Päivitetty**-sarakkeessa on aika.
|Ei aloitettu   |Tietolähteessä ei ole vielä käsiteltyjä tietoja tai se on edelleen luonnostilassa.         |
|Päivittää    |Tietoja käsittely on meneillään. Voit peruuttaa tämän toiminnon valitsemalla **Pysäytä päivittäminen** **Toiminnot**-sarakkeessa. Tietolähteen päivittämisen pysäyttäminen palauttaa sen tilaan, jossa se on viimeksi päivitetty.       |
|Epäonnistunut     |Tietojen käsittelyssä havaittiin virheitä.         |

Valitse jonkin tietolähteen **Tila**-sarakkeen arvo, jos haluat tarkastella lisätietoja. Laajenna **Edistymisen tiedot** -ruudussa **Tietolähteet**-kohta. Valitsemalla **Katso tiedot** -kohdan voit tarkastella lisätietoja päivityksen tilasta, kuten virhetiedot ja jäljempänä tapahtuvat prosessipäivitykset.

Tietojen lataaminen voi kestää jonkin aikaa. Kun päivitys on onnistunut, käsiteltyjä tietoja voi tarkastella **Entiteetit**-sivulla. Lisätietoja on kohdassa [Entiteetit](entities.md).

## <a name="refresh-a-data-source"></a>Tietolähteen päivittäminen

Tietolähteet voidaan päivittää automaattisen aikataulun mukaan tai manuaalisesti tarvittaessa. 

Määritä kaikkien käsiteltyjen tietolähteiden ajoitetut päivitykset valitsemalla **Hallinta** > **Järjestelmä** > [**Ajoitus**](system.md#schedule-tab).

Tietolähde päivitetään tarvittaessa seuraavasti:

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**

2. Valitse päivitettävän tietolähteen vieressä kolme allekkaista pistettä ja valitse sitten avattavassa luettelossa **Päivitä**.

3. Tietolähde on nyt valmis manuaaliseen päivitykseen. Tietolähteen päivittäminen päivittää sekä entiteettirakenteen että kaikkien tietolähteessä määritettyjen entiteettien tiedot.

4. Valitse **Pysäytä päivittäminen**, jos haluat peruuttaa nykyisen päivityksen, jolloin tietolähde palautuu viimeksi päivitettyyn tilaan.

## <a name="delete-a-data-source"></a>Tietolähteen poistaminen

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.

2. Valitse poistettavan tietolähteen vieressä olevat pystysuorat kolme pistettä ja valitse avattavasta valikosta **Poista**.

3. Vahvista poisto.


[!INCLUDE[footer-include](../includes/footer-banner.md)]