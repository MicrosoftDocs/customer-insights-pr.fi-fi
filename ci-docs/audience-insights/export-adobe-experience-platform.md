---
title: Customer Insights -tietojen vieminen Adobe-ympäristöpalvelimeen
description: Lisätietoja käyttäjäryhmän merkityksellisten tietojen segmenttien käytöstä Adobe-ympäristöpalvelimessa.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760097"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="d106e-103">Customer Insightsin segmenttien käyttö Adobe Experience Platformissa (esiversio)</span><span class="sxs-lookup"><span data-stu-id="d106e-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="d106e-104">Dynamics 365 Customer Insights -yleisötietojen käyttäjänä olet saattanut luoda segmenttejä markkinointikampanjoidesi tehostamiseksi kohdistamalla ne oleellisiin käyttäjäryhmiin.</span><span class="sxs-lookup"><span data-stu-id="d106e-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="d106e-105">Jos haluat käyttää käyttäjäryhmän merkityksellisiä tietoja Adobe Experience Platformista ja sovelluksista, kuten Adobe Campaign Standardista, sinun on noudatettava tässä artikkelissa kuvattuja vaiheita.</span><span class="sxs-lookup"><span data-stu-id="d106e-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Tässä artikkelissa kuvattujen vaiheiden prosessikaavio.":::

## <a name="prerequisites"></a><span data-ttu-id="d106e-107">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="d106e-107">Prerequisites</span></span>

-   <span data-ttu-id="d106e-108">Dynamics 365 Customer Insights -lisenssi</span><span class="sxs-lookup"><span data-stu-id="d106e-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="d106e-109">Adobe Experience Platform -käyttöoikeus</span><span class="sxs-lookup"><span data-stu-id="d106e-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="d106e-110">Adobe Campaign Standard -käyttöoikeus</span><span class="sxs-lookup"><span data-stu-id="d106e-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="d106e-111">Azure Blob -tallennustili</span><span class="sxs-lookup"><span data-stu-id="d106e-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="d106e-112">Kampanjan yleiskatsaus</span><span class="sxs-lookup"><span data-stu-id="d106e-112">Campaign Overview</span></span>

<span data-ttu-id="d106e-113">Katsotaanpa keksityssä esimerkkikampanjassa, miten käyttäjäryhmän merkityksellisten tietojen segmenttejä käytetään Adobe Experience Platformissa.</span><span class="sxs-lookup"><span data-stu-id="d106e-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="d106e-114">Oletetaan, että yrityksesi tarjoaa asiakkaillesi kuukausittain tilauspohjaisen palvelun Yhdysvalloissa.</span><span class="sxs-lookup"><span data-stu-id="d106e-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="d106e-115">Haluat määrittää asiakkaat, joiden tilaukset on määrä uusia seuraavien kahdeksan päivän aikana, mutta jotka eivät ole uusineet tilaustaan.</span><span class="sxs-lookup"><span data-stu-id="d106e-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="d106e-116">Säilyttääksesi nämä asiakkaat, haluat lähettää heille kampanjatarjouksen sähköpostitse Adobe-ympäristöpalvelimen avulla.</span><span class="sxs-lookup"><span data-stu-id="d106e-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="d106e-117">Tässä esimerkissä mainossähköpostikampanja suoritetaan kerran.</span><span class="sxs-lookup"><span data-stu-id="d106e-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="d106e-118">Tässä artikkelissa ei ole tietoja useammasta kuin yhdestä kampanjan käytön käyttötapauksesta.</span><span class="sxs-lookup"><span data-stu-id="d106e-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="d106e-119">Kohdekäyttäjäryhmän tunnistaminen</span><span class="sxs-lookup"><span data-stu-id="d106e-119">Identify your target audience</span></span>

<span data-ttu-id="d106e-120">Skenaariossamme oletetaan, että asiakkaiden sähköpostiosoitteet ovat käytettävissä käyttäjäryhmän merkityksellisissä tiedoissa ja heidän markkinointimieltymyksensä on analysoitu segmentin jäsenten tunnistamiseksi.</span><span class="sxs-lookup"><span data-stu-id="d106e-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="d106e-121">[Käyttäjäryhmän merkityksellisissä tiedoissa määrittämääsi segmenttiä](segments.md) kutsutaan **ChurnProneCustomers**-segmentiksi, ja aiot lähettää näille asiakkaille sähköpostikampanjan.</span><span class="sxs-lookup"><span data-stu-id="d106e-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Näyttökuva segmenttisivusta, jolla on luotu ChurnProneCustomers-segmentti.":::

<span data-ttu-id="d106e-123">Lähetettävässä tarjoussähköpostiviestissä on asiakkaan etunimi, sukunimi ja tilauksen päättymispäivä.</span><span class="sxs-lookup"><span data-stu-id="d106e-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="d106e-124">Se ilmoittaa asiakkaille alennuksista, jotka he saavat, jos he uusivat tilauksensa ennen sen päättymistä.</span><span class="sxs-lookup"><span data-stu-id="d106e-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="d106e-125">Kohdekäyttäjäryhmän vieminen</span><span class="sxs-lookup"><span data-stu-id="d106e-125">Export your target audience</span></span>

<span data-ttu-id="d106e-126">Kun kohdekäyttäjäryhmä määritetty, voimme määrittää viennin käyttäjäryhmän merkityksellisistä tiedoista Azure Blob -tallennustilatilille.</span><span class="sxs-lookup"><span data-stu-id="d106e-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="d106e-127">Yhteyden määrittäminen</span><span class="sxs-lookup"><span data-stu-id="d106e-127">Configure a connection</span></span>

1. <span data-ttu-id="d106e-128">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="d106e-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d106e-129">Valitse **Lisää yhteys** ja valitse **Azure Blob Storage** tai valitse **Määritys** **Azure Blob Storage** -ruudussa:</span><span class="sxs-lookup"><span data-stu-id="d106e-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile:</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob -tallennustilan määritysruutu."::: <span data-ttu-id="d106e-131">yhteyden määrittäminen.</span><span class="sxs-lookup"><span data-stu-id="d106e-131">to configure the connection.</span></span>

1. <span data-ttu-id="d106e-132">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="d106e-132">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d106e-133">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="d106e-133">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d106e-134">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="d106e-134">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d106e-135">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="d106e-135">Choose who can use this connection.</span></span> <span data-ttu-id="d106e-136">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="d106e-136">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d106e-137">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d106e-137">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d106e-138">Kirjoita Blob-tallennustilatilin **Tilin nimi**, **Tilin avain** ja **Säilö**, johon haluat viedä segmentin.</span><span class="sxs-lookup"><span data-stu-id="d106e-138">Enter **Account name**, **Account key**, and **Container** for your Blob storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Näyttökuva varastotilin määrityksestä. "::: 
   
    - <span data-ttu-id="d106e-140">Lisätietoja Blob-tallennustilatilin nimen ja tiliavaimen löytämisestä on ohjeaiheessa [Azure-portaalin tallennustilatilin asetusten hallinta](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="d106e-140">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="d106e-141">Lisätietoja säilön luomisesta on kohdassa [Säilön luominen](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="d106e-141">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="d106e-142">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="d106e-142">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="d106e-143">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="d106e-143">Configure an export</span></span>

<span data-ttu-id="d106e-144">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="d106e-144">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d106e-145">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d106e-145">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d106e-146">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="d106e-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d106e-147">Luo uusi vienti valitsemalla **Lisää vienti**.</span><span class="sxs-lookup"><span data-stu-id="d106e-147">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="d106e-148">Valitse **Yhteys vientiä varten** -kentässä yhteys Azure Blob Storage -osasta.</span><span class="sxs-lookup"><span data-stu-id="d106e-148">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="d106e-149">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="d106e-149">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d106e-150">Valitse segmentti, jonka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="d106e-150">Choose the segment that you want to export.</span></span> <span data-ttu-id="d106e-151">Tässä esimerkissä se on **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d106e-151">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Näyttökuva segmentin valinnan käyttöliittymästä, jossa ChurnProneCustomers-segmentti on valittu.":::

1. <span data-ttu-id="d106e-153">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="d106e-153">Select **Save**.</span></span>

<span data-ttu-id="d106e-154">Kun olet tallentanut vientikohteen, löydät sen kohdasta **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="d106e-154">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="d106e-155">Nyt voit [viedä segmentin tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d106e-155">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="d106e-156">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="d106e-156">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d106e-157">Varmista, että viedyn segmentin tietueiden määrä on Adobe Campaign Standard -käyttöoikeutesi sallitun rajan sisällä.</span><span class="sxs-lookup"><span data-stu-id="d106e-157">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="d106e-158">Viedyt tiedot tallennetaan edellä määritettyyn Azure Blob -säilöön.</span><span class="sxs-lookup"><span data-stu-id="d106e-158">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="d106e-159">Seuraava kansiopolku luodaan automaattisesti säilöön:</span><span class="sxs-lookup"><span data-stu-id="d106e-159">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="d106e-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="d106e-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="d106e-161">Esimerkki: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="d106e-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="d106e-162">Vietyjen entiteettien *model.json*-arvo on tasolla *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="d106e-162">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="d106e-163">Esimerkki: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="d106e-163">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="d106e-164">Experience Data Model (XDM) -mallin määritteleminen Adobe-ympäristöpalvelimessa</span><span class="sxs-lookup"><span data-stu-id="d106e-164">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="d106e-165">Ennen kuin käyttäjäryhmän merkityksellisiä tietoja voi käyttää Adobe Experience Platformissa, on määritettävä Experience Data Model -rakenne ja [määritettävä tiedot reaaliaikaista asiakasprofiilia varten](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="d106e-165">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="d106e-166">Tässä on tietoja [XDM:stä](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) ja [rakenteen koostumuksen perusasioista](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="d106e-166">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="d106e-167">Tietojen tuominen Adobe-ympäristöpalvelimeen</span><span class="sxs-lookup"><span data-stu-id="d106e-167">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="d106e-168">Nyt kun kaikki on valmista, meidän on tuotava valmiit käyttäjäryhmän tiedot käyttäjäryhmän merkityksellisistä tiedoista Adobe ympäristöpalvelimeen profiilien luontia varten.</span><span class="sxs-lookup"><span data-stu-id="d106e-168">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="d106e-169">Aluksi [luodaan Azure Blob -tallennustilan lähdeyhteys](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="d106e-169">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="d106e-170">Kun olet määrittänyt lähdeyhteyden, [määritä tietovirta](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pilvitallennustilan eräyhteydelle, jotta segmentin tulos tuodaan käyttäjäryhmän Adobeympäristöpalvelimeen.</span><span class="sxs-lookup"><span data-stu-id="d106e-170">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="d106e-171">Luo kohdeyleisö Adobe Campaign Standardissa</span><span class="sxs-lookup"><span data-stu-id="d106e-171">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="d106e-172">Tämän kampanjan sähköpostiviestin lähettämiseen käytetään Adobe Campaign Standardia.</span><span class="sxs-lookup"><span data-stu-id="d106e-172">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="d106e-173">Kun tiedot on tuotu Adobe Experience Platformiin, Adobe Campaign Standardissa on [luotava käyttäjäryhmä](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) Adobe-ympäristöpalvelimen tietojen avulla.</span><span class="sxs-lookup"><span data-stu-id="d106e-173">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="d106e-174">Opettele määrittämään kohdeyleisö Adobe-ympäristöpalvelimen tietojen perusteella Adobe Campaign Standardissa [segmentin muodostimen avulla](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment).</span><span class="sxs-lookup"><span data-stu-id="d106e-174">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="d106e-175">Sähköpostin luominen ja lähettäminen Adobe Campaign Standardilla</span><span class="sxs-lookup"><span data-stu-id="d106e-175">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="d106e-176">Luo sähköpostiviestin sisältö ja [testaa ja lähetä](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) sitten sähköpostiviestisi.</span><span class="sxs-lookup"><span data-stu-id="d106e-176">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Esimerkki sähköpostista, jossa on tarjous Adobe Campaign Standard -tilauksen uusimisesta.":::
