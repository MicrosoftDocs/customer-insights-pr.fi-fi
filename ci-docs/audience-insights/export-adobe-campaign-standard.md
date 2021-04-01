---
title: Customer Insights -tietojen vieminen Adobe Campaign Standardiin
description: Lisätietoja käyttäjäryhmän merkityksellisten tietojen segmenttien käytöstä Adobe Campaign Standardissa.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596311"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="3f230-103">Customer Insightsin segmenttien käyttö Adobe Campaign Standardissa (esiversio)</span><span class="sxs-lookup"><span data-stu-id="3f230-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="3f230-104">Dynamics 365 Customer Insights -yleisötietojen käyttäjänä olet saattanut luoda segmenttejä markkinointikampanjoidesi tehostamiseksi kohdistamalla ne oleellisiin käyttäjäryhmiin.</span><span class="sxs-lookup"><span data-stu-id="3f230-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="3f230-105">Jos haluat käyttää käyttäjäryhmän merkityksellisiä tietoja Adobe Experience Platformista ja sovelluksista, kuten Adobe Campaign Standardista, sinun on noudatettava tässä artikkelissa kuvattuja vaiheita.</span><span class="sxs-lookup"><span data-stu-id="3f230-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Tässä artikkelissa kuvattujen vaiheiden prosessikaavio.":::

## <a name="prerequisites"></a><span data-ttu-id="3f230-107">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="3f230-107">Prerequisites</span></span>

-   <span data-ttu-id="3f230-108">Dynamics 365 Customer Insights -lisenssi</span><span class="sxs-lookup"><span data-stu-id="3f230-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="3f230-109">Adobe Campaign Standard -käyttöoikeus</span><span class="sxs-lookup"><span data-stu-id="3f230-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="3f230-110">Azure Blob -tallennustili</span><span class="sxs-lookup"><span data-stu-id="3f230-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="3f230-111">Kampanjan yleiskatsaus</span><span class="sxs-lookup"><span data-stu-id="3f230-111">Campaign Overview</span></span>

<span data-ttu-id="3f230-112">Katsotaanpa keksityssä esimerkkikampanjassa, miten käyttäjäryhmän merkityksellisten tietojen segmenttejä käytetään Adobe Experience Platformissa.</span><span class="sxs-lookup"><span data-stu-id="3f230-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="3f230-113">Oletetaan, että yrityksesi tarjoaa asiakkaillesi kuukausittain tilauspohjaisen palvelun Yhdysvalloissa.</span><span class="sxs-lookup"><span data-stu-id="3f230-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="3f230-114">Haluat määrittää asiakkaat, joiden tilaukset on määrä uusia seuraavien kahdeksan päivän aikana, mutta jotka eivät ole uusineet tilaustaan.</span><span class="sxs-lookup"><span data-stu-id="3f230-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="3f230-115">Säilyttääksesi nämä asiakkaat, haluat lähettää heille kampanjatarjouksen sähköpostitse Adobe Campaign Standardin avulla.</span><span class="sxs-lookup"><span data-stu-id="3f230-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="3f230-116">Tässä esimerkissä mainossähköpostikampanja suoritetaan kerran.</span><span class="sxs-lookup"><span data-stu-id="3f230-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="3f230-117">Tässä artikkelissa ei ole tietoja useammasta kuin yhdestä kampanjan käytön käyttötapauksesta.</span><span class="sxs-lookup"><span data-stu-id="3f230-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="3f230-118">Voit kuitenkin määrittää käyttäjäryhmän merkitykselliset tiedot ja Adobe Campaign Standardin toimimaan myös toistuvan kampanjaskenaarion mukaisesti.</span><span class="sxs-lookup"><span data-stu-id="3f230-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="3f230-119">Kohdekäyttäjäryhmän tunnistaminen</span><span class="sxs-lookup"><span data-stu-id="3f230-119">Identify your target audience</span></span>

<span data-ttu-id="3f230-120">Skenaariossamme oletetaan, että asiakkaiden sähköpostiosoitteet ovat käytettävissä käyttäjäryhmän merkityksellisissä tiedoissa ja heidän markkinointimieltymyksensä on analysoitu segmentin jäsenten tunnistamiseksi.</span><span class="sxs-lookup"><span data-stu-id="3f230-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="3f230-121">[Käyttäjäryhmän merkityksellisissä tiedoissa määrittämääsi segmenttiä](segments.md) kutsutaan **ChurnProneCustomers**-segmentiksi, ja aiot lähettää näille asiakkaille sähköpostikampanjan.</span><span class="sxs-lookup"><span data-stu-id="3f230-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Näyttökuva segmenttisivusta, jolla on luotu ChurnProneCustomers-segmentti.":::

<span data-ttu-id="3f230-123">Lähetettävässä tarjoussähköpostiviestissä on asiakkaan etunimi, sukunimi ja tilauksen päättymispäivä.</span><span class="sxs-lookup"><span data-stu-id="3f230-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="3f230-124">Se ilmoittaa asiakkaille alennuksista, jotka he saavat, jos he uusivat tilauksensa ennen sen päättymistä.</span><span class="sxs-lookup"><span data-stu-id="3f230-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="3f230-125">Kohdekäyttäjäryhmän vieminen</span><span class="sxs-lookup"><span data-stu-id="3f230-125">Export your target audience</span></span>

<span data-ttu-id="3f230-126">Kun kohdekäyttäjäryhmä määritetty, voimme määrittää viennin käyttäjäryhmän merkityksellisistä tiedoista Azure Blob -tallennustilatilille.</span><span class="sxs-lookup"><span data-stu-id="3f230-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="3f230-127">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="3f230-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3f230-128">Valitse **Adobe-kampanja**-ruudussa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="3f230-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standardin määritysruutu.":::

1. <span data-ttu-id="3f230-130">Anna **näyttönimi** uudelle vientikohteelle ja kirjoita sitten sen Azure Blob -tallennustilatilin **Tilin nimi**, **Tiliavain** ja **Säilö**, johon haluat viedä segmentin.</span><span class="sxs-lookup"><span data-stu-id="3f230-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Näyttökuva varastotilin määrityksestä. "::: 

   - <span data-ttu-id="3f230-132">Lisätietoja Azure Blob -säilön tilinimen ja käyttöoikeusavaimen etsimisestä on kohdassa [Tallennustilatilin asetusten hallinta Azure-portaalissa](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="3f230-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="3f230-133">Lisätietoja säilön luomisesta on kohdassa [Säilön luominen](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="3f230-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="3f230-134">Valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="3f230-134">Select **Next**.</span></span>

1. <span data-ttu-id="3f230-135">Valitse segmentti, jonka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="3f230-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="3f230-136">Tässä esimerkissä se on **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="3f230-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Näyttökuva segmentin valinnan käyttöliittymästä, jossa ChurnProneCustomers-segmentti on valittu.":::

1. <span data-ttu-id="3f230-138">Valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="3f230-138">Select **Next**.</span></span>

1. <span data-ttu-id="3f230-139">Nyt yhdistämme **lähde**-kentät käyttäjäryhmän merkityksellisten tietojen segmentistä Adobe Campaign Standard -profiilirakenteen **Kohde**-kenttien nimiin.</span><span class="sxs-lookup"><span data-stu-id="3f230-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard -yhdyssovelluksen kenttämääritys.":::

   <span data-ttu-id="3f230-141">Jos haluat lisätä määritteitä, valitse **Lisää määrite**.</span><span class="sxs-lookup"><span data-stu-id="3f230-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="3f230-142">Kohdenimi voi olla eri kuin lähdekentän nimi, joten voit edelleen yhdistää segmenttituottoja käyttäjäryhmän merkityksellisistä tiedoista Adobe Campaign Standardiin, jos kentillä ei ole samaa nimeä kahdessa järjestelmässä.</span><span class="sxs-lookup"><span data-stu-id="3f230-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3f230-143">Sähköpostiosoitetta käytetään tunnistetietokenttänä, mutta voit yhdistää tietoja Adobe Campaign Standardiin käyttäjäryhmän perusteella minkä tahansa muun tunnisteen avulla.</span><span class="sxs-lookup"><span data-stu-id="3f230-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="3f230-144">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="3f230-144">Select **Save**.</span></span>

<span data-ttu-id="3f230-145">Kun olet tallentanut vientikohteen, löydät sen kohdasta **Järjestelmänvalvoja** > **Viennit** > **Omat vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="3f230-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Näyttökuva, jossa vienti- ja näytesegmentti on korostettu.":::

<span data-ttu-id="3f230-147">Nyt voit [viedä segmentin tarvittaessa](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3f230-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="3f230-148">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="3f230-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3f230-149">Varmista, että viedyn segmentin tietueiden määrä on Adobe Campaign Standard -käyttöoikeutesi sallitun rajan sisällä.</span><span class="sxs-lookup"><span data-stu-id="3f230-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="3f230-150">Viedyt tiedot tallennetaan edellä määritettyyn Azure Blob -säilöön.</span><span class="sxs-lookup"><span data-stu-id="3f230-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="3f230-151">Seuraava kansiopolku luodaan automaattisesti säilöön:</span><span class="sxs-lookup"><span data-stu-id="3f230-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="3f230-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="3f230-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="3f230-153">Esimerkki: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="3f230-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="3f230-154">Adobe Campaign Standardin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="3f230-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="3f230-155">Kun käyttäjäryhmän merkityksellisiä tietoja sisältävä segmentti viedään, se sisältää sarakkeet, jotka olet valinnut ja määrittänyt viennin kohteen edellisessä vaiheessa.</span><span class="sxs-lookup"><span data-stu-id="3f230-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="3f230-156">Näitä tietoja voi käyttää [profiilien luomiseen Adobe Campaign Standardissa](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="3f230-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="3f230-157">Adobe Campaign Standardin segmentin käyttöä varten Adobe Campaign Standardin profiilirakenne on laajennettava niin, että se sisältää kaksi lisäkenttää.</span><span class="sxs-lookup"><span data-stu-id="3f230-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="3f230-158">Opettele [laajentamaan profiiliresurssia](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) Adobe Campaign Standardin uusilla kentillä.</span><span class="sxs-lookup"><span data-stu-id="3f230-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="3f230-159">Esimerkissämme nämä kentät ovat *Segmentin nimi ja Segmentin päivämäärä (valinnainen).*</span><span class="sxs-lookup"><span data-stu-id="3f230-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="3f230-160">Näiden kenttien avulla määritetään profiileja Adobe Campaign Standardissa, jonka haluamme kohdistaa tähän kampanjaan.</span><span class="sxs-lookup"><span data-stu-id="3f230-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="3f230-161">Jos Adobe Campaign Standardissa ei ole muita tietueita kuin mitä aiot tuoda, voit ohittaa tämän vaiheen.</span><span class="sxs-lookup"><span data-stu-id="3f230-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="3f230-162">Tietojen tuominen Adobe Campaign Standardiin</span><span class="sxs-lookup"><span data-stu-id="3f230-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="3f230-163">Nyt kun kaikki on valmista, meidän on tuotava valmiit käyttäjäryhmän tiedot käyttäjäryhmän merkityksellisistä tiedoista Adobe Campaign Standardiin profiilien luontia varten.</span><span class="sxs-lookup"><span data-stu-id="3f230-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="3f230-164">Opettele [tuomaan profiileja Adobe Campaign Standardissa](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) työnkulun avulla.</span><span class="sxs-lookup"><span data-stu-id="3f230-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="3f230-165">Alla olevassa kuvassa oleva tuonnin työnkulku on määritetty suoritettavaksi 8 tunnin välein ja se etsii vietyjä käyttäjäryhmien merkityksellisiä tietoja (.csv-tiedosto Azure Blob -säilössä).</span><span class="sxs-lookup"><span data-stu-id="3f230-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="3f230-166">Työnkulku poimii .csv-tiedoston sisällön määritetyssä sarakejärjestyksessä.</span><span class="sxs-lookup"><span data-stu-id="3f230-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="3f230-167">Työnkulku on luotu suorittamaan virheiden peruskäsittely ja varmistamaan, että jokaisella tietueella on sähköpostiosoite ennen tietojen tallentamista Adobe Campaign Standardiin.</span><span class="sxs-lookup"><span data-stu-id="3f230-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="3f230-168">Työnkulku poimii myös segmentin nimen tiedostonimestä, ennen kuin se upottaa ACS-profiilin tiedot.</span><span class="sxs-lookup"><span data-stu-id="3f230-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Näyttökuva tuonnin työnkulusta Adobe Campaign Standard -käyttöliittymässä.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="3f230-170">Nouda kohdeyleisö Adobe Campaign Standardissa</span><span class="sxs-lookup"><span data-stu-id="3f230-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="3f230-171">Kun tiedot on tuotu Adobe Campaign Standardiin, [voit luoda työnkulun](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ja [tehdä kyselyjä](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) asiakkaille *segmentin nimen* ja *segmentin päivämäärän* perusteella ja valita näytekampanjalle tunnistetut profiilit.</span><span class="sxs-lookup"><span data-stu-id="3f230-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="3f230-172">Sähköpostin luominen ja lähettäminen Adobe Campaign Standardilla</span><span class="sxs-lookup"><span data-stu-id="3f230-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="3f230-173">Luo sähköpostiviestin sisältö ja [testaa ja lähetä](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) sitten sähköpostiviestisi.</span><span class="sxs-lookup"><span data-stu-id="3f230-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Esimerkki sähköpostista, jossa on tarjous Adobe Campaign Standard -tilauksen uusimisesta.":::