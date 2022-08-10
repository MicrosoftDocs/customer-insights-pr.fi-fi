---
title: Power Apps -yhdistin (esiversio)
description: Power Appsin ja Power Automaten yhdistäminen.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196896"
---
# <a name="power-apps-connector-preview"></a>Power Apps -yhdistin (esiversio)

Tuo yhdistetyt asiakasprofiilit mukautettuihin sovelluksiin Microsoft Power Appsin avulla.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Appsin ja Dynamics 365 Customer Insights -ratkaisun yhdistäminen

Customer Insights on yksi monista [käytettävissä olevista tietolähteistä Power Appsissa ](/powerapps/maker/canvas-apps/working-with-data-sources).

Katso Power Apps -dokumentaatiosta, miten voit [lisätä tietoyhteyden sovellukseen](/powerapps/maker/canvas-apps/add-data-connection). Lisäksi kannattaa tutustua siihen, [miten Power Apps käsittelee delegoinnin avulla suuria tietojoukkoja pohjaan perustuvissa sovelluksissa](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Käytettävissä olevat entiteetit

Kun Customer Insights on lisätty tietoyhteydeksi, valitse seuraavat entiteetit Power Appsissa:

- **Asiakas**: tietojen käyttäminen [yhdistetystä asiakasprofiilista](customer-profiles.md).
- **UnifiedActivity**: [aktiviteettiaikajanan](activities.md) näyttäminen sovelluksessa.
- **ContactProfile**: asiakkaan yhteyshenkilöiden näyttäminen. Tämä entiteetti on käytössä vain yritystilien Customer Insights -ympäristöjen kanssa.

## <a name="limitations"></a>Rajoitukset

### <a name="retrievable-entities"></a>Noudettavissa olevat entiteetit

Voit noutaa vain **Asiakas**-, **UnifiedActivity**-, **Segmentit**- ja **ContactProfile**-entiteetit Power Apps -yhdistimen avulla. ContactProfile on käytössä vain yritystilien Customer Insights -ympäristöjen kanssa. Muita entiteettejä näkyy, koska taustalla oleva yhdistin tukee niitä Power Automatessa olevien käynnistimien kautta.

Voit tehdä enintään 100 kutsua 60 sekunnissa. Voit kutsua ohjelmointirajapinnan päätepistettä useita kertoja käyttämällä $skip-parametria. [Lisätietoja $skip-parametristä](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegointi

Delegointi toimii **Asiakas**-entiteetin ja **UnifiedActivity**-entiteetin osalta.

- **Asiakas**-entiteetin delegointi: tämän entiteetin delegoinnin käyttö edellyttää, että kentät on indeksoitava [Hae ja suodata indeksi](search-filter-index.md) -kohdassa.  
- **UnifiedActivity**-entiteetin delegointi: Tämän entiteetin delegointi toimii vain kenttien **ActivityId** ja **CustomerId** osalta.  
- **ContactProfile**-delegointi: tämän entiteetin delegointi toimii vain kentille **ContactId** ja **CustomerId**. ContactProfile on käytössä vain yritystilien Customer Insights -ympäristöjen kanssa.

Jos haluat lisätietoja delegoinnista, siirry kohtaan [Power Appsin delegoitavat funktiot ja operaatiot](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Esimerkki galleria-ohjausobjektista

Voit myös lisätä asiakasprofiileja [gallerian ohjausobjektiin](/powerapps/maker/canvas-apps/add-gallery).

1. Lisää **Galleria**-ohjausobjekti sovellukseen, jota olet rakentamassa.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Lisää valikoimaelementti.":::

1. Valitse **Asiakas** nimikkeiden tietolähteeksi.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Valitse tietolähde.":::

1. Voit muuttaa tietopaneelia oikealla, jos haluat määrittää asiakasentiteetin valikoimassa näytettävän kentän.

1. Jos haluat näyttää jonkin valitun asiakkaan kentän valikoimassa, täytä selitteen **Teksti**-ominaisuus käyttämällä: **{Name_of_the_gallery}.Selected.{property_name}**  
    - Esimerkiksi: _Gallery1.Selected.address1_city_

1. Jos haluat näyttää asiakkaan yhdistetyn aikajanan, lisää valikoimaelementti ja lisää **Nimikkeet**-ominaisuus käyttämällä: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Esimerkiksi: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
