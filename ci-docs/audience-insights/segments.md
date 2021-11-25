---
title: Käyttäjäryhmien merkityksellisten tietojen segmentit
description: Yleiskatsaus segmenteistä ja niiden luomisesta ja hallinnasta.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 56978c984a91e85e86956e7eac1d59609c349b6a
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732584"
---
# <a name="segments-overview"></a>Segmenttien yleiskatsaus

Segmenttien avulla asiakkaita ryhmitellä demografia-, tapahtuma- tai toimintamääritteiden perusteella. Segmenttejä käyttämällä voit kohdistaa markkinointikampanjoita, myyntiaktiviteetteja ja asiakastukitoimintoja liiketoiminnan tavoitteiden saavuttamiseksi.

Segmenttimäärityksen suodattimia vastaavia asiakasprofiileita kutsutaan segmentin *jäseniksi*. Käytössä on jotakin [palvelurajoituksia](service-limits.md).

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

:::image type="content" source="media/segments-selected-segment.png" alt-text="Valittu segmentti sekä vaihtoehtojen avattava luettelo ja käytettävissä olevat vaihtoehdot.":::

Seuraava toiminto on käytettävissä, kun valitse segmentin:

- **Näytä** segmentin tietoja, mukaan lukien jäsenmäärän trendi, segmentin jäsenten esikatselu.
- **Muokkaa** segmenttiä, jos haluat muuttaa sen ominaisuuksia.
- Luo segmentin **kaksoiskappale**. Voit muokata sen ominaisuuksia heti tai tallentaa kaksoiskappaleen.
- **Päivitä** segmentti siten, että se sisältää uusimmat tiedot.
- **Aktivoi** segmentti tai **Poista aktivointi**. Segmenteillä on kaksi mahdollista tilaa: aktiivinen ja passiivinen. Näistä tiloista on hyötyä segmenttiä muokattaessa. Passiivisissa segmenteissä on segmentin määritelmä, mutta se ei sisällä vielä asiakkaita. Kun segmentti aktivoidaan, tila muuttuu passiivisesta aktiivisesti ja se aloittaa segmentin määritelmää vastaavien asiakkaiden etsimisen. Jos [aikataulutettu päivitys](system.md#schedule-tab) on määritetty, passiivisten segmenttien **Tila**-arvon on **Ohitettu**, mikä osoittaa, että päivitystä ei edes yritetty. Kun passiivinen segmentti aktivoidaan, se päivittyy ja se sisällytetään aikataulutettuihin päivityksiin.
  Voit vaihtoehtoisesti määrittää tulevan päivämäärän ja kellonajan tietyn segmentin aktivointiin ja aktivoinnin poistamiseen avattavan **Aktivoi / Poista aktivointi** -valikon **Ajoita myöhemmin** -toiminnolla.
- **Nimeä uudelleen** segmentti.
- **Lataa** jäsenten luettelo CSV-tiedostona.
- **Hallitse vientiä** tarkastellaksesi vientiin liittyviä segmenttejä ja hallita niitä. [Lisätietoja vienneistä.](export-destinations.md)
- **Poista** segmentti.

## <a name="refresh-segments"></a>Päivitä segmentit

Voit päivittää kaikki segmentit kerralla valitsemalla **Päivitä kaikki** **Segmentit**-sivulla. Halutessasi voit päivittää yhden tai useita segmenttejä, kun valitset ne ja valitse sitten **Päivitä** asetuksista. Voit myös määrittää toistuvan päivityksen kohdassa **Järjestelmänvalvoja** > **Järjestelmä** > **Ajoita**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="export-segments"></a>Segmenttien vienti

Voit viedä segmentin segmenttisivulta tai [vientisivulta](export-destinations.md). 

1. Siirry **Segmentit**-sivulle.

1. Valitse **Näytä lisää [...]** segmentistä, jonka haluat viedä.

1. Valitse **Hallitse vientejä** toimintojen avattavasta luettelosta.

1. **Segmentin vienti (esikatselu)** -sivu avautuu. Kaikki määritetyt viennit on ryhmitelty sen mukaan, sisältävätkö ne nykyisen segmentin.

   1. Jos haluat lisätä valitun segmentin vientiin, **Muokkaa** vastaavaa vientiä, jotta voit valita vastaavan segmentin ja sitten tallenna. Yksittäisten asiakkaiden ympäristöissä voit sen sijaan valita viennin luettelosta ja valita **Lisää segmentti**, jolloin saat saman tuloksen.

   1. Jos haluat luoda uuden viennin valitulla segmentillä, valitse **Lisää vienti**. Lisätietoja viennin luomisesta on ohjeaiheessa [Uuden viennin luominen](export-destinations.md#set-up-a-new-export).

1. Palaa segmenttien pääsivulle valitsemalla **Takaisin**.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)] 
