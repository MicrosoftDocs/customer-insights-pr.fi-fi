---
title: Yhtenäisten asiakasprofiilien rikastaminen
description: Asiakastietojen rikastaminen ominaisuuksien avulla.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667090"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="1e557-103">Asiakasprofiilien täydentäminen (esikatselu)</span><span class="sxs-lookup"><span data-stu-id="1e557-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="1e557-104">Voit täydentää asiakastietoja Microsoftin ja muiden kumppaneiden kaltaisten lähteiden tiedoilla.</span><span class="sxs-lookup"><span data-stu-id="1e557-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Rikastamiskeskuksen sivu":::

<span data-ttu-id="1e557-106">Käytä rikastamisasetuksia valitsemalla käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Rikastaminen**.</span><span class="sxs-lookup"><span data-stu-id="1e557-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="1e557-107">Sinulla on oltava osallistujan tai järjestelmänvalvojan oikeudet, jos haluat luoda tai muokata täydennyksiä.</span><span class="sxs-lookup"><span data-stu-id="1e557-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="1e557-108">Lisätietoja on kohdassa [Oikeudet](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="1e557-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="1e557-109">**Tutustu**-välilehdessä ovat seuraavat täydennykset:</span><span class="sxs-lookup"><span data-stu-id="1e557-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="1e557-110">Microsoft Graphin toimittamat [tuotemerkit](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="1e557-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="1e557-111">Microsoft Graphin toimittamat [kiinnostuksen kohteet](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="1e557-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="1e557-112">Leadspacen toimittamat [yritystiedot](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="1e557-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="1e557-113">Experianin toimittamat [demografiatiedot](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="1e557-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="1e557-114">HERE Technologiesin toimittamat [sijaintitiedot](enrichment-here.md)</span><span class="sxs-lookup"><span data-stu-id="1e557-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="1e557-115">[Tietojen mukauttaminen ](enrichment-SFTP-custom-import.md) suojatulla tiedostonsiirtoprotokollalla (SFTP)</span><span class="sxs-lookup"><span data-stu-id="1e557-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="1e557-116">**Omat täydennykset** -välilehdessä voit tarkastella määrittämiäsi täydennyksiä ja muokata niiden ominaisuuksia.</span><span class="sxs-lookup"><span data-stu-id="1e557-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="1e557-117">Aiemmin luotujen rikastusten hallinta</span><span class="sxs-lookup"><span data-stu-id="1e557-117">Manage existing enrichments</span></span>

<span data-ttu-id="1e557-118">Saat kaikki määritetyt rikastukset käyttöön valitsemalla **Omat rikastukset**.</span><span class="sxs-lookup"><span data-stu-id="1e557-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="1e557-119">Kullakin rikastuksella on rivi, joka sisältää lisätietoja rikastamisesta.</span><span class="sxs-lookup"><span data-stu-id="1e557-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="1e557-120">Saat käytettävissä olevat vaihtoehdot näkyviin valitsemalla rikastuksen.</span><span class="sxs-lookup"><span data-stu-id="1e557-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="1e557-121">Vaihtoehtoisesti saat vaihtoehdot näkyviin valitsemalla luettelossa kolme pistettä (...).</span><span class="sxs-lookup"><span data-stu-id="1e557-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Rikastusten hallinta-asetukset rikastamisluettelossa":::

- <span data-ttu-id="1e557-123">**Näytä** rikastuksen tiedot sekä rikastettujen asiakasprofiilien määrä.</span><span class="sxs-lookup"><span data-stu-id="1e557-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="1e557-124">**Muokkaa** rikastusmääritystä.</span><span class="sxs-lookup"><span data-stu-id="1e557-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="1e557-125">**Suorita** asiakasprofiilien rikastaminen uusimmilla tiedoilla.</span><span class="sxs-lookup"><span data-stu-id="1e557-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="1e557-126">**Poista aktivointi** aiemmin luodusta rikastuksesta, jolloin se ei enää päivity automaattisesti jokaisen ajoitetun päivityksen yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="1e557-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="1e557-127">Viimeisimmän onnistuneen päivityksen tiedot ovat edelleen käytettävissä.</span><span class="sxs-lookup"><span data-stu-id="1e557-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="1e557-128">**Aktivoi** passiivinen rikastus, jolloin automaattinen päivitys kunkin ajoitetun päivityksen yhteydessä aloitetaan uudelleen.</span><span class="sxs-lookup"><span data-stu-id="1e557-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="1e557-129">**Poista** rikastus.</span><span class="sxs-lookup"><span data-stu-id="1e557-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="1e557-130">Useita rikastamisia voi suorittaa tai poistaa käytöstä samanaikaisesti valitsemalla ne luettelossa.</span><span class="sxs-lookup"><span data-stu-id="1e557-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="1e557-131">Näyttämis- ja muokkausvaihtoehtoja ei voi käyttää joukkotoimintoja, vaan niitä voi käyttää kerralla vain yhdessä rikastamisessa.</span><span class="sxs-lookup"><span data-stu-id="1e557-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>
