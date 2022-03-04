---
title: Tietojen käsitteleminen Power Query -yhdistimen kautta (sisältää videon)
description: Power Query -pohjaisten tietolähteiden yhdistimet.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4c12933a0684094702843be309525dd6d5d9b6f4
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355517"
---
# <a name="connect-to-a-power-query-data-source"></a>Yhdistäminen Power Query -tietolähteeseen

Power Queryssa on laaja joukko yhdistimiä tietojen käsittelyä varten. Dynamics 365 Customer Insights tukee suurinta osaa näistä yhdistimistä. 

Tietolähteiden lisääminen Power Query -yhdistimien perusteella etenee yleensä tässä osassa kuvattujen vaiheiden mukaisesti. Käytettävä yhdistin kuitenkin määrittää, mitä tietoja tarvitaan. Lisätietoja yksittäisistä yhdistimistä o [Power Query -yhdistinviitteessä](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Uuden tietolähteen luominen

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.

1. Valitse **Lisää tietolähde**.

1. Valitse **Microsoft Power Query**.

1. Anna tietolähteelle **nimi** ja luo tietolähde valitsemalla **Seuraava**.

1. Valitse jokin [käytettävissä olevista yhdistimistä](#available-power-query-data-sources). Tässä esimerkissä valitaan **Text/CSV**-yhdistin.

1. Anna valitun yhdistimen pakolliset tiedot **Yhteysasetukset**-kohdassa ja esikatsele tiedot valitsemalla **Seuraava**.

1. Valitse **Muunna tiedot**. Tässä vaiheessa tietolähteisiin lisätään entiteettejä. Entiteetit ovat tietojoukkoja. Jos tietokannassa on useita tietojoukkoja, kukin tietojoukko on oma entiteetti.

1. **Power Query - Muokkaa kyselyitä** -dialogi mahdollistaa tietojen tarkistuksen ja tarkennuksen. Vasemmassa ruudussa näkyvät ne entiteetit, jotka järjestelmät tunnistivat valitussa tietolähteessä.

   > [!div class="mx-imgBorder"]
   > ![Muokkaa kyselyjä -ikkuna.](media/data-manager-configure-edit-queries.png "Muokkaa kyselyjä -ikkuna")

1. Voit myös muuntaa tietoja. Valitse muokattava tai muunnettava entiteetti. Ota muunnokset käyttöön Power Query -ikkunassa vaihtoehtojen avulla. Jokainen muunnos mainitaan **Käytössä olevat vaiheet** -luettelossa. Power Query sisältää runsaasti valmiiksi luotuja muunnosvaihtoehtoja. Lisätietoja on kohdassa  [Power Query -muunnokset](/power-query/power-query-what-is-power-query#transformations).

   On suositeltavaa käyttää seuraavia muunnoksia:

   - Jos käsiteltävät tiedot saadaan CSV-tiedostosta, ensimmäisellä rivillä on usein otsikoita. Siirry kohtaan **Muunna** ja valitse **Käytä ensimmäistä riviä otsikoina**.
   - Varmista, että tietotyyppi on määritetty oikein. Valitse esimerkiksi päivämääräkentille päivämäärätyyppi.

1. Voit lisätä entiteettejä tietolähteeseen **Muokkaa kyselyjä** -dialogissa kohdassa **Aloitussivu** valitsemalla **Hae tiedot**.

1. Valitse **Tallenna** Power Query -ikkunan alaostasta tallentaaksesi muunnokset. Tietolähteeseen voi siirtyä tallentamisen jälkeen valitsemalla **Tiedot** > **Tietolähteet**.

1. **Tietolähteet**-sivulla uuden tietolähteen tila on **Päivittyy**.

## <a name="available-power-query-data-sources"></a>Käytettävissä olevat Power Query -tietolähteet

Katso [Power Query -yhdistinviite](/power-query/connectors/) nähdäksesi luettelon yhdistimistä, joita voidaan käyttää tuomaan tietoja Customer Insightsiin. 

Yhdistimet, joilla on merkintä **Customer Insights (tietovirrat)** -sarakkeessa ovat käytettävissä uusien tietolähteiden luomiseen Power Queryn perusteella. Kun yhdistimen dokumentaatiossa on lisätietoja sen edellytyksistä, rajoituksista ja muista tiedoista.

## <a name="edit-power-query-data-sources"></a>Muokkaa Power Query -tietolähteitä

> [!NOTE]
> Jos jokin sovelluksen prosessi (kuten *segmentointi*, *vastaavuus* tai *yhdistäminen*) käyttää tietolähteitä, niin ei ehkä voi tehdä muutoksia. 
>
> Voit seurata **Asetukset**-sivulla kunkin aktiivisen prosessin etenemistä. Kun prosessi valmistuu, voit palata **Tietolähteet**-sivulle ja tehdä muutokset.

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.

2. Valitse vaihdettavan tietolähteen vieressä pystysuunnassa olevat kolme pistettä ja valitse sitten **Muokkaa** avattavasta valikosta.

   > [!div class="mx-imgBorder"]
   > ![Muokkaa-asetus.](media/edit-option-data-sources.png "Muokkaa-asetus")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Ota muutokset ja muunnokset käyttöön **Power Query - Kyselyjen muokkaaminen** -valintaikkunassa kohdassa [Luo uusi tietolähde](#create-a-new-data-source) kuvatulla tavalla.

4. Valitse **Tallenna** Power Queryssä muokkausten jälkeen muutosten tallentamiseksi.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
