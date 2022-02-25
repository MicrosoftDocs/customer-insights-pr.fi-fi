---
title: Semanttiset yhdistämismääritykset (esiversio)
description: Yleiskatsaus semanttisista yhdistämismäärityksistä ja niiden käytöstä.
ms.date: 12/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: 08b257b97704b219bb3277042516e00deb886a49
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881826"
---
# <a name="semantic-mappings-preview"></a>Semanttiset yhdistämismääritykset (esiversio)

Semanttisten yhdistämismääritysten avulla voit yhdistää ei-aktiviteettitiedot ennalta määritettyihin rakenteisiin. Nämä rakenteet auttavat käyttäjäryhmän merkityksellisiä tietoja ymmärtämään tietomääritteitäsi. Semanttiset yhdistämismääritykset ja toimitetut tiedot mahdollistivat uusia merkityksellisiä tietoja ja ominaisuuksia käyttäjäryhmän merkityksellisissä tiedoissa. Tietoja aktiviteettitietojen yhdistämisestä rakenteisiin löytyy [aktiviteettien](activities.md) ohjeista.

**Semanttiset yhdistämismääritykset on tällä hetkellä otettu käyttöön yritystileihin perustuvissa ympäristöissä**. *ContactProfile* on tällä hetkellä ainoa semanttisen yhdistämismäärityksen tyyppi, joka on käytössä käyttäjäryhmän merkityksellisissä tiedoissa.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>ContactProfilen semanttisen entiteettiyhdistämisen määrittäminen

1. Siirry käyttäjäryhmän merkityksellisissä tiedoissa kohtaan **Tiedot** > **Semanttiset yhdistämismääritykset (esiversio)**.

1. Valitse **Lisää semanttinen yhdistämismääritys** aloittaaksesi ohjatun kokemuksen.

1. Määritä **Entiteetin tiedot** -vaiheessa arvot seuraaville kentille:

   - **Semanttisen entiteettiyhdistämisen nimi**: anna nimi semanttiselle entiteettiyhdistämiselle.
   - **Lähde-entiteetti**: valitse entiteetti, joka sisältää yhteyshenkilön tiedot.
   - **Perusavain**: valitse kenttä, joka tunnistaa yhteyshenkilötietueen yksilöidysti. Siinä ei saa olla arvojen kaksoiskappaleita, tyhjiä arvoja eikä puuttuvia arvoja.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Määritä semanttinen entiteettiyhdistäminen, jossa on nimi, lähde-entiteetti ja perusavain .":::

1. Jatka valitsemalla **Seuraava**.

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
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisointi eri suhteista ja yhteyshenkilöentiteettien yhdistämisestä asiakasentiteetteihin.":::

1. Valits **Seuraava**, kun suhteiden määrittäminen on valmis.

1. Valitse **Määritä semanttinen tyyppi** -vaiheessa **Semanttinen tyyppi**. Tällä hetkellä on yksi **Semanttinen tyyppi** nimeltä *ContactProfile*.

1. Yhdistä tiedot *ContactProfile*-**Semanttiseen tyyppiin** näkyvissä oleville kentille.
   - Pakollinen kenttä: Contact ID
   - Valinnaiset kentät: etunimi, sukunimi, syntymäpäivä, sukupuoli, ensisijainen sähköposti ja ensisijainen puhelin

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Yhdistä yhteyshenkilön tietomääritteet annettuihin pakollisiin ja valinnaisiin kenttiin.":::

1. Jatka valitsemalla **Seuraava**.

1. Tarkastele **Tarkista**-vaiheessa semanttisten yhdistämismääritysten kokoonpano. Valitse vastaavalle osalle **Muokkaa**, jos haluat tehdä muutoksia.

1. Valitse **Tallenna** tallentaaksesi uuden **Semanttisen yhdistämismäärityksen**.

1. Tallentamisen jälkeen voit valita **Suorita** käsitelläksesi semanttiset yhdistämismääritykset tai voit valita **Sulje** tallentaaksesi semanttiset yhdistämismääritykset ilman käsittelyä.

1. Jos haluat suorittaa semanttiset yhdistämismääritykset myöhemmin, valitse semanttiset yhdistämismääritykset ja valitse **Lataa uudelleen**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Aiemmin luotujen semanttisten yhdistämismääritysten hallinta

Kohdassa **Tiedot** > **Semanttiset yhdistämismääritykset (esiversio)** voit tarkastella kaikkia semanttisia yhdistämismäärityksiä ja hallita niitä. Kutakin semanttista yhdistämismääritystä edustaa erillinen rivi. Saat tietoja lähde-entiteetistä, semanttisesta tyypistä, yhdistämistyypistä ja sen tilasta.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Semanttisten yhdistämismääritysten hallinta-asetukset.":::

- **Muokkaa**: Avaa semanttisten yhdistämismääritysten kokoonpanon tarkistusvaiheessa. Voit muuttaa nykyistä kokoonpanoa. Valitse **Tallenna** ja **Suorita** muutosten käsittelemiseksi.

- **Lataa uudelleen**: Lataa valitun semanttisen yhdistämismäärityksen uudelleen ajantasaisimmilla tiedoilla entiteeteistä, jotka kuuluvat sen kokoonpanoon. Kun mikä tahansa semanttinen yhdistämismääritys ladataan uudelleen, kaikki samantyyppiset semanttiset yhdistämismääritykset ladataan uudelleen.

- **Nimeä uudelleen**: Avaa dialogin, jossa voit antaa valitulle semanttiselle yhdistämismääritykselle toisen nimen. Ota muutokset käyttöön valitsemalla **Tallenna**.

- **Poista**: Avaa dialogin, joka vahvistaa valitun semanttisen yhdistämismäärityksen poistamisen. Voit myös poistaa useita semanttisia yhdistämismäärityksiä kerralla valitsemalla semanttiset yhdistämismääritykset ja poistokuvakkeen. Vahvista poisto valitsemalla **Poista**.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Yhteyshenkilötason aktiviteettien luominen ContactProfile-entiteettien semanttisen yhdistämismäärityksen avulla

Kun olet luonut semanttisen *ContactProfile*-entiteettien yhdistämismäärityksen, voit siepata yhteyshenkilöiden aktiviteetit. Sen avulla näet tilin aktiviteetin aikajanalla sen yhteyshenkilön, joka oli vastuussa kustakin aktiviteetista. Useimmat vaiheet noudattavat tyypillistä aktiviteettien yhdistämismääritystä.

   > [!NOTE]
   > Jotta yhteyshenkilötason aktiviteetit toimisivat, aktiviteettitietojen jokaiselle tietueelle on oltava sekä **AccountID**- että **ContactID**-määritteet.

1. [*ContactProfilen* semanttisen entiteettiyhdistämisen määrittäminen](#define-a-contactprofile-semantic-entity-mapping) ja suorita semanttinen yhdistämismääritys.

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Aktiviteetit**.

1. Luo uusi aktiviteetti valitsemalla **Lisää aktiviteetti**.

1. Anna aktiviteetille nimi, valitse lähdeaktiviteettientiteetti ja valitse aktiviteettientiteetin perusavain.

1. Luo **Suhteet**-vaiheessa epäsuora suhde aktiviteetin lähdetietojen ja asiakkaiden välille käyttämällä yhteyshenkilötietojasi välittävänä entiteettinä. Lisätietoja löytyy kohdasta [suorat ja epäsuorat suhdepolut](relationships.md#relationship-paths).
   - Esimerkkinä *Ostot*-nimisen aktiviteetin suhde:
      - **Ostojen lähdeaktiviteettitiedot** > **Yhteyshenkilötiedot** määritteessä **ContactID**
      - **Yhteyshenkilön tiedot** > **Asiakkaan tiedot** määritteessä **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Esimerkki suhteen määrityksestä.":::

1. Kun olet määrittänyt suhteet, valitse **Seuraava** ja viimeistele aktiviteettien yhdistämismääritykset. Aktiviteettien luonnin yksityiskohtaiset vaiheet ovat ohjeaiheessa [Aktiviteetin määritteleminen](activities.md).

1. Suorita aktiviteettien yhdistämismääritykset.

1. Yhteyshenkilötason aktiviteettisi näkyvät nyt asiakkaan aikajanalla.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Lopullinen tulos yhteyshenkilöaktiviteettien määrittämisen jälkeen":::

### <a name="contact-level-activity-timeline-filtering"></a>Yhteyshenkilötason aktiviteettiaikajanan suodatus

Kun olet määrittänyt yhteyshenkilötason aktiviteettien yhdistämismäärityksen ja suorittanut sen, asiakkaiden aktiviteettiaikajana päivittyy. Se sisältää yhteyshenkilöiden tunnukset tai nimet *ContactProfile*-määritysten mukaisesti aktiviteetteja varten, joissa he ovat toimineet. Voit suodattaa aktiviteetteja aikajanan yhteyshenkilöiden mukaan nähdäksesi tietyt yhteyshenkilöt, joista olet kiinnostunut. Voit myös tarkastella kaikkia aktiviteetteja, joita ei ole delegoitu tietylle yhteyshenkilölle, valitsemalla **Aktiviteetit, joita ei ole yhdistetty yhteyshenkilöön.**

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Yhteyshenkilötason aktiviteetteja varten käytettävissä olevat suodatusvaihtoehdot.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]