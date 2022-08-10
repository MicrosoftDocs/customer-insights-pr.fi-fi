---
title: Semanttiset yhdistämismääritykset (esiversio)
description: Yleiskatsaus semanttisista yhdistämismäärityksistä ja niiden käytöstä.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183627"
---
# <a name="semantic-mappings-preview"></a>Semanttiset yhdistämismääritykset (esiversio)

Semanttisten yhdistämismääritysten avulla voit yhdistää ei-aktiviteettitiedot ennalta määritettyihin rakenteisiin. Nämä rakenteet auttavat Customer Insightsia ymmärtämään tietomääritteitäsi. Semanttiset yhdistämismääritykset ja toimitetut tiedot mahdollistivat uusia merkityksellisiä tietoja ja ominaisuuksia Customer Insightsissa. Tietoja aktiviteettitietojen yhdistämisestä rakenteisiin löytyy [aktiviteettien](activities.md) ohjeista.

**Semanttiset yhdistämismääritykset on tällä hetkellä otettu käyttöön yritystileihin perustuvissa ympäristöissä**. *ContactProfile* on tällä hetkellä ainoa semanttisen yhdistämismäärityksen tyyppi, joka on käytössä Customer Insightsissa.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>ContactProfilen semanttisen entiteettiyhdistämisen määrittäminen

1. Siirry kohtaan **Tiedot** > **Semanttiset yhdistämismääritykset (esiversio)**.

1. Valitse **Lisää semanttinen yhdistämismääritys** aloittaaksesi ohjatun kokemuksen.

1. Määritä **Entiteetin tiedot** -vaiheessa arvot seuraaville kentille:

   - **Semanttisen entiteettiyhdistämisen nimi**: nimi semanttiselle entiteettiyhdistämismääritykselle.
   - **Lähde-entiteetti**: valitse entiteetti, joka sisältää yhteyshenkilön tiedot.
   - **Perusavain**: valitse kenttä, joka tunnistaa yhteyshenkilötietueen yksilöidysti. Siinä ei saa olla arvojen kaksoiskappaleita, tyhjiä arvoja eikä puuttuvia arvoja.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Määritä semanttinen entiteettiyhdistäminen, jossa on nimi, lähde-entiteetti ja perusavain .":::

1. Valitse **Seuraava**.

1. Määritä **Suhteet**-vaiheessa tiedot, joiden avulla yhteyshenkilön tiedot yhdistetään vastaaviin asiakastietoihin. Tässä vaiheessa visualisoidaan entiteettien väliset yhteydet.  

   Voidaan toteuttaa kahdentyyppisiä suhdepolkuja: **Suorat suhteet** ja **Epäsuorat suhteet**. Lisätietoja löytyy kohdasta [suorat ja epäsuorat suhdepolut](relationships.md#relationship-paths).

   1. Valitse **Lisää suhde** määrittääksesi suhteen.
   1. Valitse lähde-entiteetistä määrite, joka yhdistää yhteyshenkilöentiteetin toiseen entiteettiin.
   1. Valitse entiteetti, johon yhteyshenkilöentiteetti yhdistetään. Voit valita entiteetin **Asiakasentiteetit**- tai **Keskitason entiteetti** -osasta. Jos valitset keskitason entiteetin, sinun täytyy määrittää toinen suhde, joka yhdistetään kohdeasiakasentiteettiin.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Valitse joko asiakasentiteetti tai keskitason entiteetti.":::

   1. Anna **Suhteen nimi**. Jos entiteettien välinen suhde on jo olemassa, suhteen nimi on vain luku -tyyppinen. Jos suhdetta ei ole, uusi suhde luodaan käyttämällä nimeä, jonka annat.
   1. Valitse **Käytä** viimeistelläksesi suhteen määrittämisen.

   > [!NOTE]
   > Voit määrittää lisää suhteita yhteyshenkilöentiteetin ja muiden asiakasentiteettien välille keskitason entiteettien avulla.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisointi eri suhteista ja yhteyshenkilöentiteettien yhdistämisestä asiakasentiteetteihin.":::

1. Valitse **Seuraava**.

1. Valitse **Määritä semanttinen tyyppi** -vaiheessa **Semanttinen tyyppi**. Tällä hetkellä on yksi **Semanttinen tyyppi** nimeltä *ContactProfile*.

1. Yhdistä yhteyshenkilön tunnus *ContactProfile*-semanttisen tyypin **yhteyshenkilötunnukseen**. Voit halutessasi yhdistää samalla tavalla muita kenttiä. Näitä kenttiä ovat esimerkiksi etunimi, sukunimi, sukupuoli ja sähköpostiosoite.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Yhdistä yhteyshenkilön tietomääritteet annettuihin pakollisiin ja valinnaisiin kenttiin.":::

1. Valitse **Seuraava**.

1. Tarkastele **Tarkista**-vaiheessa semanttisten yhdistämismääritysten kokoonpano. Valitse vastaavalle osalle **Muokkaa**, jos haluat tehdä muutoksia.

1. Valitse **Tallenna**.

1. Valitse **Suorita** semanttisen yhdistämisen käsittelemiseksi. Voit myös tallentaa semanttisen yhdistämismäärityksen käsittelemättä sitä valitsemalla **Sulje**. Jos haluat suorittaa semanttiset yhdistämismääritykset myöhemmin, valitse semanttiset yhdistämismääritykset ja valitse **Lataa uudelleen**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Aiemmin luotujen semanttisten yhdistämismääritysten hallinta

Voit tarkastella tallennettuja semanttisia yhdistämismäärityksiä, niiden lähde-entiteettiä, semanttista tyyppiä, yhdistämistyyppiä ja tilaa valitsemalla **Tiedot** > **Semanttiset yhdistämiset (esiversio)**

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Semanttisten yhdistämismääritysten hallinta-asetukset.":::

Voit tarkastella käytettävissä olevia toimintoja valitsemalla semanttisen yhdistämisen.
- **Muokkaa** nykyistä määritystä. Valitse **Tallenna** ja **Suorita** muutosten käsittelemiseksi.
- **Päivitä** semanttinen yhdistämisen siten, että se sisältää uusimmat tiedot. Kun mikä tahansa semanttinen yhdistämismääritys ladataan uudelleen, kaikki samantyyppiset semanttiset yhdistämismääritykset ladataan uudelleen.
- **Nimeä uudelleen** semanttinen yhdistäminen. Valitse **Tallenna**.
- **Poista** semanttinen yhdistämismääritys. Voit myös poistaa useita semanttisia yhdistämismäärityksiä kerralla valitsemalla semanttiset yhdistämismääritykset ja poistokuvakkeen. Vahvista poisto valitsemalla **Poista**.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Yhteyshenkilötason aktiviteettien luominen ContactProfile-entiteettien semanttisen yhdistämismäärityksen avulla

Kun olet luonut semanttisen *ContactProfile*-entiteettien yhdistämismäärityksen, voit siepata yhteyshenkilöiden aktiviteetit. Sen avulla näet tilin aktiviteetin aikajanalla sen yhteyshenkilön, joka oli vastuussa kustakin aktiviteetista. Useimmat vaiheet noudattavat tyypillistä aktiviteettien yhdistämismääritystä.

   > [!NOTE]
   > Jotta yhteyshenkilötason aktiviteetit toimisivat, aktiviteettitietojen jokaiselle tietueelle on oltava sekä **AccountID**- että **ContactID**-määritteet.

1. [Määritä semanttinen *ContactProfile* -yhdistämismääritys](#define-a-contactprofile-semantic-entity-mapping) ja suorita semanttinen yhdistämismääritys.

1. Siirry kohtaan **Tiedot** > **Aktiviteetit**.

1. Luo uusi aktiviteetti valitsemalla **Lisää aktiviteetti**.

1. Anna aktiviteetille nimi, valitse lähdeaktiviteettientiteetti ja valitse aktiviteettientiteetin perusavain.

1. Luo **Suhteet**-vaiheessa epäsuora suhde aktiviteetin lähdetietojen ja asiakkaiden välille käyttämällä yhteyshenkilötietojasi välittävänä entiteettinä. Lisätietoja löytyy kohdasta [suorat ja epäsuorat suhdepolut](relationships.md#relationship-paths).
   - Esimerkkinä *Ostot*-nimisen aktiviteetin suhde:
      - **Ostojen lähdeaktiviteettitiedot** > **Yhteyshenkilötiedot** määritteessä **ContactID**
      - **Yhteyshenkilön tiedot** > **Asiakkaan tiedot** määritteessä **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Esimerkki suhteen määrityksestä.":::

1. Kun olet määrittänyt suhteet, valitse **Seuraava** ja viimeistele aktiviteettien yhdistämismääritykset. Aktiviteettien luonnin yksityiskohtaiset vaiheet ovat ohjeaiheessa [Aktiviteetin määritteleminen](activities.md).

1. Suorita aktiviteettien yhdistämismääritykset.

1. Kun yhteyshenkilötason aktiviteettien yhdistäminen on käynnissä, valitse **Asiakkaat**. Yhteyshenkilötason aktiviteettisi näkyvät asiakkaan aikajanalla.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Lopullinen tulos yhteyshenkilöaktiviteettien määrittämisen jälkeen":::

### <a name="contact-level-activity-timeline-filtering"></a>Yhteyshenkilötason aktiviteettiaikajanan suodatus

Asiakkaidesi aktiviteettiaikajana sisältää yhteyshenkilöiden tunnukset tai nimet *ContactProfile*-määritysten mukaisesti aktiviteetteja varten, joissa he ovat toimineet. Voit suodattaa aktiviteetteja aikajanan yhteyshenkilöiden mukaan nähdäksesi tietyt yhteyshenkilöt, joista olet kiinnostunut. Voit tarkastella kaikkia aktiviteetteja, joita ei ole delegoitu tietylle yhteyshenkilölle, valitsemalla **Aktiviteetit, joita ei ole yhdistetty yhteyshenkilöön.**

:::image type="content" source="media/Contact_Activities3.png" alt-text="Yhteyshenkilötason aktiviteetteja varten käytettävissä olevat suodatusvaihtoehdot.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
