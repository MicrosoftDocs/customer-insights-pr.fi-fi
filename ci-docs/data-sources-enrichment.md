---
title: Tietolähteen rikastus
description: Rikasta tietolähteitä ennen kuin käyt läpi tietojen yhdistämisprosessin.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 1225482c4bf432ed747537b2c9bec9ab0e692a51
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800277"
---
# <a name="enrichment-for-data-sources-preview"></a>Rikastus tietolähteitä varten (esiversio)

Käytä Microsoftin ja muiden kumppanien tietoja asiakastietojen rikastukseen ennen tietojen yhdistämistä. Tietolähteiden rikastus auttaa täydellisemmän ja laadukkaamman tiedon tuottamisessa, mikä puolestaan parantaa tietojen yhdistämisen tuloksia. Esimerkiksi normaali- ja standardimuotoisten osoitteiden käyttäminen parantaa vastaavuustulosten laatua. Luettelo tuetuista rikastuksista: [tuetut tietolähteiden rikastusasetukset](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Tietolähteen rikastus

Sinulla on oltava osallistujan tai järjestelmänvalvojan oikeudet, jotta voit luoda tai muokata rikastuksia. Lisätietoja on kohdassa [Oikeudet](permissions.md).  

1. Siirry kohtaan **Tiedot** > **Yhdistä**. Valitse entiteetti, jota haluat rikastaa, ja valitse yksi määrite entiteetin perusavaimeksi. Lisätietoja: [perusavaimen valitseminen](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Valitse **Tiedot** > **Tietolähteet**.

1. Valitse rikastettavan tietolähteen vieressä olevat pystysuuntaiset kolme pistettä (&vellip;) ja valitse **Rikasta**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Tietolähteiden rikastussivu":::

   **Etsi**-välilehti näyttää [tuetut tietolähteiden rikastusasetukset](#supported-data-source-enrichments).

1. Määritä tietolähteen rikastus valitsemalla **Rikasta tiedot**. Tulosentiteetin nimi täytetään automaattisesti.

## <a name="supported-data-source-enrichments"></a>Tuetut tietolähteen rikastukset

Tietolähteitä varten on tällä hetkellä saatavissa seuraavat rikastukset. Opi määrittäminen tutustumalla rikastuksen vaiheisiin yksityiskohtaisesti.

- [Parannetut osoitteet](enrichment-enhanced-addresses.md)
- [Parannetut yritystiedot](enrichment-enhanced-company-data.md)
- [LiveRamp-kohteen käyttäjätiedot](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Aiemmin luotujen tietolähteiden rikastusten hallinta

Siirry **Omat rikastamiset** -välilehteen, jos haluat nähdä kaikki määritetyt rikastamiset.

Valitse rikastus, jos haluat nähdä käytettävissä olevat vaihtoehdot. Voit myös valita kolme pystysuuntaista pistettä (&vellip;) luettelokohteesta, kun haluat nähdä vaihtoehdot. Jos olet määrittänyt useita rikasteita, voit etsiä sen nopeasti hakuruudun avulla.

Tietolähteen rikastuksen voi tarkastella, muokata, suorittaa tai poistaa. Lisätietoja on ohjeaiheessa [Aiemmin luotujen rikastusten hallinta](enrichment-hub.md).