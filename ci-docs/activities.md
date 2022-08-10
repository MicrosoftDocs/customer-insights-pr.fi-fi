---
title: Asiakasaktiviteetit
description: Määritä asiakasaktiviteetit ja tarkastele niitä asiakasprofiilien aikajanalla.
ms.date: 07/22/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188135"
---
# <a name="customer-activities"></a>Asiakasaktiviteetit

Asiakasaktiviteetit ovat asiakkaiden suorittamia toimintoja tai tapahtumia. Esimerkkejä aktiviteettitiedoista ovat tapahtumat, tukipuhelun kesto, verkkotarkastelut, ostot tai palautukset. Nämä aktiviteetit sisältyvät yhteen tai useampiin tietolähteisiin. Yhdistä Customers Insightsin avulla asiakasaktiviteetit näistä [tietolähteistä](data-sources.md) ja liitä ne asiakasprofiileihin. Nämä aktiviteetit näkyvät aikajärjestyksessä asiakasprofiilin aikajanalla. Sisällytä aikajana Dynamics 365 -sovelluksiin [Asiakaskortit-apuohjelmaratkaisun](customer-card-add-in.md) avulla.

## <a name="define-an-activity"></a>Aktiviteetin määrittäminen

Entiteetissä on oltava ainakin yksi määrite, jonka tyyppi on **Päivämäärä**, jotta se voidaan sisällyttää asiakkaan aikajanaa. **Lisää aktiviteetti** -ohjausobjekti poistetaan käytöstä, jos kyseistä entiteettiä ei löydy.

1. Siirry kohtaan **Tiedot** > **Aktiviteetit**.

1. Valitse **Lisää aktiviteetti** aloittaaksesi ohjatun kokemuksen.

1. Kirjoita **Aktiviteettitiedot**-toiminnossa seuraavat tiedot:

   - **Aktiviteetin nimi**: Valitse aktiviteetille nimi.
   - **Aktiviteetin entiteetti**: valitse tapahtuma-tai aktiviteettitietoja sisältävä entiteetti.
   - **Perusavain**: Valitse kenttä, joka yksilöi tietueen. Siinä ei saa olla arvojen kaksoiskappaleita, tyhjiä arvoja eikä puuttuvia arvoja.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Määritä aktiviteettitiedot: nimi, entiteetti ja perusavain.":::

1. Valitse **Seuraava**.

1. Valitse **Suhde**-vaiheessa **Lisää suhde**, jonka avulla aktiviteetin tiedot yhdistetään vastaavaan asiakastietueeseen. Tässä vaiheessa visualisoidaan entiteettien väliset yhteydet.  

   - **Entiteetin viiteavain**: Aktiviteettientiteetin viitekenttä, jonka avulla luodaan suhde toiseen entiteettiin.
   - **Vastaanottajaentiteetin nimi**: Vastaava lähdeasiakasentiteetti, johon aktiviteettientiteetti on suhteessa. Voit liittää tietoja vain lähdeasiakasentiteetteihin, joita käytetään tietojen yhdistämisprosessissa.
   - **Suhteen nimi**: entiteettien välisen suhteen osoittava nimi. Jos tämän aktiviteettientiteetin ja valitun lähdeasiakasentiteetin välinen suhde on jo olemassa, suhteen nimi on vain luku -tilassa.

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

## <a name="manage-existing-activities"></a>Aiemmin luotujen aktiviteettien hallinta

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

1. Voit poistaa suodattimia valitsemalla **Poista suodattimet** tai valitsemalla **Suodata** ja poistamalla suodattimen valintaruudun valinta.

> [!NOTE]
> Aktiviteettisuodattimet poistetaan, kun lähdet asiakasprofiilista. Ne on otettava käyttöön aina, kun avaat asiakasprofiilin.

[!INCLUDE [footer-include](includes/footer-banner.md)]
