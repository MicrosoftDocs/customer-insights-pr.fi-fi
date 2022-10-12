---
title: Tuotesuositusten ennusteen näyteopas
description: Tämän näyteoppaan avulla voi kokeilla valmista tuotesuosituksen ennustemallia.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610140"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Tuotesuositusten ennusteen näyteopas

Tässä oppaassa käsitellään kattavasti tuotesuositusennusteen esimerkkiä käyttämällä näytetietoja. Tätä ennustetta kannattaa kokeilla [uudessa ympäristössä](manage-environments.md).

## <a name="scenario"></a>Skenaario

Contoso on yritys, joka tuottaa laadukkaita kahveja ja kahvikoneita. He myyvät tuotteita Contoso Coffeen verkkosivuston kautta. Tavoitteena on ymmärtää, mitä tuotteita tulisi suositella toistuville asiakkaille. Jos tiedetään, mitä asiakkaat **todennäköisesti ostavat**, markkinointiponnisteluissa voidaan keskittyä näihin tiettyihin nimikkeisiin.

## <a name="prerequisites"></a>edellytykset

- Vähintään [osallistujan oikeudet](permissions.md) Customer Insightsissa.

## <a name="task-1---ingest-data"></a>Tehtävä 1 – Tietojen käsitteleminen

Tutustu [tietojen käsittelyä](data-sources.md) ja [tietolähteiden yhdistämistä Power Query -tietolähteeseen](connect-power-query.md) käsitteleviin artikkeleihin. Seuraavissa tiedoissa oletetaan, että tietojen käsittely on yleisesti ottaen tuttua.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Asiakas tietojen käsitteleminen sähköisen kaupankäynnin ympäristössä

1. Luo **eCommerce**-niminen Power Query -tietolähde ja valitse sitten **Text/CSV**-yhdistin.

1. Sähköisen kaupankäynnin yhteyshenkilöiden URL-osoitteen antaminen: https://aka.ms/ciadclasscontacts.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:
   - **DateOfBirth**: päivämäärä
   - **CreatedOn**: päivämäärä, aika ja aikavyöhyke

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Syntymäpäivän muuntaminen päivämääräksi.":::

1. Vaihda oikean ruudun **Nimi**-kenttään tietolähteen nimeksi **eCommerceContacts**

1. **Tallenna** tietolähde.

### <a name="ingest-online-purchase-data"></a>Verkko-ostostietojen käsitteleminen

1. Lisää toinen tietojoukko samaan **eCommerce**-tietolähteeseen. Valitse **Text/CSV**-yhdistin uudelleen.

1. Anna verkko-ostojen tietojen URL-osoitteeksi https://aka.ms/ciadclassonline.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:
   - **PurchasedOn**: päivämäärä ja aika
   - **TotalPrice**: valuutta

1. Vaihda sivuruudun **Nimi**-kenttään tietolähteen nimeksi **eCommercePurchases**.

1. **Tallenna** tietolähde.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Asiakastietojen käyttäminen kanta-asiakasrakenteesta

1. Luo **LoyaltyScheme**-niminen tietolähde ja valitse **Text/CSV**-yhdistin.

1. Kanta-asiakkaiden URL-osoitteeksi annetaan https://aka.ms/ciadclasscustomerloyalty.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:
   - **DateOfBirth**: päivämäärä
   - **RewardsPoints**: kokonaisluku
   - **CreatedOn**: päivämäärä, aika

1. Vaihda oikean ruudun **Nimi**-kentän tietolähteen nimeksi **loyCustomers**.

1. **Tallenna** tietolähde.

## <a name="task-2---data-unification"></a>Tehtävä 2 – tietojen yhtenäistäminen

Tutustu [tietojen yhdistämistä](data-unification.md) käsittelevään artikkeliin. Seuraavissa tiedoissa oletetaan, että tietojen yhdistäminen on yleisesti ottaen tuttua.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tehtävä 3 – tapahtumahistorian aktiviteetin luominen

Tutustu [asiakkaan aktiviteetteja](activities.md) käsittelevään artikkeliin. Seuraavissa tiedoissa oletetaan, että aktiviteettien luominen on yleisesti ottaen tuttua.

1. Luo **eCommercePurchases**-niminen aktiviteetti, jossa on *eCommercePurchases:eCommerce*-entiteetti ja pääavain **PurchaseId**.

1. Luo kohteiden *eCommercePurchases:eCommerce* ja *eCommerceContacts:eCommerce* välille suhde siten, että **ContactID** on kaksi entiteettiä yhdistävä viiteavain.

1. Valitse **TotalPrice** **Aikaleima**-kohdan **EventActivity**- ja **PurchasedOn**-kohdissa.

1. Valitse **Aktiviteetin tyyppi** -kohdassa **SalesOrderLine** ja yhdistä aktiviteetin tiedot semanttisesti.

1. Suorita aktiviteetti.

## <a name="task-4---configure-product-recommendation-prediction"></a>Tehtävä 4 – tuotesuositusennusteen määrittäminen

Yhdistettyjen asiakasprofiilien ja luodun aktiviteetin avulla voidaan nyt suorittaa tuotesuositusennuste.

1. Siirry kohteeseen **Tiedustelu** > **Ennusteet**.

1. Valitse **Luo**-välilehden **Tuotesuositukset (esiversio)** -ruudussa **Käytä mallia**.

1. Valitse **Aloita**.

1. Anna mallille nimi **OOB - tuotesuositusmallin ennuste** ja tulosentiteetille nimi **OOBProductRecommendationModelPrediction**.

1. Valitse **Seuraava**.

1. Malliasetusten määrittäminen:
   - **Tuotteiden määrä**: **5** määrittää, miten monta tuotetta halutaan suositella asiakkaille.
   - **Toistuvia ostoja odotetaan**: **Kyllä** sisällyttää aiemmin ostetut tuotteet suositukseen.
   - **Katso taaksepäin -ikkuna:** **365 päivää** määrittää, miten kauas malli katsoo taaksepäin, ennen kuin tuotetta suositellaan uudelleen.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Tuotesuositusmallin mallin määritykset.":::

1. Valitse **Seuraava**.

1. Valitse **Lisää ostohistoria** -vaiheessa **Lisää tiedot**.

1. Valitse ensin **SalesOrderLine** ja eCommercePurchases-entiteetti sekä sitten **Seuraava**. Pakolliset tiedot täytetään automaattisesti aktiviteetista. Valitse ensin **Tallenna** ja sitten **Seuraava**.

1. Ohita **Tuotetietojen lisääminen**- ja **Tuotesuodattimet**-vaiheet, koska tuotetietoja ei ole.

1. Määritä **Tietojen päivitykset** -vaiheessa mallin aikatauluksi **Kuukausittain**.

1. Valitse **Seuraava**.

1. Kun tiedot on tarkistettu, valitse **Tallenna ja suorita**.

## <a name="task-5---review-model-results-and-explanations"></a>Tehtävä 5 – mallin tulosten ja selitysten tarkistaminen

Anna mallin suorittaa tietojen kouluttaminen ja pisteyttäminen. Tarkista [tuotesuositusmallin selitykset](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Tehtävä 6 – eniten ostettujen tuotteiden segmentin luominen

Mallin käyttö luo uuden entiteetin, joka näkyy **Tieto** > **Entiteetit** -kohdassa. Voit luoda uuden segmentin mallin luoman entiteetin perusteella.

1. Valitse tulossivulla **Luo segmentti**.

1. Luo sääntö **OOBProductRecommendationModelPrediction**-entiteetin avulla ja määritä segmentti:
   - **Kenttä**: ProductID
   - **Arvo**: Valitse kolme suosituinta tuotetunnusta

1. Valitse **Tallenna** ja **suorita** segmentti.

Nyt on käytössä dynaamisesti päivitetty segmentti, joka määrittää viisi suosituinta tuotetta mahdollisesti ostamaan kiinnostunutta asiakasta. Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).

> [!TIP]
> Ennustemallin segmentti voidaan luoda myös **Segmentit**-sivulla valitsemalla ensin **Uusi** ja sitten **Luominen kohteesta** > **Älykäs toiminto**. Lisätietoja on kohdassa [Uuden segmenttien luominen pikasegmenttien avulla](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
