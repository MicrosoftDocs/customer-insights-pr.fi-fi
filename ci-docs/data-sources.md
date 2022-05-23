---
title: Tietojen käsitteleminen tietolähteiden avulla
description: Tietoja tietojen tuomisesta eri lähteistä.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 1fe8d6e8098831ecc8ff28e571340c56a654de6d
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/11/2022
ms.locfileid: "8739204"
---
# <a name="data-sources-overview"></a>Tietolähteiden yleiskatsaus



Dynamics 365 Customer Insights muodostaa yhteyden dataan laajasta joukosta lähteitä. Tietolähteen yhdistämistä kutsutaan usein *tietojen käsittelyprosessiksi*. Kun tiedot on käsitelty, ne voidaan [yhdistää](data-unification.md) ja niissä voidaan tehdä toimintoja.

## <a name="add-a-data-source"></a>Lisää tietolähde

Yksityiskohtaisissa artikkeleissa on lisätietoja tietolähteen lisäämisestä valitun vaihtoehdon mukaan.

Voit lisätä seuraavat tietolähteet:

- [Kymmenien Power Query -yhdistinten kautta](connect-power-query.md)
- [Common Data Model -kansiosta](connect-common-data-model.md)
- [Omasta Microsoft Dataversen Data Lake -tallennustilasta](connect-dataverse-managed-lake.md)
- [Azure Synapse Analytics ‑tietokannasta](connect-synapse.md)

## <a name="add-data-from-on-premises-data-sources"></a>Tietojen lisääminen paikallisista tietolähteistä

Tiedon keräämistä paikallisista tietolähteistä tuetaan Microsoft Power Platform -tietovoiden perusteella. Voit ottaa Dataflows-tiedot käyttöön Customer Insightsissa [antamalla Microsoft Dataverse -ympäristön URL-osoitteen](create-environment.md) ympäristön määrittämisen jälkeen.

Tietolähteet, jotka luodaan, kun Dataverse-ympäristö on liitetty Customer Insightsiin, käyttävät oletusarvoisesti [Power Platform -tietovirtoja](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Tietovuot tukevat paikallisia yhteyksiä tietoyhdyskäytävän avulla. Voit poistaa ja luoda uudelleen tietolähteitä, jotka olivat olemassa ennen Dataverse-ympäristön liittämistä, [paikallisten tietoyhdyskäytävien avulla](/data-integration/gateway/service-gateway-app).

Aiemmin luodun Power BI- tai Power Apps -ympäristön tietoyhdyskäytävät ovat näkyvissä, ja voit käyttää niitä uudelleen Customer Insightsissa. Tietolähteiden sivulla on linkki, jonka avulla voi siirtyä Microsoft Power Platform -ympäristöön paikallisten tietoyhdyskäytävien tarkastelemista ja määrittämistä varten.

> [!IMPORTANT]
> Varmista, että yhdyskäytävät on päivitetty uusimpaan versioon. Voit asentaa päivityksen ja määrittää yhdyskäytävän uudelleen yhdyskäytävän näytössä näkyvästä kehotteesta tai [ladata uusimman version](https://powerapps.microsoft.com/downloads/). Jos et käytä uusinta yhdyskäytäväversiota, tietovirran päivitys epäonnistuu ja näyttöön tulee virhesanomia, kuten **Avainsanaa ei tueta: määritysominaisuudet. Parametrin nimi: avainsana**.

## <a name="review-ingested-data"></a>Käsiteltyjen tietojen tarkistaminen
Jos ympäristö sisältää Power Platform-tietovoita, **Tietolähteet**-sivulla on kolme osaa: 
- **Jaettu**: tietolähteet, joita kaikki Customer Insights -järjestelmänvalvojat voivat hallita. Power BI-tietovuot, oma tallennustilatilisi ja Dataverse-hallittuihin tietoihin liittäminen ovat esimerkkejä jaetuista tietolähteistä.
- **Minun hallinnoimia**: Power Platform-tietovoita voit luoda ja hallita vain sinä. Muut Customer Insights -järjestelmänvalvojat voivat tarkastella vain näitä tietovirtoja mutta eivät voi muokata, päivittää tai poistaa niitä.
- **Muiden hallinnoimia**: muiden järjestelmänvalvojien luomia Power Platform-tietovoita. Voit vain tarkastella niitä. Siinä on tietovuon omistaja, johon voi ottaa yhteyttä, jos tarvitset apua.
> [!NOTE]
> Muut käyttäjät voivat tarkastella ja käyttää kaikkia entiteettejä. Käyttäjän tilannetiedot koskevat vain tietolähteitä eikä näistä tietovoista tuloksena olevia entiteettejä.

Jos Power Platform-tietovoita ei käytetä, ryhmiä tai osia ei ole näkyvissä. **Tietolähteet**-sivu sisältää vain luettelon kaikista tietolähteistä.

Näkyvissä on kunkin käsitellyn tietolähteen nimi, sen tilan ja kyseisen tietolähteen tietojen viimeisimmän päivityskerran. Tietolähdeluettelon voi lajitella kunkin sarakkeen mukaan.

> [!div class="mx-imgBorder"]
> ![Tietolähde lisättiin.](media/configure-data-datasource-added.png "Tietolähde lisättiin")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Tietojen lataaminen voi viedä aikaa. Kun päivitys on onnistunut, käsiteltyjä tietoja voi tarkastella **Entiteetit**-sivulla. Lisätietoja on kohdassa [Entiteetit](entities.md).

## <a name="refresh-a-data-source"></a>Tietolähteen päivittäminen

Tietolähteet voidaan päivittää automaattisen aikataulun mukaan tai manuaalisesti tarvittaessa. 

Määritä kaikkien käsiteltyjen tietolähteiden ajoitetut päivitykset valitsemalla **Hallinta** > **Järjestelmä** > [**Ajoitus**](system.md#schedule-tab).

Tietolähde päivitetään tarvittaessa seuraavasti:

1. Valitse **Tiedot** > **Tietolähteet**.

2. Valitse tietolähteen vieressä olevat kolme pystysuuntaista pistettä, jos haluat päivittää. Valitse avattavasta luettelosta **Päivitä**.

3. Tietolähde on nyt valmis manuaaliseen päivitykseen. Jos päivität tietolähteen, päivitetään tietolähteessä määritettyjen entiteettien sekä tiedot että entiteettirakenne.

4. Valitse **Pysäytä päivittäminen**, jos haluat peruuttaa nykyisen päivityksen, jolloin tietolähde palautuu viimeksi päivitettyyn tilaan.

## <a name="delete-a-data-source"></a>Tietolähteen poistaminen

1. Valitse **Tiedot** > **Tietolähteet**.

2. Valitse tietolähteen vieressä olevat kolme pystysuuntaista pistettä, jos haluat poistaa kohteen. Valitse avattavasta valikosta **Poista**.

3. Vahvista poisto.


[!INCLUDE [footer-include](includes/footer-banner.md)]
