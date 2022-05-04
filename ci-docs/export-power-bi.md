---
title: Power BI -yhdistin
description: Tietoja Dynamics 365 Customer Insights -yhdistimen käytöstä Power BI:ssä.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e901114703a43b4b4e751e0a93eb4876d7636c00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646315"
---
# <a name="connector-for-power-bi-preview"></a>Power BI -yhdistin (esiversio)

Tietojen visualisointien luominen Power BI Desktopin avulla. Voit luoda lisää näkemyksiä ja luoda raportteja, joissa on yhdistettyjä asiakastietoja.

## <a name="prerequisites"></a>Edellytykset

- Käytössä on yhtenäistetyt asiakasprofiilit.
- Tietokoneeseen on asennettu uusin [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/). [Lisätietoja aiheesta: Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Määritä Power BI -yhdistin

1. Valitse Power BI Desktopissa **Tiedosto** > **Nouda tiedot**.

1. Valitse **Katso lisää** ja hae **Dynamics 365 Customer Insights**

1. Valitse **Yhdistä**.

1. **Kirjaudu sisään** samalla organisaatiotilillä, jota käytät Customer Insightsissa, ja valitse **Yhdistä**.
   > [!NOTE]
   > Tässä vaiheessa ilmaistua tiliä käytetään noutamaan tietoja Customer Insightsista eikä sen tarvitse olla kuin tili, jolla kirjauduit Power BI:hin. Nollaa tietojen noutamiseen käytetty tili avaamalla Power BI ja valitsemalla **Tiedosto** > **Valinnat** > **Asetukset** > **Tietolähteen asetukset**. Valitse tietolähdeluettelossa **Dynamics 365 Customer Insightsin kirjautuminen** ja valitse sitten **Tyhjennä oikeudet**.  

1. **Siirtyminen**-valintaikkunassa. on luettelo kaikista ympäristöistä, joita voi käyttää. Laajenna ympäristö ja avaa jokin kansioista (entiteetit, mittarit, segmentit, rikastamiset). Avaa esimerkiksi **Entiteetit**-kansio, jotta voit tarkastella kaikkia tuotavia entiteettejä.

   ![Power BI -yhdistintaulukko.](media/power-bi-navigator.png "Power BI -yhdistintaulukko")

1. Valitse sisällytettävien entiteettien valintaruudut ja sitten **Lataa**. Voit valita useita entiteettejä useista ympäristöistä.

1. Latauksen valintaikkuna näkyy, kun entiteettejä ladataan. Kun kaikki valitut entiteetit on ladattu, voit visualisoida tiedot Power BI:n ominaisuuksilla.

## <a name="large-data-sets"></a>Suuret tietojoukot

Power BI:n Customer Insights -yhdistin on suunniteltu toimimaan tietojoukoilla, jotka sisältävät enintään 1 miljoonaa asiakasprofiilia. Suurempien tietojoukkojen tuominen saattaa toimia, mutta se kestää kauan. Lisäksi prosessi saattaa saavuttaa aikakatkaisun Power BI -rajoitusten vuoksi. Lisätietoja: [Power BI: Suuria tietojoukkoja koskevat suositukset](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Alitietojoukon käsitteleminen

Harkitse tietojen alijoukon käyttämistä. Voit esimerkiksi luoda [segmenttejä](segments.md) sen sijaan, että kaikki asiakastietueet vietäisiin Power BI:hin.

## <a name="troubleshooting"></a>Vianmääritys

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights -ympäristö ei näy Power BI:ssä

Ympäristöt, joissa on määritetty useampi kuin yksi [suhde](relationships.md) kahden samanlaisen Customer Insights -kohteen välille, eivät ole käytettävissä Power BI -yhdistimessä.

Voit tunnistaa ja poistaa kaksoiskappaleiden suhteita.

1. Siirry kohtaan **Tiedot** > **Suhteet** ympäristössä, jota ei ole Power BI:ssä.
2. Tunnista kaksoiskappaleiden suhteet seuraavasti:
   - Tarkista, onko kahdelle samalle entiteetille määritetty useita suhteita.
   - Tarkista, onko kahden yhdistämisprosessiin sisältyvän entiteettien välille luotu suhde. Kaikkien yhdistämisprosessiin sisältyvien entiteettien välille on määritetty implisiittinen suhde.
3. Poista kaikki tunnistetut suhteiden kaksoiskappaleet.

Kun olet poistanut suhteiden kaksoiskappaleet, yritä määrittää Power BI -yhdistin uudelleen. Ympäristön tulisi nyt olla käytettävissä.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Päivämääräkenttien virheet ladattaessa entiteettejä Power BI Desktopissa

Kun lataat entiteettejä, jotka sisältävät päiväysmuotoisia kenttiä, kuten PP/KK/VVVV, saatat kohdata virheitä, jotka johtuvat virheellisistä aluemuodoista. Tämä ristiriita ilmenee, kun Power BI Desktop -tiedostosi on määritetty jokin muu kieli kuin englanti (Yhdysvallat), koska Customer Insights -tietojen päivämääräkentät tallennetaan Yhdysvaltojen muodossa.

Power BI Desktop -tiedostossa on yksi alueasetus, jota käytetään tietoja noudettaessa. Hakeaksesi nämä päivämääräkentät oikein tulkittuna, määritä BPI-tiedoston aluekohtaiseksi asetukseksi englanti (Yhdysvallat). [Tietoja Power BI -työpöytätiedoston aluekohtaisen asetuksen muuttamisesta](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE [footer-include](includes/footer-banner.md)]
