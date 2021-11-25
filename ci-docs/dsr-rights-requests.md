---
title: Rekisteröityjen oikeuksien (DSR) pyynnöt GDPR:n mukaan | Microsoft Docs
description: Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuuden rekisteröidyn pyyntöön vastaaminen.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732676"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Rekisteröityjen oikeuksien (DSR) pyynnöt GDPR:n mukaan

Euroopan unionin yleinen tietosuoja-asetus (GDPR) on ollut voimassa 25.5.2018 alkaen. Se antaa yksityishenkilöille merkittäviä oikeuksia tietojensa osalta. Tietosuoja-asetuksen tarkoitus on suojata henkilöiden tietosuojaa ja mahdollistaa tietosuojaoikeuksien käytön. Lisätietoja Microsoftin sitoutumisesta suojaukseen ja vaatimustenmukaisuuteen on [Microsoftin luottamuskeskuksessa](https://www.microsoft.com/trust-center).

Olemme sitoutuneet auttamaan asiakkaitamme täyttämään GDPR-vaatimukset. Se sisältää oikeuden poistaa ja viedä tietoja, jotka sisältävät henkilötietoja, kuten käyttäjätunnuksia, puhelinnumeroita ja sähköpostiosoitteita. Järjestelmänvalvojat voivat panna täytäntöön käyttäjien pyyntöjä poistaa tai viedä henkilötietoja.

## <a name="audience-insights"></a>Merkityksellisiä tietoja käyttäjäryhmästä

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuuden rekisteröityjen poistopyyntöihin vastaaminen GDPR:n mukaisesti.

Oikeus poistaa henkilökohtaisia tietoja organisaation asiakastiedoista on yleisen tietosuoja-asetuksen (GDPR) tärkeä osa. Henkilökohtaisten tietojen poistaminen sisältää kaikkien henkilökohtaisten tietojen sekä järjestelmän luomien lokien poistaminen. Tähän eivät kuulu seurantalokien tiedot.

#### <a name="manage-data-subject-delete-requests"></a>Rekisteröityjen poistopyyntöjen hallinta

Käyttäjäryhmän merkitykselliset tiedot sisältävät seuraavat ominaisuudet, joilla voi poistaa tietyn asiakkaan tai käyttäjän henkilökohtaisia tietoja:

- **Asiakastietojen poistopyyntöjen hallinta**: Customer Insightsin asiakastiedot käsitellään alkuperäisistä tietolähteistä Customer Insightsin ulkopuolelta. Kaikki GDPR-poistopyynnöt on suoritettava alkuperäisessä tietolähteessä.
- **Customer Insightsin käyttäjätietojen poistopyyntöjen hallinta**:Customer Insightsin luo käyttäjien tiedot. Kaikki GDPR-poistopyynnöt on suoritettava Customer Insightsissa.

##### <a name="manage-requests-to-delete-customer-data"></a>Hallinnoi asiakastietojen poistopyyntöjä

Customer Insightsin järjestelmänvalvoja voi seurata näitä vaiheita ja poistaa asiakastiedot, jotka on poistettu tietolähteestä seuraavalla tavalla:

1. Kirjaudu Dynamics 365 Customer Insights.
2. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**
3. Jokainen luettelon tietolähde, joka sisältää poistetut asiakastiedot:
   1. Valitse (...) ja valitse sitten **Päivitä**.
   2. Tarkista tietolähteen tila **Tila**-kohdassa. Valintamerkki osoittaa, että päivitys onnistui. Varoituskolmio osoittaa, että päivitys ei onnistunut. Jos varoituskolmion näkyy, ota yhteys osoitteen D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Asiakastietojen GDPR-poistopyyntöjen käsittely.](audience-insights/media/gdpr-data-sources.png "Asiakastietojen GDPR-poistopyyntöjen käsittely")

##### <a name="manage-delete-requests-for-user-data"></a>Käyttäjätietojen poistopyyntöjen hallinta

Customer Insightsin järjestelmänvalvoja voi poistaa Customer Insightsin käyttäjätiedot seuraavasti:

1. Kirjaudu Dynamics 365 Customer Insights.
2. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Käyttöoikeudet**
3. Valitse poistettavan käyttäjän valintaruutu.
4. Valitse **Poista**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Rekisteröityjen vientipyyntöihin vastaaminen GDPR:n mukaisesti

Osana sitoumustamme toimia kumppaninasi yleisen tietosuoja-asetuksen (GDPR) noudattamisessa olemme kehittäneet ohjeistuksen, joka auttaa valmistautumisessa. Tässä dokumentaatiossa on ohjeet, jotka tekemällä voidaan tukea GDPR:n vaatimustenmukaisuutta käyttäjäryhmän merkityksellisiä tietoja käytettäessä.

#### <a name="manage-export-and-view-requests"></a>Vienti- ja tarkastelupyyntöjen hallinta

Oikeus tietojen siirrettävyyteen mahdollistaa sen, että rekisteröidyt voivat pyytää kopiota henkilökohtaisista tiedoistaan sähköisessä muodossa (rakenteellisena, usein käytettynä, koneellisesti luettavissa olevana ja yhteentoimivassa muodossa olevana), joka voidaan toimittaa toiselle tiedonkäsittelijälle.

##### <a name="export-customer-data-tenant-admin"></a>Asiakastietojen vieminen (vuokraajan järjestelmänvalvoja)

Vuokraajan järjestelmänvalvoja voi viedä tiedot seuraavasti:

1. Lähetä osoitteeseen D365CI@microsoft.com sähköposti, jossa määritetään asiakkaan pyynnössä oleva sähköpostiosoite. Customer Insights -ryhmä lähettää sähköpostin rekisteröidyn vuokraajan järjestelmänvalvojan sähköpostiosoitteeseen ja pyytää vahvistamaan tietojen viennin.
2. Kuittaa pyydetyn asiakkaan tietojen vientivahvistus.
3. Saat viedyt tiedot vuokraajan järjestelmänvalvojan sähköpostiosoitteen kautta.

##### <a name="export-user-data-tenant-admin"></a>Käyttäjätietojen vieminen (vuokraajan järjestelmänvalvoja)

1. Lähetä osoitteeseen D365CI@microsoft.com sähköposti, jossa määritetään käyttäjän pyynnössä oleva sähköpostiosoite. Customer Insights -ryhmä lähettää sähköpostin rekisteröidyn vuokraajan järjestelmänvalvojan sähköpostiosoitteeseen ja pyytää vahvistamaan tietojen viennin.
2. Kuittaa pyydetyn käyttäjän tietojen vientivahvistus.
3. Saat viedyt tiedot vuokraajan järjestelmänvalvojan sähköpostiosoitteen kautta.

## <a name="consent-management-preview"></a>Hyväksynnän hallinta (esiversio)

Hyväksynnän hallinnan ominaisuus ei kerää käyttäjätietoja suoraan. Se tuo ja käsittelee vain muiden sovellusten käyttäjien toimittamat tiedot.

Jos haluat poistaa tiettyjä käyttäjiä koskevat hyväksyntätiedot, poista ne tietolähteistä, joiden tiedot on siirretty hyväksynnän hallintaominaisuuteen. Kun tietolähde on päivitetty, myös poistetut tiedot poistetaan hyväksyntäkeskuksesta. Hyväksyntäentiteettiä käyttävät sovellukset poistavat myös tiedot, jotka on poistettu lähteestä [päivityksen](audience-insights/system.md#refresh-processes) jälkeen. Tietolähteet kannattaa päivittää nopeasti sen jälkeen, kun on vastattu rekisteröidyn henkilön pyyntöön, jotta käyttäjän tiedot voidaan poistaa muista prosesseista ja sovelluksista.


## <a name="engagement-insights-preview"></a>Vuorovaikutuksen merkitykselliset tiedot (esiversio)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Käyttäjän tunnistetietoja sisältävien tapahtumatietojen poistaminen ja vieminen

Seuraavissa osissa kuvataan, miten henkilötietoja mahdollisesti sisältävät tapahtumatiedot poistetaan ja viedään.

Tietojen poistaminen tai vieminen:

1. Merkitse tapahtumaominaisuudet, jotka sisältävät henkilötietoja sisältäviä tietoja.
2. Poista tai vie tiettyihin arvoihin (kuten tiettyyn käyttäjätunnukseen) liittyviä tietoja.

#### <a name="tag-and-update-event-properties"></a>Tapahtumaominaisuuksien merkitseminen tunnisteilla ja päivittäminen

Henkilötiedot merkitään tunnisteilla tapahtumaominaisuuden tasolla. Merkitse ensin poistettavaksi tai vietäväksi harkitut ominaisuudet tunnisteella.

Jos haluat merkitä tapahtumaominaisuuden sisältävän henkilötietoja, toimi seuraavasti:

1. Avaa tapahtuman sisältävä työtila.

1. Avaa valitun työtilan tapahtumaluettelo siirtymällä kohtaan **Tiedot** > **Tapahtumat**.
  
1. Valitse tapahtuma, jonka haluat merkitä tunnisteella.

1. Avaa valitun tapahtuman kaikki ominaisuudet sisältävä ruutu valitsemalla **Muokkaa ominaisuuksia**.
     
1. Valitse **...** ja valitse sitten **Muokkaa**, jotta pääset **Päivitä ominaisuus** -valintaikkunaan.

   ![Muokkaa tapahtumaa.](engagement-insights/media/edit-event.png "Muokkaa tapahtumaa")

1. Valitse **Päivitä ominaisuus** -ikkunassa oikeasta yläkulmasta **...** ja valitse sitten **Sisältää EUII-tietoja** -ruutu. Tallenna muutokset valitsemalla **Päivitä**.

   ![Tallenna tekemäsi muutokset.](engagement-insights/media/update-property.png "Tallenna tekemäsi muutokset")

   > [!NOTE]
   > Aina kun tapahtumarakenne muuttuu tai uusi tapahtuma luodaan, on suositeltavaa arvioida asiaan liittyvät tapahtumaominaisuudet ja merkitset ne tarvittaessa henkilötiedoiksi tai poistat kyseisen merkinnän.

#### <a name="delete-or-export-tagged-event-data"></a>Tunnisteilla merkittyjen tapahtumatietojen poistaminen tai vieminen

Jos kaikki tapahtumaominaisuudet on merkitty edellisessä vaiheessa kuvatulla tavalla, ympäristön järjestelmänvalvoja voi tehdä merkittyjen tapahtumatietojen poistopyynnön.

EUII-tietojen poisto- tai vientipyyntöjen hallinta

1. Siirry kohtaan **Järjestelmänvalvoja** > **Ympäristö** > **Asetukset**.

1. Valitse **Hallitse loppukäyttäjän yksilöiviä tietoja (EUII)** -osassa **Hallitse EUII-tietoja**.

##### <a name="deletion"></a>Poistaminen

Poistoa varten voit lisätä pilkuilla erotettujen käyttäjätunnusten luettelon **Poista käyttäjän yksilöivät tiedot (EUII)** -osaan. Näitä tunnuksia verrataan tämän jälkeen kulloisenkin ympäristön kaikkien projektien kaikkiin merkittyihin tapahtumaominaisuuksiin tarkkojen merkkijonovastaavuuksien perusteella. 

Jos ominaisuuden arvo vastaa jotakin annetuista tunnuksista, siihen liittyvä tapahtuma poistetaan pysyvästi. Koska tätä toimintoa ei voi kumota, poisto on vahvistettava, kun **Poista** on valittu.

##### <a name="export"></a>Export

Vientiprosessi on samanlainen kuin poistoprosessi tapahtumaominaisuuksien **Vie käyttäjän yksilöiviä tietoja (EUII)** -osassa tapahtuvaan arvojen määrittämiseen. Lisäksi tarvitaan **Azuren blob-tallennustilan URL-osoite** vientikohteen määrittämistä varten. Azure blob-tallennustilan URL-osoitteen on sisällettävä [Jaetun käyttöoikeuden allekirjoitus (SAS)](/azure/storage/common/storage-sas-overview).

Kun olet valinnut **Vie**, kaikki kulloisenkin ryhmän tapahtumat, jotka sisältävät vastaavia merkittyjä ominaisuuksia, viedään CSV-muodossa vientikohteeseen.

### <a name="good-practices"></a>Hyvät käytännöt

* Yritä välttää henkilötietoja sisältävien tapahtumien lähettämistä.
* Jos sinun on lähetettävä EUII-tietoja sisältäviä tapahtumia, rajoita EUII-tietoja sisältävien tapahtumien ja tapahtumaominaisuuksien määrää. Ihanteellista on niiden määrän rajoittaminen yhteen.
* Varmista, että lähetettyjä henkilötietoja voi käyttää mahdollisimman harva henkilö.
* Jos tapahtuma sisältää henkilötietoja, varmista, että määrität yhdelle ominaisuudelle yksilöivän tunnisteen, jonka voi helposti yhdistää tiettyyn käyttäjään (esimerkiksi käyttäjätunnuksen). Näin tiedot on helpompi erottaa toisistaan ja viedä tai poistaa oikeat tiedot.
* Merkitse kutakin tapahtumaa kohden vain yksi ominaisuus henkilötietoja sisältäväksi. Ihanteellisesti sellainen tapahtuma, joka sisältää yksilöivän tunnisteen.
* Älä merkitse yksityiskohtaisia arvoja (kuten koko pyynnön tekstiä) sisältäviä ominaisuuksia. Vuorovaikutuksen merkitykselliset tiedot -ominaisuudessa käytetään tarkkoja merkkijonovastaavuuksia poistettavien tai vietävien tapahtumien määrittämisessä.

[!INCLUDE[footer-include](includes/footer-banner.md)]