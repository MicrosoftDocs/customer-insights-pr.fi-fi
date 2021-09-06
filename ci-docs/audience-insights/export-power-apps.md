---
title: Power Apps -yhdistin
description: Power Appsin ja Power Automaten yhdistäminen.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: fc0af656cd5b436d9efd65b2a2c75dde9c9deb9dbcdd56ffc6a960f5878a631f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031745"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps -yhdistin (esiversio)

Tuo yhdistetyt asiakasprofiilit mukautettuihin sovelluksiiin Power Appsin avulla.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Appsin ja Dynamics 365 Customer Insights -ratkaisun yhdistäminen

Customer Insights on yksi monista [käytettävissä olevista tietolähteistä Power Appsissa ](/powerapps/maker/canvas-apps/working-with-data-sources).

Katso Power Apps -dokumentaatiosta, miten voit [lisätä tietoyhteyden sovellukseen](/powerapps/maker/canvas-apps/add-data-connection). Lisäksi kannattaa tutustua siihen, [miten Power Apps käsittelee delegoinnin avulla suuria tietojoukkoja pohjaan perustuvissa sovelluksissa](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Käytettävissä olevat entiteetit

Kun Customer Insights on lisätty tietoyhteydeksi, voit valita seuraavat entiteetit Power Appsissa:

- Asiakas: tietojen käyttäminen [yhdistetystä asiakasprofiilista](customer-profiles.md).
- UnifiedActivity: [aktiviteetin aikajanan](activities.md) näyttäminen sovelluksessa.

## <a name="limitations"></a>Rajoitukset

### <a name="retrievable-entities"></a>Noudettavissa olevat entiteetit

Power Apps-yhdistimen kautta voi noutaa vain entiteettejä **Asiakas**, **UnifiedActivity** ja **Segmentit**. Muita entiteettejä näkyy, koska taustalla oleva yhdistin tukee niitä Power Automatessa olevien käynnistimien kautta.  

### <a name="delegation"></a>Delegointi

Delegointi toimii Asiakas-entiteetin ja UnifiedActivity-entiteetin osalta. 

- **Asiakas**-entiteetin delegointi: tämän entiteetin delegoinnin käyttö edellyttää, että kentät on indeksoitava [Hae ja suodata indeksi](search-filter-index.md) -kohdassa.  

- **UnifiedActivity**-entiteetin delegointi: Tämän enditeeetin delegointi toimii vain kenttien **ActivityId** ja **CustomerId** osalta.  

- Lisätietoja delegoinnista: [Power Appsin delegoitavat funktiot ja toiminnot](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Esimerkki galleria-ohjausobjektista

Asiakasprofiileja voi lisätä esimerkiksi [valikoiman ohjausobjektissa](/powerapps/maker/canvas-apps/add-gallery).

1. Lisää **Galleria**-ohjausobjekti sovellukseen, jota olet rakentamassa.

> [!div class="mx-imgBorder"]
> ![Lisää valikoimaelementti.](media/connector-powerapps9.png "Lisää valikoimaelementti")

1. Valitse **Asiakas** nimikkeiden tietolähteeksi.

    > [!div class="mx-imgBorder"]
    > ![Valitse tietolähde.](media/choose-datasource-powerapps.png "Valitse tietolähde")

1. Voit muuttaa tietopaneelia oikealla, jos haluat määrittää asiakasentiteetin valikoimassa näytettävän kentän.

1. Jos haluat näyttää jonkin valitun asiakkaan kentän valikoimassa, täytä selitteen tekstiominaisuus: **{Name_of_the_gallery}.Selected.{property_name}**

    Esimerkki: Gallery1.Selected.address1_city

1. Jos haluat näyttää asiakkaan yhdistetyn aikajanan, lisää valikoimaelementti ja lisää sitten nimikkeiden ominaisuus: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Esimerkki: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]