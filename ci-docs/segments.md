---
title: Segmenttien yleiskatsaus
description: Yleiskatsaus segmenteistä ja niiden luomisesta ja hallinnasta.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 195a7c733f047c24f9f47a151c1cb623fe34d055
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246289"
---
# <a name="segments-overview"></a>Segmenttien yleiskatsaus

Segmenttien avulla asiakkaita ryhmitellä demografia-, tapahtuma- tai toimintamääritteiden perusteella. Segmenttejä käyttämällä voit kohdistaa markkinointikampanjoita, myyntiaktiviteetteja ja asiakastukitoimintoja liiketoiminnan tavoitteiden saavuttamiseksi.

Segmenttimäärityksen suodattimia vastaavia asiakasprofiileita kutsutaan segmentin *jäseniksi*. Käytössä on jotakin [palvelurajoituksia](/dynamics365/customer-insights/service-limits).

## <a name="create-a-segment"></a>Luo segmentti

Valitse, miten kohdeyleisön perusteella luodaan segmentti.

# <a name="individual-consumers-b-to-c"></a>[Yksittäiset kuluttajat (kuluttajakauppa)](#tab/b2c)

- Monimutkaiset segmentit segmentin muodostimen avulla: [Luo oma](segment-builder.md)
- Yksinkertaiset segmentit yhdellä operaattorilla: [Pikasegmentti](segment-quick.md)
- Tekoälyä käyttävä tapa löytää samanlaisia asiakkaita: [Samanlaiset asiakkaat](find-similar-customer-segments.md)
- Tekoälypohjaiset ehdotukset, jotka perustuvat mittareihin tai määritteisiin: [Ehdotetut segmentit mittareiden perusteella](suggested-segments.md)
- Aktiviteetteihin perustuvat ehdotukset: [Asiakasaktiviteettien perusteella ehdotetut segmentit](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Yritystilit (yritysten väliset)](#tab/b2b)

- Yksinkertaiset tai monimutkaiset segmentit segmentin muodostimen avulla: [Luo oma](segment-builder.md)

---

## <a name="manage-existing-segments"></a>Aiemmin luotujen segmenttien hallinta

Siirry **Segmentit**-sivulle, kun haluat tarkastella luomiasi segmenttejä, niiden asemaa ja tilaa, jäsenten lukumäärää ja tietojen viimeisintä päivittämisaikaa. Segmenttiluetteloa voi lajitella minkä tahansa sarakkeen perustella. Hallittavan segmentin voi etsiä myös hakuruutua käyttämällä.

Voit tarkastella käytettävissä olevia toimintoja valitsemalla segmentin.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Valittu segmentti sekä vaihtoehtojen avattava luettelo ja käytettävissä olevat vaihtoehdot." lightbox="media/segments-selected-segment.png":::

- [**Näytä**](#view-segment-details) segmentin tietoja, mukaan lukien jäsenmäärän trendi ja segmentin jäsenten esikatselu.
- **Lataa** jäsenten luettelo CSV-tiedostona.
- **Muokkaa** segmenttiä, jos haluat muuttaa sen ominaisuuksia.
- Luo segmentin **kaksoiskappale**. Voit muokata sen ominaisuuksia heti tai tallentaa kaksoiskappaleen.
- [**Päivitä**](#refresh-segments) segmentti siten, että se sisältää uusimmat tiedot.
- **Aktivoi** segmentti tai **Poista aktivointi**. Passiiviset segmentit eivät päivity [aikataulutetun päivityksen](schedule-refresh.md) aikana, ja passiivisten segmenttien **Tila**-arvo on **Ohitettu**, mikä osoittaa, että päivitystä ei edes yritetty. Aktiiviset segmentit päivittyvät tyypin mukaan: staattiset tai dynaamiset.
- **Tee staattinen** tai **tee dynaaminen** segmenttityyppi. Staattiset segmentit pitää päivittää manuaalisesti. Dynaamiset segmentit päivitetään järjestelmän päivityksen aikana automaattisesti.
- [**Etsi samanlaisia asiakkaita**](find-similar-customer-segments.md) segmentistä.
- **Nimeä uudelleen** segmentti.
- **Tunniste** segmentin [tunnisteiden hallintaa varten](work-with-tags-columns.md#manage-tags).
- [**Hallitse vientiä**](#export-segments) tarkastellaksesi vientiin liittyviä segmenttejä ja hallitaksesi niitä. [Lisätietoja vienneistä.](export-destinations.md)
- **Poista** segmentti.
- **Sarakkeet** [sarakkeiden mukauttamiseksi](work-with-tags-columns.md#customize-columns) näyttämistä varten.
- **Suodatin** [tunnisteiden suodattamiseksi](work-with-tags-columns.md#filter-on-tags).
- **Hae nimi** segmentin nimen mukaan tehtävää hakua varten.

## <a name="view-segment-details"></a>Segmentin tietojen tarkasteleminen

Valitse **Segmentit**-sivulla segmentti, jotta voit tarkastella käsittelyhistoriaa ja segmentin jäseniä.

Sivun yläosassa on trendikaavio, joka visualisoi jäsenmäärän muutokset. Vie kohdistin arvopisteiden päälle, jos haluat nähdä tietyn päivämäärän jäsenmäärän. Muuta visualisoinnin aikaväli.

:::image type="content" source="media/segment-time-range.png" alt-text="Segmentin aikaväli.":::

Alaosassa on luettelo segmentin jäsenistä.

> [!NOTE]
> Tässä luettelossa näkyvät kentät perustuvat segmentin entiteettien määritteisiin.
>
>Luettelo on täsmäävien segmentin jäsenten esikatselu. Siinä näkyvät segmentin ensimmäiset 100 tietuetta, joten voit nopeasti arvioida segmentin ja tarkistaa sen määritykset tarpeen mukaan. Jos haluat nähdä kaikki täsmäävät tietueet, sinun on [vietävä segmentti](export-destinations.md).

## <a name="refresh-segments"></a>Päivitä segmentit

Segmentit voidaan päivittää automaattisen aikataulun mukaan tai manuaalisesti tarvittaessa. Segmentit päivitetään manuaalisesti valitsemalla ensin ne ja sitten **Päivitä**.

[Automaattinen päivitys ajoitetaan](schedule-refresh.md) valitsemalla **Hallinta** > **Järjestelmä** > **Aikatauluta**. Seuraavat säännöt pätevät:

- Kaikki **Dynaaminen**- tai **Laajennus**-tyyppiset segmentit päivittyvät automaattisesti määritetyllä välillä. Kun päivitys on valmis, **Tila** ilmaisee, onko segmentin päivityksessä ongelmia. **Päivitetty viimeksi** näyttää edellisen onnistuneen päivityksen aikaleiman. Jos tapahtuu virhe, saat näkyviin tiedot siitä, mitä tapahtui, valitsemalla virheen.
- Segmenttejä, joiden tyyppinä on **Staattinen**, *ei* päivitetä automaattisesti. **Päivitetty viimeksi** -kentässä näkyy staattisen segmentin edellisen suorituksen tai manuaalisen päivityksen aikaleima.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Segmenttien vienti

Vie segmentit muihin sovelluksiin, jotta voit käyttää tietoja lisää. Voit viedä segmentin segmenttisivulta tai [vientisivulta](export-destinations.md).

1. Valitse **Segmentit**-sivulla segmentti, jonka haluat viedä.

1. Valitse **Hallitse vientejä**. **Segmentin vienti (esikatselu)** -sivu avautuu. Näytä kaikki määritetyt viennit ryhmiteltyinä sen mukaan, sisältävätkö ne nykyisen segmentin.

   1. Jos haluat lisätä valitun segmentin vientiin, **Muokkaa** vastaavaa vientiä, jotta voit valita vastaavan segmentin ja sitten tallenna. Yksittäisten asiakkaiden ympäristöissä voit valita viennin luettelosta ja valita **Lisää segmentti**, jolloin saat saman tuloksen.

   1. Jos haluat luoda uuden viennin valitulla segmentillä, valitse **Lisää vienti**. Lisätietoja viennin luomisesta on ohjeaiheessa [Uuden viennin luominen](export-destinations.md#set-up-a-new-export).

1. Palaa segmenttien pääsivulle valitsemalla **Takaisin**.

## <a name="track-usage-of-a-segment"></a>Segmentin käytön seuranta

Jos käytät sovelluksissa segmenttejä, jotka perustuvat samaan Microsoft Dataverse -organisaatioon, joka on yhteydessä Customer Insights -asiakkaaseen, voit seurata segmentin käyttöä. [Dynamics 365 Marketingin asiakassiirtymissä käytettävien Customer Insights -segmenttien osalta](/dynamics365/marketing/real-time-marketing-ci-profile) järjestelmä ilmoittaa sinulle segmentin käytöstä.

Kun muokkaat segmenttiä, jota käytetään Customer Insights -ympäristössä tai joka on asiakassiirtymä markkinointisivulla, [segmentin muodostimen](segment-builder.md) mainospalkki ilmoittaa sinulle riippuvuudet. Voit tarkastaa riippuvuustiedot suoraan mainospalkin avulla tai valitsemalla segmentin muodostimessa **Käyttö**.

**Segmentin käyttö** -ruudussa näkyvät tiedot tämän segmentin käytöstä Dataverse-pohjaisissa sovelluksissa. Asiakassiirtymissä käytetyissä segmenteissä on linkki, jolla voit tarkastaa, missä markkinointisegmentissä tätä segmenttiä käytetään. Jos sinulla on markkinointisovelluksen käyttöoikeus, voit tarkastella siellä lisätietoja.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Sivuruutu, jossa on segmentin käytön tiedot segmentin muodostimessa.":::

Järjestelmä ilmoittaa seuratun segmentin käytöstä, kun yrität poistaa sen. Jos poistettavaa segmenttiä käytetään markkinoinnin asiakassiirtymässä, se pysähtyy kaikille segmentin käyttäjille. Jos siirtymä kuuluu markkinointikampanjaan, poisto vaikuttaa itse kampanjaan. Voit kuitenkin poistaa segmentin varoituksesta huolimatta.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Valintaikkuna, jossa vahvistetaan segmentin poisto, kun segmenttiä käytetään Dataverse- sovelluksessa.":::

### <a name="supported-apps"></a>Tuetut sovellukset

Käyttöä seurataan tällä hetkellä seuraavissa Dataverse-pohjaisissa sovelluksissa:

- [Dynamics 365 Marketingin asiakassiirtymät](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
