---
title: Power BI -yhdistin (esiversio)
description: Tietoja Dynamics 365 Customer Insights -yhdistimen käytöstä Power BI:ssä.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196666"
---
# <a name="power-bi-connector-preview"></a>Power BI -yhdistin (esiversio)

Tietojen visualisointien luominen Microsoft Power BI Desktopissa. Voit luoda lisää näkemyksiä ja luoda raportteja, joissa on yhdistettyjä asiakastietoja.

## <a name="prerequisites"></a>edellytykset

- Yhdistetyt asiakasprofiilit.
- Tietokoneeseen on asennettu uusin [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/). [Lisätietoja aiheesta: Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Määritä Power BI -yhdistin

1. Valitse Power BI Desktopissa **Tiedosto** > **Nouda tiedot**.

1. Valitse **Katso lisää** ja hae **Dynamics 365 Customer Insights**

1. Valitse **Yhdistä**.

1. **Kirjaudu sisään** samalla organisaatiotilillä, jota käytät Customer Insightsissa, ja valitse **Yhdistä**.
   > [!NOTE]
   > Tässä vaiheessa ilmaistua tiliä käytetään noutamaan tietoja Customer Insightsista eikä sen tarvitse olla kuin tili, jolla kirjauduit Power BI:hin. Nollaa tietojen noutamiseen käytetty tili avaamalla Power BI ja valitsemalla **Tiedosto** > **Valinnat** > **Asetukset** > **Tietolähteen asetukset**. Valitse tietolähdeluettelossa **Dynamics 365 Customer Insightsin kirjautuminen** ja valitse sitten **Tyhjennä oikeudet**.  

1. Avaa **Siirtymistoiminto**-valintaikkunassa kaikkien käytettävissäsi olevien käyttöympäristöjen luettelo. Laajenna ympäristö ja avaa jokin kansioista (entiteetit, mittarit, segmentit, rikastamiset). Avaa esimerkiksi **Entiteetit**-kansio, jotta voit tarkastella kaikkia tuotavia entiteettejä.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Power BI -yhdistintaulukko.":::

1. Valitse sisällytettävien entiteettien valintaruudut ja sitten **Lataa**. Voit valita useita entiteettejä useista ympäristöistä.

   Latauksen valintaikkuna näkyy, kun entiteettejä ladataan. Kun kaikki valitut entiteetit on ladattu, voit visualisoida tiedot Power BI:n ominaisuuksilla.

## <a name="large-data-sets"></a>Suuret tietojoukot

Power BI:n Customer Insights -yhdistin on suunniteltu toimimaan tietojoukoilla, jotka sisältävät enintään 1 miljoonaa asiakasprofiilia. Suurten tietojoukkojen tuominen voi toimia, mutta se voi kestää kauan ja keskeytyä aikakatkaisun seurauksena Power BI -rajoitusten vuoksi. Lisätietoja: [Power BI: Suuria tietojoukkoja koskevat suositukset](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Alitietojoukon käsitteleminen

Harkitse tietojen alijoukon käyttämistä. Voit esimerkiksi luoda [segmenttejä](segments.md) sen sijaan, että kaikki asiakastietueet vietäisiin Power BI:hin.

## <a name="troubleshooting"></a>Vianmääritys

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights -ympäristö ei näy Power BI:ssä

Ympäristöt, joissa on määritetty useampi kuin yksi [suhde](relationships.md) kahden samanlaisen Customer Insights -kohteen välille, eivät ole käytettävissä Power BI -yhdistimessä.

Tunnista ja poista kaksoiskappaleiden suhteita.

1. Siirry kohtaan **Tiedot** > **Suhteet** ympäristössä, jota ei ole Power BI:ssä.
1. Tunnista kaksoiskappaleiden suhteet seuraavasti:
   - Tarkista, onko kahdelle samalle entiteetille määritetty useita suhteita.
   - Tarkista, onko kahden yhdistämisprosessiin sisältyvän entiteettien välille luotu suhde. Kaikkien yhdistämisprosessiin sisältyvien entiteettien välille on määritetty implisiittinen suhde.
1. Poista kaikki tunnistetut suhteiden kaksoiskappaleet.

Kun olet poistanut suhteiden kaksoiskappaleet, yritä määrittää Power BI -yhdistin uudelleen.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Päivämääräkenttien virheet ladattaessa entiteettejä Power BI Desktopissa

Kun lataat entiteettejä, jotka sisältävät päiväysmuotoisia kenttiä, kuten PP/KK/VVVV, saatat kohdata virheitä, jotka johtuvat virheellisistä aluemuodoista. Tämä ristiriita ilmenee, kun Power BI Desktop -tiedostosi on määritetty jokin muu kieli kuin englanti (Yhdysvallat), koska Customer Insights -tietojen päivämääräkentät tallennetaan Yhdysvaltojen muodossa.

Power BI Desktop -tiedostossa on yksi alueasetus, jota käytetään tietoja noudettaessa. Voit korjata päivämäärävirheet [määrittämällä BPI-tiedoston aluekohtaiseksi asetukseksi](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) englanti (Yhdysvallat).

[!INCLUDE [footer-include](includes/footer-banner.md)]
