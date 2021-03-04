---
title: Power BI -yhdistin
description: Tietoja Dynamics 365 Customer Insights -yhdistimen käytöstä Power BI:ssä.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477084"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="abe5b-103">Power BI -yhdistin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="abe5b-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="abe5b-104">Tietojen visualisointien luominen Power BI Desktopin avulla.</span><span class="sxs-lookup"><span data-stu-id="abe5b-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="abe5b-105">Voit luoda lisää näkemyksiä ja luoda raportteja, joissa on yhdistettyjä asiakastietoja.</span><span class="sxs-lookup"><span data-stu-id="abe5b-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="abe5b-106">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="abe5b-106">Prerequisites</span></span>

- <span data-ttu-id="abe5b-107">Käytössä on yhtenäistetyt asiakasprofiilit.</span><span class="sxs-lookup"><span data-stu-id="abe5b-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="abe5b-108">Tietokoneellasi on asennettuna [Microsoft Power BI Desktopin](https://powerbi.microsoft.com/desktop/) viimeisin versio.</span><span class="sxs-lookup"><span data-stu-id="abe5b-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="abe5b-109">[Lisätietoja aiheesta: Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="abe5b-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="abe5b-110">Määritä Power BI -yhdistin</span><span class="sxs-lookup"><span data-stu-id="abe5b-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="abe5b-111">Valitse Power BI Desktopissa **Tiedosto** > **Nouda tiedot**.</span><span class="sxs-lookup"><span data-stu-id="abe5b-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="abe5b-112">Valitse **Katso lisää** ja hae **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="abe5b-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="abe5b-113">Valitse **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="abe5b-113">Select **Connect**.</span></span>

1. <span data-ttu-id="abe5b-114">**Kirjaudu sisään** samalla organisaatiotilillä, jota käytät Customer Insightsissa, ja valitse **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="abe5b-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="abe5b-115">Tässä vaiheessa ilmaistua tiliä käytetään noutamaan tietoja Customer Insightsista eikä sen tarvitse olla kuin tili, jolla kirjauduit Power BI:hin.</span><span class="sxs-lookup"><span data-stu-id="abe5b-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="abe5b-116">Nollaa tietojen noutamiseen käytetty tili avaamalla Power BI ja valitsemalla **Tiedosto** > **Valinnat** > **Asetukset** > **Tietolähteen asetukset**.</span><span class="sxs-lookup"><span data-stu-id="abe5b-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="abe5b-117">Valitse tietolähdeluettelossa **Dynamics 365 Customer Insightsin kirjautuminen** ja valitse sitten **Tyhjennä oikeudet**.</span><span class="sxs-lookup"><span data-stu-id="abe5b-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="abe5b-118">**Siirtyminen**-valintaikkunassa.</span><span class="sxs-lookup"><span data-stu-id="abe5b-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="abe5b-119">on luettelo kaikista ympäristöistä, joita voi käyttää.</span><span class="sxs-lookup"><span data-stu-id="abe5b-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="abe5b-120">Laajenna ympäristö ja avaa jokin kansioista (entiteetit, mittarit, segmentit, rikastamiset).</span><span class="sxs-lookup"><span data-stu-id="abe5b-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="abe5b-121">Avaa esimerkiksi **Entiteetit**-kansio, jotta voit tarkastella kaikkia tuotavia entiteettejä.</span><span class="sxs-lookup"><span data-stu-id="abe5b-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="abe5b-122">![Power BI -yhdistintaulukko](media/power-bi-navigator.png "Power BI -yhdistintaulukko")</span><span class="sxs-lookup"><span data-stu-id="abe5b-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="abe5b-123">Valitse sisällytettävien entiteettien valintaruudut ja sitten **Lataa**.</span><span class="sxs-lookup"><span data-stu-id="abe5b-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="abe5b-124">Voit valita useita entiteettejä useista ympäristöistä.</span><span class="sxs-lookup"><span data-stu-id="abe5b-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="abe5b-125">Latauksen valintaikkuna näkyy, kun entiteettejä ladataan.</span><span class="sxs-lookup"><span data-stu-id="abe5b-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="abe5b-126">Kun kaikki valitut entiteetit on ladattu, voit visualisoida tiedot Power BI:n ominaisuuksilla.</span><span class="sxs-lookup"><span data-stu-id="abe5b-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="abe5b-127">Suuret tietojoukot</span><span class="sxs-lookup"><span data-stu-id="abe5b-127">Large data sets</span></span>

<span data-ttu-id="abe5b-128">Power BI:n Customer Insights -yhdistin on suunniteltu toimimaan tietojoukoilla, jotka sisältävät enintään 1 miljoonaa asiakasprofiilia.</span><span class="sxs-lookup"><span data-stu-id="abe5b-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="abe5b-129">Suurempien tietojoukkojen tuominen saattaa toimia, mutta se kestää kauan.</span><span class="sxs-lookup"><span data-stu-id="abe5b-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="abe5b-130">Lisäksi prosessi saattaa saavuttaa aikakatkaisun Power BI -rajoitusten vuoksi.</span><span class="sxs-lookup"><span data-stu-id="abe5b-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="abe5b-131">Lisätietoja: [Power BI: Suuria tietojoukkoja koskevat suositukset](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="abe5b-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="abe5b-132">Alitietojoukon käsitteleminen</span><span class="sxs-lookup"><span data-stu-id="abe5b-132">Work with a subset of data</span></span>

<span data-ttu-id="abe5b-133">Harkitse tietojen alijoukon käyttämistä.</span><span class="sxs-lookup"><span data-stu-id="abe5b-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="abe5b-134">Voit esimerkiksi luoda [segmenttejä](segments.md) sen sijaan, että kaikki asiakastietueet vietäisiin Power BI:hin.</span><span class="sxs-lookup"><span data-stu-id="abe5b-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="abe5b-135">Vianmääritys</span><span class="sxs-lookup"><span data-stu-id="abe5b-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="abe5b-136">Customer Insights -ympäristö ei näy Power BI:ssä</span><span class="sxs-lookup"><span data-stu-id="abe5b-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="abe5b-137">Ympäristöt, joissa on määritetty useita [suhteita](relationships.md) kahden identtisen entiteetin välille käyttäjäryhmän tiedoissa, eivät ole käytettävissä Power BI -yhdistimessä.</span><span class="sxs-lookup"><span data-stu-id="abe5b-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="abe5b-138">Voit tunnistaa ja poistaa kaksoiskappaleiden suhteita.</span><span class="sxs-lookup"><span data-stu-id="abe5b-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="abe5b-139">Siirry käyttäjäryhmän tiedoissa kohtaan **Tiedot** > **Suhteet** ympäristössä, jossa ei ole Power BI:tä.</span><span class="sxs-lookup"><span data-stu-id="abe5b-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="abe5b-140">Tunnista kaksoiskappaleiden suhteet seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="abe5b-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="abe5b-141">Tarkista, onko kahdelle samalle entiteetille määritetty useita suhteita.</span><span class="sxs-lookup"><span data-stu-id="abe5b-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="abe5b-142">Tarkista, onko kahden yhdistämisprosessiin sisältyvän entiteettien välille luotu suhde.</span><span class="sxs-lookup"><span data-stu-id="abe5b-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="abe5b-143">Kaikkien yhdistämisprosessiin sisältyvien entiteettien välille on määritetty implisiittinen suhde.</span><span class="sxs-lookup"><span data-stu-id="abe5b-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="abe5b-144">Poista kaikki tunnistetut suhteiden kaksoiskappaleet.</span><span class="sxs-lookup"><span data-stu-id="abe5b-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="abe5b-145">Kun olet poistanut suhteiden kaksoiskappaleet, yritä määrittää Power BI -yhdistin uudelleen.</span><span class="sxs-lookup"><span data-stu-id="abe5b-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="abe5b-146">Ympäristön tulisi nyt olla käytettävissä.</span><span class="sxs-lookup"><span data-stu-id="abe5b-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

