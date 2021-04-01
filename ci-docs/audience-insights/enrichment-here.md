---
title: Rikastaminen kolmannen osapuolen HERE Technologies -rikastamisella
description: Yleisiä tietoja HERE Technologiesin kolmannen osapuolen rikastamisesta.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597737"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="2d5de-103">Asiakasprofiilien rikastaminen HERE Technologiesin avulla (esiversio)</span><span class="sxs-lookup"><span data-stu-id="2d5de-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="2d5de-104">HERE Technologies on sijaintitietoyritys, joka toimittaa sijaintitietoja ja -palveluja.</span><span class="sxs-lookup"><span data-stu-id="2d5de-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="2d5de-105">HERE Technologiesin tietojen rikastamispalveluilla voi muodostaa tarkemman asiakkaiden sijaintitietoisuuden esimerkiksi osoitteen normalisoinnin sekä leveys- ja pituusastetietojen poiminnan avulla.</span><span class="sxs-lookup"><span data-stu-id="2d5de-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2d5de-106">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="2d5de-106">Prerequisites</span></span>

<span data-ttu-id="2d5de-107">HERE Technologiesin rikastamisen määrittämiselle on seuraavat edellytykset:</span><span class="sxs-lookup"><span data-stu-id="2d5de-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="2d5de-108">Aktiviinen HERE Technologies -tilaus.</span><span class="sxs-lookup"><span data-stu-id="2d5de-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="2d5de-109">Voit tehdä tilauksen [rekisteröitymällä täällä](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) tai ottamalla suoraan [yhteyttä HERE Technologiesiin](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="2d5de-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="2d5de-110">Lisätietoja HERE Technologiesin sijaintitietojen rikastamisesta.</span><span class="sxs-lookup"><span data-stu-id="2d5de-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="2d5de-111">HERE Technologies -ohjelmointirajapinnan avain.</span><span class="sxs-lookup"><span data-stu-id="2d5de-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="2d5de-112">[Järjestelmänvalvojan](permissions.md#administrator) käyttöoikeudet.</span><span class="sxs-lookup"><span data-stu-id="2d5de-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="2d5de-113">Määritys</span><span class="sxs-lookup"><span data-stu-id="2d5de-113">Configuration</span></span>

1. <span data-ttu-id="2d5de-114">Siirry kohtaan **Tiedot** > **Täydentäminen**.</span><span class="sxs-lookup"><span data-stu-id="2d5de-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="2d5de-115">Valitse **Rikasta tietojani** HERE Technologies -ruudussa.</span><span class="sxs-lookup"><span data-stu-id="2d5de-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2d5de-116">![HERE Technologies -ruutu](media/HERE-tile.png "HERE Technologies -ruutu")</span><span class="sxs-lookup"><span data-stu-id="2d5de-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="2d5de-117">Anna aktiivinen **HERE Technologies -ohjelmointirajapinnan avain**.</span><span class="sxs-lookup"><span data-stu-id="2d5de-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="2d5de-118">Tarkista tiedot ja hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu.</span><span class="sxs-lookup"><span data-stu-id="2d5de-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="2d5de-119">Vahvista molemmat syötteet valitsemalla **Yhdistä HERE-palveluun**.</span><span class="sxs-lookup"><span data-stu-id="2d5de-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="2d5de-120">Valitse **Lisää tiedot** ja valitse sitten **Asiakastietojoukko**, jota haluat rikastaa HERE Technologies -ratkaisun sijaintitiedoilla.</span><span class="sxs-lookup"><span data-stu-id="2d5de-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="2d5de-121">Voit valita **asiakasentiteetin**, joka rikastaa kaikkia asiakasprofiileja, tai segmenttientiteetin, joka rikastaa vain segmenttiin sisältyviä asiakasprofiileja.</span><span class="sxs-lookup"><span data-stu-id="2d5de-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Näyttökuva asiakastietojoukon valitsemisesta.":::

1. <span data-ttu-id="2d5de-123">Määritä, yhdistetäänkö kentät ensi- ja/tai toissijaiseen osoitteeseen.</span><span class="sxs-lookup"><span data-stu-id="2d5de-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="2d5de-124">Voit määrittää kummankin osoitteen (kuten koti- ja työosoitteen) kentän yhdistämismäärityksen ja rikastaa profiileja molemmilla osoitteilla erikseen.</span><span class="sxs-lookup"><span data-stu-id="2d5de-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="2d5de-125">Valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="2d5de-125">Select **Next**.</span></span>

1. <span data-ttu-id="2d5de-126">Määritä, mitä yhtenäistettyjen profiilien kenttiä käytetään hakemaan vastaavia sijaintitietoja HERE Technologies -palvelusta.</span><span class="sxs-lookup"><span data-stu-id="2d5de-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="2d5de-127">**Lähiosoite 1** ja **Postinumero** ovat pakollisia kenttiä valitussa ensi- ja/tai toissijaisen osoitteessa.</span><span class="sxs-lookup"><span data-stu-id="2d5de-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="2d5de-128">Vastaavuuden tarkkuutta voi parantaa lisäämällä kenttiä.</span><span class="sxs-lookup"><span data-stu-id="2d5de-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2d5de-129">![HERE Technologies -rikastamisen määrityssivu](media/enrichment-HERE-configuration.png "HERE Technologies -rikastamisen määrityssivu")</span><span class="sxs-lookup"><span data-stu-id="2d5de-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="2d5de-130">Viimeistele kentän yhdistämismääritys valitsemalla **Käytä**.</span><span class="sxs-lookup"><span data-stu-id="2d5de-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="2d5de-131">Rikastamisen tulokset</span><span class="sxs-lookup"><span data-stu-id="2d5de-131">Enrichment results</span></span>

<span data-ttu-id="2d5de-132">Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="2d5de-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="2d5de-133">Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana.</span><span class="sxs-lookup"><span data-stu-id="2d5de-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2d5de-134">Käsittelyaika määräytyy asiakastietojen koon ja ohjelmointirajapinnan HERE Technologies -vasteajan mukaan.</span><span class="sxs-lookup"><span data-stu-id="2d5de-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="2d5de-135">Kun rikastamisprosessi on valmis, voit tarkastella juuri rikastettujen asiakasprofiilien tietoja valitsemalla **Omat rikastukset**.</span><span class="sxs-lookup"><span data-stu-id="2d5de-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="2d5de-136">Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.</span><span class="sxs-lookup"><span data-stu-id="2d5de-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="2d5de-137">Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.</span><span class="sxs-lookup"><span data-stu-id="2d5de-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2d5de-138">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="2d5de-138">Next steps</span></span>

<span data-ttu-id="2d5de-139">Voit hyödyntää rikastettuja asiakastietoja.</span><span class="sxs-lookup"><span data-stu-id="2d5de-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2d5de-140">Voit antaa asiakkaille mukautettuja kokemuksia luomalla [segmenttejä](segments.md) ja [mittoja](measures.md) sekä [viemällä tietoja](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2d5de-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2d5de-141">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="2d5de-141">Data privacy and compliance</span></span>

<span data-ttu-id="2d5de-142">Kun tietojen lähetys HERE Technologiesiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="2d5de-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2d5de-143">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että HERE Technologies noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="2d5de-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2d5de-144">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2d5de-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2d5de-145">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.</span><span class="sxs-lookup"><span data-stu-id="2d5de-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]