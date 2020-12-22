---
title: Rikastaminen kolmannen osapuolen HERE Technologies -rikastamisella
description: Yleisiä tietoja HERE Technologiesin kolmannen osapuolen rikastamisesta.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668674"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="8fcd2-103">Asiakasprofiilien rikastaminen HERE Technologiesin avulla (esiversio)</span><span class="sxs-lookup"><span data-stu-id="8fcd2-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="8fcd2-104">HERE Technologies on sijaintitietoyritys, joka toimittaa sijaintitietoja ja -palveluja.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="8fcd2-105">HERE Technologiesin tietojen rikastamispalveluilla voi muodostaa tarkemman asiakkaiden sijaintitietoisuuden esimerkiksi osoitteen normalisoinnin sekä leveys- ja pituusastetietojen poiminnan avulla.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8fcd2-106">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="8fcd2-106">Prerequisites</span></span>

<span data-ttu-id="8fcd2-107">HERE Technologiesin rikastamisen määrittämiselle on seuraavat edellytykset:</span><span class="sxs-lookup"><span data-stu-id="8fcd2-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="8fcd2-108">Aktiviinen HERE Technologies -tilaus.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="8fcd2-109">Voit tehdä tilauksen [rekisteröitymällä täällä](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) tai ottamalla suoraan [yhteyttä HERE Technologiesiin](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="8fcd2-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="8fcd2-110">Lisätietoja HERE Technologiesin sijaintitietojen rikastamisesta.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="8fcd2-111">HERE Technologies -ohjelmointirajapinnan avain.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="8fcd2-112">[Järjestelmänvalvojan](permissions.md#administrator) käyttöoikeudet.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="8fcd2-113">Määritys</span><span class="sxs-lookup"><span data-stu-id="8fcd2-113">Configuration</span></span>

1. <span data-ttu-id="8fcd2-114">Siirry kohtaan **Tiedot** > **Täydentäminen**.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="8fcd2-115">Valitse **Rikasta tietojani** HERE Technologies -ruudussa.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8fcd2-116">![HERE Technologies -ruutu](media/HERE-tile.png "HERE Technologies -ruutu")</span><span class="sxs-lookup"><span data-stu-id="8fcd2-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="8fcd2-117">Anna aktiivinen **HERE Technologies -ohjelmointirajapinnan avain**.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="8fcd2-118">Tarkista tiedot ja hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="8fcd2-119">Vahvista molemmat syötteet valitsemalla **Yhdistä HERE-palveluun**.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="8fcd2-120">Valitse **Lisää tiedot** ja valitse, yhdistetäänkö kentät ensi- ja/tai toissijaiseen osoitteeseen.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="8fcd2-121">Voit määrittää kummankin osoitteen (kuten koti- ja työosoitteen) kentän yhdistämismäärityksen ja rikastaa profiileja molemmilla osoitteilla erikseen.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="8fcd2-122">Valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-122">Select **Next**.</span></span>

1. <span data-ttu-id="8fcd2-123">Määritä, mitä yhtenäistettyjen profiilien kenttiä käytetään hakemaan vastaavia sijaintitietoja HERE Technologies -palvelusta.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="8fcd2-124">**Lähiosoite 1** ja **Postinumero** ovat pakollisia kenttiä valitussa ensi- ja/tai toissijaisen osoitteessa.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="8fcd2-125">Vastaavuuden tarkkuutta voi parantaa lisäämällä kenttiä.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8fcd2-126">![HERE Technologies -rikastamisen määrityssivu](media/enrichment-HERE-configuration.png "HERE Technologies -rikastamisen määrityssivu")</span><span class="sxs-lookup"><span data-stu-id="8fcd2-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="8fcd2-127">Viimeistele kentän yhdistämismääritys valitsemalla **Käytä**.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="8fcd2-128">Rikastamisen tulokset</span><span class="sxs-lookup"><span data-stu-id="8fcd2-128">Enrichment results</span></span>

<span data-ttu-id="8fcd2-129">Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="8fcd2-130">Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8fcd2-131">Käsittelyaika määräytyy asiakastietojen koon ja ohjelmointirajapinnan HERE Technologies -vasteajan mukaan.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="8fcd2-132">Kun rikastamisprosessi on valmis, voit tarkastella juuri rikastettujen asiakasprofiilien tietoja valitsemalla **Omat rikastukset**.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="8fcd2-133">Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="8fcd2-134">Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8fcd2-135">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="8fcd2-135">Next steps</span></span>

<span data-ttu-id="8fcd2-136">Voit hyödyntää rikastettuja asiakastietoja.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="8fcd2-137">Voit antaa asiakkaille mukautettuja kokemuksia luomalla [segmenttejä](segments.md) ja [mittoja](measures.md) sekä [viemällä tietoja](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8fcd2-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8fcd2-138">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="8fcd2-138">Data privacy and compliance</span></span>

<span data-ttu-id="8fcd2-139">Kun tietojen lähetys HERE Technologiesiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8fcd2-140">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että HERE Technologies noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8fcd2-141">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8fcd2-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8fcd2-142">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
