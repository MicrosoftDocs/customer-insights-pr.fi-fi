---
title: Tarkastele järjestelmän kokoonpanoa
description: Lisätietoja Dynamics 365 Customer Insightsin järjestelmän asetuksista.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 6e60bf7c18939a29f660e06989e262deeb59a39b
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/02/2022
ms.locfileid: "9395997"
---
# <a name="view-system-configuration"></a>Tarkastele järjestelmän kokoonpanoa

Tarkastele järjestelmän tietoja, järjestelmän tilaa ja ohjelmointirajapinnan käyttöä.

## <a name="view-api-usage"></a>Tarkastele ohjelmointirajapinta käyttöä

Tarkastele reaaliaikaisen ohjelmointirajapinnan käyttöä koskevia tietoja ja katso, mitä tapahtumia tiettynä aikavälinä on suoritettu.

1. Siirry kohtaan **Järjestelmänvalvoja** > **Järjestelmä** ja valitse **Ohjelmointirajapinnan käyttö** -välilehti.

1. **Valitse aikaväli**, jota haluat tarkastella.

   **Ohjelmointirajapinnan käyttö** -sivu sisältää seuraavat kolme osaa:

   - **Ohjelmointirajapinnan kutsut** - kaavio, joka visualisoi ohjelmointirajapinnan koostettujen kutsujen määrän valittuna aikavälinä.
   - **Tietojen siirto** - kaavio, joka näyttää valitun ohjelmointirajapinnan kautta siirrettyjen tietojen määrän valittuna aikavälinä.
   - **Toiminnot** - taulukko, jossa on rivejä kullekin käytettävissä olevalle ohjelmointirajapinnan toiminnolle sekä toimintojen käyttöä koskevat tiedot. Valitse toiminnon nimi siirtyäksesi [ohjelmointirajapinnan viitteeseen](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

## <a name="view-system-information"></a>Järjestelmän tietojen näyttäminen

Tarkastele ympäristön näyttönimeä, tunnusta, aluetta, tyyppiä ja istuntotunnusta.

1. Siirry kohtaan **Järjestelmänvalvoja** > **Järjestelmä** ja valitse **Tietoja**-välilehti.

1. Voit tarkastella kieltä sekä maata tai aluetta valitsemalla **Yleiset**-välilehden.

### <a name="update-preferred-language-or-countryregion"></a>Ensisijaisen kielen tai maan/alueen päivittäminen

Customer Insights [tukee useita kieliä](/dynamics365/get-started/availability). Sovellus käyttää kieliasetuksia näyttämään elementit, kuten valikon, selitetekstin ja järjestelmän sanomat, ensisijaisella kielellä.

Tuotuja tietoja ja manuaalisesti annettuja tietoja ei käännetä.

1. Siirry kohtaan **Järjestelmänvalvoja** > **Järjestelmä** ja valitse **Yleiset**-välilehti.

1. Jos haluat vaihtaa ensisijaista kieltä, valitse **Kieli** avattavasta luettelosta.

1. Jos haluat muuttaa päivämäärien, kellonaikojen ja lukujen muotoilua, käytä avattavaa **Maan/alueen muoto** -valikkoa. Näyttöön tulee muotoilun esiversio. Järjestelmä ehdottaa automaattisesti valintaa, kun valitset uuden kielen.

1. Valitse **Tallenna**.

## <a name="view-system-status"></a>Näytä järjestelmän tila

Seuraa tehtävien etenemistä, tietojen käyttöä, tietojen vientiä ja monia muita tärkeitä tuoteprosesseja. Tarkista tiedot ja varmista, että aktiiviset tehtävät ja prosessit ovat täydellisiä.

1. Siirry kohtaan **Järjestelmänvalvoja** > **Järjestelmä** ja valitse **Tila**-välilehti.

   Eri prosessien tila- ja käsittelytiedot näkyvät. Tarkastele tehtävän **nimeä**, **tilaa**, jossa se on useimmiten suoritettu ja sen **edellistä päivityspäivää**.

1. Tarkastellaksesi useiden viime suoritusten tietoja, valitse tehtävän tai prosessin nimi.

1. Jos haluat tarkastella tehtävän edistymistä, valitse tila. Näkyviin tulee **Edistymisen tiedot** -ruutu.

   :::image type="content" source="media/system-progress-details.png" alt-text="Järjestelmän Edistymisen tiedot -ruutu":::

1. Jos haluat tarkastella kaikkien tehtävien edistymistä, valitse **Koko työnkulku**.

### <a name="status-definitions"></a>Tilamääritykset

Järjestelmä käyttää tehtäviä ja prosesseja varten seuraavia tiloja:

|Status  |Määritelmä  |
|---------|---------|
|Peruutettu |Käyttäjä on peruuttanut tehtävän tai käsittelyn, ennen kuin se valmistui.   |
|Epäonnistunut   |Tehtävän tai prosessin aikana tapahtui virheitä.         |
|Virhe  |Tehtävä tai prosessi on epäonnistunut.  |
|Ei aloitettu   |Tietolähteessä ei ole vielä käsiteltyjä tietoja tai tehtävä on edelleen luonnostilassa.         |
|Käsittely  |Tehtävä tai prosessi on käynnissä.  |
|Päivittää    |Tehtävä tai prosessi on käynnissä. Jos haluat peruuttaa tämän toiminnon, valitse **Päivitys** ja **Peruuta työ**. Tehtävän tai prosessin päivittämisen pysäyttäminen palauttaa sen tilaan, jossa se on viimeksi päivitetty.       |
|Ohitettu  |Tehtävä tai prosessi ohitettiin. Vähintään yksi palvelimelta siirrettävä prosessi, josta tämä tehtävä on riippuvainen, on epäonnistumassa tai se ohitettiin.|
|Onnistui  |Tehtävä tai prosessi on suoritettu. Tietolähteiden osalta ilmaisee, että tiedot on käsitelty onnistuneesti, jos **Päivitetty**-sarakkeessa mainitaan aika.|
|Jonossa | Käsittely asetetaan jonoon, ja se käynnistyy, kun kaikki alkuvaiheen tehtävät ja prosessit on suoritettu. Lisätietoja on aiheessa [Prosessien päivittäminen](#refresh-processes).|

### <a name="refresh-processes"></a>Prosessien päivittäminen

Tehtävien ja prosessien päivitys suoritetaan [määritetyn aikataulun](schedule-refresh.md) mukaisesti.

|Prosessi  |Kuvaus  |
|---------|---------|
|Aktiviteetti  |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu yhdistämisprosessista. Merktiykselliset tiedot riippuvat sen käsittelystä.|
|Analyysin linkitys |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu segmenteistä.  |
|Analyysin valmistelu |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu segmenteistä.  |
|Tietojen valmistelu   |Entiteetti on suoritettava. Tietolähde-entiteetit määräytyvät käsittelyn mukaan. Rikastetut entiteetit määräytyvät rikastusten mukaan. Asiakas-entiteetti määräytyy yhdistämisen mukaan.  |
|Tietolähteet   |Ei riipu mistään muusta prosessista. Vastaavuus riippuu tämän prosessin onnistuneesta suorittamisesta.  |
|Rikastukset   |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu yhdistämisprosessista. |
|Vientikohteet |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu segmenteistä.  |
|Näkemykset |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu segmenteistä.  |
|Analytiikka   |Määräytyy yhdistämisen mukaan.   |
|Täsmäytä |Määräytyy vastaavuusmäärityksessä käytettyjen tietolähteiden käsittelyn mukaan.      |
|Mittarit  |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu yhdistämisprosessista.  |
|Yhdistä   |Riippuu täsmäytysprosessin suorittamisesta. Segmentit, mittarit, rikastus, haku, aktiviteetit, ennusteet ja tietojen valmistelu riippuvat tämän prosessin onnistuneesta suorittamisesta.   |
|Profiilit   |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu yhdistämisprosessista. |
|Hae   |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu yhdistämisprosessista. |
|Segmentit  |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu yhdistämisprosessista. Merktiykselliset tiedot riippuvat sen käsittelystä.|
|Järjestelmä   |Riippuu täsmäytysprosessin suorittamisesta. Segmentit, mittarit, rikastus, haku, aktiviteetit, ennusteet ja tietojen valmistelu riippuvat tämän prosessin onnistuneesta suorittamisesta.   |
|Käyttäjä  |Suoritetaan manuaalisesti (yksittäinen päivitys). Riippuu entiteeteistä.  |

Valitse prosessin tila, jos haluat nähdä koko työn edistymistiedot. Yllä olevien päivitysprosessien avulla saat tietoja siitä, miten voit käsitellä **ohitettua** tai **jonoon määritettyä** tehtävää tai prosessia.


[!INCLUDE [footer-include](includes/footer-banner.md)]
