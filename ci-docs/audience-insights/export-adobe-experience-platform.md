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
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="bb5fb-103">Customer Insightsin segmenttien käyttö Adobe Experience Platformissa (esiversio)</span><span class="sxs-lookup"><span data-stu-id="bb5fb-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="bb5fb-104">Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen käyttäjä on voinut luoda segmenttejä markkinointikampanjoiden tehostamiseksi kohdistamalla kampanjat liittyviin käyttäjäryhmiin.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="bb5fb-105">Jos haluat käyttää käyttäjäryhmän merkityksellisiä tietoja Adobe Experience Platformista ja sovelluksista, kuten Adobe Campaign Standardista, sinun on noudatettava tässä artikkelissa kuvattuja vaiheita.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Tässä artikkelissa kuvattujen vaiheiden prosessikaavio.":::

## <a name="prerequisites"></a><span data-ttu-id="bb5fb-107">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="bb5fb-107">Prerequisites</span></span>

-   <span data-ttu-id="bb5fb-108">Dynamics 365 Customer Insights -lisenssi</span><span class="sxs-lookup"><span data-stu-id="bb5fb-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="bb5fb-109">Adobe Experience Platform -käyttöoikeus</span><span class="sxs-lookup"><span data-stu-id="bb5fb-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="bb5fb-110">Adobe Campaign Standard -käyttöoikeus</span><span class="sxs-lookup"><span data-stu-id="bb5fb-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="bb5fb-111">Azure Blob -tallennustili</span><span class="sxs-lookup"><span data-stu-id="bb5fb-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="bb5fb-112">Kampanjan yleiskatsaus</span><span class="sxs-lookup"><span data-stu-id="bb5fb-112">Campaign Overview</span></span>

<span data-ttu-id="bb5fb-113">Katsotaanpa keksityssä esimerkkikampanjassa, miten käyttäjäryhmän merkityksellisten tietojen segmenttejä käytetään Adobe Experience Platformissa.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="bb5fb-114">Oletetaan, että yrityksesi tarjoaa asiakkaillesi kuukausittain tilauspohjaisen palvelun Yhdysvalloissa.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="bb5fb-115">Haluat määrittää asiakkaat, joiden tilaukset on määrä uusia seuraavien kahdeksan päivän aikana, mutta jotka eivät ole uusineet tilaustaan.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="bb5fb-116">Säilyttääksesi nämä asiakkaat, haluat lähettää heille kampanjatarjouksen sähköpostitse Adobe-ympäristöpalvelimen avulla.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="bb5fb-117">Tässä esimerkissä mainossähköpostikampanja suoritetaan kerran.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="bb5fb-118">Tässä artikkelissa ei ole tietoja useammasta kuin yhdestä kampanjan käytön käyttötapauksesta.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="bb5fb-119">Kohdekäyttäjäryhmän tunnistaminen</span><span class="sxs-lookup"><span data-stu-id="bb5fb-119">Identify your target audience</span></span>

<span data-ttu-id="bb5fb-120">Skenaariossamme oletetaan, että asiakkaiden sähköpostiosoitteet ovat käytettävissä käyttäjäryhmän merkityksellisissä tiedoissa ja heidän markkinointimieltymyksensä on analysoitu segmentin jäsenten tunnistamiseksi.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="bb5fb-121">[Käyttäjäryhmän merkityksellisissä tiedoissa määrittämääsi segmenttiä](segments.md) kutsutaan **ChurnProneCustomers**-segmentiksi, ja aiot lähettää näille asiakkaille sähköpostikampanjan.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Näyttökuva segmenttisivusta, jolla on luotu ChurnProneCustomers-segmentti.":::

<span data-ttu-id="bb5fb-123">Lähetettävässä tarjoussähköpostiviestissä on asiakkaan etunimi, sukunimi ja tilauksen päättymispäivä.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="bb5fb-124">Se ilmoittaa asiakkaille alennuksista, jotka he saavat, jos he uusivat tilauksensa ennen sen päättymistä.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="bb5fb-125">Kohdekäyttäjäryhmän vieminen</span><span class="sxs-lookup"><span data-stu-id="bb5fb-125">Export your target audience</span></span>

<span data-ttu-id="bb5fb-126">Kun kohdekäyttäjäryhmä määritetty, voimme määrittää viennin käyttäjäryhmän merkityksellisistä tiedoista Azure Blob -tallennustilatilille.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="bb5fb-127">Yhteyden määrittäminen</span><span class="sxs-lookup"><span data-stu-id="bb5fb-127">Configure a connection</span></span>

1. <span data-ttu-id="bb5fb-128">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bb5fb-129">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Azure Blob Storage**. Vaihtoehtoisesti voit valita **Azure Blob Storage** -ruudussa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob -tallennustilan määritysruutu."::: 

1. <span data-ttu-id="bb5fb-131">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bb5fb-132">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bb5fb-133">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bb5fb-134">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-134">Choose who can use this connection.</span></span> <span data-ttu-id="bb5fb-135">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bb5fb-136">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bb5fb-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bb5fb-137">Kirjoita Blob Storage -tilille **Tilin nimi**, **Tilin avain** ja **Säilö**, johon haluat viedä segmentin.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Näyttökuva varastotilin määrityksestä. "::: 
   
    - <span data-ttu-id="bb5fb-139">Lisätietoja Blob Storage -tilin nimen ja tiliavaimen löytämisestä on ohjeaiheessa [Azure-portaalin tallennustilatilin asetusten hallinta](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="bb5fb-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="bb5fb-140">Lisätietoja säilön luomisesta on kohdassa [Säilön luominen](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="bb5fb-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="bb5fb-141">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="bb5fb-142">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="bb5fb-142">Configure an export</span></span>

<span data-ttu-id="bb5fb-143">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bb5fb-144">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bb5fb-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bb5fb-145">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bb5fb-146">Luo uusi vienti valitsemalla **Lisää vienti**.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="bb5fb-147">Valitse **Yhteys vientiä varten** -kentässä yhteys Azure Blob Storage -osasta.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="bb5fb-148">Jos et näe tämän osan nimeä, nämä yhteystyypit eivät ole käytettävissä.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="bb5fb-149">Valitse segmentti, jonka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="bb5fb-150">Tässä esimerkissä se on **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Näyttökuva segmentin valinnan käyttöliittymästä, jossa ChurnProneCustomers-segmentti on valittu.":::

1. <span data-ttu-id="bb5fb-152">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-152">Select **Save**.</span></span>

<span data-ttu-id="bb5fb-153">Kun olet tallentanut vientikohteen, löydät sen kohdasta **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="bb5fb-154">Nyt voit [viedä segmentin tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bb5fb-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="bb5fb-155">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bb5fb-156">Varmista, että viedyn segmentin tietueiden määrä on Adobe Campaign Standard -käyttöoikeutesi sallitun rajan sisällä.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="bb5fb-157">Viedyt tiedot tallennetaan edellä määritettyyn Azure Blob -säilöön.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="bb5fb-158">Seuraava kansiopolku luodaan automaattisesti säilöön:</span><span class="sxs-lookup"><span data-stu-id="bb5fb-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="bb5fb-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="bb5fb-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="bb5fb-160">Esimerkki: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="bb5fb-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="bb5fb-161">Vietyjen entiteettien *model.json*-arvo on tasolla *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="bb5fb-162">Esimerkki: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="bb5fb-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="bb5fb-163">Experience Data Model (XDM) -mallin määritteleminen Adobe-ympäristöpalvelimessa</span><span class="sxs-lookup"><span data-stu-id="bb5fb-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="bb5fb-164">Ennen kuin käyttäjäryhmän merkityksellisiä tietoja voi käyttää Adobe Experience Platformissa, on määritettävä Experience Data Model -rakenne ja [määritettävä tiedot reaaliaikaista asiakasprofiilia varten](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="bb5fb-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="bb5fb-165">Tässä on tietoja [XDM:stä](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) ja [rakenteen koostumuksen perusasioista](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="bb5fb-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="bb5fb-166">Tietojen tuominen Adobe-ympäristöpalvelimeen</span><span class="sxs-lookup"><span data-stu-id="bb5fb-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="bb5fb-167">Nyt kun kaikki on valmista, meidän on tuotava valmiit käyttäjäryhmän tiedot käyttäjäryhmän merkityksellisistä tiedoista Adobe ympäristöpalvelimeen profiilien luontia varten.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="bb5fb-168">Aluksi [luodaan Azure Blob -tallennustilan lähdeyhteys](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="bb5fb-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="bb5fb-169">Kun olet määrittänyt lähdeyhteyden, [määritä tietovirta](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pilvitallennustilan eräyhteydelle, jotta segmentin tulos tuodaan käyttäjäryhmän Adobeympäristöpalvelimeen.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="bb5fb-170">Luo kohdeyleisö Adobe Campaign Standardissa</span><span class="sxs-lookup"><span data-stu-id="bb5fb-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="bb5fb-171">Voit lähettää sähköpostia tähän kampanjaan käyttämällä Adobe Campaign Standardia.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="bb5fb-172">Kun tiedot on tuotu Adobe Experience Platformiin, Adobe Campaign Standardissa on [luotava käyttäjäryhmä](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) Adobe-ympäristöpalvelimen tietojen avulla.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="bb5fb-173">Opettele määrittämään kohdeyleisö Adobe-ympäristöpalvelimen tietojen perusteella Adobe Campaign Standardissa [segmentin muodostimen avulla](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html).</span><span class="sxs-lookup"><span data-stu-id="bb5fb-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="bb5fb-174">Sähköpostin luominen ja lähettäminen Adobe Campaign Standardilla</span><span class="sxs-lookup"><span data-stu-id="bb5fb-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="bb5fb-175">Luo sähköpostiviestin sisältö ja [testaa ja lähetä](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) sitten sähköpostiviestisi.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Esimerkki sähköpostista, jossa on tarjous Adobe Campaign Standard -tilauksen uusimisesta.":::
