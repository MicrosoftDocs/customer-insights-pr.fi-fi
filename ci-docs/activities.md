---
title: Asiakkaan tai työyhteyshenkilön aktiviteetit
description: Määritä asiakkaan tai työyhteyshenkilön aktiviteetit ja tarkastele niitä asiakasprofiilien aikajanalla.
ms.date: 10/26/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: srivas15
ms.author: shsri
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: d8caa477278f04c3a0a95ced15f4bea2a22aa8cd
ms.sourcegitcommit: da6a2d189edacc8f2c0f2abedcb28245f26fe74c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/27/2022
ms.locfileid: "9723777"
---
# <a name="customer-or-business-contact-activities"></a>Asiakkaan tai työyhteyshenkilön aktiviteetit

Asiakasaktiviteetit ovat asiakkaiden tai työyhteyshenkilöiden suorittamia toimintoja tai tapahtumia. Esimerkkejä aktiviteettitiedoista ovat tapahtumat, tukipuhelun kesto, verkkotarkastelut, ostot tai palautukset. Nämä aktiviteetit sisältyvät yhteen tai useampiin tietolähteisiin. Yhdistä Customers Insightsin avulla asiakasaktiviteetit näistä [tietolähteistä](data-sources.md) ja liitä ne asiakasprofiileihin. Nämä aktiviteetit näkyvät aikajärjestyksessä asiakasprofiilin aikajanalla. Sisällytä aikajana Dynamics 365 -sovelluksiin [Asiakaskortit-apuohjelmaratkaisun](customer-card-add-in.md) avulla.

## <a name="define-a-customer-activity"></a>Määritä asiakasaktiviteetti

Entiteetissä on oltava ainakin yksi määrite, jonka tyyppi on **Päivämäärä**, jotta se voidaan sisällyttää asiakkaan aikajanaa. **Lisää aktiviteetti** -ohjausobjekti poistetaan käytöstä, jos kyseistä entiteettiä ei löydy.

1. Siirry kohtaan **Tiedot** > **Aktiviteetit**.

1. Valitse **Lisää aktiviteetti** aloittaaksesi ohjatun kokemuksen.

1. Kirjoita **Aktiviteettitiedot**-toiminnossa seuraavat tiedot:

   - **Aktiviteetin nimi**: Valitse aktiviteetille nimi.
   - **Activity entity**: valitse tapahtuma- tai aktiviteettitietoja sisältävä entiteetti.
   - **Perusavain**: Valitse kenttä, joka yksilöi tietueen. Siinä ei saa olla arvojen kaksoiskappaleita, tyhjiä arvoja eikä puuttuvia arvoja.

     > [!NOTE]
     > Kunkin rivin perusavaimen on pysyttävä yhtenäisenä tietolähteen päivityksissä. Jos rivin perusavain päivitetään tietolähteessä, se luo kaksoiskappaleet tulosaktiviteettientiteettiin. 

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Määritä aktiviteettitiedot: nimi, entiteetti ja perusavain.":::

1. Valitse **Seuraava**.

1. Valitse **Suhde**-vaiheessa **Lisää suhde**, jonka avulla aktiviteetin tiedot yhdistetään vastaavaan asiakastietueeseen. Tässä vaiheessa visualisoidaan entiteettien väliset yhteydet.  

   - **Viiteavain**: Aktiviteettientiteetin viitekenttä, jonka avulla luodaan suhde toiseen entiteettiin.
   - **Vastaanottajaentiteetin nimi**: Vastaava lähdeasiakasentiteetti, johon aktiviteettientiteetti on suhteessa. Voit liittää tietoja vain lähdeasiakasentiteetteihin, joita käytetään tietojen yhdistämisprosessissa.
   - **Suhteen nimi**: Jos tämän aktiviteettikohteen ja valitun lähdeasiakasentiteetin välinen suhde on jo olemassa, suhteen nimi on vain luku -tilassa. Jos tällaista suhdetta ei ole, luodaan uusi suhde. Sen nimeksi tulee tähän ruutuun määritetty nimi.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Entiteettisuhteen määrittäminen.":::

   > [!TIP]
   > Yritystenvälisessä ympäristöissä voi valita tilientiteettien ja muiden entiteettien välillä. Jos valitset tilientiteetin, suhteen polku määritetään automaattisesti. Muiden entiteettien suhteen polku on määritettävä vähintään yhden keskitason entiteetin päälle, kunnes asiakasentiteetti tavoitetaan.

1. Valitse **Käytä** luodaksesi suhteen.

1. Valitse **Seuraava**.

1. Valitse **Aktiviteetin yhdistäminen** -vaiheessa aktiviteettitapahtuma ja aktiviteetin aloitusaika.
   - **Pakolliset kentät**
      - **Tapahtuma-aktiviteetti**: kenttä, joka on tämän aktiviteetin tapahtuma.
      - **Aikaleima**: Kenttä, joka edustaa aktiviteetin aloitusaikaa.

   - **Valinnaiset kentät**
      - **Lisätietoja**: Kenttä, jossa on tähän aktiviteettiin liittyviä tietoja.
      - **Kuvake**: kuvake, joka parhaiten edustaa tätä aktiviteettityyppiä.
      - **WWW-osoite**: Kenttä, joka sisältää tätä aktiviteettia koskevat tiedot sisältävän URL-osoitteen. Esimerkiksi tapahtumajärjestelmä, joka on tämän aktiviteetin aiheuttaja. Tämä URL-osoite voi olla mikä tahansa tietolähteen kenttä, tai se voidaan muodostaa uutena kenttänä Power Query -muunnosta käyttämällä. URL-osoitteen tiedot tallennetaan *Yhdistetty aktiviteetti* -entiteettiin, jota voidaan käyttää [ohjelmointirajapintojen](apis.md) käytön jälkeen.

   - **Näytä aikajanalla**
      - Valitse näytetäänkö tämä tapahtuma asiakasprofiilien aikajananäkymässä. Valitse **Kyllä**, jos haluat, että aktiviteetti näkyy aikajanalla tai **Ei**, jos haluat piilottaa sen.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Määritä asiakasaktiviteetin tiedot Yhdistetty aktiviteetti -entiteetissä.":::

1. Valitse aktiviteetin tyyppi valitsemalla **Seuraava** tai valitsemalla **Viimeistele ja tarkista**, kun aktiviteettityypiksi on määritetty **Muu**.

1. Valitse **Aktiviteettityyppi**-vaiheessa aktiviteetin tyyppi ja valitse tarvittaessa, haluatko yhdistää jotkin aktiviteettityypit semanttisesti käytettäväksi muissa Customer Insights -alueissa. *Palaute*-, *Uskollisuus*-, *SalesOrder*-, *SalesOrderLine* ja *Tilaus*-aktiviteettityyppi tukevat tällä hetkellä semantiikkaa sen jälkeen, kun kenttien yhdistämisen on hyväksytty. Jos aktiviteettityypillä ei ole merkitystä uudelle aktiviteetille, voit valita mukautetulle aktiviteettityypille *Muu* tai *Luo uusi*.

1. Valitse **Seuraava**.

1. Tarkista valinnat **Tarkista**-vaiheessa. Palaa mihin tahansa edellä esitettyyn vaiheeseen ja päivitä tiedot tarvittaessa.

1. Valitse **Tallenna aktiviteetti**, jos haluat ottaa muutokset käyttöön ja palata kohtaan **Tiedot** > **Aktiviteetit** valitsemalla **Valmis**. Luotu aktiviteetti tulee näkyviin.

1. Kun olet luonut kaikki aktiviteetit, voit käsitellä ne valitsemalla **Suorita**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-customer-activities"></a>Aiemmin luotujen asiakasaktiviteettien hallinta

Siirry kohtaan **Tieto** > **Aktiviteetit**, kun haluat tarkastella tallennettuja aktiviteettejasi, niiden lähde-entiteettiä ja aktiviteettityyppiä ja sitä, sisältyvätkö ne asiakkaan aikajanalle. Aktiviteettiluetteloa voi lajitella minkä tahansa sarakkeen perustella. Hallittavan aktiviteetin voi etsiä myös hakuruutua käyttämällä.

Voit tarkastella käytettävissä olevia toimintoja valitsemalla aktiviteetin.

- **Muokkaa** aktiviteettia, jos haluat muuttaa sen määritystä. Määritys avaa arvosteluvaiheen. Kun olet muuttanut kokoonpanoa, valitse **Tallenna aktiviteetti** ja käsittele sitten muutokset valitsemalla **Suorita**.
- **Nimeä aktiviteetti uudelleen**. Ota muutokset käyttöön valitsemalla **Tallenna**.
- **Poista** aktiviteetti. Voit poistaa useita aktiviteetteja kerralla valitsemalla aktiviteetit ja valitsemalla sitten **poistokuvakkeen**. Vahvista poisto.

## <a name="view-activity-timelines-on-customer-profiles"></a>Aktiviteettien aikajanan tarkasteleminen asiakasprofiileissa

1. Jos valitsit **Näytä aktiviteettien aikajanalla** aktiviteetin määrityksessä, siirry kohtaan **Asiakkaat** ja valitse asiakasprofiili, jotta voit nähdä asiakkaasi aktiviteetit **Aktiviteetin aikajana** -osiossa.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Näytä määritetyt aktiviteetit asiakasprofiileissa.":::

1. Aktiviteettien suodattaminen aikajanalla:

   - Voit valita yhden aktiviteettikuvakkeen tai useita aktiviteettikuvakkeita, jos haluat tarkentaa tuloksia niin, että ne sisältävät vain valitut tyypit.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Suodata aktiviteetit tyypin mukaan kuvakkeiden avulla.":::

   - Valitset kohta **Suodatin**, jotta voit avata suodatinpaneelin ja määrittää aikajanasuodattimet. Voit suodattaa *Aktiviteetin tyypin* ja/tai *Päivämäärän* mukaan. Valitse **Käytä**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Määritä suodatusehdot suodatinpaneelin avulla.":::

> [!NOTE]
> Aktiviteettisuodattimet poistetaan, kun lähdet asiakasprofiilista. Ne on otettava käyttöön aina, kun avaat asiakasprofiilin.

## <a name="define-a-contact-activity"></a>Määritä yhteyshenkilöaktiviteetti

Yritystileille (B2B) yhteyshenkilöiden aktiviteetit voi siepata *ContactProfile*-entiteetin avulla. Näet tilin aktiviteetin aikajanalla sen yhteyshenkilön, joka oli vastuussa kustakin aktiviteetista. Useimmat vaiheet noudattavat asiakasaktiviteettien yhdistämismääritystä.

   > [!NOTE]
   > Yhteyshenkilötason aktiviteetin määrittämiseksi on luotava *ContactProfile*-entiteetti joko [yhtenäisenä yhteyshenkilöprofiilina ](data-unification-contacts.md)tai [semanttisen yhdistämismäärityksen](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping) kautta.
   >
   > Aktiviteettitietojen jokaiselle tietueelle on oltava sekä **AccountID**- että **ContactID**-määritteet.
  
1. Siirry kohtaan **Tiedot** > **Aktiviteetit**.

1. Valitse **Lisää aktiviteetti**.

1. Kirjoita **Aktiviteettitiedot**-toiminnossa seuraavat tiedot:

   - **Aktiviteetin nimi**: Valitse aktiviteetille nimi.
   - **Activity entity**: valitse tapahtuma- tai aktiviteettitietoja sisältävä entiteetti.
   - **Perusavain**: Valitse kenttä, joka yksilöi tietueen. Siinä ei saa olla arvojen kaksoiskappaleita, tyhjiä arvoja eikä puuttuvia arvoja.

     > [!NOTE]
     > Kunkin rivin perusavaimen on pysyttävä yhtenäisenä tietolähteen päivityksissä. Jos rivin perusavain päivitetään tietolähteessä, se luo kaksoiskappaleet tulosaktiviteettientiteettiin. 


1. Luo **Suhteet**-vaiheessa epäsuora suhde aktiviteetin lähdetietojen ja asiakkaiden välille käyttämällä yhteyshenkilötietojasi välittävänä entiteettinä. Lisätietoja löytyy kohdasta [suorat ja epäsuorat suhdepolut](relationships.md#relationship-paths).
   - Esimerkkinä *Ostot*-nimisen aktiviteetin suhde:
      - **Ostojen lähdeaktiviteettitiedot** > **Yhteyshenkilötiedot** määritteessä **ContactID**
      - **Yhteyshenkilön tiedot** > **Asiakkaan tiedot** määritteessä **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Esimerkki suhteen määrityksestä.":::

1. Kun olet määrittänyt suhteet, valitse **Seuraava** ja viimeistele aktiviteettien yhdistämismääritykset. Aktiviteettien luonnin yksityiskohtaiset vaiheet ovat ohjeaiheessa [asiakasaktiviteetin määritteleminen](#define-a-customer-activity).

1. Suorita aktiviteettien yhdistämismääritykset.

1. Yhteyshenkilötason aktiviteettisi näkyvät nyt asiakkaan aikajanalla.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Lopullinen tulos yhteyshenkilöaktiviteettien määrittämisen jälkeen":::

## <a name="contact-level-activity-timeline-filtering"></a>Yhteyshenkilötason aktiviteettiaikajanan suodatus

Kun olet määrittänyt yhteyshenkilötason aktiviteettien yhdistämismäärityksen ja suorittanut sen, asiakkaiden aktiviteettiaikajana päivittyy. Se sisältää yhteyshenkilöiden tunnukset tai nimet *ContactProfile*-määritysten mukaisesti aktiviteetteja varten, joissa he ovat toimineet. Voit suodattaa aktiviteetteja aikajanan yhteyshenkilöiden mukaan nähdäksesi tietyt yhteyshenkilöt, joista olet kiinnostunut. Voit myös tarkastella kaikkia aktiviteetteja, joita ei ole delegoitu tietylle yhteyshenkilölle, valitsemalla **Aktiviteetit, joita ei ole yhdistetty yhteyshenkilöön.**

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Yhteyshenkilötason aktiviteetteja varten käytettävissä olevat suodatusvaihtoehdot.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
