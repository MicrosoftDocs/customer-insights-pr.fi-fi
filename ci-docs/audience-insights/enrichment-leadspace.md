---
title: Yritysprofiilien rikastaminen kolmannen osapuolen Leadspace-rikastamisella
description: Yleisiä tietoja kolmannen osapuolen Leadspace-rikastamisesta.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269418"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="79a75-103">Yritysprofiilien täydentäminen Leadspacen avulla (esikatselu)</span><span class="sxs-lookup"><span data-stu-id="79a75-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="79a75-104">Leadspace on tietotekniikkayritys, joka tarjoaa yritysten välisten asiakastietojen ympäristön.</span><span class="sxs-lookup"><span data-stu-id="79a75-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="79a75-105">Sen avulla voidaan täydentää niiden asiakkaiden tietoja, joilla on yhtenäiset asiakasprofiilit yrityksissä.</span><span class="sxs-lookup"><span data-stu-id="79a75-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="79a75-106">Rikastamiset sisältävät lisämääritteitä, kuten yrityksen koko, sijainti ja toimiala.</span><span class="sxs-lookup"><span data-stu-id="79a75-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="79a75-107">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="79a75-107">Prerequisites</span></span>

<span data-ttu-id="79a75-108">Voit määrittää Leadspacen, jos seuraavat edellytykset täyttyvät:</span><span class="sxs-lookup"><span data-stu-id="79a75-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="79a75-109">Aktiivinen Leadspace-käyttöoikeus ja pysyvä avain (johon viitataan **Leadspace-tunnuksena**).</span><span class="sxs-lookup"><span data-stu-id="79a75-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="79a75-110">Saat lisätietoja tuotteesta ottamalla yhteyttä suoraan [Leadspaceen](https://www.leadspace.com/products/leadspace-on-demand/).</span><span class="sxs-lookup"><span data-stu-id="79a75-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="79a75-111">[Järjestelmänvalvojan](permissions.md#administrator) käyttöoikeudet.</span><span class="sxs-lookup"><span data-stu-id="79a75-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="79a75-112">Sinulla on [yhtenäiset asiakasprofiilit](customer-profiles.md) yrityksiä varten.</span><span class="sxs-lookup"><span data-stu-id="79a75-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="79a75-113">Määritys</span><span class="sxs-lookup"><span data-stu-id="79a75-113">Configuration</span></span>

1. <span data-ttu-id="79a75-114">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Rikastaminen**.</span><span class="sxs-lookup"><span data-stu-id="79a75-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="79a75-115">Valitse **Rikasta tietojani** Leadspace-ruudussa.</span><span class="sxs-lookup"><span data-stu-id="79a75-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Näyttökuvassa Leadspace-ruutu":::

1. <span data-ttu-id="79a75-117">Valitse **Aloita** ja anna sitten aktiivinen **Leadspace-tunnus** (pysyvä avain).</span><span class="sxs-lookup"><span data-stu-id="79a75-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="79a75-118">Tarkista tiedot ja hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu.</span><span class="sxs-lookup"><span data-stu-id="79a75-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="79a75-119">Vahvista molemmat syötteet valitsemalla **Yhdistä Leadspaceen**.</span><span class="sxs-lookup"><span data-stu-id="79a75-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="79a75-120">Valitse **Yhdistä tiedot** ja valitse sitten tietojoukko, jota haluat rikastaa Leadspacen yritystiedoilla.</span><span class="sxs-lookup"><span data-stu-id="79a75-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="79a75-121">Voit valita *asiakasentiteetin*, joka rikastaa kaikkia asiakasprofiileja, tai segmenttientiteetin, joka rikastaa vain segmenttiin sisältyviä asiakasprofiileja.</span><span class="sxs-lookup"><span data-stu-id="79a75-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Valitse asiakasprofiilin tai segmentin rikastaminen.":::

1. <span data-ttu-id="79a75-123">Valitse **Seuraava** ja määritä, mitä yhtenäisten profiilien kenttiä käytetään vastaavien yritystietojen hakemiseen Leadspacesta.</span><span class="sxs-lookup"><span data-stu-id="79a75-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="79a75-124">**Yrityksen nimi** on pakollinen kenttä.</span><span class="sxs-lookup"><span data-stu-id="79a75-124">The **Name of company** field is required.</span></span> <span data-ttu-id="79a75-125">Tarkkuutta voi parantaa lisäämällä enintään kaksi muuta kenttää: **Yrityksen verkkosivusto** ja **Yrityksen sijainti**.</span><span class="sxs-lookup"><span data-stu-id="79a75-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace-kentän yhdistämismääritysruutu":::
   
1. <span data-ttu-id="79a75-127">Viimeistele kentän yhdistämismääritys valitsemalla **Käytä**.</span><span class="sxs-lookup"><span data-stu-id="79a75-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="79a75-128">Valitse **Suorita**, jos haluat täydentää yritysprofiileja.</span><span class="sxs-lookup"><span data-stu-id="79a75-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="79a75-129">Rikastamisen kesto määräytyy yhtenäisten asiakasprofiilien määrän mukaan.</span><span class="sxs-lookup"><span data-stu-id="79a75-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="79a75-130">Rikastamisen tulokset</span><span class="sxs-lookup"><span data-stu-id="79a75-130">Enrichment results</span></span>

<span data-ttu-id="79a75-131">Kun rikastaminen on päivitetty, voit tarkastella uusia rikastettuja yritystietoja [Omat rikastukset](enrichment-hub.md) -kohdassa.</span><span class="sxs-lookup"><span data-stu-id="79a75-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="79a75-132">Voit etsiä viimeisimmän päivityksen ajankohdan ja täydennettyjen profiilien määrän.</span><span class="sxs-lookup"><span data-stu-id="79a75-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="79a75-133">Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.</span><span class="sxs-lookup"><span data-stu-id="79a75-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="79a75-134">Lisätietoja on kohdassa [Leadspacen ohjelmointirajapinnat](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="79a75-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="79a75-135">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="79a75-135">Next steps</span></span>

<span data-ttu-id="79a75-136">Voit hyödyntää rikastettuja asiakastietoja.</span><span class="sxs-lookup"><span data-stu-id="79a75-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="79a75-137">Voit antaa asiakkaille mukautettuja kokemuksia luomalla [segmenttejä](segments.md) ja [mittoja](measures.md) sekä [viemällä tietoja](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="79a75-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="79a75-138">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="79a75-138">Data privacy and compliance</span></span>

<span data-ttu-id="79a75-139">Kun tietojen lähetys Leadspaceen otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="79a75-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="79a75-140">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Leadspace noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="79a75-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="79a75-141">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="79a75-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="79a75-142">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.</span><span class="sxs-lookup"><span data-stu-id="79a75-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]