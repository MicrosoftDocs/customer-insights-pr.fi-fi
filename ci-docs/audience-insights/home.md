---
title: Käyttäjäryhmän merkityksellisten tietojen aloitussivu
description: Sovellukseen tutustumisen aloittaminen aloitussivulta.
ms.date: 01/07/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7cc767f5d80b213a4c1bb5b2e8062bd44c15279b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477037"
---
# <a name="create-a-new-environment"></a>Luo uusi ympäristö

## <a name="create-a-trial-environment"></a>Kokeiluympäristön luominen

Voit rekisteröityä kokeiluversioon [kokeiluversion rekisteröitymissivulla](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Kokeiluversiot vanhentuvat 30 päivän kuluttua.

1. Valitse ensin **Rekisteröidy ilmaisen kokeiluversion käyttäjäksi** ja sitten **Rekisteröidy nyt**.

1. Anna työpaikan tai oppilaitoksen sähköpostiosoite, kerro jotain itsestäsi ja valitse **Seuraava**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Valintaikkuna kokeiluesiintymään rekisteröitymistä varten":::

1. Anna uudelle ympäristölle **nimi**. 

1. Valitse kokeiluversion tyyppi.

1. Valitse ympäristön **alue**.

1. Valinnainen Dynamics 365 -organisaation järjestelmänvalvojille: Valitse **Lisäasetukset** ja anna organisaation URL-osoite, jos haluat käyttää ennustetoimintoja, kuten asiakasvaihtuvuutta.

1. Valitse **Luo**. 

Ympäristön luomiseen jälkeen, näkyvissä on **Esittely**-ympäristö, joissa voit tutustua sovellukseen kuvitteellisten tietojen avulla. Voit vaihtaa näytetiedot omaa toimialaa vastaavaksi. Valitse otsikossa ensin **Asetukset**-kuvake ja valitse sitten **Esittelyn asetukset**. Voit muuttaa myös visuaalisen teeman. 

[Siirry ympäristöön](#switch-environments), jonka loit rekisteröitymisprosessin aikana, käsittelemään omia tietoja.

## <a name="create-a-new-production-or-sandbox-environment"></a>Uuden tuotanto- ja eristysympäristön luominen

Valitse ympäristössä **Ympäristöt**-valitsin sovelluksen otsikossa ja valitse sitten **Uusi**.

Toimi samalla tavalla kuin [loisit kokeiluympäristön](#create-a-trial-environment). Oletusarvoisesti tiedot tallennetaan hallittuun Customer Insightsin Data Lake -tallennustilaan. Valitsemalla **Lisäasetukset** saat käyttöösi lisäasetuksen, jolla voit tallentaa tietoja omaan Azure Data Lake -tallennustilaan. Muodosta yhteys Azure Data Lake -tallennustilaan antamalla tilin nimi ja tiliavain. 

> [!IMPORTANT]
> Kun tallennat tiedot Azure Data Lake Storageen, hyväksyt, että tiedot siirretään ja tallennetaan kyseisen Azure-tallennustilin mukaiseen maantieteelliseen sijaintiin. Tämä voi poiketa siitä, mihin tiedot on tallennettu Dynamics 365 Customer Insightsissa. [Lisätietoja on Microsoftin luottamuskeskuksessa.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Aloitussivuun tutustuminen

Voit [käyttää käyttäjäryhmän tietoja Dynamics 365 Customer Insightsssa](https://home.ci.ai.dynamics.com/) seuraavassa URL-osoitteessa: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Aloitussivulla** on segmenttien, mittareiden ja rikastuksen tietojen (jos ne on määritetty) yleiskatsaus sen jälkeen, kun [vastaavuusmääritys](map-entities.md)-, [vastaavuus](match-entities.md)- ja [yhdistäminen](merge-entities.md)-vaiheet on suoritettu.

> [!div class="mx-imgBorder"] 
> ![Merkityksellisiä tietoja aloitussivulla](media/home-page-insights.png "Merkityksellisiä tietoja aloitussivulla")

**Viimeaikaiset segmentit** -kohdassa esitetään asiakasryhmiä määrittämiesi demografia-, käyttäytymis- tai tapahtumamääritteiden perusteella. [Segmenttien luominen](segments.md) auttaa asiakaskannan ryhmittelemisessä ja liiketoiminnan aktiviteettien kohdentamisessa.

**Viimeaikaiset mittarit** -kohdassa on ruudut, joissa on määritetyt [tunnusluvut (KPI-luvut)](measures.md). Esimerkiksi keskimääräinen asiakasvaihtuvuus tai asiakkaan keskimääräinen kulutus verkossa.

**Viimeaikaiset rikastukset** -osa sisältää tulokset viime aikoina suoritetuista rikastamisprosesseista. [Rikastukset](enrichment-hub.md) lisäävät tietoja asiakaskunnasta. Esimerkiksi antamalla tietoja asiakkaiden kiinnostuksen kohteista ja suosikkibrändeistä.

## <a name="switch-environments"></a>Ympäristöjen vaihtaminen

Voit vaihtaa ympäristöä valitsemalla sivun oikeassa yläkulmassa **Ympäristöt**.

> [!div class="mx-imgBorder"] 
> ![Vaihda ympäristöä](media/home-page-environment-switcher.png "Vaihda ympäristöä")

Järjestelmänvalvojat voivat luoda ja hallita [useita ympäristöjä](manage-environments.md). Useamman kuin yhden ympäristön ylläpitäminen voi olla hyödyllistä esimerkiksi silloin, jos organisaatiosi toimii kansainvälisesti ja sinun täytyy eristää tiedot ja oivallukset eri tavoilla.

## <a name="next-step"></a>Seuraava vaihe

Jos haluat nähdä omat tärkeät tiedot aloitussivulla, sinun täytyy ensin [lisätä tietolähteitä](data-sources.md) ja [yhtenäistää](data-unification.md) tiedot, jotta voit muodostaa asiakasprofiileja.


[!INCLUDE[footer-include](../includes/footer-banner.md)]