---
title: Yritysprofiilien rikastaminen kolmannen osapuolen Leadspace-rikastamisella
description: Yleisiä tietoja kolmannen osapuolen Leadspace-rikastamisesta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895909"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="f0186-103">Yritysprofiilien täydentäminen Leadspacen avulla (esikatselu)</span><span class="sxs-lookup"><span data-stu-id="f0186-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="f0186-104">Leadspace on tietotekniikkayritys, joka tarjoaa yritysten välisten asiakastietojen ympäristön.</span><span class="sxs-lookup"><span data-stu-id="f0186-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="f0186-105">Sen avulla voidaan täydentää niiden asiakkaiden tietoja, joilla on yhtenäiset asiakasprofiilit yrityksissä.</span><span class="sxs-lookup"><span data-stu-id="f0186-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="f0186-106">Rikastuksissa on enemmän määritteitä, kuten esim. yrityksen koko, sijainti ja toimiala.</span><span class="sxs-lookup"><span data-stu-id="f0186-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f0186-107">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="f0186-107">Prerequisites</span></span>

<span data-ttu-id="f0186-108">Voit määrittää Leadspacen, jos seuraavat edellytykset täyttyvät:</span><span class="sxs-lookup"><span data-stu-id="f0186-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f0186-109">Sinulla on aktiivinen Leadspace-käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="f0186-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="f0186-110">Sinulla on [yhtenäiset asiakasprofiilit](customer-profiles.md) yrityksiä varten.</span><span class="sxs-lookup"><span data-stu-id="f0186-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="f0186-111">Leadspace-yhteys on jo määritetty järjestelmänvalvojan toimesta tai sinulla on [järjestelmänvalvojan](permissions.md#administrator) oikeudet ja "pysyvä avain" (**Leadspace-tunnus**).</span><span class="sxs-lookup"><span data-stu-id="f0186-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="f0186-112">Jos haluat lisätietoja tuotteesta, ota suoraan yhteyttä [Leadspaceen](https://www.leadspace.com/products/leadspace-on-demand/).</span><span class="sxs-lookup"><span data-stu-id="f0186-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="f0186-113">Määritä rikastus</span><span class="sxs-lookup"><span data-stu-id="f0186-113">Configure the enrichment</span></span>

1. <span data-ttu-id="f0186-114">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Rikastaminen**.</span><span class="sxs-lookup"><span data-stu-id="f0186-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="f0186-115">Valitse Leadspace-ruudussa **Rikasta tietojani** ja valitse **Aloita**.</span><span class="sxs-lookup"><span data-stu-id="f0186-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Näyttökuvassa Leadspace-ruutu":::

1. <span data-ttu-id="f0186-117">Valitse [yhteys](connections.md) avattavasta luettelosta.</span><span class="sxs-lookup"><span data-stu-id="f0186-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="f0186-118">Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.</span><span class="sxs-lookup"><span data-stu-id="f0186-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="f0186-119">Jos olet järjestelmänvalvoja, voit luoda yhteyden valitsemalla **Lisää yhteys** ja sitten **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="f0186-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="f0186-120">Vahvista yhteys valitsemalla **Yhdistä Leadspaceen**.</span><span class="sxs-lookup"><span data-stu-id="f0186-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="f0186-121">Valitse **Seuraava** ja valitse **Asiakastietojoukko**, jonka haluat rikastaa Leadspacen yritystiedoilla.</span><span class="sxs-lookup"><span data-stu-id="f0186-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="f0186-122">Voit valita **asiakasentiteetin**, joka rikastaa kaikkia asiakasprofiileja, tai segmenttientiteetin, joka rikastaa vain segmenttiin sisältyviä asiakasprofiileja.</span><span class="sxs-lookup"><span data-stu-id="f0186-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Näyttökuva asiakastietojoukon valitsemisesta.":::

1. <span data-ttu-id="f0186-124">Valitse **Seuraava** ja määritä, mitä yhtenäisten profiilien kenttiä käytetään Leadspacen vastaavien yritystietojen etsimiseen.</span><span class="sxs-lookup"><span data-stu-id="f0186-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="f0186-125">**Yrityksen nimi** on pakollinen kenttä.</span><span class="sxs-lookup"><span data-stu-id="f0186-125">The **Name of company** field is required.</span></span> <span data-ttu-id="f0186-126">Tarkkuutta voi parantaa lisäämällä enintään kaksi muuta kenttää: **Yrityksen verkkosivusto** ja **Yrityksen sijainti**.</span><span class="sxs-lookup"><span data-stu-id="f0186-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace-kentän yhdistämismääritysruutu":::

1. <span data-ttu-id="f0186-128">Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="f0186-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="f0186-129">Anna rikastusta varten nimi ja valitse vaihtoehtojen tarkistamisen jälkeen **Tallenna rikastus**.</span><span class="sxs-lookup"><span data-stu-id="f0186-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="f0186-130">Leadspace-yhteyden määrittäminen</span><span class="sxs-lookup"><span data-stu-id="f0186-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="f0186-131">Yhteyksien määrittämiseen tarvitaan järjestelmänvalvojan oikeudet.</span><span class="sxs-lookup"><span data-stu-id="f0186-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="f0186-132">Valitse rikastusta määritettäessä **Lisää yhteys** *tai* siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja valitse Leadspace-ruudussa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="f0186-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="f0186-133">Valitse **Aloita**</span><span class="sxs-lookup"><span data-stu-id="f0186-133">Select **Get Started**</span></span> 

1. <span data-ttu-id="f0186-134">Kirjoita yhteyden nimi **Näyttönimi**-ruutuun.</span><span class="sxs-lookup"><span data-stu-id="f0186-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="f0186-135">Anna voimassa oleva Leadspace-tunnus.</span><span class="sxs-lookup"><span data-stu-id="f0186-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="f0186-136">Tarkista tiedot ja hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu</span><span class="sxs-lookup"><span data-stu-id="f0186-136">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="f0186-137">Tarkista määritys valitsemalla **Tarkista**.</span><span class="sxs-lookup"><span data-stu-id="f0186-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="f0186-138">Kun tarkistus on suoritettu, valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="f0186-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace-yhteyden määrityssivu.":::

## <a name="enrichment-results"></a><span data-ttu-id="f0186-140">Rikastamisen tulokset</span><span class="sxs-lookup"><span data-stu-id="f0186-140">Enrichment results</span></span>

<span data-ttu-id="f0186-141">Kun rikastaminen on päivitetty, voit tarkastella uusia rikastettuja yritystietoja [Omat rikastukset](enrichment-hub.md) -kohdassa.</span><span class="sxs-lookup"><span data-stu-id="f0186-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="f0186-142">Voit etsiä viimeisimmän päivityksen ajankohdan ja täydennettyjen profiilien määrän.</span><span class="sxs-lookup"><span data-stu-id="f0186-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f0186-143">Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.</span><span class="sxs-lookup"><span data-stu-id="f0186-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="f0186-144">Lisätietoja on kohdassa [Leadspacen ohjelmointirajapinnat](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="f0186-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f0186-145">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="f0186-145">Next steps</span></span>

<span data-ttu-id="f0186-146">Voit hyödyntää rikastettuja asiakastietoja.</span><span class="sxs-lookup"><span data-stu-id="f0186-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f0186-147">Voit antaa asiakkaille mukautettuja kokemuksia luomalla [segmenttejä](segments.md) ja [mittoja](measures.md) sekä [viemällä tietoja](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f0186-147">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f0186-148">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="f0186-148">Data privacy and compliance</span></span>

<span data-ttu-id="f0186-149">Kun tietojen lähetys Leadspaceen otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="f0186-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f0186-150">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Leadspace noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="f0186-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f0186-151">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f0186-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f0186-152">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.</span><span class="sxs-lookup"><span data-stu-id="f0186-152">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
