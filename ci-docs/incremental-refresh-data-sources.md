---
title: Power Query- ja Azure Data Lake -tietolähteiden lisäävä päivitys
description: Power Query- tai Azure Data Lake -tietolähteisiin perustuvien suurten tietolähteiden uusien tai päivitettyjen tietojen päivitys.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: de39743eb8728fac34e417724c5f73bf44309c89
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207133"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Power Query- ja Azure Data Lake -tietolähteiden lisäävä päivitys

Power Queryyn tai Azure Data Lakeen perustuvissa tietolähteiden lisäävässä päivityksessä on seuraavat edut:

- **Päivitysten nopeutuminen** – Vain muuttuneet tiedot päivitetään. Esimerkiksi historiallisessa tietojoukossa päivitetään vain viisi viimeisintä päivää.
- **Parantuntu luotettavuus** – koska päivitykset ovat pienempiä, yhteyksiä epävakaisiin lähdejärjestelmiin ei tarvitse ylläpitää yhtä pitkään, mikä vähentää yhteysongelmien riskiä.
- **Resurssin kulutus vähenee** – vain kaikkien tietojen alijoukon päivittäminen tehostaa laskentaresurssien käyttöä ja vähentää ympäristön rasitusta.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Power Queryyn perustuvien tietolähteiden lisäävän päivityksen määrittäminen

Customer Insights sallii Power Queryn kautta tuotujen, lisäävää käsittelyä tukevien tietolähteiden lisäävän päivityksen. Esimerkiksi Azure SQL -tietokannat, joiden päivämäärä- ja aikakentät ilmaisevat, milloin tietotietueet päivitettiin viimeksi.

1. [Luo uusi Power Queryyn perustuva tietolähde](connect-power-query.md).

1. Valitse lisäävää päivitystä tukeva tietolähde, kuten [Azure SQL -tietokanta](/power-query/connectors/azuresqldatabase).

1. Valitse käsiteltävät entiteetit tai taulukot.

1. Tee muunnoksen vaiheet ja valitse **Seuraava**.

1. Avaa **Lisäävän päivityksen asetukset** valitsemalla **Määritä lisäävä päivitys** -valintaikkunassa **Määritä**. Jos valitset **Ohita**, tietolähde päivittää koko tietojoukon.
   > [!TIP]
   > Voit käyttää lisäävää päivitystä myös myöhemmin muokkaamalla aiemmin luotua tietolähdettä.

1. **Lisäävän päivityksen asetukset** -kohdassa määritetään kaikkien tietolähdettä luotaessa valittujen entiteettien lisäävä päivitys.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Lisäävän päivityksen asetusten määrittäminen":::

1. Valitse entiteetti ja anna seuraavat tiedot:

   - **Valitse ensisijainen avain**: valitse entiteetin tai taulukon perusavain.
   - **Määritä viimeksi päivitetty -kenttä**: Tässä kentässä näytetään vain päivämäärä- ja aikatyypin määritteitä. Valitse määrite, joka ilmaisee, milloin tietueet viimeksi päivitettiin. Sen avulla määritetään tietueet, jotka sijoittuvat lisäävän päivityksen aikavälille.
   - **Etsi päivityksiä joka**: määritä, kuinka pitkä lisäävän päivityksen aikaväli on.

1. Viimeistele tietolähteen luonti valitsemalla **Tallenna**. Ensimmäinen tietojen päivitys on täydellinen päivitys. Sen jälkeen tietojen lisäävä päivitys tapahtuu edellisessä vaiheessa määritetyllä tavalla.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Azure Data Lake -tietolähteiden lisäävän päivityksen määrittäminen

Customer Insights sallii Azure Data Lake Storageen yhdistettyjen tietolähteiden lisäävän päivityksen. Entiteetissä voi käyttää lisäävää käsittelyä ja päivitystä määrittämällä kyseinen entiteetti Azure Data Lake -tietolähdettä lisättäessä tai myöhemmin tietolähteen muokkauksen yhteydessä. Entiteetin tietokansiossa on oltava seuraavat kansiot:

- **FullData**: kansio, jossa on alkutietueita sisältävät datatiedostot.
- **IncrementalData**: Kansio, jonka päivämäärän ja ajan hiearkiakansiot ovat **vvvv/kk/pp/tt**-muotoisia ja jotka sisältävät lisäävät päivitykset. **tt** ilmaisee päivityksen tunnit UTC-aikana sekä sisältää **Upsert**- ja **Poistot**-kansiot. **Upsert** sisältää datatiedostot sekä aiemmin luotujen tietueiden päivitykset tai uudet tietueet. **Poistot** sisältää poistettavat tietueet sisältävät datatiedostot.

1. Tietolähteen voi lisätä tai sitä voi muokata siirtymällä entiteetin **Määritteet**-ruutuun.

1. Tarkista määritteet. Varmista, että luotuun tai viimeksi päivitettyyn päivämäärämääritteeseen on määritetty **tietomuodoksi** *dateTime* ja **semanttiseksi tyypiksi** *Calendar.Date*. Muokkaa määritettä tarvittaessa ja valitse **Valmis**.

1. Muokkaa entiteettiä **Valitse entiteetit** -ruudussa. **Lisäävä käsittely** -valintaruutu on valittu.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Tietolähteen entiteettien määrittäminen lisäävää päivitystä varten.":::

   1. Siirry pääkansioon, joka sisältää täydellisten tietojen, lisäävän tiedon upsert-toiminnon ja lisäävän tiedon poiston .csv- tai .parquet-tiedostot.
   1. Anna sekä täydellisten tietojen että lisäävien tiedostojen tiedostotunniste (\.csv tai \.parquet).
   1. Jos .csv-tiedosto, valitse sarakkeen erotin ja haluatko tiedoston ensimmäisen rivin sarakeotsikoksi.
   1. Valitse **Tallenna**.

1. Valitse **Päivitetty viimeksi** -kohdassa päivämäärän aikaleimamäärite.

1. Jos **Perusavain** ei valittuna, valitse perusavain. Perusavain on entiteetin yksilöllinen määrite. Jotta määrite olisi kelvollinen perusavain, se ei saa sisältää arvojen kaksoiskappaleita, siitä ei saa puuttua arvoja eikä siinä saa olla tyhjiä arvoja. Merkkijono-, kokonaisluku- ja GUID-tietotyypin määritteitä tuetaan perusavaimina.

1. Tallenna ja sulje ruutu valitsemalla **Sulje**.

1. Jata tietolähteen lisäämistä tai muokkaamista.

[!INCLUDE [footer-include](includes/footer-banner.md)]
