---
title: Rekisteröityjen oikeuksien (DSR) pyynnöt GDPR:n mukaan | Microsoft Docs
description: Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuuden rekisteröidyn pyyntöön vastaaminen.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350265"
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


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]