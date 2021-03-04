---
title: Asiakasaktiviteetit
description: Asiakasaktiviteettien määrittäminen ja niiden näyttäminen asiakkaan aikajanalla.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267428"
---
# <a name="customer-activities"></a>Asiakasaktiviteetit

Yhdistämällä asiakasaktiviteetteja Dynamics 365 Customer Insightsin [eri tietolähteistä](data-sources.md) voidaan luoda asiakkaan aikajana, jolla aktiviteetit ovat kronologisessa järjestyksessä. Voit sisällyttää aikajanan Dynamics 365:n asiakkaan osallistamissovelluksiin [asiakaskortin apuohjelmalla](customer-card-add-in.md) tai Power BI -koontinäytön avulla.

## <a name="define-an-activity"></a>Aktiviteetin määrittäminen

Tietolähteet sisältävät entiteettejä, joissa on tapahtuma- ja aktiviteettitietoja useita tietolähteistä. Määritä, mitä nämä entiteetit ovat, ja valitse aktiviteetit, joita haluat tarkastella asiakkaan aikajanalla. Valitse entiteetti, joka sisältää kohdeaktiviteetit.

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Aktiviteetit**.

1. Valitse **Lisää aktiviteetti**.

   > [!NOTE]
   > Entiteetissä on oltava ainakin yksi määrite, jonka tyyppi on **Päivämäärä**, jotta se voidaan sisällyttää asiakkaan aikajanaa, eikä entiteettejä, joissa ei ole **Päivämäärä**-kenttiä, voi lisätä. **Lisää aktiviteetti** -ohjausobjekti poistetaan käytöstä, jos kyseistä entiteettiä ei löydy.

1. Määritä **Lisää aktiviteetti** -ruudussa seuraavien kenttien arvot:

   - **Entiteetti**: valitse tapahtuma-tai aktiviteettitietoja sisältävä entiteetti.
   - **Perusavain**: Valitse kenttä, joka yksilöi tietueen. Siinä ei saa olla arvojen kaksoiskappaleita, tyhjiä arvoja eikä puuttuvia arvoja.
   - **Aikaleima**: valitse kenttä, joka ilmaisee aktiviteetin aloitusajan.
   - **Tapahtuma**: valitse kenttä, joka on aktiviteetin tapahtuma.
   - **WWW-osoite**: Valitse kenttä, joka kuvaa URL-osoitetta ja sisältää tämän aktiviteetin lisätiedot. Esimerkiksi tapahtumajärjestelmä, joka on tämän aktiviteetin aiheuttaja. Tämä URL-osoite voi olla mikä tahansa tietolähteen kenttä, tai se voidaan muodostaa uutena kenttänä käyttämällä Power Query -muunnosta. Nämä URL-tiedot tallennetaan Unified Activity -kohteeseen, joka voidaan käyttää siirtämällä palvelimelta ohjelmointirajapintojen avulla.
   - **Tiedot**: vaihtoehtoisesti voit valita lisätietoja varten lisättävän kentän.
   - **Kuvake**: vaihtoehtoisesti voit valita tämän aktiviteetin ilmaisevan kuvakkeen.
   - **Aktiviteetin tyyppi**: Määritä sellainen aktiviteetin tyypin viittaus Common Data Modeliin, joka parhaiten kuvaa aktiviteetin semanttista määritelmää.

1. Määritä **Määritä suhde** -osassa tiedot, jotka yhdistävät aktiviteettitiedot vastaavaan asiakkaaseen.

    - **Aktiviteetin entiteettikenttä**: Valitse aktiviteettikohteen kenttä, jonka avulla luodaan suhde toiseen entiteettiin.
    - **Asiakasentiteetti**: Valitse vastaava lähdeasiakas-entiteetti, johon aktiviteettikohde on suhteessa. Voit liittyä vain sellaisiin lähdeasiakaskohteisiin, joita käytetään tietojen yhdistämisprosessissa.
    - **Asiakkaan entiteettikenttä**: Tässä kentässä näkyy lähdeasiakasentiteetin ensisijainen avain, joka on valittu yhdistämisprosessissa. Tämän lähdeasiakaskohteen perusavainkentän avulla luodaan suhde aktiviteettientiteettiin.
    - **Nimi**: Jos tämän aktiviteettikohteen ja valitun lähdeasiakasentiteetin välinen suhde on jo olemassa, suhteen nimi on vain luku -tilassa. Jos tällaista suhdetta ei ole olemassa, luodaan uusi suhde, jolla on tässä annettu nimi.
   
   > [!div class="mx-imgBorder"]
   > ![Entiteettisuhteen määrittäminen](media/activities-entities-define.png "Entiteettisuhteen määrittäminen")

1. Ota muutokset käyttöön valitsemalla **Tallenna**.

1. Valitse **Aktiviteetit**-sivulla **Suorita**.

> [!TIP]
> Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types). Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies). Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja. Kun työn jossakin tehtävissä on valittu **Näytä tiedot**, saat lisätietoja: käsittelyajan, viimeisimmän käsittelypäivämäärän sekä kaikki tehtävään liitetyt virheet ja varoitukset.

## <a name="edit-an-activity"></a>Aktiviteetin muokkaaminen

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Aktiviteetit**.

2. Valitse aktiviteettientiteetti, jota haluat muokata ja valitse **Muokkaa**. Voit myös siirtää kohdistimen entiteettirivin kohdalle ja valita **Muokkaa**-kuvakkeen.

3. Napsauta **Muokkaa**-kuvaketta.

4. Päivitä **Muokkaa aktiviteettia** -ruudussa arvot ja valitse **Tallenna**.

5. Valitse **Aktiviteetit**-sivulla **Suorita**.

## <a name="delete-an-activity"></a>Aktiviteetin poistaminen

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Aktiviteetit**.

2. Valitse aktiviteettientiteetti, jonka haluat poistaa ja valitse **Poista**. Voit myös siirtää kohdistimen entiteettirivin kohdalle ja valita **Poista**-kuvakkeen. Voit myös valita useita aktiviteettikohteita poistettavaksi kerralla.
   > [!div class="mx-imgBorder"]
   > ![Muokkaa tai poista entiteettisuhde](media/activities-entities-edit-delete.png "Muokkaa tai poista entiteettisuhde").

3. Valitse **Poista**-kuvake.

4. Vahvista poisto.


[!INCLUDE[footer-include](../includes/footer-banner.md)]