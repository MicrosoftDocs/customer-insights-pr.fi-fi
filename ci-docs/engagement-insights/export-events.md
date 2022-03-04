---
title: Tarkennettujen tapahtumien vieminen
description: Tarkennettujen tapahtumien ja perustapahtumien vienti.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: d062e2982c1041454b083630404f2b68f0da9669
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232884"
---
# <a name="export-events"></a>Tapahtumien vieminen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tapahtuma edustaa käyttäjän käyttäytymistä. Se kirjaa ylös, milloin käyttäjä tarkastelee sivua (katselutapahtuma) tai on vuorovaikutuksessa sen sisällön kanssa (toimintotapahtuma). Kun voit päättää, mitkä tietojen ominaisuudet haluat näyttää raportissa, tätä tietojen virtuaalista näkymää kutsutaan *tarkennetuksi* tapahtumaksi. Saat lisätietoja kohdasta [Tapahtumien luominen ja muokkaaminen](refined-events.md).

- Voit viedä tapahtumia ja tarkennettuja tapahtumia ulkoiseen tallennustilaan. 
- Viennit ovat eteenpäin kulkeva tietovirta. Viestivirtaa ei voi täyttää uudelleen. 
- Vienneissä on kiinteät rakenteet. Jos lisäät tapahtumaan mukautettuja ominaisuuksia, niitä ei sisällytetä. Sinun on luotava uusi vienti.

## <a name="prerequisites"></a>Edellytykset

Ennen kuin määrität viennin, sinulla on oltava käyttöoikeus ja voimassa oleva tilaus Azure-portaaliin. Tarvitset tallennustilin tiedot viennin aikana. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Azure Data Lake Storage Gen 2 -tilin luominen

1. Kirjaudu Azure-portaaliin ja [luo uusi tallennustilatili](/azure/storage/common/storage-account-create). 

1. Varmista, että **Hierarkkinen nimitila on käytössä** **Lisäasetukset**-välilehdessä. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Ota hierarkkinen nimitila käyttöön lisäasetusten välilehdessä.":::

1. Kun se on otettu käyttöön, siirry juuri luodulle tallennustilatilille. Valitse siirtymisruudussa **Asetukset** > **Käyttöoikeusavaimet**. 

1. Kopioi **Tilin nimi** ja **Avain**, jotta voit käyttää niitä uutta vientiä luotaessa.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Tallennustilin käyttöoikeusavaimet.":::

## <a name="export-events"></a>Vie tapahtumat

**Vie tapahtumat** -dialogin voi tuoda esiin kahdella tavalla: 
- Siirry kohtaan **Tiedot** > **Viennit** ja valitse **Uusi vienti**.
- Siirry kohtaan **Tiedot** > **Tapahtumat** ja valitse vietävän tapahtuman vieressä oleva **Lisää [...]**. Valitse lopuksi avattavasta valikosta **Vie**. 

:::image type="content" source="media/new-export.png" alt-text="Luo uusi vienti":::

Sinut opastetaan viennin luomisen vaiheiden läpi:

1. Anna **Viennin nimi** ja valitse sitten **Seuraava**.

1. Valitse avattavasta **Tapahtumien valinta** -luettelosta perustapahtumat ja muutetut tapahtumat vientiin. 

1. Valitse **Tiedostorakenne**-osassa tahti (tunneittain tai päivittäin), luodaksesi uusia tiedostoja kohdetallennustilassa ja valitse sitten **Seuraava**. Tapahtumia viedään jatkuvasti niiden saapuessa.

1. Valitse **Valitse muoto** -dialogissa viennin muoto. Valitse muotojen **Common Data Model**, **CSV** ja **JSON** välillä. Jos haluat käyttää vientiä muiden Dynamics 365 -sovellusten kanssa, on suositeltavaa käyttää **Common Data Model** -muotoa.

1. Määritä **Valitse kohde** -dialogissa Azure Data Lake Storage Gen 2 -sijainti.
    1. **ADLS Gen 2:n tilin nimi** on sen tallennustilatilin nimi, johon haluat tallentaa vientisi. 
    1. **Kansiopolku** määrittää, mihin vienti tallennetaan tallennustilatilin tiedostojärjestelmässä ja hakemistorakenteessa.
    1. **Jaettu avain** on käytettävissä Azure-portaalissa tallennustilatilin osalta.

1. Viimeistele toimenpide tarkistamalla ja vahvistamalla valintasi.

## <a name="view-and-manage-exports"></a>Vientien tarkasteleminen ja hallinta

Kun olet määrittänyt viennin, voit tarkastella sitä kohdassa **Tiedot** > **Viennit**. Voit muokata tai poistaa olemassa olevia raportteja valitsemalla niiden vierestä **Lisää [...]**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
