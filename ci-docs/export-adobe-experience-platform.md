---
title: Segmenttien vienti Adobe Experience Platformiin (esiversio)
description: Tietoja Customer Insights -segmenttien käyttämisestä Adobe Experience Platformissa.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195286"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Segmenttien vienti Adobe Experience Platformiin (esiversio)

Vie segmentit, jotka kohdistavat oleellisen kohdeyleisön Adobe Experience Platform -sovellukseen.

:::image type="content" source="media/AEP-flow.png" alt-text="Tässä artikkelissa kuvattujen vaiheiden prosessikaavio.":::

## <a name="prerequisites"></a>edellytykset

- Adobe Experience Platform -käyttöoikeus.
- Adobe Campaign Standard -lisenssi.
- [Azure Blob -tallennustilatilin](/azure/storage/blobs/create-data-lake-storage-account) nimi ja tiliavain. Lisätietoja nimen ja tiliavaimen löytämisestä on ohjeaiheessa [Azure-portaalin tallennustilatilin asetusten hallinta](/azure/storage/common/storage-account-manage).
- [Azure Blob -tallennussäilö](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

## <a name="campaign-overview"></a>Kampanjan yleiskatsaus

Katsotaanpa keksityssä esimerkkikampanjassa, miten voit käyttää Customer Insightsin segmenttejä Adobe Experience Platform -kampanjassa.

Oletetaan, että yrityksesi tarjoaa asiakkaillesi kuukausittain tilauspohjaisen palvelun Yhdysvalloissa. Haluat määrittää asiakkaat, joiden tilaukset on määrä uusia seuraavien kahdeksan päivän aikana, mutta jotka eivät ole uusineet tilaustaan. Jos haluat säilyttää nämä asiakkaat, haluat lähettää heille kampanjatarjouksen sähköpostitse Adobe Experience Platformin avulla.

Tässä esimerkissä mainossähköpostikampanja suoritetaan kerran. Tässä artikkelissa ei ole tietoja useammasta kuin yhdestä kampanjan käytön käyttötapauksesta.

## <a name="identify-your-target-audience"></a>Kohdekäyttäjäryhmän tunnistaminen

Skenaariossamme oletetaan, että asiakkaiden sähköpostiosoitteet ovat käytettävissä Customer Insightsissa ja heidän markkinointimieltymyksiksensä on analysoitu segmentin jäsenten tunnistamiseksi.

[Customer Insightsissa määrittämäsi segmentin](segments.md) nimi on **ChurnProneCustomers**, ja aiot lähettää näille asiakkaille sähköpostikampanjan.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Näyttökuva segmenttisivusta, jolla on luotu ChurnProneCustomers-segmentti.":::

Lähetettävässä tarjoussähköpostiviestissä on asiakkaan etunimi, sukunimi ja tilauksen päättymispäivä. Se ilmoittaa asiakkaille alennuksista, jotka he saavat, jos he uusivat tilauksensa ennen sen päättymistä.

## <a name="export-your-target-audience"></a>Kohdekäyttäjäryhmän vieminen

Määritetään vienti Customer Insightsista Azure Blob -tallennustilatilille.

### <a name="set-up-connection-to-azure-blob-storage"></a>Määritä yhteys Azure Blob Tallennus -säilöön

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **Azure Blob -tallennus**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Kirjoita Blob Storage -tilille **Tilin nimi**, **Tilin avain** ja **Säilö**, johon haluat viedä segmentin.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Näyttökuva varastotilin määrityksestä. ":::

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Viimeistele yhteys valitsemalla **Tallenna**.

### <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Azure Blob Storage -osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Valitse segmentti, jonka haluat viedä. Tässä esimerkissä se on **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Näyttökuva segmentin valinnan käyttöliittymästä, jossa ChurnProneCustomers-segmentti on valittu.":::

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Varmista, että viedyn segmentin tietueiden määrä on Adobe Campaign Standard -käyttöoikeutesi sallitun rajan sisällä.

Viedyt tiedot tallennetaan määritettyyn Azure Blob -säilöön. Säilöön luodaan automaattisesti seuraavat kansiopolut:

- Lähde-entiteetit ja järjestelmän luomat entiteetit:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Esimerkki: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- Vietyjen entiteettien *model.json*-arvo on tasolla *%ExportDestinationName%*.

  Esimerkki: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Määritä kokemustietomalli (XDM) Adobe Experience Platformissa

Ennen kuin Customer Insightsin vietyjä tietoja voidaan käyttää Adobe Experience Platformissa, määritä kokemustietomallirakenne ja [määritettävä tiedot reaaliaikaista asiakasprofiilia varten](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Tässä on tietoja [XDM:stä](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) ja [rakenteen koostumuksen perusasioista](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Tuo tiedot Adobe Experience Platformen

Tuo valmiit kohdeyleisötiedot Customer Insightsista ohjelmaan Adobe Experience Platform.

1. [Luo Azure Blob -tallennustilan lähdeyhteys](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Määritä tietovuo](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pilvitallennustilan eräyhteydelle, jotta segmentin tulos tuodaan Customer Insightsista Adobe Experience Platformiin.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Luo käyttäjäryhmä Adobe Campaign Standardissa

Voit lähettää sähköpostia tähän kampanjaan käyttämällä Adobe Campaign Standardia.

1. [Luo kohdeyleisö](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) Adobe Campaign Standardissa käyttämällä Adobe Experience Platform -tietoja.

1. [Käytä segmentin luontityökalua](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) Adobe Campaign Standardissa käyttäjäryhmän Adobe Experience Platform -tietojen perusteella.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Sähköpostin luominen ja lähettäminen Adobe Campaign Standardilla

Luo sähköpostiviestin sisältö ja [testaa ja lähetä](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) sitten sähköpostiviestisi.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Esimerkki sähköpostista, jossa on Adobe Campaign Standardin uusimistarjous.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
