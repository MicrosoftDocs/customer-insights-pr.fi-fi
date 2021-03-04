---
title: Power BI -yhdistin
description: Tietoja Dynamics 365 Customer Insights -yhdistimen käytöstä Power BI:ssä.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477084"
---
# <a name="connector-for-power-bi-preview"></a>Power BI -yhdistin (esiversio)

Tietojen visualisointien luominen Power BI Desktopin avulla. Voit luoda lisää näkemyksiä ja luoda raportteja, joissa on yhdistettyjä asiakastietoja.

## <a name="prerequisites"></a>Edellytykset

- Käytössä on yhtenäistetyt asiakasprofiilit.
- Tietokoneellasi on asennettuna [Microsoft Power BI Desktopin](https://powerbi.microsoft.com/desktop/) viimeisin versio. [Lisätietoja aiheesta: Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Määritä Power BI -yhdistin

1. Valitse Power BI Desktopissa **Tiedosto** > **Nouda tiedot**.

1. Valitse **Katso lisää** ja hae **Dynamics 365 Customer Insights**

1. Valitse **Yhdistä**.

1. **Kirjaudu sisään** samalla organisaatiotilillä, jota käytät Customer Insightsissa, ja valitse **Yhdistä**.
   > [!NOTE]
   > Tässä vaiheessa ilmaistua tiliä käytetään noutamaan tietoja Customer Insightsista eikä sen tarvitse olla kuin tili, jolla kirjauduit Power BI:hin. Nollaa tietojen noutamiseen käytetty tili avaamalla Power BI ja valitsemalla **Tiedosto** > **Valinnat** > **Asetukset** > **Tietolähteen asetukset**. Valitse tietolähdeluettelossa **Dynamics 365 Customer Insightsin kirjautuminen** ja valitse sitten **Tyhjennä oikeudet**.  

1. **Siirtyminen**-valintaikkunassa. on luettelo kaikista ympäristöistä, joita voi käyttää. Laajenna ympäristö ja avaa jokin kansioista (entiteetit, mittarit, segmentit, rikastamiset). Avaa esimerkiksi **Entiteetit**-kansio, jotta voit tarkastella kaikkia tuotavia entiteettejä.

   ![Power BI -yhdistintaulukko](media/power-bi-navigator.png "Power BI -yhdistintaulukko")

1. Valitse sisällytettävien entiteettien valintaruudut ja sitten **Lataa**. Voit valita useita entiteettejä useista ympäristöistä.

1. Latauksen valintaikkuna näkyy, kun entiteettejä ladataan. Kun kaikki valitut entiteetit on ladattu, voit visualisoida tiedot Power BI:n ominaisuuksilla.

## <a name="large-data-sets"></a>Suuret tietojoukot

Power BI:n Customer Insights -yhdistin on suunniteltu toimimaan tietojoukoilla, jotka sisältävät enintään 1 miljoonaa asiakasprofiilia. Suurempien tietojoukkojen tuominen saattaa toimia, mutta se kestää kauan. Lisäksi prosessi saattaa saavuttaa aikakatkaisun Power BI -rajoitusten vuoksi. Lisätietoja: [Power BI: Suuria tietojoukkoja koskevat suositukset](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Alitietojoukon käsitteleminen

Harkitse tietojen alijoukon käyttämistä. Voit esimerkiksi luoda [segmenttejä](segments.md) sen sijaan, että kaikki asiakastietueet vietäisiin Power BI:hin.

## <a name="troubleshooting"></a>Vianmääritys

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights -ympäristö ei näy Power BI:ssä

Ympäristöt, joissa on määritetty useita [suhteita](relationships.md) kahden identtisen entiteetin välille käyttäjäryhmän tiedoissa, eivät ole käytettävissä Power BI -yhdistimessä.

Voit tunnistaa ja poistaa kaksoiskappaleiden suhteita.

1. Siirry käyttäjäryhmän tiedoissa kohtaan **Tiedot** > **Suhteet** ympäristössä, jossa ei ole Power BI:tä.
2. Tunnista kaksoiskappaleiden suhteet seuraavasti:
   - Tarkista, onko kahdelle samalle entiteetille määritetty useita suhteita.
   - Tarkista, onko kahden yhdistämisprosessiin sisältyvän entiteettien välille luotu suhde. Kaikkien yhdistämisprosessiin sisältyvien entiteettien välille on määritetty implisiittinen suhde.
3. Poista kaikki tunnistetut suhteiden kaksoiskappaleet.

Kun olet poistanut suhteiden kaksoiskappaleet, yritä määrittää Power BI -yhdistin uudelleen. Ympäristön tulisi nyt olla käytettävissä.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

