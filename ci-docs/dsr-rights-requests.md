---
title: Rekisteröityjen oikeuksien (DSR) pyynnöt GDPR:n mukaan | Microsoft Docs
description: Dynamics 365 Customer Insightsin rekisteröityjen pyyntöihin vastaaminen.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: af2583295627f98e980adbca4f216b9c34c3cad8
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808542"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Rekisteröityjen oikeuksien (DSR) pyynnöt GDPR:n mukaan

Euroopan unionin yleinen tietosuoja-asetus (GDPR) on ollut voimassa 25.5.2018 alkaen. Se antaa yksityishenkilöille merkittäviä oikeuksia tietojensa osalta. Tietosuoja-asetuksen tarkoitus on suojata henkilöiden tietosuojaa ja mahdollistaa tietosuojaoikeuksien käytön. Lisätietoja Microsoftin sitoutumisesta suojaukseen ja vaatimustenmukaisuuteen on [Microsoftin luottamuskeskuksessa](https://www.microsoft.com/trust-center).

Olemme sitoutuneet auttamaan asiakkaitamme täyttämään GDPR-vaatimukset. Se sisältää oikeuden poistaa ja viedä tietoja, jotka sisältävät henkilötietoja, kuten käyttäjätunnuksia, puhelinnumeroita ja sähköpostiosoitteita. Järjestelmänvalvojat voivat panna täytäntöön käyttäjien pyyntöjä poistaa tai viedä henkilötietoja.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insightsin rekisteröityjen poistopyyntöihin vastaaminen GDPR:n mukaisesti

Oikeus poistaa henkilökohtaisia tietoja organisaation asiakastiedoista on yleisen tietosuoja-asetuksen (GDPR) tärkeä osa. Henkilökohtaisten tietojen poistaminen sisältää kaikkien henkilökohtaisten tietojen sekä järjestelmän luomien lokien poistaminen. Tähän eivät kuulu seurantalokien tiedot.

#### <a name="manage-data-subject-delete-requests"></a>Rekisteröityjen poistopyyntöjen hallinta

Customer Insights sisältää seuraavat ominaisuudet, joilla voi poistaa tietyn asiakkaan tai käyttäjän henkilökohtaisia tietoja:

- **Asiakastietojen poistopyyntöjen hallinta**: Customer Insightsin asiakastiedot käsitellään alkuperäisistä tietolähteistä Customer Insightsin ulkopuolelta. Kaikki GDPR-poistopyynnöt on suoritettava alkuperäisessä tietolähteessä.
- **Customer Insightsin käyttäjätietojen poistopyyntöjen hallinta**:Customer Insightsin luo käyttäjien tiedot. Kaikki GDPR-poistopyynnöt on suoritettava Customer Insightsissa.

##### <a name="manage-requests-to-delete-customer-data"></a>Hallinnoi asiakastietojen poistopyyntöjä

Customer Insightsin järjestelmänvalvoja voi seurata näitä vaiheita ja poistaa asiakastiedot, jotka on poistettu tietolähteestä seuraavalla tavalla:

1. Kirjaudu Dynamics 365 Customer Insights.
2. Valitse **Tiedot** > **Tietolähteet**
3. Jokainen luettelon tietolähde, joka sisältää poistetut asiakastiedot:
   1. Valitse kolme pystysuuntaista pistettä (&vellip;) ja valitse sitten **Päivitä**.
   2. Tarkista tietolähteen tila **Tila**-kohdassa. Valintamerkki osoittaa, että päivitys onnistui. Varoituskolmio osoittaa, että päivitys ei onnistunut. Jos varoituskolmion näkyy, ota yhteys osoitteen D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Asiakastietojen GDPR-poistopyyntöjen käsittely.](media/gdpr-data-sources.png "Asiakastietojen GDPR-poistopyyntöjen käsittely")

##### <a name="manage-delete-requests-for-user-data"></a>Käyttäjätietojen poistopyyntöjen hallinta

Customer Insightsin järjestelmänvalvoja voi poistaa Customer Insightsin käyttäjätiedot seuraavasti:

1. Kirjaudu Dynamics 365 Customer Insights.
2. Valitse **Järjestelmänvalvoja** > **Tietoturva** > **Oikeudet**.
3. Valitse poistettavan käyttäjän valintaruutu.
4. Valitse **Poista**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Rekisteröityjen vientipyyntöihin vastaaminen GDPR:n mukaisesti

Osana sitoumustamme toimia kumppaninasi yleisen tietosuoja-asetuksen (GDPR) noudattamisessa olemme kehittäneet ohjeistuksen, joka auttaa vastaamaan tietojen kohteen pyyntöihin.

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

Jos haluat poistaa tiettyjä käyttäjiä koskevat hyväksyntätiedot, poista ne tietolähteistä, joiden tiedot on siirretty hyväksynnän hallintaominaisuuteen. Kun tietolähde on päivitetty, myös poistetut tiedot poistetaan hyväksyntäkeskuksesta. Hyväksyntäentiteettiä käyttävät sovellukset poistavat myös tiedot, jotka on poistettu lähteestä [päivityksen](system.md#refresh-processes) jälkeen. Tietolähteet kannattaa päivittää nopeasti sen jälkeen, kun on vastattu rekisteröidyn henkilön pyyntöön, jotta käyttäjän tiedot voidaan poistaa muista prosesseista ja sovelluksista.

[!INCLUDE [footer-include](includes/footer-banner.md)]