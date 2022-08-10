---
title: Yhteyden muodostaminen Power Query -tietolähteeseen (sisältää videon)
description: Tietojen käsitteleminen Power Query -yhdistimen kautta (sisältää videon).
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 7af51ed04fbd28149ea501c58e6fe71b5fa6d4b6
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207041"
---
# <a name="connect-to-a-power-query-data-source"></a>Yhdistäminen Power Query -tietolähteeseen

Power Queryssa on laaja joukko yhdistimiä tietojen käsittelyä varten. Dynamics 365 Customer Insights tukee suurinta osaa näistä yhdistimistä.

Tietolähteiden lisääminen Power Query -yhdistimien perusteella etenee yleensä tässä osassa kuvattujen vaiheiden mukaisesti. Käytettävä yhdistin kuitenkin määrittää, mitä tietoja tarvitaan. Lisätietoja yksittäisistä yhdistimistä o [Power Query -yhdistinviitteessä](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Uuden tietolähteen luominen

1. Valitse **Tiedot** > **Tietolähteet**.

1. Valitse **Lisää tietolähde**.

1. Valitse **Microsoft Power Query**.

1. Anna tietolähteen **nimi** ja valinnaisena **kuvaus** sekä valitse **Seuraava**.

1. Valitse jokin [käytettävissä olevista yhdistimistä](#available-power-query-data-sources). Tässä esimerkissä valitaan **Text/CSV**-yhdistin.

1. Anna valitun yhdistimen pakolliset tiedot **Yhteysasetukset**-kohdassa ja esikatsele tiedot valitsemalla **Seuraava**.

1. Valitse **Muunna tiedot**.

1. **Power Query - Muokkaa kyselyitä** -dialogi mahdollistaa tietojen tarkistuksen ja tarkennuksen. Vasemmassa ruudussa näkyvät ne entiteetit, jotka järjestelmät tunnistivat valitussa tietolähteessä.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Muokkaa kyselyjä -ikkuna":::

1. Voit myös muuntaa tietoja. Valitse muokattava tai muunnettava entiteetti. Ota muunnokset käyttöön Power Query -ikkunassa vaihtoehtojen avulla. Kukin muunto on mainittu luettelossa **Käytössä olevat vaiheet** -kohdassa. Power Query sisältää runsaasti [valmiiksi luotuja muunnosvaihtoehtoja](/power-query/power-query-what-is-power-query#transformations).

   On suositeltavaa käyttää seuraavia muunnoksia:

   - Jos käsiteltävät tiedot saadaan CSV-tiedostosta, ensimmäisellä rivillä on usein otsikoita. Siirry kohtaan **Muunna** ja valitse **Käytä ensimmäistä riviä otsikoina**.
   - Varmista, että tietotyyppi on määritetty oikein. Valitse esimerkiksi päivämääräkentille päivämäärätyyppi.

1. Voit lisätä entiteettejä tietolähteeseen **Muokkaa kyselyjä** -dialogissa kohdassa **Aloitussivu** valitsemalla **Hae tiedot**. Toista vaiheet 5–10, kunnes kaikki tämän tietolähteen entiteetit on lisätty. Jos tietokannassa on useita tietojoukkoja, kukin tietojoukko on oma entiteetti.

1. Valitse **Tallenna**. Avautuvalla **Tietolähteet**-sivulla on näkyy uusi tietolähde, jonka tilana on **Päivitetään**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Tietojen lataaminen voi viedä aikaa. Kun päivitys on onnistunut, käsiteltyjä tietoja voi tarkastella [**Entiteetit**](entities.md)-sivulla.

> [!CAUTION]
> Power Query -pohjainen tietolähde tuottaa [tietovuon järjestelmässä Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Älä muuta Customer Insightsissa käytetyn tietovuon nimeä Power Platform -hallintakeskuksessa. Työvuon uudelleennimeäminen aiheuttaa ongelmia Customer Insightsin tietolähteen ja Dataverse -tietovuon välisissä viittauksissa.

### <a name="available-power-query-data-sources"></a>Käytettävissä olevat Power Query -tietolähteet

Katso [Power Query -yhdistinviite](/power-query/connectors/) nähdäksesi luettelon yhdistimistä, joita voidaan käyttää tuomaan tietoja Customer Insightsiin.

Yhdistimet, joilla on merkintä **Customer Insights (tietovirrat)** -sarakkeessa ovat käytettävissä uusien tietolähteiden luomiseen Power Queryn perusteella. Yhdistinkohtaisissa ohjeissa on lisätietoja siihen liittyvistä edellytyksistä, [kyselyrajoituksista](/power-query/power-query-online-limits) ja muista tiedoista.

## <a name="add-data-from-on-premises-data-sources"></a>Tietojen lisääminen paikallisista tietolähteistä

Tiedon keräämistä paikallisista tietolähteistä tuetaan Microsoft Power Platform -tietovoiden (PPDF) perusteella. Tietovuot otetaan käyttöön Customer Insightsissa [antamalla Microsoft Dataverse -ympäristön URL-osoitteen](create-environment.md) ympäristön määrittämisen jälkeen.

Tietolähteet, jotka luodaan, kun Dataverse-ympäristö on liitetty Customer Insightsiin, käyttävät oletusarvoisesti [Power Platform -tietovirtoja](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Tietovuot tukevat paikallisia yhteyksiä tietoyhdyskäytävän avulla. Voit poistaa ja luoda uudelleen tietolähteitä, jotka olivat olemassa ennen Dataverse-ympäristön liittämistä, [paikallisten tietoyhdyskäytävien avulla](/data-integration/gateway/service-gateway-app).

Aiemmin luodun Power BI- tai Power Apps -ympäristön tietoyhdyskäytävät ovat näkyvissä, ja voit käyttää niitä uudelleen Customer Insightsissa. Tietolähteiden sivulla on linkki, jonka avulla voi siirtyä Microsoft Power Platform -ympäristöön paikallisten tietoyhdyskäytävien tarkastelemista ja määrittämistä varten.

> [!IMPORTANT]
> Varmista, että yhdyskäytävät on päivitetty uusimpaan versioon. Voit asentaa päivityksen ja määrittää yhdyskäytävän uudelleen yhdyskäytävän näytössä näkyvästä kehotteesta tai [ladata uusimman version](https://powerapps.microsoft.com/downloads/). Jos et käytä uusinta yhdyskäytäväversiota, tietovirran päivitys epäonnistuu ja näyttöön tulee virhesanomia, kuten **Avainsanaa ei tueta: määritysominaisuudet. Parametrin nimi: avainsana**.
>
> Customer Insightsin paikalliset tietoyhdyskäytävien virheet johtuvat usein määritysongelmista. Lisätietoja tietoyhdyskäytävien ongelmien vianmäärityksestä: [Paikallisten tietoyhdyskäytävien vianmääritys](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Muokkaa Power Query -tietolähteitä

> [!NOTE]
> Jos jokin sovelluksen prosessi (kuten segmentointi tai tietojen yhdistäminen) käyttää tietolähteitä, niin ei ehkä voi tehdä muutoksia.
>
> Voit seurata **Asetukset**-sivulla kunkin aktiivisen prosessin etenemistä. Kun prosessi valmistuu, voit palata **Tietolähteet**-sivulle ja tehdä muutokset.

1. Valitse **Tiedot** > **Tietolähteet**.

1. Valitse päivitettävän tietolähteen vieressä **Muokkaa**.

1. Ota muutokset ja muunnokset käyttöön **Power Query - Kyselyjen muokkaaminen** -valintaikkunassa kohdassa [Luo uusi tietolähde](#create-a-new-data-source) kuvatulla tavalla.

1. Ota muutokset käyttöön ja palaa **Tietolähteet**-sivulle valitsemalla **Tallenna**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
