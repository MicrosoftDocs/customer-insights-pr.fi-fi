---
title: Tietolähteiden yleiskatsaus
description: Tietoja eri lähteistä peräisin olevien tietojen tuonnista tai käsittelystä.
ms.date: 09/29/2022
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
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610048"
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

Tietolähteet voidaan päivittää automaattisen aikataulun mukaan tai manuaalisesti tarvittaessa. [Paikalliset tietolähteet](connect-power-query.md#add-data-from-on-premises-data-sources) päivitetään oman, tietojen käsittelyn aikana määritettävän aikataulun mukaan. Vianmääritysvihjeitä on kohdassa [PPDF Power Query -pohjaisten tietolähteen päivitysongelmien vianmääritys](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

Liitettyjen tietolähteiden osalta tietojen käsittelyssä käytetään kyseisen tietolähteen viimeisimpiä saatavana olevia tietoja.

Valitsemalla **Hallinta** > **Järjestelmä** > [**Aikataulu**](schedule-refresh.md) määritetään järjestelmän aikatauluttamat käsiteltyjen tietolähteiden päivitykset.

Tietolähteen päivittäminen pyynnöstä:

1. Valitse **Tiedot** > **Tietolähteet**.

1. Valitse päivitettävä tietolähde ja valitse sitten **Päivitä**. Tietolähde on nyt valmis manuaaliseen päivitykseen. Jos päivität tietolähteen, päivitetään tietolähteessä määritettyjen entiteettien sekä tiedot että entiteettirakenne.

1. Valitse tila, jos haluat avata **Edistymisen tiedot** -ruudun ja tarkastella edistymistä. Peruuta työ valitsemalla ruudun alareunassa **Peruuta työ**.

## <a name="corrupt-data-sources"></a>Vioittuneet tietolähteet

Käsiteltävissä tiedoissa voi olla vioittuneita tietueita, joiden vuoksi tietojen käsittelyprosessi kyllä valmistuu mutta tuloksena on virheitä tai varoituksia.

> [!NOTE]
> Jos tietojen käsittely valmistuu mutta tuloksena on virheitä, tämän jälkeen kyseistä tietolähdettä hyödyntävä käsittely (kuten yhdistäminen tai aktiviteetin luonti) ohitetaan. Jos käsittely valmistuu mutta tuloksena on varoituksia, tämän jälkeen jatketaan käsittelyjä mutta joitakin tietueita ei ehkä sisällytetä.

Näitä virheitä voi tarkastella tehtävän tiedoissa.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Tehtävän tiedoissa näkyy vioittuneista tiedoista ilmoittava virhe":::

Vioittuneet tietueet näytetään järjestelmän luomissa entiteeteissä.

### <a name="fix-corrupt-data"></a>Vioittuneiden tietojen korjaaminen

1. Vioittuneita tietoja voi tarkastella valitsemalla **Tiedot** > **Entiteetit** ja etsimällä vioittuneet entiteetit **Järjestelmä**-osassa. Vioittuneiden entiteettien nimeämisrakenne: DataSourceName_EntityName_corrupt.

1. Valitse ensin vioittunut entiteetti ja sitten **Tiedot**-välilehti.

1. Selvitä tietueen vioittuneet kentät ja niiden syy.

   :::image type="content" source="media/corruption-reason.png" alt-text="Vioittumisen syy." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **Tiedot** > **Entiteetit** -kohdassa näkyy vain osa vioittuneista tietueista. Kaikkia vioittuneita tietueita voi tarkastella viemällä tiedostot tallennustilillä olevaan säilöön [Customer Insightsin vientiprosessin](export-destinations.md) mukaisesti. Jos käytössä on oma tallennustili, myös Customer Insights -kansiota voidaan tarkastella tallennustilillä.

1. Korjaa vioittuneet tiedot. Esimerkiksi Azure Data Lake -tietolähteissä [tiedot korjataan Data Lake Storagessa tai tietotyypit päivitetään manifest- tai model.json-tiedostossa](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data). Power Query -tietolähteissä tiedot korjataan lähdetiedostossa ja [tietotyyppi korjataan muunnosvaiheessa](connect-power-query.md#data-type-does-not-match-data) **Power Query – Muokkaa kyselyjä** -sivulla.

Tietolähteen seuraavan päivityksen yhteydessä korjatut tietueet päivitetään Customer Insightsiin ja välitetään jatkoprosesseihin.

Esimerkiksi syntymäpäiväsarakkeen tietotyypiksi on määritetty päivämäärä. Asiakasrekisterin syntymäpäiväksi on merkitty "1.1.19777". Järjestelmä merkitsee tämän tietueen vioittuneeksi. Vaihda syntymäpäiväksi lähdejärjestelmässä 1977. Tietolähteiden automaattisen päivityksen jälkeen kentän muoto on nyt kelvollinen ja tietue poistetaan vioittuneesta entiteetistä.

[!INCLUDE [footer-include](includes/footer-banner.md)]
