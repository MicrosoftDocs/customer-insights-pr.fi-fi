---
title: Tietolähteen rikastus
description: Rikasta tietolähteitä ennen kuin käyt läpi tietojen yhdistämisprosessin.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 56f6a8ad20224922f9968f0ad3b6a0e0a400214b
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376575"
---
# <a name="enrichment-for-data-sources-preview"></a>Rikastus tietolähteitä varten (esiversio)

Käytä Microsoftin ja muiden kumppanien tietoja asiakastietojen rikastukseen ennen tietojen yhdistämistä. Tietolähteiden rikastus auttaa täydellisemmän ja laadukkaamman tiedon tuottamisessa, mikä puolestaan parantaa tietojen yhdistämisen tuloksia. Esimerkiksi normaali- ja standardimuotoisten osoitteiden käyttäminen parantaa vastaavuustulosten laatua. Luettelo tuetuista rikastuksista: [tuetut tietolähteiden rikastusasetukset](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Tietolähteen rikastus

Sinulla on oltava osallistujan tai järjestelmänvalvojan oikeudet, jotta voit luoda tai muokata rikastuksia. Lisätietoja on kohdassa [Oikeudet](permissions.md).  

1. Siirry kohtaan **Tiedot** > **Yhdistä**. Valitse entiteetti, jota haluat rikastaa, ja valitse yksi määrite entiteetin perusavaimeksi. Lisätietoja: [perusavaimen valitseminen](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Valitse **Tiedot** > **Tietolähteet**.
 
1. Valitse rikastettavan tietolähteen vieressä olevat pystysuuntaiset kolme pistettä ja valitse **Rikasta**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Tietolähteiden rikastussivu":::

   **Etsi**-välilehti näyttää [tuetut tietolähteiden rikastusasetukset](#supported-data-source-enrichments).

1. Määritä tietolähteen rikastus valitsemalla **Rikasta tiedot**. Tulosentiteetin nimi täytetään automaattisesti.

## <a name="supported-data-source-enrichments"></a>Tuetut tietolähteen rikastukset

Tietolähteitä varten on tällä hetkellä saatavissa seuraavat rikastukset. Opi määrittäminen tutustumalla rikastuksen vaiheisiin yksityiskohtaisesti.

- [Parannetut osoitteet](enrichment-enhanced-addresses.md)
- [Parannetut yritystiedot](enrichment-enhanced-company-data.md)

## <a name="manage-existing-data-source-enrichments"></a>Aiemmin luotujen tietolähteiden rikastusten hallinta

Siirry **Omat rikastamiset** -välilehteen, jos haluat nähdä kaikki määritetyt rikastamiset.

Valitse rikastus, jos haluat nähdä käytettävissä olevat vaihtoehdot. Voit myös valita luettelokohteesta kolme pistettä (...), kun haluat nähdä vaihtoehdot. Jos olet määrittänyt useita rikasteita, voit etsiä sen nopeasti hakuruudun avulla.

Tietolähteen rikastuksen voi tarkastella, muokata, suorittaa tai poistaa. Lisätietoja on ohjeaiheessa [Aiemmin luotujen rikastusten hallinta](enrichment-hub.md).
