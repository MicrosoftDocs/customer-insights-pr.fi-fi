---
title: Tietolähteiden yleiskatsaus
description: Tietoja eri lähteistä peräisin olevien tietojen tuonnista tai käsittelystä.
ms.date: 05/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: fbe44f655bdbc20ef7f0956022395e2dcb570adf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051449"
---
# <a name="data-sources-overview"></a>Tietolähteiden yleiskatsaus

Dynamics 365 Customer Insights muodostaa yhteyksiä, joilla voidaan tuoda tietoja monenlaisesta lähdejoukosta. Tietolähteen yhdistämistä kutsutaan usein *tietojen käsittelyprosessiksi*. Tietojen käsittelyn jälkeen, tietoja voidaan [yhdistää](data-unification.md), niistä voidaan saada merkityksellisiä tietoja ja ne voidaan ottaa käyttöön. Tällä tavoin voidaan muodostaa mukautettuja kokemuksia.

## <a name="add-data-sources"></a>Tietolähteiden lisääminen

Tietolähteitä voidaan liittää tai tuoda Customer Insightsiin. Seuraavat linkit sisältävät tietolähteiden lisäämisohjeita.

**Tietolähteen liittäminen**

Jos tiedot on valmisteltu jossain Microsoftin Azure-tietolähteessä, Customer Insights voi muodostaa kätevästi yhteyden tietolähteeseen ilman tietojen uudelleenkäsittelyjä. Mahdolliset vaihtoehdot:
- [Azure Data Lake Storage (csv- tai parquet-tiedostot Common Data Model -kansiossa)](connect-common-data-model.md)
- [Azure Synapse Analytics (Data Lake -tietokannat)](connect-synapse.md)
- [Microsoft Dataverse Data Lake -tallennustila](connect-dataverse-managed-lake.md)

**Tuonti ja muunto**

Jos käytössä on paikallisia tietolähteitä, Microsoftin tai kolmas osapuoli tuo ja muuntaa tiedot Power Query -yhdistimien avulla.
- [Power Query ‑yhdistimet](connect-power-query.md)

## <a name="review-data-sources"></a>Tietolähteiden tarkistaminen

Jos ympäristö oli määritetty käyttämään Customer Insights -tallennustilaa ja käytössä on paikalliset tietolähteet, käytössä on Power Platform -tietovuot. Power Platform -tietovoiden avulla voidaan tarkastella jaettuja tietolähteitä ja muiden hallitsemia tietolähteitä. **Tietolähteet**-sivulla on kolmiosainen tietolähdeluettelo:
- **Jaettu**: tietolähteet, joita kaikki Customer Insights -järjestelmänvalvojat voivat hallita. Power Platform -tietovuot, oma tallennustilatili ja Dataversessa hallittuun Data Lake -tallennustilaan liittäminen ovat esimerkkejä jaetuista tietolähteistä.
- **Minun hallinnoimia**: Power Platform -tietovoita voidaan luoda ja hallita vain itse Muut Customer Insights -järjestelmänvalvojat voivat tarkastella vain näitä tietovirtoja mutta eivät voi muokata, päivittää tai poistaa niitä.
- **Muiden hallinnoimia**: muiden järjestelmänvalvojien luomia Power Platform-tietovoita. Voit vain tarkastella niitä. Siinä on tietovuon omistaja, johon voi ottaa yhteyttä, jos tarvitset apua.
> [!NOTE]
> Muut käyttäjät voivat tarkastella ja käyttää kaikkia entiteettejä. Vaikka tietolähteet luonut käyttäjä omistaa ne, jokainen Customer Insights -käyttäjä voi käyttää tietojen käsittelyn tuloksena syntyneitä entiteettejä.

Jos ympäristö ei käytä Power Platform -tietovoita, **Tietolähteet** -sivulla on ainoastaan kaikki tietolähteet sisältävä luettelo. Erillisiä osia ei ole näkyvissä.

Valitsemalla **Tiedot** > **Tietolähteet** voidaan tarkastella kunkin käsitellyn tietolähteen nimeä, sen tilaa ja ajankohtaa, jolloin kyseisen lähteen tiedot viimeksi päivitettiin. Tietolähdeluettelon voi lajitella kunkin sarakkeen mukaan.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Tietolähde lisättiin.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Tietojen lataaminen voi viedä aikaa. Kun päivitys on onnistunut, käsiteltyjä tietoja voi tarkastella **Entiteetit**-sivulla. Lisätietoja on kohdassa [Entiteetit](entities.md).

## <a name="refresh-data-sources"></a>Tietolähteiden päivittäminen

Tietolähteet voidaan päivittää automaattisen aikataulun mukaan tai manuaalisesti tarvittaessa. [Paikalliset tietolähteet](connect-power-query.md#add-data-from-on-premises-data-sources) päivitetään oman, tietojen käsittelyn aikana määritettävän aikataulun mukaan. Liitettyjen tietolähteiden osalta tietojen käsittelyssä käytetään kyseisen tietolähteen viimeisimpiä saatavana olevia tietoja.

Valitsemalla **Hallinta** > **Järjestelmä** > [**Aikataulu**](system.md#schedule-tab) määritetään järjestelmän aikatauluttamat käsiteltyjen tietolähteiden päivitykset.

Tietolähde päivitetään tarvittaessa seuraavasti:

1. Valitse **Tiedot** > **Tietolähteet**.

1. Valitse tietolähteen vieressä olevat kolme pystysuuntaista pistettä (&vellip;), jos haluat päivittää. Valitse avattavasta luettelosta **Päivitä**. Tietolähde on nyt valmis manuaaliseen päivitykseen. Jos päivität tietolähteen, päivitetään tietolähteessä määritettyjen entiteettien sekä tiedot että entiteettirakenne.

1. Valitse **Pysäytä päivittäminen**, jos haluat peruuttaa nykyisen päivityksen, jolloin tietolähde palautuu viimeksi päivitettyyn tilaan.

## <a name="delete-a-data-source"></a>Tietolähteen poistaminen

Tietolähde voidaan poistaa vain, jos tietoja ei käytetään missään käsittelyssä, kuten yhdistämisessä, merkityksellisissä tiedoissa, aktivoinneissa tai vienneissä.

1. Valitse **Tiedot** > **Tietolähteet**.

2. Valitse tietolähteen vieressä olevat kolme pystysuuntaista pistettä (&vellip;), jos haluat poistaa kohteen. Valitse avattavasta valikosta **Poista**.

3. Vahvista poisto.


[!INCLUDE [footer-include](includes/footer-banner.md)]
