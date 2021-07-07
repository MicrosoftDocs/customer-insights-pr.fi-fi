---
title: Tietojen käyttäminen Power Query -yhdistimen avulla
description: Power Queryyn perustuvien tietolähteiden yhdistimet.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 50c231070ff9930c1ea82971bf4f8541a89d5027
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305887"
---
# <a name="connect-to-a-power-query-data-source"></a>Yhteyden muodostaminen Power Query -tietolähteeseen

Power Queryssä on laaja valikoima tietojen käsittelyyn tarkoitettuja yhdistimiä. Dynamics 365 Customer Insights tukee suurinta osaa näistä yhdistimistä. Power Query -yhdistimiin perustuvia tietolähteitä lisätään yleensä seuraavassa osassa kuvattujen vaiheiden mukaisesti. Käytettävä yhdistin kuitenkin määrittää, mitä tietoja tarvitaan. Lisätietoja yhdistinkohtaisista ohjeista on [Power Query -yhdistimien viitesivulla](/power-query/connectors/).

## <a name="create-a-new-data-source"></a>Uuden tietolähteen luominen

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.

1. Valitse **Lisää tietolähde**.

1. Valitse **Tuo tiedot** -menetelmä ja valitse sitten **Seuraava**.

1. Anna tietolähteelle **nimi** ja luo tietolähde valitsemalla **Seuraava**. Nimen ohjeet: 
   - Alussa on oltava kirjain.
   - Käytä vain kirjaimia ja numeroita. Erikoismerkit ja välilyönnit eivät ole sallittuja.
   - Käytä 3–64 merkkiä.

1. Valitse jokin [käytettävissä olevista yhdistimistä](#available-power-query-data-sources). Tässä esimerkissä valitaan **Text/CSV**-yhdistin.

1. Anna valitun yhdistimen pakolliset tiedot **Yhteysasetukset**-kohdassa ja esikatsele tiedot valitsemalla **Seuraava**.

1. Valitse **Muunna tiedot**. Tässä vaiheessa tietolähteisiin lisätään entiteettejä. Entiteetit ovat tietojoukkoja. Jos tietokannassa on useita tietojoukkoja, kukin tietojoukko on oma entiteetti.

1. Voit tarkistaa tiedot ja tarkentaa niitä **Power Query – Muokkaa kyselyjä** -valintaikkunassa. Vasemmassa ruudussa näkyvät ne entiteetit, jotka järjestelmät tunnistivat valitussa tietolähteessä.

   > [!div class="mx-imgBorder"]
   > ![Muokkaa kyselyjä -ikkuna](media/data-manager-configure-edit-queries.png "Muokkaa kyselyjä -ikkuna")

1. Voit myös muuntaa tietoja. Valitse muokattava tai muunnettava entiteetti. Tee muunnokset Power Query -ikkunassa olevilla asetuksilla. Jokainen muunnos mainitaan **Käytössä olevat vaiheet** -luettelossa. Power Query sisältää useita valmiita muunnosvaihtoehtoja. Lisätietoja on kohdassa [Power Query -muunnokset](/power-query/power-query-what-is-power-query#transformations).

1. Voit lisätä tietolähteeseen entiteettejä valitsemalla **Nouda tiedot** **Muokkaa kyselyjä** -valintaikkunassa.

   Seuraavien muunnosten tekeminen on suositeltavaa:

   - Jos käsiteltävät tiedot saadaan CSV-tiedostosta, ensimmäisellä rivillä on usein otsikoita. Valitse ensin **Muunna taulukko** ja sitten **Käytä otsikoita ensimmäisenä rivinä**.
   - Varmista, että tietotyyppi on määritetty oikein.

1. Tallenna muunnokset valitsemalla Power Query -ikkunan alareunassa **Tallenna**. Tietolähteeseen voi siirtyä tallentamisen jälkeen valitsemalla **Tiedot** > **Tietolähteet**.

1. **Tietolähteet**-sivulla uuden tietolähteen tila on **Päivittyy**.

## <a name="available-power-query-data-sources"></a>Käytettävissä olevat Power Query -tietolähteet

[Power Query -yhdistimien viitesivulla](/power-query/connectors/) on ajantasainen luettelo yhdistimistä, jotka voidaan valita tuomaan tietoja Customer Insightsiin. 

Yhdistimiä, joiden **Customer Insights (tietovuot)** -sarakkeessa on valintamerkki, voidaan käyttää uusien Power Queryyn perustuvien tietolähteiden luomiseen. Kun yhdistimen dokumentaatiossa on lisätietoja sen edellytyksistä, rajoituksista ja muista tiedoista.

## <a name="edit-power-query-data-sources"></a>Power Query -tietolähteiden muokkaaminen

> [!NOTE]
> Jos jokin sovelluksen prosessi (kuten *segmentointi*, *vastaavuus* tai *yhdistäminen*) käyttää tietolähteitä, niin ei ehkä voi tehdä muutoksia. 
>
> Voit seurata **Asetukset**-sivulla kunkin aktiivisen prosessin etenemistä. Kun prosessi valmistuu, voit palata **Tietolähteet**-sivulle ja tehdä muutokset.

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.

2. Valitse vaihdettavan tietolähteen vieressä pystysuunnassa olevat kolme pistettä ja valitse sitten **Muokkaa** avattavasta valikosta.

   > [!div class="mx-imgBorder"]
   > ![Muokkaa-asetus](media/edit-option-data-sources.png "Muokkaa-asetus")

3. Lisätietoja muutosten ja muunnosten käyttämisestä **Power Query – Muokkaa kyselyjä** -ikkunassa on kohdassa [Uuden tietolähteen luominen](#create-a-new-data-source).

4. Kun lopetat muokkaamisen, tallenna muutokset valitsemalla **Tallenna** Power Queryssä.


[!INCLUDE[footer-include](../includes/footer-banner.md)]