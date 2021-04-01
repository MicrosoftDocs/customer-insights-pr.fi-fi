---
title: Customer Insights -tietojen vieminen Adobe-ympäristöpalvelimeen
description: Lisätietoja käyttäjäryhmän merkityksellisten tietojen segmenttien käytöstä Adobe-ympäristöpalvelimessa.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596265"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="cf217-103">Customer Insightsin segmenttien käyttö Adobe Experience Platformissa (esiversio)</span><span class="sxs-lookup"><span data-stu-id="cf217-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="cf217-104">Dynamics 365 Customer Insights -yleisötietojen käyttäjänä olet saattanut luoda segmenttejä markkinointikampanjoidesi tehostamiseksi kohdistamalla ne oleellisiin käyttäjäryhmiin.</span><span class="sxs-lookup"><span data-stu-id="cf217-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="cf217-105">Jos haluat käyttää käyttäjäryhmän merkityksellisiä tietoja Adobe Experience Platformista ja sovelluksista, kuten Adobe Campaign Standardista, sinun on noudatettava tässä artikkelissa kuvattuja vaiheita.</span><span class="sxs-lookup"><span data-stu-id="cf217-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Tässä artikkelissa kuvattujen vaiheiden prosessikaavio.":::

## <a name="prerequisites"></a><span data-ttu-id="cf217-107">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="cf217-107">Prerequisites</span></span>

-   <span data-ttu-id="cf217-108">Dynamics 365 Customer Insights -lisenssi</span><span class="sxs-lookup"><span data-stu-id="cf217-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="cf217-109">Adobe Experience Platform -käyttöoikeus</span><span class="sxs-lookup"><span data-stu-id="cf217-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="cf217-110">Adobe Campaign Standard -käyttöoikeus</span><span class="sxs-lookup"><span data-stu-id="cf217-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="cf217-111">Azure Blob -tallennustili</span><span class="sxs-lookup"><span data-stu-id="cf217-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="cf217-112">Kampanjan yleiskatsaus</span><span class="sxs-lookup"><span data-stu-id="cf217-112">Campaign Overview</span></span>

<span data-ttu-id="cf217-113">Katsotaanpa keksityssä esimerkkikampanjassa, miten käyttäjäryhmän merkityksellisten tietojen segmenttejä käytetään Adobe Experience Platformissa.</span><span class="sxs-lookup"><span data-stu-id="cf217-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="cf217-114">Oletetaan, että yrityksesi tarjoaa asiakkaillesi kuukausittain tilauspohjaisen palvelun Yhdysvalloissa.</span><span class="sxs-lookup"><span data-stu-id="cf217-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="cf217-115">Haluat määrittää asiakkaat, joiden tilaukset on määrä uusia seuraavien kahdeksan päivän aikana, mutta jotka eivät ole uusineet tilaustaan.</span><span class="sxs-lookup"><span data-stu-id="cf217-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="cf217-116">Säilyttääksesi nämä asiakkaat, haluat lähettää heille kampanjatarjouksen sähköpostitse Adobe-ympäristöpalvelimen avulla.</span><span class="sxs-lookup"><span data-stu-id="cf217-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="cf217-117">Tässä esimerkissä mainossähköpostikampanja suoritetaan kerran.</span><span class="sxs-lookup"><span data-stu-id="cf217-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="cf217-118">Tässä artikkelissa ei ole tietoja useammasta kuin yhdestä kampanjan käytön käyttötapauksesta.</span><span class="sxs-lookup"><span data-stu-id="cf217-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="cf217-119">Kohdekäyttäjäryhmän tunnistaminen</span><span class="sxs-lookup"><span data-stu-id="cf217-119">Identify your target audience</span></span>

<span data-ttu-id="cf217-120">Skenaariossamme oletetaan, että asiakkaiden sähköpostiosoitteet ovat käytettävissä käyttäjäryhmän merkityksellisissä tiedoissa ja heidän markkinointimieltymyksensä on analysoitu segmentin jäsenten tunnistamiseksi.</span><span class="sxs-lookup"><span data-stu-id="cf217-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="cf217-121">[Käyttäjäryhmän merkityksellisissä tiedoissa määrittämääsi segmenttiä](segments.md) kutsutaan **ChurnProneCustomers**-segmentiksi, ja aiot lähettää näille asiakkaille sähköpostikampanjan.</span><span class="sxs-lookup"><span data-stu-id="cf217-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Näyttökuva segmenttisivusta, jolla on luotu ChurnProneCustomers-segmentti.":::

<span data-ttu-id="cf217-123">Lähetettävässä tarjoussähköpostiviestissä on asiakkaan etunimi, sukunimi ja tilauksen päättymispäivä.</span><span class="sxs-lookup"><span data-stu-id="cf217-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="cf217-124">Se ilmoittaa asiakkaille alennuksista, jotka he saavat, jos he uusivat tilauksensa ennen sen päättymistä.</span><span class="sxs-lookup"><span data-stu-id="cf217-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="cf217-125">Kohdekäyttäjäryhmän vieminen</span><span class="sxs-lookup"><span data-stu-id="cf217-125">Export your target audience</span></span>

<span data-ttu-id="cf217-126">Kun kohdekäyttäjäryhmä määritetty, voimme määrittää viennin käyttäjäryhmän merkityksellisistä tiedoista Azure Blob -tallennustilatilille.</span><span class="sxs-lookup"><span data-stu-id="cf217-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="cf217-127">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="cf217-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="cf217-128">Valitse **Azure Blob -säilö** -ruudussa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="cf217-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob -tallennustilan määritysruutu.":::

1. <span data-ttu-id="cf217-130">Anna **näyttönimi** uudelle vientikohteelle ja kirjoita sitten sen Azure Blob -tallennustilatilin **Tilin nimi**, **Tiliavain** ja **Säilö**, johon haluat viedä segmentin.</span><span class="sxs-lookup"><span data-stu-id="cf217-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Näyttökuva varastotilin määrityksestä. "::: 

   - <span data-ttu-id="cf217-132">Lisätietoja Azure Blob -säilön tilinimen ja käyttöoikeusavaimen etsimisestä on kohdassa [Tallennustilatilin asetusten hallinta Azure-portaalissa](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="cf217-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="cf217-133">Lisätietoja säilön luomisesta on kohdassa [Säilön luominen](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="cf217-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="cf217-134">Valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="cf217-134">Select **Next**.</span></span>

1. <span data-ttu-id="cf217-135">Valitse segmentti, jonka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="cf217-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="cf217-136">Tässä esimerkissä se on **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="cf217-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Näyttökuva segmentin valinnan käyttöliittymästä, jossa ChurnProneCustomers-segmentti on valittu.":::

1. <span data-ttu-id="cf217-138">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="cf217-138">Select **Save**.</span></span>

<span data-ttu-id="cf217-139">Kun olet tallentanut vientikohteen, löydät sen kohdasta **Järjestelmänvalvoja** > **Viennit** > **Omat vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="cf217-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Näyttökuva, jossa vienti- ja näytesegmentti on korostettu.":::

<span data-ttu-id="cf217-141">Nyt voit [viedä segmentin tarvittaessa](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="cf217-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="cf217-142">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="cf217-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="cf217-143">Varmista, että viedyn segmentin tietueiden määrä on Adobe Campaign Standard -käyttöoikeutesi sallitun rajan sisällä.</span><span class="sxs-lookup"><span data-stu-id="cf217-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="cf217-144">Viedyt tiedot tallennetaan edellä määritettyyn Azure Blob -säilöön.</span><span class="sxs-lookup"><span data-stu-id="cf217-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="cf217-145">Seuraava kansiopolku luodaan automaattisesti säilöön:</span><span class="sxs-lookup"><span data-stu-id="cf217-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="cf217-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="cf217-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="cf217-147">Esimerkki: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="cf217-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="cf217-148">Vietyjen entiteettien *model.json*-arvo on tasolla *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="cf217-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="cf217-149">Esimerkki: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="cf217-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="cf217-150">Experience Data Model (XDM) -mallin määritteleminen Adobe-ympäristöpalvelimessa</span><span class="sxs-lookup"><span data-stu-id="cf217-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="cf217-151">Ennen kuin käyttäjäryhmän merkityksellisiä tietoja voi käyttää Adobe Experience Platformissa, on määritettävä Experience Data Model -rakenne ja [määritettävä tiedot reaaliaikaista asiakasprofiilia varten](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="cf217-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="cf217-152">Tässä on tietoja [XDM:stä](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) ja [rakenteen koostumuksen perusasioista](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="cf217-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="cf217-153">Tietojen tuominen Adobe-ympäristöpalvelimeen</span><span class="sxs-lookup"><span data-stu-id="cf217-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="cf217-154">Nyt kun kaikki on valmista, meidän on tuotava valmiit käyttäjäryhmän tiedot käyttäjäryhmän merkityksellisistä tiedoista Adobe ympäristöpalvelimeen profiilien luontia varten.</span><span class="sxs-lookup"><span data-stu-id="cf217-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="cf217-155">Aluksi [luodaan Azure Blob -tallennustilan lähdeyhteys](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="cf217-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="cf217-156">Kun olet määrittänyt lähdeyhteyden, [määritä tietovirta](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pilvitallennustilan eräyhteydelle, jotta segmentin tulos tuodaan käyttäjäryhmän Adobeympäristöpalvelimeen.</span><span class="sxs-lookup"><span data-stu-id="cf217-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="cf217-157">Luo kohdeyleisö Adobe Campaign Standardissa</span><span class="sxs-lookup"><span data-stu-id="cf217-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="cf217-158">Tämän kampanjan sähköpostiviestin lähettämiseen käytetään Adobe Campaign Standardia.</span><span class="sxs-lookup"><span data-stu-id="cf217-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="cf217-159">Kun tiedot on tuotu Adobe Experience Platformiin, Adobe Campaign Standardissa on [luotava käyttäjäryhmä](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) Adobe-ympäristöpalvelimen tietojen avulla.</span><span class="sxs-lookup"><span data-stu-id="cf217-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="cf217-160">Opettele määrittämään kohdeyleisö Adobe-ympäristöpalvelimen tietojen perusteella Adobe Campaign Standardissa [segmentin muodostimen avulla](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment).</span><span class="sxs-lookup"><span data-stu-id="cf217-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="cf217-161">Sähköpostin luominen ja lähettäminen Adobe Campaign Standardilla</span><span class="sxs-lookup"><span data-stu-id="cf217-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="cf217-162">Luo sähköpostiviestin sisältö ja [testaa ja lähetä](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) sitten sähköpostiviestisi.</span><span class="sxs-lookup"><span data-stu-id="cf217-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Esimerkki sähköpostista, jossa on tarjous Adobe Campaign Standard -tilauksen uusimisesta.":::