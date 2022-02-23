---
title: Tietojen käsitteleminen tietolähteiden avulla
description: Tietoja tietojen tuomisesta eri lähteistä.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ca979527c9cb8418e12af4a74513033047e4901c
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046584"
---
# <a name="data-sources-overview"></a>Tietolähteiden yleiskatsaus



Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuus yhdistää tietoihin monenlaisista lähteistä. Tietolähteen yhdistämistä kutsutaan usein *tietojen käsittelyprosessiksi*. Kun tiedot on käsitelty, ne voidaan [yhdistää](data-unification.md) ja niissä voidaan tehdä toimintoja.

## <a name="add-a-data-source"></a>Lisää tietolähde

Yksityiskohtaisissa artikkeleissa on lisätietoja tietolähteen lisäämisestä valitun vaihtoehdon mukaan.

Voit lisätä seuraavat tietolähteet:

- [Power Query ‑yhdistimet](connect-power-query.md)
- [Common Data Model](connect-common-data-model.md)
- [Microsoft Dataversen data lake](connect-dataverse-managed-lake.md)

> [!NOTE]
> Jos käytät kokeiluversiota, tuontitavat-osassa on **Customer Insights -tietokirjasto** -vaihtoehto. Valitse tämä vaihtoehto, jos haluat valita tietojoukon, joka on käytettävissä eri toimialoja varten. Saat lisätietoja [Dynamics 365 Customer Insights kokeilusta](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Tietojen lisääminen paikallisista tietolähteistä

Käyttäjäryhmän merkityksellisten tietojen paikallisten tietolähteiden tietojen käsittelemistä tuetaan Microsoft Power Platform -tietotyönkulkujen perusteella. Voit ottaa Dataflows-tiedot käyttöön Customer Insightsissa [antamalla Microsoft Dataverse -ympäristön URL-osoitteen](create-environment.md) ympäristön määrittämisen jälkeen.

Tietolähteet, jotka luodaan, kun Dataverse-ympäristö on liitetty Customer Insightsiin, käyttävät oletusarvoisesti [Power Platform -tietovirtoja](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Tietovuot tukevat paikallisia yhteyksiä tietoyhdyskäytävän avulla. Voit poistaa ja luoda uudelleen tietolähteitä, jotka olivat olemassa ennen Dataverse-ympäristön liittämistä, [paikallisten tietoyhdyskäytävien avulla](/data-integration/gateway/service-gateway-app).

Aiemmin luodun Power BI- tai Power Apps -ympäristön tietoyhdyskäytävät ovat näkyvissä, ja voit käyttää niitä uudelleen Customer Insightsissa. Tietolähteiden sivulla on linkki, jonka avulla voi siirtyä Microsoft Power Platform -ympäristöön paikallisten tietoyhdyskäytävien tarkastelemista ja määrittämistä varten.

## <a name="review-ingested-data"></a>Käsiteltyjen tietojen tarkistaminen

Näkyvissä on kunkin käsitellyn tietolähteen nimi, sen tilan ja kyseisen tietolähteen tietojen viimeisimmän päivityskerran. Tietolähdeluettelon voi lajitella kunkin sarakkeen mukaan.

> [!div class="mx-imgBorder"]
> ![Tietolähde lisättiin.](media/configure-data-datasource-added.png "Tietolähde lisättiin")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

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
