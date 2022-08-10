---
title: Rekisteröityjen oikeuksien (DSR) pyynnöt GDPR:n mukaan | Microsoft Docs
description: Dynamics 365 Customer Insightsin rekisteröityjen pyyntöihin vastaaminen.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6c6ce49c18de3a09d28138316d893e6842919042
ms.sourcegitcommit: ff0f4b5664d995870c91adb87c7d3780a582efca
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2022
ms.locfileid: "9146691"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Rekisteröityjen oikeuksien (DSR) pyynnöt GDPR:n mukaan

Euroopan unionin yleinen tietosuoja-asetus (GDPR) on ollut voimassa 25.5.2018 alkaen. Se antaa yksityishenkilöille merkittäviä oikeuksia tietojensa osalta. Tietosuoja-asetuksen tarkoitus on suojata henkilöiden tietosuojaa ja mahdollistaa tietosuojaoikeuksien käytön. Lisätietoja Microsoftin sitoutumisesta suojaukseen ja vaatimustenmukaisuuteen on [Microsoftin luottamuskeskuksessa](https://www.microsoft.com/trust-center).

Olemme sitoutuneet auttamaan asiakkaitamme täyttämään GDPR-vaatimukset. Se sisältää oikeuden poistaa ja viedä tietoja, jotka sisältävät henkilötietoja, kuten käyttäjätunnuksia, puhelinnumeroita ja sähköpostiosoitteita. Järjestelmänvalvojat voivat panna täytäntöön käyttäjien pyyntöjä poistaa tai viedä henkilötietoja.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insightsin rekisteröityjen poistopyyntöihin vastaaminen GDPR:n mukaisesti

Oikeus poistaa henkilökohtaisia tietoja organisaation asiakastiedoista on yleisen tietosuoja-asetuksen (GDPR) tärkeä osa. Henkilökohtaisten tietojen poistaminen sisältää kaikkien henkilökohtaisten tietojen sekä järjestelmän luomien lokien poistaminen. Tähän eivät kuulu seurantalokien tiedot.

#### <a name="manage-data-subject-delete-requests"></a>Rekisteröityjen poistopyyntöjen hallinta

Customer Insights sisältää seuraavat ominaisuudet, joilla voi poistaa tietyn asiakkaan tai käyttäjän henkilökohtaisia tietoja:

- **Asiakastietojen poistopyyntöjen hallinta**: Customer Insightsin asiakastiedot käsitellään alkuperäisistä tietolähteistä Customer Insightsin ulkopuolelta. GDPR-poistopyynnöt on suoritettava ensin alkuperäisessä tietolähteessä.
- **Customer Insightsin käyttäjätietojen poistopyyntöjen hallinta**:Customer Insightsin luo käyttäjien tiedot. Kaikki GDPR-poistopyynnöt on suoritettava Customer Insightsissa.

##### <a name="manage-requests-to-delete-customer-data"></a>Hallinnoi asiakastietojen poistopyyntöjä

Customer Insightsin järjestelmänvalvoja voi seurata näitä vaiheita ja poistaa asiakastiedot, jotka on poistettu tietolähteestä seuraavalla tavalla. Varmista, että poistopyyntö on tehty tietolähteessä, ennen kuin jatkat alla olevien ohjevaiheiden mukaisesti. 

1. Kirjaudu Dynamics 365 Customer Insights.
1. Valitse **Tiedot** > **Tietolähteet**
1. Jokainen luettelon tietolähde, joka sisältää poistetut asiakastiedot:
   1. Valitse kolme pystysuuntaista pistettä (&vellip;) ja valitse sitten **Päivitä**.
   1. Tarkista tietolähteen tila **Tila**-kohdassa. Valintamerkki osoittaa, että päivitys onnistui. Varoituskolmio osoittaa, että päivitys ei onnistunut. Jos varoituskolmion näkyy, ota yhteys osoitteen D365CI@microsoft.com.
1. Kun tietolähteet on päivitetty onnistuneesti, suorita myös loppuvaiheen päivitykset. Erityisesti jos sinulla ei ole aikataulutettu toistuvaa täydellistä Customer Insights -päivitystä. 

> [!IMPORTANT]
> Staattiset segmentit eivät sisälly täydelliseen päivitykseen tai loppuvaiheen päivityksiä varten poistopyynnön jälkeen. Voit varmistaa, että asiakastiedot poistetaan myös staattisista segmentistä, luomalla staattiset segmentit uudelleen päivitetyillä lähdetiedoilla.

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

Oikeus tietojen siirrettävyyteen mahdollistaa sen, että rekisteröidyt voivat pyytää kopiota henkilökohtaisista tiedoistaan sähköisessä muodossa (rakenteellisena, usein käytettynä, koneellisesti luettavissa olevana ja yhteen toimivassa muodossa olevana), joka voidaan toimittaa toiselle tiedonkäsittelijälle.

##### <a name="export-customer-data-tenant-admin"></a>Asiakastietojen vieminen (vuokraajan järjestelmänvalvoja)

Vuokraajan järjestelmänvalvoja voi viedä tiedot seuraavasti:

1. Lähetä osoitteeseen D365CI@microsoft.com sähköposti, jossa määritetään asiakkaan pyynnössä oleva sähköpostiosoite. Customer Insights -ryhmä lähettää sähköpostin rekisteröidyn vuokraajan järjestelmänvalvojan sähköpostiosoitteeseen ja pyytää vahvistamaan tietojen viennin.
2. Kuittaa pyydetyn asiakkaan tietojen vientivahvistus.
3. Saat viedyt tiedot vuokraajan järjestelmänvalvojan sähköpostiosoitteen kautta.

##### <a name="export-user-data-tenant-admin"></a>Käyttäjätietojen vieminen (vuokraajan järjestelmänvalvoja)

1. Lähetä osoitteeseen D365CI@microsoft.com sähköposti, jossa määritetään käyttäjän pyynnössä oleva sähköpostiosoite. Customer Insights -ryhmä lähettää sähköpostin rekisteröidyn vuokraajan järjestelmänvalvojan sähköpostiosoitteeseen ja pyytää vahvistamaan tietojen viennin.
2. Kuittaa pyydetyn käyttäjän tietojen vientivahvistus.
3. Saat viedyt tiedot vuokraajan järjestelmänvalvojan sähköpostiosoitteen kautta.

### <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Tietojen poiston käsittely Dynamics 365 Customer Insightsissa

1. Tiedot poistetaan (tieto-osiot ja tietojen tilannevedokset), jos tieto-osiot ja tietojen tilannevedokset ovat passiivisia yli 30 päivän ajan, mikä tarkoittaa sitä, että ne on korvattu uudella tieto-osiolla ja tilannevedoksella tietolähteiden päivityksen kautta.
2. Kaikkia tietoja ja tilannevedoksia ei poisteta. Uusin tieto-osio ja tietojen tilannevedos ovat oletusarvoisesti aktiivisia, koska niitä käytetään Customer Insightsissa. Uusimpien tietojen osalta ei ole merkityksellistä, päivitettiinkö tietolähteitä viimeksi kuluneiden 30 päivän aikana.

[!INCLUDE [footer-include](includes/footer-banner.md)]
