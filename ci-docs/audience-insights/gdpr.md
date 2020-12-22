---
title: Rekisteröityjen oikeuksien (DSR) pyynnöt GDPR:n mukaan | Microsoft Docs
description: Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuuden rekisteröidyn pyyntöön vastaaminen.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405610"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Rekisteröityjen oikeuksien (DSR) pyynnöt GDPR:n mukaan

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuuden rekisteröityjen poistopyyntöihin vastaaminen GDPR:n mukaisesti.

Oikeus poistaa henkilökohtaisia tietoja organisaation asiakastiedoista on yleisen tietosuoja-asetuksen (GDPR) tärkeä osa. Henkilökohtaisten tietojen poistaminen sisältää kaikkien henkilökohtaisten tietojen sekä järjestelmän luomien lokien poistaminen. Tähän eivät kuulu seurantalokien tiedot.

### <a name="manage-data-subject-delete-requests"></a>Rekisteröityjen poistopyyntöjen hallinta

Käyttäjäryhmän merkitykselliset tiedot sisältävät seuraavat ominaisuudet, joilla voi poistaa tietyn asiakkaan tai käyttäjän henkilökohtaisia tietoja:

- **Asiakastietojen poistopyyntöjen hallinta**: Customer Insightsin asiakastiedot käsitellään alkuperäisistä tietolähteistä Customer Insightsin ulkopuolelta. Kaikki GDPR-poistopyynnöt on suoritettava alkuperäisessä tietolähteessä.
- **Customer Insightsin käyttäjätietojen poistopyyntöjen hallinta**:Customer Insightsin luo käyttäjien tiedot. Kaikki GDPR-poistopyynnöt on suoritettava Customer Insightsissa.

#### <a name="manage-delete-requests-for-customer-data"></a>Asiakastietojen poistopyyntöjen hallinta

Customer Insightsin järjestelmänvalvoja voi seurata näitä vaiheita ja poistaa asiakastiedot, jotka on poistettu tietolähteestä seuraavalla tavalla:

1. Kirjaudu Dynamics 365 Customer Insights.
2. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**
3. Jokainen luettelon tietolähde, joka sisältää poistetut asiakastiedot:
   1. Valitse (...) ja valitse sitten **Päivitä**.
   2. Tarkista tietolähteen tila **Tila**-kohdassa. Valintamerkki osoittaa, että päivitys onnistui. Varoituskolmio osoittaa, että päivitys ei onnistunut. Jos varoituskolmion näkyy, ota yhteys osoitteen D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Asiakastietojen GDPR-poistopyyntöjen käsittely](media/gdpr-data-sources.png "Asiakastietojen GDPR-poistopyyntöjen käsittely")

#### <a name="manage-delete-requests-for-user-data"></a>Käyttäjätietojen poistopyyntöjen hallinta

Customer Insightsin järjestelmänvalvoja voi poistaa Customer Insightsin käyttäjätiedot seuraavasti:

1. Kirjaudu Dynamics 365 Customer Insights.
2. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Käyttöoikeudet**
3. Valitse poistettavan käyttäjän valintaruutu.
4. Valitse **Poista**.

> [!div class="mx-imgBorder"]
> ![Käyttäjätietojen poistopyyntöjen käsittely GDPR:n mukaisesti](media/gdpr-permissions.png "Käyttäjätietojen poistopyyntöjen käsittely GDPR:n mukaisesti")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Rekisteröityjen vientipyyntöihin vastaaminen GDPR:n mukaisesti

Osana sitoumustamme toimia kumppaninasi yleisen tietosuoja-asetuksen (GDPR) noudattamisessa olemme kehittäneet ohjeistuksen, joka auttaa valmistautumisessa. Tässä dokumentaatiossa on ohjeet, jotka tekemällä voidaan tukea GDPR:n vaatimustenmukaisuutta käyttäjäryhmän merkityksellisiä tietoja käytettäessä.

### <a name="manage-export-and-view-requests"></a>Vienti- ja tarkastelupyyntöjen hallinta

Oikeus tietojen siirrettävyyteen mahdollistaa sen, että rekisteröidyt voivat pyytää kopiota henkilökohtaisista tiedoistaan sähköisessä muodossa (rakenteellisena, usein käytettynä, koneellisesti luettavissa olevana ja yhteentoimivassa muodossa olevana), joka voidaan toimittaa toiselle tiedonkäsittelijälle.

#### <a name="export-customer-data-tenant-admin"></a>Asiakastietojen vieminen (vuokraajan järjestelmänvalvoja)

Vuokraajan järjestelmänvalvoja voi viedä tiedot seuraavasti:

1. Lähetä osoitteeseen D365CI@microsoft.com sähköposti, jossa määritetään asiakkaan pyynnössä oleva sähköpostiosoite. Customer Insights -ryhmä lähettää sähköpostin rekisteröidyn vuokraajan järjestelmänvalvojan sähköpostiosoitteeseen ja pyytää vahvistamaan tietojen viennin.
2. Kuittaa pyydetyn asiakkaan tietojen vientivahvistus.
3. Saat viedyt tiedot vuokraajan järjestelmänvalvojan sähköpostiosoitteen kautta.

#### <a name="export-user-data-tenant-admin"></a>Käyttäjätietojen vieminen (vuokraajan järjestelmänvalvoja)

1. Lähetä osoitteeseen D365CI@microsoft.com sähköposti, jossa määritetään käyttäjän pyynnössä oleva sähköpostiosoite. Customer Insights -ryhmä lähettää sähköpostin rekisteröidyn vuokraajan järjestelmänvalvojan sähköpostiosoitteeseen ja pyytää vahvistamaan tietojen viennin.
2. Kuittaa pyydetyn käyttäjän tietojen vientivahvistus.
3. Saat viedyt tiedot vuokraajan järjestelmänvalvojan sähköpostiosoitteen kautta.
