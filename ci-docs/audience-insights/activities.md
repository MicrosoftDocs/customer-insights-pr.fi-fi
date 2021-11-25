---
title: Asiakasaktiviteetit
description: Määritä asiakasaktiviteetit ja tarkastele niitä asiakasprofiilien aikajanalla.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c99ec2e7d5e4bf32a509bbe4c0c53999129b2305
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732442"
---
# <a name="customer-activities"></a>Asiakasaktiviteetit

Yhdistämällä [eri tietolähteiden](data-sources.md) asiakasaktiviteetteja Dynamics 365 Customer Insightsissa voit luoda aikajanan, jossa aktiviteetit näkyvät aikajärjestyksessä. Sisällytä aikajana Dynamics 365 -sovelluksiin [Asiakaskortin-apuohjelma](customer-card-add-in.md) -ratkaisulla tai Power BI -koontinäytön avulla.

## <a name="define-an-activity"></a>Aktiviteetin määrittäminen

Tietolähteet voivat sisältää entiteettejä, joissa on tapahtuma- ja aktiviteettitietoja useita tietolähteistä. Määritä, mitä nämä entiteetit ovat, ja valitse aktiviteetit, joita haluat tarkastella asiakkaan aikajanalla. Valitse entiteetti, joka sisältää kohdeaktiviteetit.

Entiteetissä on oltava ainakin yksi määrite, jonka tyyppi on **Päivämäärä**, jotta se voidaan sisällyttää asiakkaan aikajanaa, eikä entiteettejä, joissa ei ole **Päivämäärä**-kenttiä, voi lisätä. **Lisää aktiviteetti** -ohjausobjekti poistetaan käytöstä, jos kyseistä entiteettiä ei löydy.

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Aktiviteetit**.

1. Valitse **Lisää aktiviteetti**, jos haluat aloittaa ohjatun käyttökokemuksen aktiviteetin määritysprosessille.

1. Määritä **Aktiviteettitiedot**-vaiheessa seuraavien kenttien arvot:

   - **Aktiviteetin nimi**: Valitse aktiviteetille nimi.
   - **Entiteetti**: valitse tapahtuma-tai aktiviteettitietoja sisältävä entiteetti.
   - **Perusavain**: Valitse kenttä, joka yksilöi tietueen. Siinä ei saa olla arvojen kaksoiskappaleita, tyhjiä arvoja eikä puuttuvia arvoja.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Määritä aktiviteettitiedot: nimi, entiteetti ja perusavain.":::

1. Siirry seuraavaan vaiheeseen valitsemalla **Seuraava**.

1. Määritä **Suhde**-vaiheessa tiedot, joiden avulla aktiviteetin tiedot yhdistetään vastaavaan asiakastietueeseen. Tässä vaiheessa visualisoidaan entiteettien väliset yhteydet.  

   - **Ensimmäinen**: Aktiviteettientiteetin viitekenttä, jonka avulla luodaan suhde toiseen entiteettiin.
   - **Toinen**: Vastaava lähdeasiakasentiteetti, johon aktiviteettientiteetti on suhteessa. Voit liittää tietoja vain lähdeasiakasentiteetteihin, joita käytetään tietojen yhdistämisprosessissa.
   - **Kolmas**: Jos tämän aktiviteettientiteetin ja valitun lähdeasiakasentiteetin välinen suhde on jo olemassa, suhteen nimi on vain luku -tilassa. Jos tällaista suhdetta ei ole, luodaan uusi suhde. Sen nimeksi tulee tähän ruutuun määritetty nimi.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Entiteettisuhteen määrittäminen.":::

   > [!TIP]
   > Yritystenvälisessä ympäristöissä voi valita tilientiteettien ja muiden entiteettien välillä. Jos valitset tilientiteetin, suhteen polku määritetään automaattisesti. Muiden entiteettien suhteen polku on määritettävä vähintään yhden keskitason entiteetin päälle, kunnes asiakasentiteetti tavoitetaan.

1. Siirry seuraavaan vaiheeseen valitsemalla **Seuraava**. 

1. Valitse **Aktiviteetin yhdistäminen** -vaiheessa aktiviteettitapahtuma ja aktiviteetin aloitusaika. 
   - **Pakolliset kentät**
      - **Tapahtuma-aktiviteetti**: kenttä, joka on tämän aktiviteetin tapahtuma.
      - **Aikaleima**: Kenttä, joka edustaa aktiviteetin aloitusaikaa.

   - **Valinnaiset kentät**
      - **Lisätietoja**: Kenttä, jossa on tähän aktiviteettiin liittyviä tietoja.
      - **Kuvake**: kuvake, joka parhaiten edustaa tätä aktiviteettityyppiä.
      - **WWW-osoite**: Kenttä, joka sisältää tätä aktiviteettia koskevat tiedot sisältävän URL-osoitteen. Esimerkiksi tapahtumajärjestelmä, joka on tämän aktiviteetin aiheuttaja. Tämä URL-osoite voi olla mikä tahansa tietolähteen kenttä, tai se voidaan muodostaa uutena kenttänä käyttämällä Power Query -muunnosta. URL-osoitteen tiedot tallennetaan *Yhdistetty aktiviteetti* -entiteettiin, jota voidaan käyttää [ohjelmointirajapintojen](apis.md) käytön jälkeen.

   - **Näytä aikajanalla**
      - Valitse näytetäänkö tämä tapahtuma asiakasprofiilien aikajananäkymässä. Valitse **Kyllä**, jos haluat, että aktiviteetti näkyy aikajanalla tai **Ei**, jos haluat piilottaa sen.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Määritä asiakasaktiviteetin tiedot Yhdistetty aktiviteetti -entiteetissä.":::

1. Siirry seuraavaan vaiheeseen valitsemalla **Seuraava**. Voit tallentaa aktiviteetin nyt valitsemalla **Viimeistele ja tarkista**, kun aktiviteettityypiksi on määritetty **Muu**. 

1. Valitse **Aktiviteettityyppi**-vaiheessa aktiviteetin tyyppi ja valitse tarvittaessa, haluatko yhdistää jotkin aktiviteettityypit semanttisesti käytettäväksi muissa Customer Insights -alueissa. Tällä hetkellä *Palaute*-, *Uskollisuus*-, *Myyntitilaus*-, *Myyntitilausrivi*-, and *Tilaus*-aktiviteettityypit voidaan yhdistää semanttisesti sen jälkeen, kun on tehty päätös kenttien yhdistämisestä. Jos aktiviteettityypillä ei ole merkitystä uudelle aktiviteetille, voit valita mukautetulle aktiviteettityypille *Muu* tai *Luo uusi*.

1. Siirry seuraavaan vaiheeseen valitsemalla **Seuraava**. 

1. Tarkista valinnat **Tarkista**-vaiheessa. Palaa mihin tahansa edellä esitettyyn vaiheeseen ja päivitä tiedot tarvittaessa.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Tarkista aktiviteetin määritetyt kentät.":::
   
1. Valitse **Tallenna aktiviteetti**, jos haluat ottaa muutokset käyttöön ja palata kohtaan **Tiedot** > **Aktiviteetit** valitsemalla **Valmis**. Tässä näet aikajanalla näytettävät aktiviteetit. 

1. Käsittele aktiviteetti valitsemalla **Aktiviteetit**-sivulla **Suorita**. 

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Aiemmin luotujen aktiviteettien hallinta

Kohdassa **Tiedot** > **Aktiviteetit** voit tarkastella kaikkia tallennettuja aktiviteetteja ja hallita niitä. Kutakin aktiviteettia edustaa rivi, joka sisältää myös lähdettä, entiteettiä ja aktiviteettityyppiä koskevat tiedot.

Seuraavat toiminnot ovat käytettävissä, kun valitset aktiviteetin. 

- **Muokkaa**: avaa aktiviteettiasetukset tarkistusvaiheessa. Voit muuttaa mitä tahansa tai kaikkia nykyisiä määrityksiä tässä vaiheessa. Kun olet muuttanut kokoonpanoa, valitse **Tallenna aktiviteetti** ja käsittele sitten muutokset valitsemalla **Suorita**.

- **Nimeä uudelleen**: Avaa valintaikkunan, jossa voit syöttää valitulle aktiviteetille eri nimen. Ota muutokset käyttöön valitsemalla **Tallenna**.

- **Poista**: avaa dialogin, joka vahvistaa valitun aktiviteetin poistamisen. Voit myös poistaa useita aktiviteetteja kerralla valitsemalla aktiviteetit ja valitsemalla sitten poistokuvakkeen. Vahvista poisto valitsemalla **Poista**.

## <a name="view-activity-timelines-on-customer-profiles"></a>Aktiviteettien aikajanan tarkasteleminen asiakasprofiileissa

Kun olet määrittänyt asiakasaktiviteetit, valitse **Näytä aktiviteettien aikajanalla** aktiviteetin määrityksessä, jotta voit nähdä asiakkaasi kaikki aktiviteetit asiakasprofiilissa.

Jos haluat nähdä asiakkaan aikajanan, siirry kohtaan **Asiakkaat** ja valitse asiakasprofiili, jota haluat tarkastella.

Jos asiakas on osallistunut aktiviteettiin, jonka olet määrittänyt, löydät sen **Aktivitieettien aikajana** -osasta.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Näytä määritetyt aktiviteetit asiakasprofiileissa.":::

Aktiviteettien aikajanalla voi suodattaa aktiviteetteja useilla tavoilla:

- Voit valita yhden aktiviteettikuvakkeen tai useita aktiviteettikuvakkeita, jos haluat tarkentaa tuloksia niin, että ne sisältävät vain valitut tyypit.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Suodata aktiviteetit tyypin mukaan kuvakkeiden avulla.":::

- Voit valita kohdan **Suodatin**, jotta voit avata suodatinpaneelin ja määrittää aikajanasuodattimet.

   1. Voit suodattaa *Aktiviteetin tyypin* ja *Päivämäärän* mukaan.
   1. Valitse **Käytä** käyttääksesi suodattimia aktiviteettiaikajanalla.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Määritä suodatusehdot suodatinpaneelin avulla.":::

Jos haluat poistaa suodattimet, valitse **x** jokaisen aikajanaan sovelletun suodattimen vierestä tai valitse **Poista suodattimet**.


> [!NOTE]
> Aktiviteettisuodattimet poistetaan, kun lähdet asiakasprofiilista. Ne on otettava käyttöön aina, kun avaat asiakasprofiilin.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
