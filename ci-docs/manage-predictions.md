---
title: Jaetut tehtävät ennusteskenaarioita varten
description: Opettele hallitsemaan, määrittämään vikoja ja hiomaan ennusteita.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c4d269e1b542e84ade8c6e63c1dadace51ddde32
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646420"
---
# <a name="manage-predictions"></a>Hallitse ennusteita

Tässä artikkelissa käsitellään joitakin tehtäviä, jotka useimmat ennusteskenaariot jakavat.

## <a name="troubleshoot-a-failed-prediction"></a>Epäonnistuneen ennusteen vianmääritys

1. Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.

1. Valitse kolme allekkain olevaa pistettä sen ennusteen vieressä, jonka virhelokeja haluat tarkastella.

1. Valitse **Lokit**.

1. Tarkastele kaikkia virheitä. Mahdollisia virhe tyyppejä on useita. Ne osoittavat, mikä ehto aiheutti virheen. Esimerkiksi virhe, joka osoittaa olemassa olevien tietojen olevan riittämättömät tarkan ennusteen luomiseksi, ratkaistaan yleensä lataamalla lisää tietoja Customer Insightsiin.

## <a name="input-data-usability-report"></a>Syötetietojen käytettävyysraportti

Syöttötietojen käytettävyysraportti tarjoaa konsolidoidun kuvan virheistä ja varoituksista, joita valmiit ennusteet saattavat tuottaa. Se antaa myös suosituksia mallin suorituskyvyn parantamista varten.

Raportti on käytettävissä sen jälkeen, kun malli on suorittanut sen koulutusprosessin. Se luodaan kullekin mallille erikseen riippumatta siitä, onnistuiko malli.

### <a name="view-the-input-data-usability-report"></a>Näytä syötetietojen käytettävyysraportti

Kun valmiin mallin koulutusvaihe on valmis, tarkastele raporttia:
- Valitse mallin nimen vierestä kolme pistettä ja valitse sitten **Syötetietojen käytettävyysraportti**.
- Valitse mallin tila valitsemalla sivuruudusta **Näytä tietojen käytettävyysraportti**.
- Valitse luettelosta jokin malleista ja valitse komentopalkissa **Tietojen käytettävyysraportti**.
- Avaa mallien tulossivu ja valitse komentopalkissa **Tietojen käytettävyysraportti**.

### <a name="information-in-the-input-data-usability-report"></a>Tiedot syötetietojen käytettävyysraportissa

Seuraavissa raportin sarakkeissa on hyödyllisiä tietoja mallin tietojen parantamiseksi.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Esimerkki syöttötietojen käytettävyysraportista, jossa näkyy taulukko, jossa on virheitä, varoituksia ja suosituksia.":::

- **Nimi:** virheen, varoituksen tai suosituksen kuvaileva nimi.
- **Vaihe:** mallivaihe, kouluttaa tai pisteyttää, tietoihin viitataan.
- **Tila:** tietojen vakavuus (virhe, varoitus, suositus).
- **Sarakkeen nimi:** Entiteetin sarake, jota on muutettava mallin suorituskyvyn parantamiseksi.
- **Entiteetin nimi:** Entiteetin nimi, jota on muutettava mallin suorituskyvyn parantamiseksi.
- **Tiedot:** Tietoja virheestä, varoituksesta tai suosituksista.

## <a name="refresh-a-prediction"></a>Ennusteen päivittäminen

Ennusteet päivittyvät automaattisesti saman [aikataulun mukaan kuin tiedot päivitetään](system.md#schedule-tab) asetuksissa määritetyllä tavalla. Voit päivittää ne myös manuaalisesti.

1. Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.

1. Valitse päivitettävän ennusteen vieressä olevat allekkaiset pisteet.

1. Valitse **Päivitä**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Ennusteen poistaminen

Ennusteen poistaminen poistaa myös sen tuloste-entiteetin.

1. Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.

1. Valitse poistettavan ennusteen vieressä olevat allekkaiset pisteet.

1. Valitse **Poista**.
