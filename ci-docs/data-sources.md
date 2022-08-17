---
title: Tietolähteiden yleiskatsaus
description: Tietoja eri lähteistä peräisin olevien tietojen tuonnista tai käsittelystä.
ms.date: 07/26/2022
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
ms.openlocfilehash: 591353bf1ba2f9ca05ddd137e1cf29dc0b0fba97
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245645"
---
# <a name="data-sources-overview"></a>Tietolähteiden yleiskatsaus

Dynamics 365 Customer Insights muodostaa yhteyksiä, joilla voidaan tuoda tietoja monenlaisesta lähdejoukosta. Tietolähteen yhdistämistä kutsutaan usein *tietojen käsittelyprosessiksi*. Tietojen käsittelyn jälkeen, tietoja voidaan [yhdistää](data-unification.md), niistä voidaan saada merkityksellisiä tietoja ja ne voidaan ottaa käyttöön. Tällä tavoin voidaan muodostaa mukautettuja kokemuksia.

## <a name="add-or-edit-data-sources"></a>Tietolähteiden lisääminen tai muokkaaminen

Tietolähteitä voidaan liittää tai tuoda Customer Insightsiin. Seuraavat linkit sisältävät tietolähteiden lisäämis- ja muokkausohjeita.

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

## <a name="manage-existing-data-sources"></a>Aiemmin luotujen tietolähteiden hallinta

Valitsemalla **Tiedot** > **Tietolähteet** voidaan tarkastella kunkin käsitellyn tietolähteen nimeä, sen tilaa ja ajankohtaa, jolloin kyseisen lähteen tiedot viimeksi päivitettiin. Tietolähdeluetteloa voi lajitella minkä tahansa sarakkeen perustella. Hallittavan tietolähteen voi etsiä myös hakuruutua käyttämällä.

Voit tarkastella käytettävissä olevia toimintoja valitsemalla tietolähteen.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Tietolähde lisättiin.":::

- [**Muokkaa**](#add-or-edit-data-sources) tietolähdettä, jos haluat muuttaa sen ominaisuuksia.
- [**Päivitä**](#refresh-data-sources) tietolähde siten, että se sisältää uusimmat tiedot.
- Tietolähteen [**rikastus**](data-sources-enrichment.md) ennen yhdistämistä.
- **Poista** tietolähde. Tietolähde voidaan poistaa vain, jos tietoja ei käytetään missään käsittelyssä, kuten yhdistämisessä, merkityksellisissä tiedoissa, aktivoinneissa tai vienneissä.

## <a name="refresh-data-sources"></a>Tietolähteiden päivittäminen

Tietolähteet voidaan päivittää automaattisen aikataulun mukaan tai manuaalisesti tarvittaessa. [Paikalliset tietolähteet](connect-power-query.md#add-data-from-on-premises-data-sources) päivitetään oman, tietojen käsittelyn aikana määritettävän aikataulun mukaan. Liitettyjen tietolähteiden osalta tietojen käsittelyssä käytetään kyseisen tietolähteen viimeisimpiä saatavana olevia tietoja.

Valitsemalla **Hallinta** > **Järjestelmä** > [**Aikataulu**](schedule-refresh.md) määritetään järjestelmän aikatauluttamat käsiteltyjen tietolähteiden päivitykset.

Tietolähteen päivittäminen pyynnöstä:

1. Valitse **Tiedot** > **Tietolähteet**.

1. Valitse päivitettävä tietolähde ja valitse sitten **Päivitä**. Tietolähde on nyt valmis manuaaliseen päivitykseen. Jos päivität tietolähteen, päivitetään tietolähteessä määritettyjen entiteettien sekä tiedot että entiteettirakenne.

1. Valitse tila, jos haluat avata **Edistymisen tiedot** -ruudun ja tarkastella edistymistä. Peruuta työ valitsemalla ruudun alareunassa **Peruuta työ**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
