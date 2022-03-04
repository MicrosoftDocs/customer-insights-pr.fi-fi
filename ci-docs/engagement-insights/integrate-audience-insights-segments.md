---
title: Analyysitietojen käyttäjäryhmäsegmenttien käyttäminen sitoutumistietoraporttien suodattamiseen
description: Käytä käyttäjäryhmätilastosegmenttejä vuorovaikutteisissa analyyseissä käyttäytymistiedoista, jotka on kerätty sitouttamistietojen avulla asiakkaan verkkosivustolla.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230482"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Analyysitietojen käyttäjäryhmäsegmenttien käyttäminen sitoutumistietoraporttien suodattamiseen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Sitoutumistietojen avulla voit käyttää käyttäjäryhmätilastosegmenttejä vuorovaikutteisissa analyyseissä käyttäytymistiedoista, jotka on kerätty sitouttamistietojen avulla verkkosivustoillasi.

## <a name="prerequisite"></a>Edellytykset

- Sitoutumistilastoympäristö, jossa sinulla on käyttäjäryhmätietosegmentit linkitettyinä käyttäjätietoympäristöön, jossa segmentit ja asiakasprofiilit luodaan. Lisätietoja: [Linkin luominen kohdeyleisön ja sitoutumistietojen välille](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Käyttäjäryhmän merkityksellisten tietojen segmenttien luominen 

> [!IMPORTANT]
> Jotta käyttäjäryhmätietoja ilmestyy sitoutumistietoihin, sinun tulee ensin [suorittaa yhdistämis- ja jatkoprosessit](../audience-insights/merge-entities.md). Myöhemmät prosessit ovat tärkeitä, koska ne luovat ainutlaatuisen taulukon, joka valmistelee käyttäjäryhmien segmentit jaettavaksi sitoutumistietojen kanssa. (Jos järjestelmä päivitetään, se sisältää automaattisesti jatkoprosessit.)

Voit käyttää käyttäjäryhmän tietosegmenttejä valmiista sitoutumistietoraporteista tai luomistasi mukautetuista raporteista. Lisätietoja on kohdassa [Valmiit profiiliraportit](profile-reports.md) ja [Mukautettujen raporttien luominen ja muokkaaminen](custom-reports.md).

**Analyysitietojen käyttäjäryhmäsegmenttien käyttäminen sitoutumistietoraporteissa**

1. Valitse **Työtila**-sivulla **Tiedot** ja valitse sitten **Segmentit**-välilehti.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Valitse Segmentit-välilehti.":::

   >[!NOTE]
   > Kun valitset käyttäjäryhmätietoja, käyttäjäryhmän avulla saat tietoja siitä, miten tämä segmentti on luotu sääntöjen ja logiikan mukaan. Lisätietoja käyttäjäryhmätietojen segmentistä on kohdassa [Näytä ja luo segmenttejä](../audience-insights/segments.md).

2. Valitse pikaraportti tai [luo mukautettu raportti](custom-reports.md) ja valitse sitten **Lisää ehto**. (Tässä esimerkissä valitsimme **Sivunäkymät**-raportin.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Ehdon lisääminen.":::

3. Valitse **Suodata segmentin mukaan**, laajenna **Segmenttityyppi**-luettelo ja valitse sitten **Demografiatiedot**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Valitse demografiasegmentin tyyppi.":::

4. Laajenna **Segmentin nimi** -luettelo ja valitse sitten käyttäjäryhmän tietosegmentti.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Valitse segmentti.":::

5. Voit käyttää vähintään yhtä segmenttiä, kuten käyttäytymis- (sitoutumistiedot) ja demografisia (käyttäjäryhmä) segmenttejä. 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Sivunäkymät-raportti on rajoitettu Vain Yhdysvaltojen asiakkaille- ja Kotisivu-segmentteihin.":::

Edeltävässä kuvassa on valittu **USA:n asiakkaat**- ja **Kotisivu**-segmentit, mikä rajoittaa **Sivunäkymät**-raportin näyttämiseen vain nämä kaksi segmenttiä. 


>[!NOTE]
> Käyttäjäryhmän tietosegmenttien avulla voit suodattaa valmiita raportteja, muokattuja raportteja ja sitoutumistilastojen kanavia. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]