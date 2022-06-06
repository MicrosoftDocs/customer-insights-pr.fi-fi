---
title: Segmentit Customer Insightsissa
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
ms.openlocfilehash: d616ec8273115203dddb59334a348c66e72fa678
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800738"
---
# <a name="segments-overview"></a>Segmenttien yleiskatsaus

Segmenttien avulla asiakkaita ryhmitellä demografia-, tapahtuma- tai toimintamääritteiden perusteella. Segmenttejä käyttämällä voit kohdistaa markkinointikampanjoita, myyntiaktiviteetteja ja asiakastukitoimintoja liiketoiminnan tavoitteiden saavuttamiseksi.

Segmenttimäärityksen suodattimia vastaavia asiakasprofiileita kutsutaan segmentin *jäseniksi*. Käytössä on jotakin [palvelurajoituksia](/dynamics365/customer-insights/service-limits).

## <a name="create-a-new-segment"></a>Luo uusi segmentti

Uuden segmentin voi luoda useilla tavoilla: 

# <a name="individual-consumers-b-to-c"></a>[Yksittäiset kuluttajat (kuluttajakauppa)](#tab/b2c)

- Monimutkainen segmentti segmentin muodostimen avulla: [Luo oma](segment-builder.md#create-a-new-segment) 
- Yksinkertaiset segmentit yhdellä operaattorilla: [Pikasegmentti](segment-builder.md#quick-segments) 
- Tekoälyä käyttävä tapa löytää samanlaisia asiakkaita: [Samanlaiset asiakkaat](find-similar-customer-segments.md) 
- Tekoälypohjaiset ehdotukset, jotka perustuvat mittareihin tai määritteisiin: [Ehdotetut segmentit mittareiden parantamiseksi](suggested-segments.md) 
- Aktiviteetteihin perustuvat ehdotukset: [Asiakasaktiviteettien perusteella ehdotetut segmentit](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Yritystilit (yritysten väliset)](#tab/b2b)

- Monimutkainen segmentti segmentin muodostimen avulla: [Luo oma](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Aiemmin luotujen segmenttien hallinta

Siirry **Segmentit**-sivulle nähdäksesi kaikki tallennetut segmentit ja hallitaksesi niitä.

Jokaista segmenttiä edustaa rivi, joka sisältää segmentin lisätietoja.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Valittu segmentti sekä vaihtoehtojen avattava luettelo ja käytettävissä olevat vaihtoehdot." lightbox="media/segments-selected-segment.png":::

Seuraavat toiminnot ovat käytettävissä, kun valitset segmentin:

- **Näytä** segmentin tietoja, mukaan lukien jäsenmäärän trendi, segmentin jäsenten esikatselu.
- **Lataa** jäsenten luettelo CSV-tiedostona.
- **Muokkaa** segmenttiä, jos haluat muuttaa sen ominaisuuksia.
- Luo segmentin **kaksoiskappale**. Voit muokata sen ominaisuuksia heti tai tallentaa kaksoiskappaleen.
- **Päivitä** segmentti siten, että se sisältää uusimmat tiedot.
- **Aktivoi** segmentti tai **Poista aktivointi**. Passiivisissa segmenteissä on segmentin määritelmä, mutta se ei sisällä vielä asiakkaita. Aktiivinen segmentti hakee asiakkaita, jotka vastaavat segmentin määritystä. Jos [aikataulutettu päivitys](system.md#schedule-tab) on määritetty, passiivisten segmenttien **Tila**-arvon on **Ohitettu**, mikä osoittaa, että päivitystä ei edes yritetty. Kun passiivinen segmentti aktivoidaan, se päivittyy ja se sisällytetään aikataulutettuihin päivityksiin.
  Voit vaihtoehtoisesti määrittää tulevan päivämäärän ja kellonajan tietyn segmentin aktivointiin ja aktivoinnin poistamiseen avattavan **Aktivoi / Poista aktivointi** -valikon **Ajoita myöhemmin** -toiminnolla.
- **[Etsi samanlaisia asiakkaita](find-similar-customer-segments.md)** segmentistä.
- **Nimeä uudelleen** segmentti.
- **Tunniste** segmentin [tunnisteiden hallintaa varten](work-with-tags-columns.md#manage-tags).
- **Lataa** jäsenten luettelo CSV-tiedostona.
- **Hallitse vientiä** tarkastellaksesi vientiin liittyviä segmenttejä ja hallita niitä. [Lisätietoja vienneistä.](export-destinations.md)
- **Poista** segmentti.
- **Sarakkeet** [sarakkeiden mukauttamiseksi](work-with-tags-columns.md#customize-columns) näyttämistä varten.
- **Suodatin** [tunnisteiden suodattamiseksi](work-with-tags-columns.md#filter-on-tags).
- **Hae nimi** segmentin nimen mukaan tehtävää hakua varten.

## <a name="refresh-segments"></a>Päivitä segmentit

Voit päivittää kaikki segmentit kerralla valitsemalla **Päivitä kaikki** **Segmentit**-sivulla. Halutessasi voit päivittää yhden tai useita segmenttejä, kun valitset ne ja valitse sitten **Päivitä** asetuksista. Voit myös määrittää toistuvan päivityksen kohdassa **Järjestelmänvalvoja** > **Järjestelmä** > **Ajoita**. Kun toistuva päivitys määritetään, seuraavat säännöt ovat voimassa:

- Kaikki **Dynaaminen**- tai **Laajennus**-tyyppiset segmentit päivittyvät automaattisesti määritetyllä välillä. Kun päivitys on valmis, **Tila** ilmaisee, onko segmentin päivityksessä ongelmia. **Päivitetty viimeksi** näyttää edellisen onnistuneen päivityksen aikaleiman. Jos tapahtuu virhe, saat näkyviin tiedot siitä, mitä tapahtui, valitsemalla virheen.
- Segmenttejä, joiden tyyppinä on **Staattinen**, *ei* päivitetä automaattisesti. **Päivitetty viimeksi** -kentässä näkyy staattisten segmenttien edellisen suorituksen tai manuaalisen päivityksen aikaleima.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Segmenttien vienti

Voit viedä segmentin segmenttisivulta tai [vientisivulta](export-destinations.md). 

1. Siirry **Segmentit**-sivulle.

1. Valitse vietävän segmentin kohdalla kolme allekkaista pistettä (&vellip;).

1. Valitse **Hallitse vientejä** toimintojen avattavasta luettelosta.

1. **Segmentin vienti (esikatselu)** -sivu avautuu. Kaikki määritetyt viennit on ryhmitelty sen mukaan, sisältävätkö ne nykyisen segmentin.

   1. Jos haluat lisätä valitun segmentin vientiin, **Muokkaa** vastaavaa vientiä, jotta voit valita vastaavan segmentin ja sitten tallenna. Yksittäisten asiakkaiden ympäristöissä voit sen sijaan valita viennin luettelosta ja valita **Lisää segmentti**, jolloin saat saman tuloksen.

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

## <a name="view-processing-history-and-segment-members"></a>Tarkastele käsittelyhistoriaa ja segmentin jäseniä

Voit tarkastella segmentin yhdistettyjä tietoja tarkastelemalla sen tietoja.

Valitse **Segmentit**-sivulla segmentti, jota haluat tarkastella.

Sivun yläosassa on trendikaavio, joka visualisoi jäsenmäärän muutokset. Vie kohdistin arvopisteiden päälle, jos haluat nähdä tietyn päivämäärän jäsenmäärän.

Voit päivittää visualisoinnin aikavälin.

> [!div class="mx-imgBorder"]
> ![Segmentin aikaväli.](media/segment-time-range.png "Segmentin aikaväli")

Alaosassa on luettelo segmentin jäsenistä.

> [!NOTE]
> Tässä luettelossa näkyvät kentät perustuvat segmentin entiteettien määritteisiin.
>
>Luettelo on täsmäävien segmentin jäsenten esikatselu. Siinä näkyvät segmentin ensimmäiset 100 tietuetta, joten voit nopeasti arvioida segmentin ja tarkistaa sen määritykset tarpeen mukaan. Jos haluat nähdä kaikki täsmäävät tietueet, sinun on [vietävä segmentti](export-destinations.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
