---
title: Power Apps -yhdistin (esiversio)
description: Power Appsin ja Power Automaten yhdistäminen.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 0b71f723d1e491d422d24b1be6616d2f33c95d40
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055256"
---
# <a name="power-apps-connector-preview"></a>Power Apps -yhdistin (esiversio)

Tuo yhdistetyt asiakasprofiilit mukautettuihin sovelluksiiin Microsoft Power Appsin avulla.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Appsin ja Dynamics 365 Customer Insights -ratkaisun yhdistäminen

Customer Insights on yksi monista [käytettävissä olevista tietolähteistä Power Appsissa ](/powerapps/maker/canvas-apps/working-with-data-sources).

Katso Power Apps -dokumentaatiosta, miten voit [lisätä tietoyhteyden sovellukseen](/powerapps/maker/canvas-apps/add-data-connection). Lisäksi kannattaa tutustua siihen, [miten Power Apps käsittelee delegoinnin avulla suuria tietojoukkoja pohjaan perustuvissa sovelluksissa](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Käytettävissä olevat entiteetit

Kun Customer Insights on lisätty tietoyhteydeksi, voit valita seuraavat entiteetit Power Appsissa:

- **Asiakas**: tietojen käyttäminen [yhdistetystä asiakasprofiilista](customer-profiles.md).
- **UnifiedActivity**: [aktiviteettiaikajanan](activities.md) näyttäminen sovelluksessa.
- **ContactProfile**: asiakkaan yhteyshenkilöiden näyttäminen. Tämä entiteetti on käytössä vain yritystilien Customer Insights -ympäristöjen kanssa.

## <a name="limitations"></a>Rajoitukset

### <a name="retrievable-entities"></a>Noudettavissa olevat entiteetit

Voit noutaa vain **Asiakas**-, **UnifiedActivity**-, **Segmentit**- ja **ContactProfile**-entiteetit Power Apps -yhdistimen avulla. ContactProfile on käytössä vain yritystilien Customer Insights -esiintymien kanssa. Muita entiteettejä näkyy, koska taustalla oleva yhdistin tukee niitä Power Automatessa olevien käynnistimien kautta.

Voit tehdä enintään 100 kutsua 60 sekunnissa. Voit kutsua ohjelmointirajapinnan päätepistettä useita kertoja käyttämällä $skip-parametria. [Lisätietoja $skip-parametristä](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegointi

Delegointi toimii **Asiakas**-entiteetin ja **UnifiedActivity**-entiteetin osalta. 

- **Asiakas**-entiteetin delegointi: tämän entiteetin delegoinnin käyttö edellyttää, että kentät on indeksoitava [Hae ja suodata indeksi](search-filter-index.md) -kohdassa.  
- **UnifiedActivity**-entiteetin delegointi: Tämän enditeeetin delegointi toimii vain kenttien **ActivityId** ja **CustomerId** osalta.  
- **ContactProfile**-delegointi: tämän entiteetin delegointi toimii vain kentille **ContactId** ja **CustomerId**. ContactProfile on käytössä vain yritystilien Customer Insights -ympäristöjen kanssa.

Jos haluat lisätietoja delegoinnista, siirry kohtaan [Power Appsin delegoitavat funktiot ja operaatiot](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Esimerkki galleria-ohjausobjektista

Voit lisätä asiakasprofiileja [gallerian ohjausobjektiin](/powerapps/maker/canvas-apps/add-gallery).

1. Lisää **Galleria**-ohjausobjekti sovellukseen, jota olet rakentamassa.

    > [!div class="mx-imgBorder"]
    > ![Lisää valikoimaelementti.](media/connector-powerapps9.png "Lisää valikoimaelementti.")

2. Valitse **Asiakas** nimikkeiden tietolähteeksi.

    > [!div class="mx-imgBorder"]
    > ![Valitse tietolähde.](media/choose-datasource-powerapps.png "Valitse tietolähde.")

3. Voit muuttaa tietopaneelia oikealla, jos haluat määrittää asiakasentiteetin valikoimassa näytettävän kentän.

4. Jos haluat näyttää jonkin valitun asiakkaan kentän valikoimassa, täytä selitteen **Teksti**-ominaisuus käyttämällä: **{Name_of_the_gallery}.Selected.{property_name}**  
    - Esimerkiksi: _Gallery1.Selected.address1_city_

5. Jos haluat näyttää asiakkaan yhdistetyn aikajanan, lisää valikoimaelementti ja lisää **Nimikkeet**-ominaisuus käyttämällä: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Esimerkiksi: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
