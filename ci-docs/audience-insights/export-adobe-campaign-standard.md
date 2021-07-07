---
title: Customer Insights -tietojen vieminen Adobe Campaign Standardiin
description: Lisätietoja käyttäjäryhmän merkityksellisten tietojen segmenttien käytöstä Adobe Campaign Standardissa.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 917ab9559416f3ee0ffd66e471e590e8da3faffc
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305382"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Customer Insightsin segmenttien käyttö Adobe Campaign Standardissa (esiversio)

Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen käyttäjä on voinut luoda segmenttejä markkinointikampanjoiden tehostamiseksi kohdistamalla kampanjat liittyviin käyttäjäryhmiin. Jos haluat käyttää käyttäjäryhmän merkityksellisiä tietoja Adobe Experience Platformista ja sovelluksista, kuten Adobe Campaign Standardista, sinun on noudatettava tässä artikkelissa kuvattuja vaiheita.

:::image type="content" source="media/ACS-flow.png" alt-text="Tässä artikkelissa kuvattujen vaiheiden prosessikaavio.":::

## <a name="prerequisites"></a>Edellytykset

-   Dynamics 365 Customer Insights -lisenssi
-   Adobe Campaign Standard -käyttöoikeus
-   Azure Blob -tallennustili

## <a name="campaign-overview"></a>Kampanjan yleiskatsaus

Katsotaanpa keksityssä esimerkkikampanjassa, miten käyttäjäryhmän merkityksellisten tietojen segmenttejä käytetään Adobe Experience Platformissa.

Oletetaan, että yrityksesi tarjoaa asiakkaillesi kuukausittain tilauspohjaisen palvelun Yhdysvalloissa. Haluat määrittää asiakkaat, joiden tilaukset on määrä uusia seuraavien kahdeksan päivän aikana, mutta jotka eivät ole uusineet tilaustaan. Säilyttääksesi nämä asiakkaat, haluat lähettää heille kampanjatarjouksen sähköpostitse Adobe Campaign Standardin avulla.

Tässä esimerkissä mainossähköpostikampanja suoritetaan kerran. Tässä artikkelissa ei ole tietoja useammasta kuin yhdestä kampanjan käytön käyttötapauksesta. Voit kuitenkin määrittää käyttäjäryhmän merkitykselliset tiedot ja Adobe Campaign Standardin toimimaan myös toistuvan kampanjaskenaarion mukaisesti.

## <a name="identify-your-target-audience"></a>Kohdekäyttäjäryhmän tunnistaminen

Skenaariossamme oletetaan, että asiakkaiden sähköpostiosoitteet ovat käytettävissä käyttäjäryhmän merkityksellisissä tiedoissa ja heidän markkinointimieltymyksensä on analysoitu segmentin jäsenten tunnistamiseksi.

[Käyttäjäryhmän merkityksellisissä tiedoissa määrittämääsi segmenttiä](segments.md) kutsutaan **ChurnProneCustomers**-segmentiksi, ja aiot lähettää näille asiakkaille sähköpostikampanjan.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Näyttökuva segmenttisivusta, jolla on luotu ChurnProneCustomers-segmentti.":::

Lähetettävässä tarjoussähköpostiviestissä on asiakkaan etunimi, sukunimi ja tilauksen päättymispäivä. Se ilmoittaa asiakkaille alennuksista, jotka he saavat, jos he uusivat tilauksensa ennen sen päättymistä.

## <a name="export-your-target-audience"></a>Kohdekäyttäjäryhmän vieminen

### <a name="configure-a-connection"></a>Yhteyden määrittäminen

Kun kohdekäyttäjäryhmä määritetty, voimme määrittää viennin käyttäjäryhmän merkityksellisistä tiedoista Azure Blob -tallennustilatilille.

1. Siirry kohdeyleisön merkityksellisissä tiedoissa kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Adobe Campaign**. Vaihtoehtoisesti voit valita **Adobe Campaign** -ruudussa **Määritä**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standardin määritysruutu.":::

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Kirjoita sen Azure Blob -tallennustilatilin **Tilin nimi**, **Tilin avain** ja **Säilö**, johon haluat viedä segmentin.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Näyttökuva varastotilin määrityksestä. "::: 

   - Lisätietoja Azure Blob -säilön tilinimen ja käyttöoikeusavaimen etsimisestä on kohdassa [Tallennustilatilin asetusten hallinta Azure-portaalissa](/azure/storage/common/storage-account-manage).

   - Lisätietoja säilön luomisesta on kohdassa [Säilön luominen](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Viimeistele yhteys valitsemalla **Tallenna**.

### <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Adobe Campaign -osasta. Jos et näe tämän osan nimeä, nämä yhteystyypit eivät ole käytettävissä.

1. Valitse segmentti, jonka haluat viedä. Tässä esimerkissä se on **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Näyttökuva segmentin valinnan käyttöliittymästä, jossa ChurnProneCustomers-segmentti on valittu.":::

1. Valitse **Seuraava**.

1. Nyt yhdistämme **lähde**-kentät käyttäjäryhmän merkityksellisten tietojen segmentistä Adobe Campaign Standard -profiilirakenteen **Kohde**-kenttien nimiin.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard -yhdyssovelluksen kenttämääritys.":::

   Jos haluat lisätä määritteitä, valitse **Lisää määrite**. Kohdenimi voi olla eri kuin lähdekentän nimi, joten voit edelleen yhdistää segmenttituottoja käyttäjäryhmän merkityksellisistä tiedoista Adobe Campaign Standardiin, jos kentillä ei ole samaa nimeä kahdessa järjestelmässä.

   > [!NOTE]
   > Sähköpostiosoitetta käytetään tunnistetietokenttänä, mutta voit yhdistää tietoja Adobe Campaign Standardiin käyttäjäryhmän perusteella minkä tahansa muun tunnisteen avulla.

1. Valitse **Tallenna**.

Kun olet tallentanut vientikohteen, löydät sen kohdasta **Tiedot** > **Viennit**.

Nyt voit [viedä segmentin tarvittaessa](export-destinations.md#run-exports-on-demand). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md) yhteydessä.

> [!NOTE]
> Varmista, että viedyn segmentin tietueiden määrä on Adobe Campaign Standard -käyttöoikeutesi sallitun rajan sisällä.

Viedyt tiedot tallennetaan edellä määritettyyn Azure Blob -säilöön. Seuraava kansiopolku luodaan automaattisesti säilöön:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Esimerkki: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standardin määrittäminen

Kun käyttäjäryhmän merkityksellisiä tietoja sisältävä segmentti viedään, se sisältää sarakkeet, jotka olet valinnut ja määrittänyt viennin kohteen edellisessä vaiheessa. Näitä tietoja voi käyttää [profiilien luomiseen Adobe Campaign Standardissa](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Adobe Campaign Standardin segmentin käyttöä varten Adobe Campaign Standardin profiilirakenne on laajennettava niin, että se sisältää kaksi lisäkenttää. Opettele [laajentamaan profiiliresurssia](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) Adobe Campaign Standardin uusilla kentillä.

Esimerkissämme nämä kentät ovat *Segmentin nimi ja Segmentin päivämäärä (valinnainen)*.

Näiden kenttien avulla määritetään profiileja Adobe Campaign Standardissa, jonka haluamme kohdistaa tähän kampanjaan.

Jos Adobe Campaign Standardissa ei ole muita tietueita kuin mitä aiot tuoda, voit ohittaa tämän vaiheen.

## <a name="import-data-into-adobe-campaign-standard"></a>Tietojen tuominen Adobe Campaign Standardiin

Nyt kun kaikki on valmista, meidän on tuotava valmiit käyttäjäryhmän tiedot käyttäjäryhmän merkityksellisistä tiedoista Adobe Campaign Standardiin profiilien luontia varten. Opettele [tuomaan profiileja Adobe Campaign Standardissa](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) työnkulun avulla.

Alla olevassa kuvassa oleva tuonnin työnkulku on määritetty suoritettavaksi kahdeksan tunnin välein. Se etsii vietyjä käyttäjäryhmän merkityksellisten tietojen segmenttejä (.csv-tiedosto Azure Blob Storagessa). Työnkulku poimii .csv-tiedoston sisällön määritetyssä sarakejärjestyksessä. Työnkulku on luotu suorittamaan virheiden peruskäsittely ja varmistamaan, että jokaisella tietueella on sähköpostiosoite ennen tietojen tallentamista Adobe Campaign Standardiin. Työnkulku poimii myös segmentin nimen tiedostonimestä, ennen kuin se lisää tai päivittää Adobe Campaign Standard -profiilin tiedot.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Näyttökuva tuonnin työnkulusta Adobe Campaign Standard -käyttöliittymässä.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Nouda kohdeyleisö Adobe Campaign Standardissa

Kun tiedot on tuotu Adobe Campaign Standardiin, [voit luoda työnkulun](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ja [tehdä kyselyjä](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) asiakkaille *segmentin nimen* ja *segmentin päivämäärän* perusteella ja valita näytekampanjalle tunnistetut profiilit.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Sähköpostin luominen ja lähettäminen Adobe Campaign Standardilla

Luo sähköpostiviestin sisältö ja [testaa ja lähetä](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) sitten sähköpostiviestisi.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Esimerkki sähköpostista, jossa on tarjous Adobe Campaign Standard -tilauksen uusimisesta.":::