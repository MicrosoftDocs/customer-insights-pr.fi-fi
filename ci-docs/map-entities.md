---
title: Entiteettien ja määritteiden yhdistäminen tietojen yhtenäistämistä varten
description: Valitse entiteetit, määritteet, perusavaimet ja semanttiset tyypit, joiden avulla tiedot voidaan yhdistää yhtenäiseen asiakasprofiiliin.
ms.date: 10/18/2020
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: bebc600e91db471c3cd50eccb5e42be309ff09c9
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646078"
---
# <a name="map-entities-and-attributes"></a>Entiteettien ja määritteiden yhdistäminen

**Kartta** on tietojen yhdistämisprosessin ensimmäinen vaihe. Yhdistäminen koostuu kolmesta vaiheesta:

- *Entiteetin valinta*: Määritä yhdisteltävät entiteetit, jotka muodostavat aiempaa täydellisemmän tietojoukon asiakkaiden tiedoista.
- *Määritteen valinta*: Määritä jokaiselle entiteetille sarakkeet, jotka haluat yhdistää, ja täsmäytä *vastaavuus*- ja *yhdistämisvaiheet*. Näitä sarakkeita kutsutaan *määritteiksi*.
- *Perusavaimen ja semanttisen tyypin valinta*: Määritä kullekin entiteetille määrite, jonka haluat määrittää entiteetin perusavaimeksi, ja määritä kullekin määritteelle semanttinen tyyppi, joka parhaiten kuvaa kyseistä määritettä.

Lisätietoja tietojen yhdistämisen yleisprosessista on kohdassa [Yhdistäminen](data-unification.md).

## <a name="select-the-first-entities"></a>Valitse ensimmäiset entiteetit

1. Valitse **Tiedot** > **Yhtenäistä** > **Määritä vastaavuus**.

2. Aloita yhdistämisvaihe valitsemalla **Valitse entiteettejä** -kohta.

3. Valitse entiteetit ja määritteet, joita haluat käyttää vaiheissa *vastaavuuksien etsiminen* ja *yhdistäminen*. Voit valita tarvittavat määritteet yksitellen entiteetistä tai lisätä kaikki entiteetin määritteet valitsemalla **Sisällytä kaikki kentät** -valintaruutu entiteettitasolla. Kannattaa valita ainakin kaksi entiteettiä, jotta tietojen yhdistämisprosessista on hyötyä.

   > [!div class="mx-imgBorder"]
   > ![Entiteettien lisääminen, esimerkki.](media/data-manager-configure-map-add-entities-example.png "Entiteettien lisääminen, esimerkki")

   Tässä esimerkissä lisätään entiteetit **eCommerceContacts** ja **loyCustomers**. Valitsemalla nämä entiteetit voit johtaa tietoja siitä, ketkä verkkoliiketoiminnan asiakkaista kuuluvat kanta-asiakasohjelman piiriin.
   
   Voit hakea avainsanoilla kaikista määritteistä ja entiteeteistä ja valita tarvittavat määritteet, jotka haluat yhdistää.
   
     > [!div class="mx-imgBorder"]
   > ![Esimerkki hakukentästä.](media/data-manager-configure-map-search-fields-example.png "Esimerkki hakukentästä")

4. Vahvista valintasi valitsemalla **Käytä**.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Valitse määritteille perusavain ja semanttinen tyyppi

Kun olet valinnut entiteetit, valitut entiteetit tulevat tarkasteltavaksi **Yhdistä**-sivulla. Määritä entiteetin perusavain ja määritä entiteetin määritteelle semanttinen tyyppi.

- **Perusavain**: Valitse jokaiselle entiteetille yksi määrite perusavaimeksi. Jotta määrite olisi kelvollinen perusavain, se ei saa sisältää arvojen kaksoiskappaleita, siitä ei saa puuttua arvoja eikä siinä saa olla tyhjiä arvoja. Merkkijonon, kokonaisluvun ja GUID-tunnusten tietotyyppimääritteitä tuetaan perusavaimina, ja ne näytetään kentässä, josta voit valita ne.

- **Määritteen semanttinen tyyppi**: Määritteiden luokat, kuten sähköpostiosoite tai nimi. Määritä **Älykäs yhdistämismääritys** -asetukseksi **Käytössä**, jos haluat käyttää semantiikan älykkääseen ennakointiin, ajan säästämiseen ja tarkkuuden parantamiseen tekoälymalleja. Älykäs yhdistämismääritys korostaa tekoälyyn perustuvat semanttiset suositukset **Tyyppi**-kentässä. Jos asetukseksi määritetään **Pois käytöstä**, tavalliset yhdistämismäärityssuositukset tulevat näkyviin. Voit valita minkä tahansa vaihtoehtoluettelossa olevan semanttisen tyypin ja ohittaa ehdotetun valinnan.

> [!div class="mx-imgBorder"]
> ![Määritetyyppi ja semanttinen ennuste.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Määritetyyppi ja semanttinen ennuste")

Myös mukautetun semantiikkatyypin voi lisätä. Valitse määritteen tyypin kenttä ja kirjoita mukautetun semanttisen tyypin nimi. Tällä tavoin voit myös vaihtaa määritetyyppejä, jotka järjestelmä on tunnistanut.

Kaikki määritteet, joiden semanttinen tyyppi tunnistetaan automaattisesti, kootaan **Tarkista yhdistetyt kentät** -osaan. Tarkista nämä määritteet ja niiden semanttiset tyypit, koska niitä käytetään entiteettien yhdistelemiseen tietojen yhtenäistämisen yhdistämisvaiheessa.

Määritteet, joita ei yhdistetä automaattisesti semanttiseen tyyppiin, kootaan **Määritä yhdistämättömien kenttien tiedot** -osaan. Valitse yhdistämättömien määritteiden semanttisen tyypin kenttä tai syötä mukautetun määritetyyppisi nimi.

> [!div class="mx-imgBorder"]
> ![Perusavain ja määritetyyppi.](media/data-manager-configure-map-add-attributes.png "Perusavain ja määritetyyppi")

> [!NOTE]
> Yhden kentän pitäisi yhdistyä semanttiseen tyyppiin Person.FullName, jotta asiakkaan nimi täytetään asiakaskortissa. Muussa tapauksessa asiakaskortit näkyvät nimettöminä. 

## <a name="add-and-remove-attributes-and-entities"></a>Määritteiden ja entiteettien lisääminen ja poistaminen

1. Valitse kohdassa **Yhtenäistä** > **Yhdistä** valinta **Muokkaa kenttiä**.

2. Lisää tai poista määritteitä ja entiteettejä **Muokkaa kenttiä** -ruudussa. Etsi ja valitse haluamasi määritteet ja entiteetit haun tai vierityksen avulla. Yhdistettyjä määritteitä tai entiteettejä ei voi poistaa.

   > [!div class="mx-imgBorder"]
   > ![Määritteiden lisääminen tai poistaminen.](media/configure-data-map-edit.png "Määritteiden lisääminen tai poistaminen")

3. Valitse **Käytä**.

## <a name="add-images-to-profiles"></a>Kuvien lisääminen profiileihin

Jos entiteetti sisältää URL-osoitteita julkisesti saatavilla oleviin profiilikuviin tai logoihin, voit lisätä ne yhdistettyyn asiakasprofiiliin.

Valitse entiteetti ja etsi kenttä, joka sisältää URL-osoitteen profiilikuvaan. Kirjoita **Tyyppi**-kenttään manuaalisesti seuraava arvo: 
- Henkilölle: Person.ProfileImage
- Organisaatiolle: Organization.LogoImage

Jatka yhtenäistämisvaiheita ja varmista, että myös kuvan URL-osoitteen sisältävä määrite lisätään [yhdistämisvaiheessa](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Määritä organisaatioiden määritteet

Organisaatioiden (esikatselu) määritetyypin vastaavuus on määritettävä Organization.Name-kohteeseen
> [!div class="mx-imgBorder"]
> ![Perusavain ja määritetyyppinä yritystenvälinen](media/configure-data-map-edit-b2b.png "Perusavain ja määritetyyppinä yritystenvälinen")

## <a name="next-step"></a>Seuraava vaihe

Tietojen yhdistämisprosessiin kuuluu myös **Täsmäyttäminen**-sivulle siirtyminen. Saat lisätietoja tästä vaiheesta [**Täsmäyttäminen**](match-entities.md)-sivulta.

> [!TIP]
> Katso seuraava video: [Aloittaminen: Yhdistetyn asiakasprofiilin luominen](https://youtu.be/oBfGEhucAxs).


[!INCLUDE [footer-include](includes/footer-banner.md)]