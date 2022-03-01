---
title: Luo uusi ympäristö
description: Ympäristön tarkoitus ja uuden ympäristön luominen.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 5e301b4ff0a7586fb143b154b773791b3bd645b7
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648113"
---
# <a name="create-a-new-environment"></a>Luo uusi ympäristö 

## <a name="overview"></a>Yleiskuvaus

Ympäristö on paikka, jossa voit hallita työtiloja ja yhteyksiä. Ympäristön käyttö vaihtelee organisaation ja käyttötapauksen mukaan. Voit esimerkiksi luoda

- yksittäisen ympäristön.
- erillisiä ympäristöjä testausta ja tuotantoa varten.
- erillisiä kullekin kohderyhmälle merkityksellisiä tapahtumia sisältäviä ympäristöjä organisaation tietyille ryhmille tai osastoille.
- erillisiä ympäristöjä yrityksen eri puolilla maailmaa sijaitseville haaroille.
- yhteyksiä Customer Insightsin kohderyhmän merkitykselliset tiedot -ominaisuuteen.

## <a name="create-a-new-environment"></a>Luo uusi ympäristö

1. Valitse pääpalkin oikeasta reunasta ympäristön valitsin ja sitten **+Uusi**.

   :::image type="content" source="media/environment-picker.png" alt-text="Valitse ympäristön valitsin.":::

1. Kirjoita **Asetukset**-ruudussa **Ympäristön nimi**.

1. Valitse tilin **Tyyppi** sopimuksesi mukaan.

1. Valitse **Alue** ja valitse **Seuraava**. 

1. Kirjoita **Työtilan nimi**, jonka avulla voit kerätä tietoja tiettyjä sivustoja tai sovelluksia varten. Lisätietoja on kohdassa [Työtilan luonti](create-workspace.md).

1. Valitse luomasi **Työtilan tyyppi** (verkko tai mobiili). 

1. Valitse **Näytä lisäasetukset**, jotta voit ottaa käyttöön ja tai poistaa käytöstä nämä valinnaiset asetukset:

   - Vaihda **Tuntemattomasta tunnettuun** arvoon "käytössä", jotta voit liittää verkkotaphtumia aiemmin todennettuihin käyttäjiin. Lisätietoja on kohdassa [Todennettujen vierailijoiden verkkotapahtumien tunnistaminen](unknown-to-known.md)
   - Vaihda **Suodata bottiliikenne** arvoon "käytössä", jotta voit poistaa tämän työtilan bottiverkkoliikenteen. 

1. Valitse **Valmis**, kun olet valmis. 

1. Asenna koodikatkelma, jotta voit alkaa vastaanottaa tietoja ja valitse sitten **Valmis** luodaksesi työtilan. Lisätietoja on kohdassa [Kehittäjän resurssien yleiskatsaus](developer-resources.md).

> [!NOTE]
> Voit nyt lisätä jäseniä ja delegoida heille käyttöoikeustasoja **Rooli**-luettelosta. Lisätietoja: [Roolit ja oikeudet](user-roles.md). 

Lisätietoja: [Ympäristöjen ja työtilojen hallinta](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Käytä uutta ympäristöäsi

- [Luo työtila](../engagement-insights/create-workspace.md) ja lisää jäseniä.
- [Lisää koodi sivustollesi](../engagement-insights/instrument-website.md) tai [mobiilisovellukseesi](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Tarkastele [reaaliaikaista raporttia](../engagement-insights/view-reports.md) tai luo [mukautettuja raportteja](../engagement-insights/custom-reports.md).
- [Luo tarkennettuja tapahtumia](../engagement-insights/refined-events.md) vietäväksi.
- [Vie tiedot](../engagement-insights/export-events.md) Data Lake Storageen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
