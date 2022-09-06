---
title: Rekisteröityjen oikeuksien (DSR) pyynnöt GDPR:n mukaan | Microsoft Docs
description: Dynamics 365 Customer Insightsin rekisteröityjen pyyntöihin vastaaminen.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387107"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Rekisteröityjen oikeuksien (DSR) pyynnöt GDPR:n mukaan

Euroopan unionin yleinen tietosuoja-asetus (GDPR) on ollut voimassa 25.5.2018 alkaen. Se antaa yksityishenkilöille merkittäviä oikeuksia tietojensa osalta. Tietosuoja-asetuksen tarkoitus on suojata henkilöiden tietosuojaa ja mahdollistaa tietosuojaoikeuksien käytön. Lisätietoja Microsoftin sitoutumisesta suojaukseen ja vaatimustenmukaisuuteen on [Microsoftin luottamuskeskuksessa](https://www.microsoft.com/trust-center).

Olemme sitoutuneet auttamaan asiakkaitamme täyttämään GDPR-vaatimukset. Se sisältää oikeuden poistaa tai viedä tietoja, jotka sisältävät henkilötietoja, kuten käyttäjätunnuksia, puhelinnumeroita ja sähköpostiosoitteita. Järjestelmänvalvojat voivat panna täytäntöön käyttäjien pyyntöjä poistaa tai viedä henkilötietoja.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Customer Insightsin rekisteröityjen poistopyyntöihin vastaaminen GDPR:n mukaisesti

Oikeus poistaa henkilökohtaisia tietoja organisaation asiakastiedoista on yleisen tietosuoja-asetuksen (GDPR) tärkeä osa. Henkilökohtaisten tietojen poistaminen sisältää kaikkien henkilökohtaisten tietojen sekä järjestelmän luomien lokien poistaminen. Tähän eivät kuulu seurantalokien tiedot.

### <a name="manage-data-subject-delete-requests"></a>Rekisteröityjen poistopyyntöjen hallinta

Customer Insights sisältää seuraavat ominaisuudet, joilla voi poistaa tietyn asiakkaan tai käyttäjän henkilökohtaisia tietoja:

- **Asiakastietojen poistopyyntöjen hallinta**: Customer Insightsin asiakastiedot käsitellään alkuperäisistä tietolähteistä Customer Insightsin ulkopuolelta. GDPR-poistopyynnöt on suoritettava ensin alkuperäisessä tietolähteessä.
- **Customer Insightsin käyttäjätietojen poistopyyntöjen hallinta**:Customer Insightsin luo käyttäjien tiedot. Suorita kaikki GDPR-poistopyynnöt Customer Insightsissa.

#### <a name="manage-requests-to-delete-customer-data"></a>Hallinnoi asiakastietojen poistopyyntöjä

Customer Insightsin järjestelmänvalvojana poista Customer Insights -asiakastiedot, jotka on poistettu tietolähteestä. Varmista, että GDPR-poistopyynnöt suoritetaan alkuperäisessä tietolähteessä.

1. Kirjaudu Dynamics 365 Customer Insights.

1. Valitse **Tiedot** > **Tietolähteet**.

1. Jokainen luettelon tietolähde, joka sisältää poistetut asiakastiedot:
   1. Valitse tietolähde ja valitse sitten **Päivitä**.
   1. Tarkista tietolähteen tila **Tila**-kohdassa. Valintamerkki osoittaa, että päivitys onnistui. Varoituskolmio osoittaa, että päivitys ei onnistunut. Jos varoituskolmion näkyy, ota yhteys osoitteen D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Asiakastietojen GDPR-poistopyyntöjen käsittely.":::

1. Kun tietolähteet on päivitetty onnistuneesti, suorita myös loppuvaiheen päivitykset. Erityisesti jos sinulla ei ole aikataulutettu toistuvaa täydellistä Customer Insights -päivitystä.

   > [!IMPORTANT]
   > Staattiset segmentit eivät sisälly täydelliseen päivitykseen tai loppuvaiheen päivityksiä varten poistopyynnön jälkeen. Voit varmistaa, että asiakastiedot poistetaan myös staattisista segmentistä, luomalla staattiset segmentit uudelleen päivitetyillä lähdetiedoilla.

#### <a name="manage-delete-requests-for-user-data"></a>Käyttäjätietojen poistopyyntöjen hallinta

Customer Insightsin järjestelmänvalvojana poista Customer Insightsin käyttäjätiedot.

1. Kirjaudu Dynamics 365 Customer Insights.

1. Siirry kohtaan **Järjestelmänvalvoja** > **Suojaus** > ja valitse **Käyttäjät**-välilehti.

1. Valitse poistettavien käyttäjien valintaruudut.

1. Valitse **Poista**.

1. Vahvista poisto.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Rekisteröityjen vientipyyntöihin vastaaminen GDPR:n mukaisesti

Oikeus tietojen siirrettävyyteen mahdollistaa sen, että rekisteröidyt voivat pyytää kopiota henkilökohtaisista tiedoistaan sähköisessä muodossa (rakenteellisena, usein käytettynä, koneellisesti luettavissa olevana ja yhteen toimivassa muodossa olevana), joka voidaan toimittaa toiselle tiedonkäsittelijälle.

### <a name="manage-export-and-view-requests"></a>Vienti- ja tarkastelupyyntöjen hallinta

Hallinnoi asiakas- tai käyttäjätietojen vientipyyntöjä.

#### <a name="export-customer-data-tenant-admin"></a>Asiakastietojen vieminen (vuokraajan järjestelmänvalvoja)

Vie asiakastiedot vuokraajan järjestelmänvalvojana.

1. Lähetä osoitteeseen D365CI@microsoft.com sähköposti, jossa määritetään asiakkaan pyynnössä oleva sähköpostiosoite. Customer Insights -ryhmä lähettää sähköpostin rekisteröidyn vuokraajan järjestelmänvalvojan sähköpostiosoitteeseen ja pyytää vahvistamaan tietojen viennin.
2. Kuittaa pyydetyn asiakkaan tietojen vientivahvistus.
3. Saat viedyt tiedot vuokraajan järjestelmänvalvojan sähköpostiosoitteen kautta.

#### <a name="export-user-data-tenant-admin"></a>Käyttäjätietojen vieminen (vuokraajan järjestelmänvalvoja)

Vie käyttäjätiedot vuokraajan järjestelmänvalvojana.

1. Lähetä osoitteeseen D365CI@microsoft.com sähköposti, jossa määritetään käyttäjän pyynnössä oleva sähköpostiosoite. Customer Insights -ryhmä lähettää sähköpostin rekisteröidyn vuokraajan järjestelmänvalvojan sähköpostiosoitteeseen ja pyytää vahvistamaan tietojen viennin.
1. Kuittaa pyydetyn käyttäjän tietojen vientivahvistus.
1. Saat viedyt tiedot vuokraajan järjestelmänvalvojan sähköpostiosoitteen kautta.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Tietojen poiston käsittely Dynamics 365 Customer Insightsissa

Tiedot poistetaan (tieto-osiot ja tietojen tilannevedokset), jos tieto-osiot ja tietojen tilannevedokset ovat passiivisia yli 30 päivän ajan, mikä tarkoittaa sitä, että ne on korvattu uudella tieto-osiolla ja tilannevedoksella tietolähteiden päivityksen kautta.

Kaikkia tietoja ja tilannevedoksia ei poisteta. Uusin tieto-osio ja tietojen tilannevedos ovat aktiivisia, koska niitä käytetään Customer Insightsissa. Uusimpien tietojen osalta ei ole merkityksellistä, päivitettiinkö tietolähteitä viimeksi kuluneiden 30 päivän aikana.

[!INCLUDE [footer-include](includes/footer-banner.md)]
