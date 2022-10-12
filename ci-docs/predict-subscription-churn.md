---
title: Tilauksen vaihtuvuuden ennustaminen (sisältää videon)
description: Ennusta riski sille, että asiakas ei enää käytä yrityksesi tilaustuotteita tai -palveluja.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610232"
---
# <a name="predict-subscription-churn"></a>Ennakoi tilausten vaihtuvuus

Ennusta riski sille, että asiakas ei enää käytä yrityksesi tilaustuotteita tai -palveluja. Tilauksen tiedot sisältävät kunkin asiakkaan aktiiviset ja passiiviset tilaukset, joten kullakin asiakastunnuksella on useita merkintöjä.

Liiketoiminnan tietämystä tarvitaan, jotta voidaan hahmottaa, mitä vaihtuvuus merkitsee yritykselle. Aikaperustaisia vaihtuvuusmäärityksiä tuetaan. Tämä tarkoittaa sitä, että asiakasta pidetään menetettynä, kun tilauksen päättymisestä on kulunut tietty aika.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Tilauksen vaihtuvuusennustetta voi kokeilla näytetietojen avulla: [Tilauksen vaihtuvuusennusteen näyteopas](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>edellytykset

- Ainakin [osallistujan käyttöoikeudet](permissions.md).
- Vähintään 10 asiakasprofiilia, mielellään yli 1 000 yksilöllistä asiakasta.
- Asiakastunniste on yksilöivä asiakkaiden tilauksia vastaava tunniste.
- Tilaustiedot vähintään kaksinkertaisena valittuun aikaikkunaan verrattuna. Tilaustietoja ovat mielellään 2–3 vuoden ajalta. Tilaushistorian on sisällettävä seuraavat tiedot:
  - **Tilauksen tunnus:** tilauksen yksilöivä tunniste.
  - **Tilauksen päättymispäivä:** päivämäärä, jona asiakkaan tilaus päättyy.
  - **Tilauksen alkamispäivä:** päivämäärä, jona asiakkaan tilaus alkaa.
  - **Tapahtumapäivä:** Tilauksen muutoksen päivämäärä. Esimerkiksi tapahtuma, jossa asiakas ostaa tai peruuttaa tilauksen.
  - **Onko kyseessä toistuva tilaus:** Totuusarvon Tosi/epätosi-kenttä, joka määrittää, uusitaanko tilaus samalla tilaustunnuksella ilman asiakkaan toimia.
  - **Toistumisväli (kuukausina):** Toistuvien tilausten kuukausi, jolloin tilaus uusitaan. Esimerkiksi asiakkaalle automaattisesti vuosittain uusittavan tilauksen arvo on 12.
  - **Tilausmäärä:** Summa, jonka asiakas maksaa tilauksen uusimisesta. Sen avulla voidaan määrittää tilausten eri tasojen mallit.
- Vähintään kaksi aktiviteettitietuetta 50 prosentille asiakkaista, joiden vaihtuvuus halutaan laskea. Asiakkaan aktiviteettien on sisällettävä seuraavat tiedot:
  - **Perusavain:** Aktiviteetin yksilöivä tunnus. Esimerkiksi verkkosivustokäynti tai käyttötietue, jossa näkyy asiakkaan katsoma TV-sarjan jakso.
  - **Aikaleima:** perusavaimen tunnistaman tapahtuman päivämäärä ja aika.
  - **Tapahtuma:** Käytettävän tapahtuman nimi. Esimerkiksi suoratoistovideopalvelussa kenttä, jonka nimi on Käyttäjän toiminto, voi saada arvon Katsottu.
  - **Tiedot:** Tapahtuman yksityiskohtaiset tiedot. Esimerkiksi suoratoistovideopalvelussa kenttä, jonka nimi on Ohjelman nimi, voi saada arvoksi asiakkaan katsoman videon.
- Puuttuvia arvoja alle 20 % annetun entiteetin tietokentässä.

## <a name="create-a-subscription-churn-prediction"></a>Tilausten vaihtuvuusennusteen luominen

Ennuste voidaan tallentaa koska tahansa luonnoksena valitsemalla **Tallenna luonnos**. Ennusteluonnos näkyy **Omat ennusteet** -välilehdessä.

1. Siirry kohteeseen **Tiedustelu** > **Ennusteet**.

1. Valitse **Luo**-välilehden **Asiakasvaihtuvuusmalli**-ruudussa **Käytä mallia**.

1. Valitse vaihtuvuuden tyypiksi **Tilaus** ja valitse sitten **Aloita**.

1. **Anna tälle mallille** ja **tulosentiteetille nimi**, jotta ne voidaan erottaa muista malleista tai entiteeteistä.

1. Valitse **Seuraava**.

### <a name="define-customer-churn"></a>Määritä asiakasvaihtuma

1. Anna **Päivät tilauksen päättymisestä** -kohtaan arvo, jonka jälkeen yritys pitää asiakasta menetettynä. Tämä kausi linkittyy yleensä yrityksen aktiviteetteihin, kuten tarjouksiin tai muihin markkinointitoimintoihin, joiden avulla yritetään estää asiakkaiden menettäminen.

1. Anna **Tulevaisuuden päivien määrä vaihtuvuuden ennustamista varten**. Ennustetaan esimerkiksi asiakkaiden vaihtuvuusriski seuraavan 90 päivän aikana siten, että se on linjassa markkinoinnin säilyttämispyrkimysten kanssa. Asiakaspoistuman riskin ennustaminen pitkällä tai lyhyemmällä ajanjaksolla voi vaikeuttaa riskiprofiilin tekijöiden käsittelyä yrityksesi tarpeista riippuen.

1. Valitse **Seuraava**.

### <a name="add-required-data"></a>Lisää pakolliset tiedot

1. Valitse **Lisää tiedot** **Tilaushistoria**-kohdassa.

1. Valitse semanttinen aktiviteettityyppi **Subscription**, joka sisältää tilaushistoriatiedot. Jos aktiviteettia ei ole määritetty, valitse **täällä** ja luo se.

1. Jos aktiviteetin määritteet on yhdistetty semanttisesti aktiviteettia luotaessa, valitse **Aktiviteetit**- kohdassa määritteet tai entiteetti, joihin laskelma keskittyy. Jos semanttista yhdistämismääritystä ei tehty, valitse **Muokkaa** ja yhdistä tiedot.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Asiakkaan tilauksen vaihtuvuusmalliin tarvittavien tietojen lisääminen":::

1. Valitse **Seuraava** ja tarkista mallissa tarvittavat määritteet.

1. Valitse **Tallenna**.

1. Valitse **Lisää tiedot** **Asiakasaktiviteetit**-kohdassa.

1. Valitse semanttinen aktiviteettityyppi, jolla asiakasaktiviteetin tiedot saadaan. Jos aktiviteettia ei ole määritetty, valitse **täällä** ja luo se.

1. Jos aktiviteetin määritteet on yhdistetty semanttisesti aktiviteettia luotaessa, valitse **Aktiviteetit**- kohdassa määritteet tai entiteetti, joihin laskelma keskittyy. Jos semanttista yhdistämismääritystä ei tehty, valitse **Muokkaa** ja yhdistä tiedot.

1. Valitse **Seuraava** ja tarkista mallissa tarvittavat määritteet.

1. Valitse **Tallenna**.

1. Lisää enemmän aktiviteetteja ja valitse **Seuraava**.

### <a name="set-update-schedule"></a>Päivitysaikataulun määrittäminen

1. Valitse mallin uudelleenkouluttamistiheys. Tämä asetus on tärkeä, jotta ennusteiden tarkkuus voidaan päivittää, kun uusia tietoja päivitetään Customer Insightsissa. Useimmat yritykset voivat kouluttaa uudelleen kerran kuukaudessa ja saada hyvän tarkkuuden ennusteille.

1. Valitse **Seuraava**.

### <a name="review-and-run-the-model-configuration"></a>Mallimäärityksen tarkasteleminen ja suorittaminen

**Tarkistus ja suoritus** -vaiheessa näkyy määritysten yhteenveto. Siinä on myös mahdollista tehdä muutoksia ennen ennusteen luontia.

1. Tee tarkistukset ja tarvittavat muutokset valitsemalla **Muokkaa**.

1. Jos olet tyytyväinen valintoihin, aloita mallin suorittaminen valitsemalla **Tallenna ja suorita**. Valitse **Valmis**. **Omat ennusteet** -välilehti on näkyvissä, kun ennustetta luodaan. Prosessin valmistumiseen voi kulua useita tunteja ennusteessa käytettyjen tietojen määrästä riippuen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Ennusteen tulosten näyttäminen

1. Siirry kohteeseen **Tiedustelu** > **Ennusteet**.

1. Valitse **Omat ennusteet** -välilehdessä tarkasteltava ennuste.

Tulossivulla on seuraavat kolme ensisijaista tieto-osaa:

- **Koulutusmallin suorituskyky**: Luokka A, B tai C osoittaa ennusteen suorituskyvyn. Sen avulla voit päättää, käytetäänkö tulosentiteettiin tallennettuja tuloksia.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Kuva mallin pisteiden tietoruudusta, jossa luokka on A.":::

  Luokat määritetään seuraavien sääntöjen perusteella:
  - **A**, kun mallin tarkkuudeksi on ennustettu vähintään 50 % ennusteesta yhteensä ja kun vaihtuvuusasiakkaiden tarkka ennusteprosentti on ainakin 10 % suurempi kuin historiallinen vaihtuvuusprosentti.
  - **A**, kun mallin tarkkuudeksi on ennustettu vähintään 50 % ennusteesta yhteensä ja kun vaihtuvuusasiakkaiden tarkka ennusteprosentti on enintään 10 % suurempi kuin historiallinen vaihtuvuusprosentti.
  - **C**, kun malli on ennustettu oikein enintään 50 prosentissa kaikista ennusteista tai kun prosenttiosuus tarkoille vaihtuneiden asiakkaiden ennusteille on pienempi kuin historiallisen vaihtuvuusprosentin keskiarvo.
  
- **Vaihtuvuuden todennäköisyys (asiakkaiden määrä)**: Asiakasryhmät ennustetun vaihtuvuusriskin perusteella. Valinnaisesti voidaan [luoda asiakassegmentti](prediction-based-segment.md) asiakkaista, joilla on korkea vaihtuvuusriski. Tällaiset segmentit auttavat ymmärtämään, missä segmentin jäsenyyden rajan on oltava.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Kaavio, jossa näkyvät vaihtuvuuden tulosten jakelu eriteltynä välille 0 - 100 %":::

- **Tärkeimmät tekijät:** Ennusteen luomisessa otetaan huomioon useita tekijöitä. Kunkin tekijän tärkeys lasketaan mallin luomille kooste-ennusteille. Näiden tekijöiden avulla voidaan tarkistaa ennusteen tulokset. Näitä tietoja voi käyttää myös myöhemmin sellaisten [segmenttien luontiin](.//prediction-based-segment.md), joilla voi olla vaikutusta asiakkaiden vaihtuvuusriskiin.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Luettelo, jossa on vaikuttavat tekijät ja niiden tärkeys vaihtuuvuustulosten ennustamisessa.":::

> [!NOTE]
> Tämän mallin tulosentiteetissä *ChurnScore* on poistuman ennustettu todennäköisyys ja *IsChurn* on *ChurnScore*-raja-arvoon 0,5 perustuva binaarinen selite. Jos tämä oletusraja-arvo ei toimi omassa skenaariossa, ensisijaisen raja-arvon sisältävä [uusi segmentti voidaan luoda](segments.md). Vaihtuvuuden pistemäärää voi tarkastella valitsemalla **Tiedot** > **Entiteetit** ja tarkastelemalla malliin määritetyn tulosentiteetin tietovälilehteä.

[!INCLUDE [footer-include](includes/footer-banner.md)]
