---
title: Customer Insights -segmenttien vienti Adobe Campaign Standardiin (esiversio)
description: Tietoja Customer Insights -segmenttien käyttämisestä Adobe Campaign Standardissa.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195516"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Customer Insights -segmenttien vienti Adobe Campaign Standardiin (esiversio)

Vie segmentit, jotka kohdistavat oleellisen kohdeyleisön Adobe Campaign Standardiin.

:::image type="content" source="media/ACS-flow.png" alt-text="Tässä artikkelissa kuvattujen vaiheiden prosessikaavio.":::

## <a name="prerequisites"></a>edellytykset

- Adobe Campaign Standard -lisenssi.
- [Azure Blob -tallennustilatilin](/azure/storage/blobs/create-data-lake-storage-account) nimi ja tiliavain. Lisätietoja nimen ja tiliavaimen löytämisestä on ohjeaiheessa [Azure-portaalin tallennustilatilin asetusten hallinta](/azure/storage/common/storage-account-manage).
- [Azure Blob -tallennussäilö](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

## <a name="campaign-overview"></a>Kampanjan yleiskatsaus

Katsotaanpa keksityssä esimerkkikampanjassa, miten voit käyttää Customer Insightsin segmenttejä Adobe Experience Platform -kampanjassa.

Oletetaan, että yrityksesi tarjoaa asiakkaillesi kuukausittain tilauspohjaisen palvelun Yhdysvalloissa. Haluat määrittää asiakkaat, joiden tilaukset on määrä uusia seuraavien kahdeksan päivän aikana, mutta jotka eivät ole uusineet tilaustaan. Jos haluat säilyttää nämä asiakkaat, haluat lähettää heille kampanjatarjouksen sähköpostitse Adobe Campaign Standardin avulla.

Tässä esimerkissä mainossähköpostikampanja suoritetaan kerran. Tässä artikkelissa ei ole tietoja useammasta kuin yhdestä kampanjan käytön käyttötapauksesta. Customer Insights- ja Adobe Campaign Standard -määritykset voidaan kuitenkin määrittää toimimaan myös toistuvassa kampanjaskenaariossa.

## <a name="identify-your-target-audience"></a>Kohdekäyttäjäryhmän tunnistaminen

Skenaariossamme oletetaan, että asiakkaiden sähköpostiosoitteet ovat käytettävissä Customer Insightsissa ja heidän markkinointimieltymyksiksensä on analysoitu segmentin jäsenten tunnistamiseksi.

[Customer Insightsissa määrittämäsi segmentin](segments.md) nimi on **ChurnProneCustomers**, ja aiot lähettää näille asiakkaille sähköpostikampanjan.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Näyttökuva segmenttisivusta, jolla on luotu ChurnProneCustomers-segmentti.":::

Lähetettävässä tarjoussähköpostiviestissä on asiakkaan etunimi, sukunimi ja tilauksen päättymispäivä. Se ilmoittaa asiakkaille alennuksista, jotka he saavat, jos he uusivat tilauksensa ennen sen päättymistä.

## <a name="export-your-target-audience"></a>Kohdekäyttäjäryhmän vieminen

### <a name="set-up-connection-to-adobe-campaign"></a>Määritä yhteys Adobe Campaigniin

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **Adobe Campaign**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna **Tilin nimi**, **Tilin avain** ja **Säilö** Blob-tallennustilille.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Näyttökuva varastotilin määrityksestä. ":::

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Viimeistele yhteys valitsemalla **Tallenna**.

### <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Adobe Campaign -osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Valitse segmentti, jonka haluat viedä. Tässä esimerkissä se on **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Näyttökuva segmentin valinnan käyttöliittymästä, jossa ChurnProneCustomers-segmentti on valittu.":::

1. Valitse **Seuraava**.

1. Yhdistä Customer Insights -segmentin **lähde**-kentät Adobe Campaign Standard -profiilirakenteen **Kohde**-kenttien nimiin.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard -yhdistimen kenttien yhdistämismääritys.":::

   Jos haluat lisätä määritteitä, valitse **Lisää määrite**. Kohdenimi voi olla eri kuin lähdekentän nimi, joten voit edelleen yhdistää segmentin tuotoksen Customer Insightsista Adobe Campaign Standardiin, jos kentillä ei ole samaa nimeä kahdessa järjestelmässä.

   > [!NOTE]
   > Sähköpostiosoitetta käytetään tunnistetietokenttänä, mutta voit yhdistää tietoja Adobe Campaign Standard -kohteeseen käyttämällä mitä tahansa muuta asiakasprofiilin tunnusta.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Varmista, että viedyn segmentin tietueiden määrä on Adobe Campaign Standard -käyttöoikeutesi sallitun rajan sisällä.

Viedyt tiedot tallennetaan edellä määritettyyn Azure Blob -säilöön. Seuraava kansiopolku luodaan automaattisesti säilöön: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Esimerkki: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standardin määrittäminen

Viedyt segmentit sisältävät sarakkeet, jotka valitsit määrittäessäsi viennin kohdetta. Näitä tietoja voi käyttää [profiilien luomiseen Adobe Campaign Standardissa](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Jotta segmenttiä voidaan käyttää Adobe Campaign Standardissa, Adobe Campaign Standardin [profiilirakenne on laajennettava](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) niin, että se sisältää kaksi lisäkenttää.

Esimerkissämme nämä kentät ovat Segmentin nimi ja Segmentin päivämäärä. Näiden kenttien avulla määritetään kampanjaan halutut kohdeprofiilit Adobe Campaign Standardissa.

Jos Adobe Campaign Standardissa ei ole muita tietueita kuin mitä aiot tuoda, voit ohittaa tämän vaiheen.

## <a name="import-data-into-adobe-campaign-standard"></a>Tietojen tuominen Adobe Campaign Standardiin

Tuo valmiit käyttäjäryhmän tiedot Customer Insightsista Adobe Campaign Standardiin [luodaksesi profiilit työnkulun avulla](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Alla olevassa kuvassa oleva tuonnin työnkulku on määritetty suoritettavaksi kahdeksan tunnin välein ja etsimään vietyjä Customer Insights -segmenttejä (.csv-tiedosto Azure Blob -säilöstä). Työnkulku poimii .csv-tiedoston sisällön määritetyssä sarakejärjestyksessä. Työnkulku on luotu suorittamaan virheiden peruskäsittely ja varmistamaan, että jokaisella tietueella on sähköpostiosoite ennen tietojen tallentamista Adobe Campaign Standardiin. Työnkulku poimii myös segmentin nimen tiedostonimestä, ennen kuin se lisää tai päivittää Adobe Campaign Standard -profiilin tiedot.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Näyttökuva tuonnin työnkulusta Adobe Campaign Standard -käyttöliittymässä.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Nouda käyttäjäryhmä Adobe Campaign Standardissa

Kun tiedot on tuotu Adobe Campaign Standardiin, [voit luoda työnkulun](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ja [tehdä kyselyjä](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) asiakkaille segmentin nimen ja segmentin päivämäärän perusteella ja valita näytekampanjalle tunnistetut profiilit.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Sähköpostin luominen ja lähettäminen Adobe Campaign Standardilla

Luo sähköpostiviestin sisältö ja [testaa ja lähetä](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) sitten sähköpostiviestisi.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Esimerkki sähköpostista, jossa on Adobe Campaign Standardin uusimistarjous.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
