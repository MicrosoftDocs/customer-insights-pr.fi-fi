---
title: Rikastaminen kolmannen osapuolen Experian-rikastamisella
description: Yleisiä tietoja kolmannen osapuolen Experian-rikastamisesta.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597783"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="61ff2-103">Asiakasprofiilien rikastaminen Experianin demografiatiedoilla (esiversio)</span><span class="sxs-lookup"><span data-stu-id="61ff2-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="61ff2-104">Experian on maailman johtava kuluttaja- ja yritysluottojen raportointi- ja markkinointipalvelujen toimittaja.</span><span class="sxs-lookup"><span data-stu-id="61ff2-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="61ff2-105">Experianin tietojen rikastamispalveluilla voidaan syventää tietoja asiakkaista rikastamalla asiakasprofiileja demografiatiedoilla, kuten sillä, minkä kokoinen talous on kyseessä ja minkälaiset tulot sillä on käytettävissä.</span><span class="sxs-lookup"><span data-stu-id="61ff2-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="61ff2-106">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="61ff2-106">Prerequisites</span></span>

<span data-ttu-id="61ff2-107">Experianin määrittäminen edellyttää seuraavien edellytysten toteutumista:</span><span class="sxs-lookup"><span data-stu-id="61ff2-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="61ff2-108">Aktiivinen Experian-tilaus.</span><span class="sxs-lookup"><span data-stu-id="61ff2-108">You have an active Experian subscription.</span></span> <span data-ttu-id="61ff2-109">Tilaus tehdään suoraan [Experianilta](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="61ff2-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="61ff2-110">[Lisätietoja Experianin tietojen rikastamisesta](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="61ff2-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="61ff2-111">Sinulla on Experianin luoma SSH-yhteensopivan ST (Secure Transport) -tilin käyttäjätunnus, osapuolen tunnus ja mallinumero.</span><span class="sxs-lookup"><span data-stu-id="61ff2-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="61ff2-112">Sinulla on käyttäjäryhmän merkityksellisten tietojen [järjestelmänvalvojan](permissions.md#administrator) oikeudet.</span><span class="sxs-lookup"><span data-stu-id="61ff2-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="61ff2-113">Määritys</span><span class="sxs-lookup"><span data-stu-id="61ff2-113">Configuration</span></span>

1. <span data-ttu-id="61ff2-114">Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.</span><span class="sxs-lookup"><span data-stu-id="61ff2-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="61ff2-115">Valitse Experian-ruudussa **Rikasta tietojani**.</span><span class="sxs-lookup"><span data-stu-id="61ff2-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="61ff2-116">![Experian-ruutu](media/experian-tile.png "Experian-ruutu")</span><span class="sxs-lookup"><span data-stu-id="61ff2-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="61ff2-117">Valitse **Aloita** ja Experianin ST (Secure Transport) -tilin käyttäjätunnus, osapuolen tunnus ja mallinumero.</span><span class="sxs-lookup"><span data-stu-id="61ff2-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="61ff2-118">Tarkista tiedot ja hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu.</span><span class="sxs-lookup"><span data-stu-id="61ff2-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="61ff2-119">Vahvista kaikki syötteet valitsemalla **Käytä**:</span><span class="sxs-lookup"><span data-stu-id="61ff2-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="61ff2-120">Yhdistä kenttäsi</span><span class="sxs-lookup"><span data-stu-id="61ff2-120">Map your fields</span></span>

1.  <span data-ttu-id="61ff2-121">Valitse **Lisää tiedot** ja valitse **asiakastietojoukko**, jota haluat rikastaa Experianin demografiatiedoilla.</span><span class="sxs-lookup"><span data-stu-id="61ff2-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="61ff2-122">Voit valita **asiakasentiteetin**, joka rikastaa kaikkia asiakasprofiileja, tai segmenttientiteetin, joka rikastaa vain segmenttiin sisältyviä asiakasprofiileja.</span><span class="sxs-lookup"><span data-stu-id="61ff2-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="61ff2-123">Valitse avaintunnisteet **Nimi ja osoite**-, **Sähköposti**- tai **Puhelin**-kohdasta ja lähetä ne Experianille ratkaisun määrittämistä varten.</span><span class="sxs-lookup"><span data-stu-id="61ff2-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="61ff2-124">Mitä enemmän avaintunnisteiden määritteitä lähetetään Experianiin, sitä korkeampi vastaavuusaste on.</span><span class="sxs-lookup"><span data-stu-id="61ff2-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="61ff2-125">Valitse **Seuraava** ja yhdistä vastaavat määritteet valittujen avaintunnistekenttien yhdistetystä asiakasentiteetistä.</span><span class="sxs-lookup"><span data-stu-id="61ff2-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="61ff2-126">Valitsemalla **Lisää määrite** voit yhdistää lisämääritteet, jotka halutaan lähettää Experianiin.</span><span class="sxs-lookup"><span data-stu-id="61ff2-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="61ff2-127">Viimeistele kenttien yhdistäminen valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="61ff2-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="61ff2-128">![Experianin kenttämääritys](media/experian-field-mapping.png "Experianin kenttämääritys")</span><span class="sxs-lookup"><span data-stu-id="61ff2-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="61ff2-129">Rikastamisen tulokset</span><span class="sxs-lookup"><span data-stu-id="61ff2-129">Enrichment results</span></span>

<span data-ttu-id="61ff2-130">Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="61ff2-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="61ff2-131">Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana.</span><span class="sxs-lookup"><span data-stu-id="61ff2-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="61ff2-132">Käsittelyaika määräytyy asiakastietojen koon ja Experianin tilille määrittämän rikastamisprosessin perusteella.</span><span class="sxs-lookup"><span data-stu-id="61ff2-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="61ff2-133">Kun rikastamisprosessi on valmis, voit tarkastella juuri rikastettujen asiakasprofiilien tietoja valitsemalla **Omat rikastukset**.</span><span class="sxs-lookup"><span data-stu-id="61ff2-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="61ff2-134">Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.</span><span class="sxs-lookup"><span data-stu-id="61ff2-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="61ff2-135">Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.</span><span class="sxs-lookup"><span data-stu-id="61ff2-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="61ff2-136">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="61ff2-136">Next steps</span></span>

<span data-ttu-id="61ff2-137">Voit hyödyntää rikastettuja asiakastietoja.</span><span class="sxs-lookup"><span data-stu-id="61ff2-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="61ff2-138">Voit antaa asiakkaille mukautettuja kokemuksia luomalla [segmenttejä](segments.md) ja [mittoja](measures.md) sekä [viemällä tietoja](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="61ff2-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="61ff2-139">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="61ff2-139">Data privacy and compliance</span></span>

<span data-ttu-id="61ff2-140">Kun tietojen lähetys Experianiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="61ff2-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="61ff2-141">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Experian noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="61ff2-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="61ff2-142">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="61ff2-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="61ff2-143">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.</span><span class="sxs-lookup"><span data-stu-id="61ff2-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]