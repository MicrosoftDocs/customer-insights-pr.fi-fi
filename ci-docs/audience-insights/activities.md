---
title: Asiakasaktiviteetit
description: Asiakasaktiviteettien määrittäminen ja niiden näyttäminen asiakkaan aikajanalla.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866403"
---
# <a name="customer-activities"></a>Asiakasaktiviteetit

Yhdistämällä [eri tietolähteiden](data-sources.md) asiakasaktiviteetteja Dynamics 365 Customer Insightsissa voit luoda aikajanan, jossa aktiviteetit näkyvät aikajärjestyksessä. Sisällytä aikajana Dynamics 365 -sovelluksiin [Asiakaskortin-apuohjelma](customer-card-add-in.md) -ratkaisulla tai Power BI -koontinäytön avulla.

## <a name="define-an-activity"></a>Aktiviteetin määrittäminen

Tietolähteet voivat sisältää entiteettejä, joissa on tapahtuma- ja aktiviteettitietoja useita tietolähteistä. Määritä, mitä nämä entiteetit ovat, ja valitse aktiviteetit, joita haluat tarkastella asiakkaan aikajanalla. Valitse entiteetti, joka sisältää kohdeaktiviteetit.

> [!NOTE]
> Entiteetissä on oltava ainakin yksi määrite, jonka tyyppi on **Päivämäärä**, jotta se voidaan sisällyttää asiakkaan aikajanaa, eikä entiteettejä, joissa ei ole **Päivämäärä**-kenttiä, voi lisätä. **Lisää aktiviteetti** -ohjausobjekti poistetaan käytöstä, jos kyseistä entiteettiä ei löydy.

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Aktiviteetit**.

1. Valitse **Lisää aktiviteetti**, jos haluat aloittaa ohjatun käyttökokemuksen aktiviteetin määritysprosessille.

1. Määritä **Aktiviteettitiedot**-vaiheessa seuraavien kenttien arvot:

   - **Aktiviteetin nimi**: Valitse aktiviteetille nimi.
   - **Entiteetti**: valitse tapahtuma-tai aktiviteettitietoja sisältävä entiteetti.
   - **Perusavain**: Valitse kenttä, joka yksilöi tietueen. Siinä ei saa olla arvojen kaksoiskappaleita, tyhjiä arvoja eikä puuttuvia arvoja.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Määritä aktiviteettitiedot: nimi, entiteetti ja perusavain.":::

1. Siirry seuraavaan vaiheeseen valitsemalla **Seuraava**.

1. Määritä **Suhde**-vaiheessa tiedot, jotka yhdistät aktiviteettitiedot vastaavaan asiakkaaseen. Tässä vaiheessa visualisoidaan entiteettien väliset yhteydet.  

   - **Ensimmäinen**: Aktiviteettientiteetin viitekenttä, jonka avulla luodaan suhde toiseen entiteettiin.
   - **Toinen**: Vastaava lähdeasiakasentiteetti, johon aktiviteettientiteetti on suhteessa. Voit liittää tietoja vain lähdeasiakasentiteetteihin, joita käytetään tietojen yhdistämisprosessissa.
   - **Kolmas**: Jos tämän aktiviteettientiteetin ja valitun lähdeasiakasentiteetin välinen suhde on jo olemassa, suhteen nimi on vain luku -tilassa. Jos tällaista suhdetta ei ole, uusi suhde luodaan tässä ruudussa annettavalla nimellä.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Entiteettisuhteen määrittäminen.":::

1. Siirry seuraavaan vaiheeseen valitsemalla **Seuraava**. 

1. Valitse **Aktiviteetin yhdistäminen** -vaiheessa aktiviteettitapahtuma ja aktiviteetin aloitusaika. 
   - **Pakolliset kentät**
      1. **Tapahtuma-aktiviteetti**: kenttä, joka on tämän aktiviteetin tapahtuma
      2. **Aikaleima**: Kenttä, joka edustaa aktiviteetin aloitusaikaa.

   - **Valinnaiset kentät**
      1. **Lisätietoja**: Kenttä, jossa on tähän aktiviteettiin liittyviä tietoja.
      2. **Kuvake**: kuvake, joka parhaiten edustaa tätä aktiviteettityyppiä.
      3. **WWW-osoite**: Kenttä, joka sisältää tätä aktiviteettia koskevat tiedot sisältävän URL-osoitteen. Esimerkiksi tapahtumajärjestelmä, joka on tämän aktiviteetin aiheuttaja. Tämä URL-osoite voi olla mikä tahansa tietolähteen kenttä, tai se voidaan muodostaa uutena kenttänä käyttämällä Power Query -muunnosta. URL-osoitteen tiedot tallennetaan *Yhdistetty aktiviteetti* -entiteettiin, jota voidaan käyttää [ohjelmointirajapintojen](apis.md) käytön jälkeen.
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Määritä asiakasaktiviteetin tiedot Yhdistetty aktiviteetti -entiteetissä.":::

1. Siirry seuraavaan vaiheeseen valitsemalla **Seuraava**. Voit tallentaa aktiviteetin nyt valitsemalla **Viimeistele ja tarkista**, kun aktiviteettityypiksi on määritetty **Muu**. 

1. Valitse **Aktiviteettityyppi**-vaiheessa aktiviteetin tyyppi ja valitse tarvittaessa, haluatko yhdistää jotkin aktiviteettityypit semanttisesti käytettäväksi muissa Customer Insights -alueissa. *Subscription* & *SalesOrderLine* -aktiviteettityypit voidaan tällä hetkellä yhdistää semanttisesti, kun kenttien yhdistämiseen suostutaan. Jos aktiviteettityypillä ei ole merkitystä uudelle aktiviteetille, voit valita mukautetulle aktiviteettityypille *Muu* tai *Luo uusi*.

1. Siirry seuraavaan vaiheeseen valitsemalla **Seuraava**. 

1. Tarkista valinnat **Tarkista**-vaiheessa. Voit palata mihin tahansa edellä kuvattuun vaiheeseen ja päivittää tiedot tarvittaessa.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Tarkista aktiviteetin määritetyt kentät.":::
   
1. Valitse **Tallenna aktiviteetti**, jos haluat ottaa muutokset käyttöön ja palata kohtaan **Tiedot** > **Aktiviteetit** valitsemalla **Valmis**. Tässä näet aikajanalla näytettävät aktiviteetit. 

1. Käsittele aktiviteetti valitsemalla **Aktiviteetit**-sivulla **Suorita**. 

> [!TIP]
> Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types). Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies). Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja. Kun työn jossakin tehtävissä on valittu **Näytä tiedot**, saat lisätietoja: käsittelyajan, viimeisimmän käsittelypäivämäärän sekä kaikki tehtävään liitetyt virheet ja varoitukset.


## <a name="manage-existing-activities"></a>Aiemmin luotujen aktiviteettien hallinta

Kohdassa **Tiedot** > **Aktiviteetit** voit tarkastella kaikkia tallennettuja aktiviteetteja ja hallita niitä. Kutakin aktiviteettia edustaa rivi, joka sisältää myös lähdettä, entiteettiä ja aktiviteettityyppiä koskevat tiedot.

Seuraavat toiminnot ovat käytettävissä, kun valitset aktiviteetin. 

- **Muokkaa**: avaa aktiviteettiasetukset tarkistusvaiheessa. Voit muuttaa mitä tahansa tai kaikkia nykyisiä määrityksiä tässä vaiheessa. Kun olet muuttanut kokoonpanoa, valitse **Tallenna aktiviteetti** ja käsittele sitten muutokset valitsemalla **Suorita**.

- **Nimeä uudelleen**: avaa dialogin, jossa voit kirjoittaa valitulle aktiviteetille toisen nimen. Ota muutokset käyttöön valitsemalla **Tallenna**.

- **Poista**: avaa dialogin, joka vahvistaa valitun aktiviteetin poistamisen. Voit myös poistaa useita aktiviteetteja kerralla valitsemalla aktiviteetit ja valitsemalla sitten poistokuvakkeen. Vahvista poisto valitsemalla **Poista**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
