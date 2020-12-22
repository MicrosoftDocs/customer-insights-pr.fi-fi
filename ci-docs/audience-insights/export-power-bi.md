---
title: Power BI -yhdistin
description: Tietoja Dynamics 365 Customer Insights -yhdistimen käytöstä Power BI:ssä.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405584"
---
# <a name="connector-for-power-bi-preview"></a>Power BI -yhdistin (esiversio)

Tietojen visualisointien luominen Power BI Desktopin avulla. Voit luoda lisää näkemyksiä ja luoda raportteja, joissa on yhdistettyjä asiakastietoja.

## <a name="prerequisites"></a>Edellytykset

- Käytössä on yhtenäistetyt asiakasprofiilit.
- Tietokoneellasi on asennettuna [Microsoft Power BI Desktopin](https://powerbi.microsoft.com/desktop/) viimeisin versio. [Lisätietoja aiheesta: Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Määritä Power BI -yhdistin

1. Valitse Power BI Desktopissa **Tiedosto** > **Nouda tiedot**.

1. Valitse **Katso lisää** ja hae **Dynamics 365 Customer Insights**

1. Valitse tulos ja valitse **Yhdistä**.

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
