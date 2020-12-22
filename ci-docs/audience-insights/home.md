---
title: Käyttäjäryhmän merkityksellisten tietojen aloitussivu
description: Sovellukseen tutustumisen aloittaminen aloitussivulta.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405609"
---
# <a name="create-a-new-environment"></a>Luo uusi ympäristö

## <a name="create-a-trial-environment"></a>Kokeiluympäristön luominen

Voit rekisteröityä kokeiluversioon [kokeiluversion rekisteröitymissivulla](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Kokeiluversiot vanhentuvat 30 päivän kuluttua.

1. Valitse ensin **Rekisteröidy ilmaisen kokeiluversion käyttäjäksi** ja sitten **Rekisteröidy nyt**.

1. Anna työpaikan tai oppilaitoksen sähköpostiosoite, kerro jotain itsestäsi ja valitse **Seuraava**.

1. Anna uudelle ympäristölle **nimi**. 

1. Valitse kokeiluversion tyyppi.

1. Valitse ympäristön **alue**.

1. Valinnainen Dynamics 365 -organisaation järjestelmänvalvojille: Valitse **Lisäasetukset** ja anna organisaation URL-osoite, jos haluat käyttää ennustetoimintoja, kuten asiakasvaihtuvuutta.

1. Valitse **Luo**. 

Ympäristön luomiseen jälkeen, näkyvissä on **Esittely**-ympäristö, joissa voit tutustua sovellukseen kuvitteellisten tietojen avulla. Voit vaihtaa näytetiedot omaa toimialaa vastaavaksi. Valitse otsikossa ensin **Asetukset**-kuvake ja valitse sitten **Esittelyn asetukset**. Voit muuttaa myös visuaalisen teeman. 

[Siirry ympäristöön](#change-between-environments), jonka loit rekisteröitymisprosessin aikana, käsittelemään omia tietoja.

## <a name="create-a-new-production-or-sandbox-environment"></a>Uuden tuotanto- ja eristysympäristön luominen

Valitse ympäristössä **Asetukset**-kuvake otsikossa ja valitse **Uusi ympäristö**.

Toimi samalla tavalla kuin [loisit kokeiluympäristön](#create-a-trial-environment). Valitsemalla **Lisäasetukset** saat käyttöösi lisäasetuksen, jolla voit tallentaa tietoja omaan Azure Data Lake -tallennustilaan. Muodosta yhteys Azure Data Lake -tallennustilaan antamalla tilin nimi ja tiliavain. Oletusarvoisesti tiedot tallennetaan hallittuun Customer Insightsin Data Lake -tallennustilaan.

> [!IMPORTANT]
> Kun tallennat tiedot Azure Data Lake Storageen, hyväksyt, että tiedot siirretään ja tallennetaan kyseisen Azure-tallennustilin mukaiseen maantieteelliseen sijaintiin. Tämä voi poiketa siitä, mihin tiedot on tallennettu Dynamics 365 Customer Insightsissa. [Lisätietoja on Microsoftin luottamuskeskuksessa.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Aloitussivuun tutustuminen

Voit [käyttää Customer Insights -ympäristöä](https://home.ci.ai.dynamics.com/) seuraavassa URL-osoitteessa: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Aloitussivulla** on yhteenveto asiakaskunnastasi ja keskeisistä mittareista, joilla seurataan yrityksen kuntoa.

> [!div class="mx-imgBorder"] 
> ![Merkityksellisiä tietoja aloitussivulla](media/home-page-insights.png "Merkityksellisiä tietoja aloitussivulla")

**Viimeaikaiset segmentit** -kohdassa esitetään asiakasryhmiä määrittämiesi demografia-, käyttäytymis- tai tapahtumamääritteiden perusteella. [Segmenttien luominen](segments.md) auttaa kohdentamaan liiketoiminnan aktiviteetit paremmin.

**Viimeaikaiset toimenpiteet** -kohdassa näkyy [mittareita](measures.md) sisältäviä ruutuja. Mitat ovat määrittämiäsi tunnuslukuja (KPI). Esimerkiksi asiakasvaihtuvuuden keskimääräinen todennäköisyys tai keskimääräinen asiakaskohtainen verkossa käytetty rahamäärä.

**Viimeaikaiset rikastukset** -osa sisältää tulokset viime aikoina suoritetuista rikastamisprosesseista. Rikastukset lisäävät tietoja asiakaskunnastasi. Esimerkiksi antamalla tietoja asiakkaiden kiinnostuksen kohteista ja suosikkibrändeistä. Näiden tietojen lukitus voidaan poistaa käyttämällä [täydennysominaisuuksia](enrichment-microsoft-graph.md) sen jälkeen, kun [vastaavuuden määrityksen](map-entities.md), [vastaavuuden](match-entities.md) ja [yhdistämisen](merge-entities.md) vaiheet on suoritettu.

## <a name="change-between-environments"></a>Ympäristöjen välillä siirtyminen

Kun olet asettanut ja määrittänyt [tietolähteet](data-sources.md), voit siirtyä esittely-ympäristöstä live-ympäristöön. Tuotantoympäristöä käyttämällä voit käsitellä omia asiakastietojasi. Voit vaihtaa ympäristöä valitsemalla sivun oikeassa yläkulmassa **Ympäristöt**.

> [!div class="mx-imgBorder"] 
> ![Vaihda ympäristöä](media/home-page-environment-switcher.png "Vaihda ympäristöä")

Järjestelmänvalvojat voivat luoda ja hallita [useita ympäristöjä](manage-environments.md). Useamman kuin yhden ympäristön ylläpitäminen voi olla hyödyllistä esimerkiksi silloin, jos organisaatiosi toimii kansainvälisesti ja sinun täytyy eristää tiedot ja oivallukset eri tavoilla.

## <a name="next-step"></a>Seuraava vaihe

Jos haluat nähdä omat tärkeät tiedot aloitussivulla, sinun täytyy ensin [lisätä tietolähteitä](data-sources.md) ja [yhtenäistää](data-unification.md) tiedot, jotta voit muodostaa asiakasprofiileja.
