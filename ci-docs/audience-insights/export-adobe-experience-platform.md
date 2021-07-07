---
title: Customer Insights -tietojen vieminen Adobe-ympäristöpalvelimeen
description: Lisätietoja Adobe Experience Platformin käyttäjäryhmien merkityksellisten tietojen segmenttien käyttämisestä.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305520"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Customer Insightsin segmenttien käyttö Adobe Experience Platformissa (esiversio)

Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen käyttäjä on voinut luoda segmenttejä markkinointikampanjoiden tehostamiseksi kohdistamalla kampanjat liittyviin käyttäjäryhmiin. Jos haluat käyttää käyttäjäryhmän merkityksellisiä tietoja Adobe Experience Platformista ja sovelluksista, kuten Adobe Campaign Standardista, sinun on noudatettava tässä artikkelissa kuvattuja vaiheita.

:::image type="content" source="media/AEP-flow.png" alt-text="Tässä artikkelissa kuvattujen vaiheiden prosessikaavio.":::

## <a name="prerequisites"></a>Edellytykset

-   Dynamics 365 Customer Insights -lisenssi
-   Adobe Experience Platform -käyttöoikeus
-   Adobe Campaign Standard -käyttöoikeus
-   Azure Blob -tallennustili

## <a name="campaign-overview"></a>Kampanjan yleiskatsaus

Katsotaanpa keksityssä esimerkkikampanjassa, miten käyttäjäryhmän merkityksellisten tietojen segmenttejä käytetään Adobe Experience Platformissa.

Oletetaan, että yrityksesi tarjoaa asiakkaillesi kuukausittain tilauspohjaisen palvelun Yhdysvalloissa. Haluat määrittää asiakkaat, joiden tilaukset on määrä uusia seuraavien kahdeksan päivän aikana, mutta jotka eivät ole uusineet tilaustaan. Säilyttääksesi nämä asiakkaat, haluat lähettää heille kampanjatarjouksen sähköpostitse Adobe-ympäristöpalvelimen avulla.

Tässä esimerkissä mainossähköpostikampanja suoritetaan kerran. Tässä artikkelissa ei ole tietoja useammasta kuin yhdestä kampanjan käytön käyttötapauksesta.

## <a name="identify-your-target-audience"></a>Kohdekäyttäjäryhmän tunnistaminen

Skenaariossamme oletetaan, että asiakkaiden sähköpostiosoitteet ovat käytettävissä käyttäjäryhmän merkityksellisissä tiedoissa ja heidän markkinointimieltymyksensä on analysoitu segmentin jäsenten tunnistamiseksi.

[Käyttäjäryhmän merkityksellisissä tiedoissa määrittämääsi segmenttiä](segments.md) kutsutaan **ChurnProneCustomers**-segmentiksi, ja aiot lähettää näille asiakkaille sähköpostikampanjan.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Näyttökuva segmenttisivusta, jolla on luotu ChurnProneCustomers-segmentti.":::

Lähetettävässä tarjoussähköpostiviestissä on asiakkaan etunimi, sukunimi ja tilauksen päättymispäivä. Se ilmoittaa asiakkaille alennuksista, jotka he saavat, jos he uusivat tilauksensa ennen sen päättymistä.

## <a name="export-your-target-audience"></a>Kohdekäyttäjäryhmän vieminen

Kun kohdekäyttäjäryhmä määritetty, voimme määrittää viennin käyttäjäryhmän merkityksellisistä tiedoista Azure Blob -tallennustilatilille.

### <a name="configure-a-connection"></a>Yhteyden määrittäminen

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Azure Blob Storage**. Vaihtoehtoisesti voit valita **Azure Blob Storage** -ruudussa **Määritä**.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob -tallennustilan määritysruutu."::: 

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Kirjoita Blob Storage -tilille **Tilin nimi**, **Tilin avain** ja **Säilö**, johon haluat viedä segmentin.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Näyttökuva varastotilin määrityksestä. "::: 
   
    - Lisätietoja Blob Storage -tilin nimen ja tiliavaimen löytämisestä on ohjeaiheessa [Azure-portaalin tallennustilatilin asetusten hallinta](/azure/storage/common/storage-account-manage).
    - Lisätietoja säilön luomisesta on kohdassa [Säilön luominen](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Viimeistele yhteys valitsemalla **Tallenna**. 

### <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Azure Blob Storage -osasta. Jos et näe tämän osan nimeä, nämä yhteystyypit eivät ole käytettävissä.

1. Valitse segmentti, jonka haluat viedä. Tässä esimerkissä se on **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Näyttökuva segmentin valinnan käyttöliittymästä, jossa ChurnProneCustomers-segmentti on valittu.":::

1. Valitse **Tallenna**.

Kun olet tallentanut vientikohteen, löydät sen kohdasta **Tiedot** > **Viennit**.

Nyt voit [viedä segmentin tarvittaessa](export-destinations.md#run-exports-on-demand). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md) yhteydessä.

> [!NOTE]
> Varmista, että viedyn segmentin tietueiden määrä on Adobe Campaign Standard -käyttöoikeutesi sallitun rajan sisällä.

Viedyt tiedot tallennetaan edellä määritettyyn Azure Blob -säilöön. Seuraava kansiopolku luodaan automaattisesti säilöön:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Esimerkki: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Vietyjen entiteettien *model.json*-arvo on tasolla *%ExportDestinationName%*.

Esimerkki: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Experience Data Model (XDM) -mallin määritteleminen Adobe-ympäristöpalvelimessa

Ennen kuin käyttäjäryhmän merkityksellisiä tietoja voi käyttää Adobe Experience Platformissa, on määritettävä Experience Data Model -rakenne ja [määritettävä tiedot reaaliaikaista asiakasprofiilia varten](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Tässä on tietoja [XDM:stä](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) ja [rakenteen koostumuksen perusasioista](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Tietojen tuominen Adobe-ympäristöpalvelimeen

Nyt kun kaikki on valmista, meidän on tuotava valmiit käyttäjäryhmän tiedot käyttäjäryhmän merkityksellisistä tiedoista Adobe ympäristöpalvelimeen profiilien luontia varten.

Aluksi [luodaan Azure Blob -tallennustilan lähdeyhteys](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Kun olet määrittänyt lähdeyhteyden, [määritä tietovirta](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pilvitallennustilan eräyhteydelle, jotta segmentin tulos tuodaan käyttäjäryhmän Adobeympäristöpalvelimeen.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Luo kohdeyleisö Adobe Campaign Standardissa

Voit lähettää sähköpostia tähän kampanjaan käyttämällä Adobe Campaign Standardia. Kun tiedot on tuotu Adobe Experience Platformiin, Adobe Campaign Standardissa on [luotava käyttäjäryhmä](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) Adobe-ympäristöpalvelimen tietojen avulla.


Opettele määrittämään kohdeyleisö Adobe-ympäristöpalvelimen tietojen perusteella Adobe Campaign Standardissa [segmentin muodostimen avulla](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html).

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Sähköpostin luominen ja lähettäminen Adobe Campaign Standardilla

Luo sähköpostiviestin sisältö ja [testaa ja lähetä](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) sitten sähköpostiviestisi.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Esimerkki sähköpostista, jossa on tarjous Adobe Campaign Standard -tilauksen uusimisesta.":::
