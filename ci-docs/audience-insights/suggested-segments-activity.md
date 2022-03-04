---
title: Aktiviteetin perusteella ehdotetut segmentit.
description: Anna koneoppimisen auttaa sinua löytämään uusia ja mielenkiintoisia segmenttejä asiakasaktiviteettien perusteella.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: 9c10a32b770ea110a1166f20f72116a3a12cb92e
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354459"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Aktiviteettitietojen perusteella ehdotetut segmentit (esiversio)

Löydä mielenkiintoisia asiakassegmenttejä asiakasaktiviteettitietojen perusteella, jota Customer Insights käsittelee. Esimerkkejä aktiviteettitiedoista ovat tapahtumat, tukipuhelun kesto, ostot tai palautukset. Aktiviteettitiedoista analysoidaan segmenttien ehdottamista varten niiden viimeaikaisuutta, toistuvuutta ja rahallista arvoa (tai kestoa). Vaihtoehtoisesti voidaan luoda [ehdotettuja segmenttejä mittarin parantamista varten tai ymmärryksen parantamiseksi siitä, mikä vaikuttaa määritteeseen](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Ehdotetut segmentit -välilehti, jossa näkyvät aktiviteettiin perustuvat ja määritteisiin perustuvat segmenttiehdotukset.":::

## <a name="categorize-customers-by-activity"></a>Luokittele asiakkaat aktiviteetin mukaan

Customer Insightsissa saatavilla olevien [aktiviteettitietojen](activities.md) avulla voimme luoda asiakasryhmiä edustavia ehdotuksia:

- aktiivisimmat asiakkaat 
- asiakkaat, jotka ovat tehneet eniten ostoksia 
- asiakkaat, jotka tuottivat eniten tuloja 
- asiakkaat, jotka eivät ole olleet aktiivisia viime aikoina 
- asiakkaat, jotka ovat usein vuorovaikutuksessa yrityksesi kanssa  

Jos sinulla on vähittäiskauppa, voit selvittää, mitkä asiakkaat tuovat eniten tuottoa, ja palkita heidät kupongilla. Voit myös tunnistaa satunnaisia asiakkaita ja tarjota heille liittymistä palkinto-ohjelmaan, jotta he vierailisivat yrityksessäsi useammin.
Jos olet julkisen terveydenhuollon alalla ja tavoitteenasi on minimoida yksittäisten potilaiden kulut. Yksi tapa tehdä se voisi olla toistuvien käyntien vähentäminen tarjoamalla parasta mahdollista hoitoa mahdollisimman harvoilla käynneillä. Tässä tapauksessa tavoitteenasi on pitää käyntitiheys alhaisena ja minimoida potilaiden toistuvat kustannukset. Tai voit tunnistaa sellaisten potilaiden segmentit, joilla on usein toistuvia tapaamisia ja korkeat toistuvat kustannukset ja analysoida näitä tapauksia yksilön hoidon parantamiseksi. 

## <a name="required-data"></a>Pakolliset tiedot

Ehdotukset luodaan valittujen syötetietojen perusteella. 

- Asiakasprofiilit: Kaikki asiakkaat tai tietyn segmentin jäsenet. 

- Ajanjakso: Viime kuussa, viime vuonna tai millä tahansa mukautetulla aikavälillä.

- Aktiviteettityyppi: ostot, vähittäismyyntitapahtumat, verkkotapahtumat, asiakastuen palvelupyynnöt, tilaukset ja niin edelleen.  

- Customer Insights -entiteetti, joka sisältää aktiviteettitiedot: UnifiedActivity-entiteetti tai tietyn aktiviteetin entiteetti. 

- Sisällytettävät dimensiot: Viimeaikaisuus, toistuvuus tai rahallinen dimensio riippuen yrityksesi vaatimuksista.

## <a name="generate-suggested-segments"></a>Ehdotettujen segmenttien luominen

1. Valitse **Segmentit**.

1. Valitse **Ehdotukset (esiversio)** -välilehti.

1. Valitse **Etsi uusia ehdotuksia** ja valitse **Näytä tai ennakoi asiakkaan käyttäytymistä**. Suorita ohjattu käyttökokemus valitsemalla **Käynnistä**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Ohjatun määritystoiminnon ensimmäinen vaihe ehdotetulle segmentille aktiviteetin perusteella.":::

1. Anna tarvittavat syötetiedot ja valitse **Seuraava** jatkaaksesi.

   - Valitse asiakkaat: Sisällytä kaikki asiakkaat tai tietty segmentti.
   - Valitse aktiviteetti: Valitse aktiviteettityyppi ja aktiviteettia kuvaavat entiteetit.
   - Asetukset: Määritä huomioon otettava ajanjakso sekä ehdotuksiin vaikuttavat tekijät ja yhdistä määritteet.

1. Tarkista syötteesi ja valitse **Suorita** suorittaaksesi mallin ja luodaksesi ehdotuksia.

1. Asiakasprofiilien ja valittujen aktiviteettien määrästä riippuen sen suorittamiseen voi mennä muutama minuutti. 

Ehdotusten luomisen jälkeen niitä voidaan suodattaa kiinnostavimman dimension tai arvon perusteella. 

## <a name="view-details-of-a-suggested-segment"></a>Ehdotetun segmentin tietojen tarkasteleminen

Kun ehdotukset on luotu, luettelo niistä näkyy **Segmentit** > **Ehdotukset (esiversio)** **Aktiviteetteihin perustuvat ehdotukset** -osassa.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Laajennettu sivuruutu, jossa näkyvät ehdotetun segmentin yksityiskohtaiset tiedot.":::

Valitse **Katso ehdotus** ehdotetusta segmentistä, jos haluat tarkastella segmentin tietoja. Sivuruudussa on tietoja, kuten kunkin dimension laajuus kohderyhmään verrattuna. Segmentin mahdollisten jäsenten määrä ja vastaava prosenttiosuus kaikista asiakkaista näkyvät korostettuina. Jos haluat säilyttää ehdotuksen segmenttinä, valitse **Luo segmentti**.    

## <a name="save-a-suggestion-as-a-segment"></a>Ehdotuksen tallentaminen segmenttinä

1. Siirry kohtaan **Segmentit** > **Ehdotukset (esiversio)**.

1. Valitse segmentti, jonka haluat tallentaa. 

1. Valitse sivuruudussa **Luo segmentti**. 

1. Segmentin tallentamisen jälkeen se näkyy segmenttiluettelossa **Kaikki segmentit** -välilehdellä. Se voidaan nyt [päivittää tai poistaa, kuten mikä tahansa muu segmentti](segments.md). Et voi muokata segmentin tietoja. Voit kuitenkin muuttaa ehdotusten syötteiden ehtoja ja luoda erilaisia ehdotuksia.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Ehdotusjoukon päivittäminen tai muokkaaminen

1. Siirry kohtaan **Segmentit**  > **Ehdotukset (esiversio)** ja etsi segmenttiä **Aktiviteetteihin perustuvat ehdotukset** -osasta.

1. Valitse **Päivitä ehdotukset**, jos haluat päivittää ehdotukset ja säilyttää määritetyt määritteet. Voit myös valita **Muokkaa ehdotuksia** määritysten muokkaamista varten. Järjestelmä suorittaa prosessin uudelleen, luo segmenttiehdotukset viimeisimpien tietojen perusteella ja korvaa nykyiset ehdotukset.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
