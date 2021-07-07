---
title: Rikastaminen kolmannen osapuolen rikastamisen HERE Technologies -ratkaisun avulla
description: Yleisiä tietoja HERE Technologiesin kolmannen osapuolen rikastamisesta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305290"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="b3682-103">Asiakasprofiilien rikastaminen HERE Technologiesin avulla (esiversio)</span><span class="sxs-lookup"><span data-stu-id="b3682-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="b3682-104">HERE Technologies on sijaintitietoyritys, joka toimittaa sijaintitietoja ja -palveluja.</span><span class="sxs-lookup"><span data-stu-id="b3682-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="b3682-105">HERE Technologiesin tietojen rikastamispalveluilla voi muodostaa tarkemman asiakkaiden sijaintitietoisuuden esimerkiksi osoitteen normalisoinnin sekä leveys- ja pituusastetietojen poiminnan avulla.</span><span class="sxs-lookup"><span data-stu-id="b3682-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b3682-106">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="b3682-106">Prerequisites</span></span>

<span data-ttu-id="b3682-107">HERE Technologiesin rikastamisen määrittämiselle on seuraavat edellytykset:</span><span class="sxs-lookup"><span data-stu-id="b3682-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b3682-108">Aktiviinen HERE Technologies -tilaus.</span><span class="sxs-lookup"><span data-stu-id="b3682-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="b3682-109">Voit tehdä tilauksen [rekisteröitymällä täällä](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) tai ottamalla suoraan [yhteyttä HERE Technologiesiin](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="b3682-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="b3682-110">Lisätietoja HERE Technologiesin sijaintitietojen rikastamisesta.</span><span class="sxs-lookup"><span data-stu-id="b3682-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="b3682-111">[HERE-yhteys](connections.md) on käytettävissä *tai* sinulla on [järjestelmänvalvojan](permissions.md#administrator) oikeudet ja HERE Technologies -ohjelmointirajapinnan avain.</span><span class="sxs-lookup"><span data-stu-id="b3682-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="b3682-112">Määritä rikastus</span><span class="sxs-lookup"><span data-stu-id="b3682-112">Configure the enrichment</span></span>

1. <span data-ttu-id="b3682-113">Siirry kohtaan **Tiedot** > **Täydentäminen**.</span><span class="sxs-lookup"><span data-stu-id="b3682-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="b3682-114">Valitse HERE Technologies -ruudussa **Rikasta tietojani** ja valitse **Aloita**.</span><span class="sxs-lookup"><span data-stu-id="b3682-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b3682-115">![HERE Technologies -ruutu](media/HERE-tile.png "HERE Technologies -ruutu")</span><span class="sxs-lookup"><span data-stu-id="b3682-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="b3682-116">Valitse [yhteys](connections.md) avattavasta luettelosta.</span><span class="sxs-lookup"><span data-stu-id="b3682-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="b3682-117">Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.</span><span class="sxs-lookup"><span data-stu-id="b3682-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="b3682-118">Jos olet järjestelmänvalvoja, voit luoda yhteyden valitsemalla **Lisää yhteys**.</span><span class="sxs-lookup"><span data-stu-id="b3682-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="b3682-119">Valitse avattavasta luettelosta **HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="b3682-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="b3682-120">Vahvista valinta valitsemalla **Yhdistä HERE Technologiesiin**.</span><span class="sxs-lookup"><span data-stu-id="b3682-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="b3682-121">Valitse **Seuraava** ja valitse **Asiakastietojoukko**, jonka haluat rikastaa HERE Technologiesin sijaintitiedoilla.</span><span class="sxs-lookup"><span data-stu-id="b3682-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="b3682-122">Voit valita **asiakasentiteetin**, joka rikastaa kaikkia asiakasprofiileja, tai segmenttientiteetin, joka rikastaa vain segmenttiin sisältyviä asiakasprofiileja.</span><span class="sxs-lookup"><span data-stu-id="b3682-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Näyttökuva asiakastietojoukon valitsemisesta.":::

1. <span data-ttu-id="b3682-124">Määritä, yhdistetäänkö kentät ensi- ja/tai toissijaiseen osoitteeseen.</span><span class="sxs-lookup"><span data-stu-id="b3682-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="b3682-125">Voit määrittää kenttien yhdistämismäärityksen molemmille osoitteille että rikastaa profiileja molemmille osoitteille erikseen.</span><span class="sxs-lookup"><span data-stu-id="b3682-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="b3682-126">Jos esimerkiksi on koti- ja yritysosoite.</span><span class="sxs-lookup"><span data-stu-id="b3682-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="b3682-127">Valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="b3682-127">Select **Next**.</span></span>

1. <span data-ttu-id="b3682-128">Määritä, mitä yhtenäistettyjen profiilien kenttiä käytetään hakemaan vastaavia sijaintitietoja HERE Technologies -palvelusta.</span><span class="sxs-lookup"><span data-stu-id="b3682-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="b3682-129">**Lähiosoite 1** ja **Postinumero** ovat pakollisia kenttiä valitussa ensi- ja/tai toissijaisen osoitteessa.</span><span class="sxs-lookup"><span data-stu-id="b3682-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="b3682-130">Vastaavuuden tarkkuutta voi parantaa lisäämällä kenttiä.</span><span class="sxs-lookup"><span data-stu-id="b3682-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b3682-131">![HERE Technologies -rikastamisen määrityssivu](media/enrichment-HERE-configuration.png "HERE Technologies -rikastamisen määrityssivu")</span><span class="sxs-lookup"><span data-stu-id="b3682-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="b3682-132">Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="b3682-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="b3682-133">Kirjoita rikastuksen nimi.</span><span class="sxs-lookup"><span data-stu-id="b3682-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="b3682-134">Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.</span><span class="sxs-lookup"><span data-stu-id="b3682-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="b3682-135">HERE Technologies -yhteyden määrittäminen</span><span class="sxs-lookup"><span data-stu-id="b3682-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="b3682-136">Yhteyksien määrittämiseen tarvitaan järjestelmänvalvojan oikeudet.</span><span class="sxs-lookup"><span data-stu-id="b3682-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="b3682-137">Valitse rikastusta määritettäessä **Lisää yhteys** *tai* siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja valitse HERE Technologies -ruudussa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="b3682-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="b3682-138">Kirjoita yhteyden nimi **Näyttönimi**-ruutuun.</span><span class="sxs-lookup"><span data-stu-id="b3682-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="b3682-139">Anna kelvollinen HERE Technologiesin API-avain.</span><span class="sxs-lookup"><span data-stu-id="b3682-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="b3682-140">Tarkista **Tietojen yksityisyys ja vaatimustenmukaisuus** -kohta ja hyväksy se valitsemalla **Hyväksyn**.</span><span class="sxs-lookup"><span data-stu-id="b3682-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="b3682-141">Tarkista määritys valitsemalla **Tarkista**.</span><span class="sxs-lookup"><span data-stu-id="b3682-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="b3682-142">Kun tarkistus on suoritettu, valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="b3682-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b3682-143">![HERE Technologies -yhteyden määrityssivu](media/enrichment-HERE-connection.png "HERE Technologies -yhteyden määrityssivu")</span><span class="sxs-lookup"><span data-stu-id="b3682-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="b3682-144">Rikastamisen tulokset</span><span class="sxs-lookup"><span data-stu-id="b3682-144">Enrichment results</span></span>

<span data-ttu-id="b3682-145">Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="b3682-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="b3682-146">Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana.</span><span class="sxs-lookup"><span data-stu-id="b3682-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b3682-147">Käsittelyaika määräytyy asiakastietojen koon ja ohjelmointirajapinnan HERE Technologies -vasteajan mukaan.</span><span class="sxs-lookup"><span data-stu-id="b3682-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="b3682-148">Kun rikastamisprosessi on valmis, voit tarkastella juuri rikastettujen asiakasprofiilien tietoja valitsemalla **Omat rikastukset**.</span><span class="sxs-lookup"><span data-stu-id="b3682-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="b3682-149">Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.</span><span class="sxs-lookup"><span data-stu-id="b3682-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="b3682-150">Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.</span><span class="sxs-lookup"><span data-stu-id="b3682-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b3682-151">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="b3682-151">Next steps</span></span>

<span data-ttu-id="b3682-152">Voit hyödyntää rikastettuja asiakastietoja.</span><span class="sxs-lookup"><span data-stu-id="b3682-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b3682-153">Voit luoda [segmenttejä](segments.md) ja [mittareita](measures.md) ja jopa [viedä tietoja](export-destinations.md), jos haluat tarjota asiakkaille mukautettuja käyttökokemuksia.</span><span class="sxs-lookup"><span data-stu-id="b3682-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b3682-154">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="b3682-154">Data privacy and compliance</span></span>

<span data-ttu-id="b3682-155">Kun tietojen lähetys HERE Technologiesiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="b3682-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b3682-156">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että HERE Technologies noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="b3682-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b3682-157">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b3682-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b3682-158">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.</span><span class="sxs-lookup"><span data-stu-id="b3682-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
