---
title: Linkin luominen kohdeyleisön ja sitoutumistietojen välille
description: Luomalla aktiivisen linkin käyttäjäryhmätietojen ja sitoutumistietojen välille voit mahdollistaa tietojen kaksisuuntaisen jakamisen.
ms.date: 09/08/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 56adc206d83bc6e34a55f11383393b5ac66da531
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229868"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Linkin luominen kohdeyleisön ja sitoutumistietojen välille

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Integraatio sitoutumistietojen ja käyttäjäryhmätietojen välillä yhdistää ympäristöt molemmista ominaisuuksista ja mahdollistaa tietojen jakamisen kaksisuuntaisesti niiden välillä.

Käyttämällä yhtenäisiä profiileja ja segmenttejä saat käyttäjäryhmätietoja analyysivaihtoehdoista. Vie tapahtumia, joilla on suuri liiketoiminta-arvo sitouttamistietojen perusteella. Näiden tapahtumien avulla voit lisätä tietoja yhtenäisiksi profiileiksi käyttäjäryhmätietojen perusteella.

## <a name="prerequisites"></a>Edellytykset

- Käyttäjäryhmätiedot on tallennettava Azure Data Lake Storage -tilillesi tai [Microsoft Dataversen](/powerapps/maker/data-platform/data-platform-intro)&ndash;hallitsemaan Data Lake -tallennustilaan. 
- Käyttäjäryhmätietojen tulisi olla liitetty Dataverse-ympäristöön. Jos ympäristö käyttää myös Dataverseä tietojen tallennustilana, varmista, että valitset **Ota tietojen jakaminen käyttöön** -asetuksen käyttäjäryhmän merkityksellisissä tiedoissa. Lisätietoja on kohdassa [Ympäristön luominen ja määrittäminen käyttäjäryhmän merkityksellisissä tiedoissa](../audience-insights/create-environment.md).
- Tarvitset järjestelmänvalvojan oikeudet sekä sitouttamistieto- että käyttäjäryhmän tietoympäristöihin.
- Linkitettyjen ympäristöjen on oltava samalla maantieteellisellä alueella.

> [!NOTE]
> - Jos käyttäjäryhmätiedot-tilauksesi on kokeiluversio, joka käyttää käyttäjäryhmätietoja sisäisesti hallitussa Data Lake -tallennustilassa, ota yhteyttä osoitteeseen [pirequest@microsoft.com](mailto:pirequest@microsoft.com) saadaksesi apua. 
> - Jos käyttäjäryhmän tietoympäristö käyttää omaa Azure Data Lake Storageasi tietojen tallentamiseen, sinun on lisättävä tallennustilatiliisi sitouttamistietojen Azure-palvelun pääkäyttäjä. Lisätietoja on kohdassa [Yhteyden muodostaminen Azure Data Lake Storage -tiliin, jolla on Azure-palvelun käyttäjäryhmätietoja](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Ympäristölinkin luominen

Voit luoda ympäristölinkin päivittämällä **Hallinta** > **Ympäristö** -asetukset seurantatietojen perusteella.

**Aktiivisen linkin luominen kohdeyleisön ja sitoutumistietojen välille**

1. Valitse **Ympäristön hallinta** -sivulla **Linkitä ympäristöt** -välilehti.

    :::image type="content" source="media/integrate1.png" alt-text="Aseta ympäristö.":::

1. Valitse **Asennusympäristöt** vasemmasta yläkulmasta tai näytön alareunasta.

     :::image type="content" source="media/integrate2.png" alt-text="Valitse käyttäjäryhmien merkityksellisten tietojen ympäristö.":::

1. Valitse käyttäjäryhmätietojen ympäristö ja valitse sitten **Valmis**. Nyt voit valita valinnaisia ominaisuuksia linkitettyihin ympäristöihin.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Ota käyttöön käyttäjäryhmän yhdistetyt profiilit -määritteet ja -segmentit

Linkitettyäsi ympäristöt voit valita valinnaisia ominaisuuksia linkitettyihin ympäristöihin. Nämä ominaisuudet mahdollistavat yhtenäiset profiilimääritteet ja segmentit käyttäjäryhmätietojen perusteella, jotta asiakasdataa voidaan vuorovaikutteisesti analysoida.

> [!IMPORTANT]
> Jotta käyttäjäryhmätietoja ilmestyy sitoutumistietoihin, sinun tulee ensin [suorittaa yhdistämis- ja jatkoprosessit](../audience-insights/merge-entities.md). Myöhemmät prosessit ovat tärkeitä, koska ne luovat ainutlaatuisen taulukon, joka valmistelee käyttäjäryhmien segmentit jaettavaksi sitoutumistietojen kanssa. (Jos järjestelmä päivitetään, se sisältää automaattisesti jatkoprosessit.)

**Verkkotietojen analysoiminen sitoutumistietoina**

1. Ota **Ympäristön hallinta** -sivulla käyttöön **Jaa käyttäjäryhmätietoja sitoutumistietojen kanssa** -vaihto ja valitse sitten **Seuraava**.

    :::image type="content" source="media/integrate4.png" alt-text="Valitse ominaisuudet.":::

1. Valitse yhtenäisten profiilien määritteet, joista tulee sitoutumistietojen dimensioita. (Kaikki määritteet eivät ole hyödyllisiä dimensioita. Et esimerkiksi todennäköisesti tarvitse **etunimi**- tai **sukunimi**-määritettä sivustotapahtumien analysointia varten.)

    :::image type="content" source="media/integrate5.png" alt-text="Valitse dimensioita.":::

   >[!NOTE]
   > Kaikki käyttäjäryhmätietojen profiilimääritteet, jotka edustavat tunnisteita (kuten **tunnus** ja **vaihtoehtoinen tunnus**), suodatetaan pois käytettävissä olevista määritteistä, ja niistä tulee seurantatietojen dimensioita.

1. Kun olet valinnut määritteet, valitse **Seuraava**.
1. Lisää käyttäjät, jotka voivat tarkastella käyttäjäryhmän tietoprofiilin dimensioita ja segmenttejä sitoutumistiedoissa.

    :::image type="content" source="media/integrate6.png" alt-text="Hallitse käyttöoikeuksia asiakastietoihin.":::

   > [!IMPORTANT]
   > Jos et lisää käyttäjiä erikseen tässä vaiheessa, tiedot piilotetaan käyttäjiltä sitoutumistiedoissa.
   > Jotta käyttäjäryhmätietoja ilmestyy sitoutumistietoihin, sinun tulee ensin [suorittaa yhdistämis- ja jatkoprosessit](../audience-insights/merge-entities.md). Myöhemmät prosessit ovat tärkeitä, koska ne luovat ainutlaatuisen taulukon, joka valmistelee käyttäjäryhmien segmentit jaettavaksi sitoutumistietojen kanssa. (Jos järjestelmä päivitetään, se sisältää automaattisesti jatkoprosessit.)

1. Tarkista valinta ja valitse sitten **Valmis**.

    :::image type="content" source="media/integrate7.png" alt-text="Tarkista asiakastietojen asetukset.":::

## <a name="export-refined-events-to-audience-insights"></a>Täsmennettyjen tapahtumien vienti käyttäjäryhmän merkityksellisiin tietoihin

Kun olet luonut linkin ympäristöjen välille, voit viedä täsmennettyjä tapahtumia sitoutumistiedoista käyttäjäryhmätietoihin ja käyttää niitä uutena tietolähteenä. 

Lisätietoja on kohdassa [Sitoutumistietojen verkkotietojen integroiminen käyttäjäryhmätietoihin](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
