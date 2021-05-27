---
title: Yhtenäisten asiakasprofiilien rikastaminen
description: Asiakastietojen rikastaminen ominaisuuksien avulla.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954483"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="b0df6-103">Asiakasprofiilien täydentäminen (esikatselu)</span><span class="sxs-lookup"><span data-stu-id="b0df6-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="b0df6-104">Voit täydentää asiakastietoja Microsoftin ja muiden kumppaneiden kaltaisten lähteiden tiedoilla.</span><span class="sxs-lookup"><span data-stu-id="b0df6-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Rikastamiskeskuksen sivu":::

<span data-ttu-id="b0df6-106">Käytä rikastamisasetuksia valitsemalla käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Rikastaminen**.</span><span class="sxs-lookup"><span data-stu-id="b0df6-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="b0df6-107">Sinulla on oltava osallistujan tai järjestelmänvalvojan oikeudet, jos haluat luoda tai muokata täydennyksiä.</span><span class="sxs-lookup"><span data-stu-id="b0df6-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="b0df6-108">Lisätietoja on kohdassa [Oikeudet](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b0df6-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="b0df6-109">**Tutustu**-välilehdessä ovat seuraavat täydennykset:</span><span class="sxs-lookup"><span data-stu-id="b0df6-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="b0df6-110">[Tuotemerkit](enrichment-microsoft.md), jotka toimittaa Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0df6-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="b0df6-111">[Kiinnostuksen kohteet](enrichment-microsoft.md), jotka toimittaa Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0df6-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="b0df6-112">Microsoftin toimittamat [Parannetut osoitteet](enrichment-enhanced-addresses.md)</span><span class="sxs-lookup"><span data-stu-id="b0df6-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="b0df6-113">Leadspacen toimittamat [yritystiedot](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="b0df6-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="b0df6-114">Experianin toimittamat [demografiatiedot](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="b0df6-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="b0df6-115">HERE Technologiesin toimittamat [sijaintitiedot](enrichment-here.md)</span><span class="sxs-lookup"><span data-stu-id="b0df6-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="b0df6-116">[Tietojen mukauttaminen ](enrichment-SFTP-custom-import.md) suojatulla tiedostonsiirtoprotokollalla (SFTP)</span><span class="sxs-lookup"><span data-stu-id="b0df6-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="b0df6-117">**Omat täydennykset** -välilehdessä voit tarkastella määrittämiäsi täydennyksiä ja muokata niiden ominaisuuksia.</span><span class="sxs-lookup"><span data-stu-id="b0df6-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="b0df6-118">Aiemmin luotujen rikastusten hallinta</span><span class="sxs-lookup"><span data-stu-id="b0df6-118">Manage existing enrichments</span></span>

<span data-ttu-id="b0df6-119">Saat kaikki määritetyt rikastukset käyttöön valitsemalla **Omat rikastukset**.</span><span class="sxs-lookup"><span data-stu-id="b0df6-119">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="b0df6-120">Kullakin rikastuksella on rivi, joka sisältää lisätietoja rikastamisesta.</span><span class="sxs-lookup"><span data-stu-id="b0df6-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="b0df6-121">Saat käytettävissä olevat vaihtoehdot näkyviin valitsemalla rikastuksen.</span><span class="sxs-lookup"><span data-stu-id="b0df6-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="b0df6-122">Voit myös valita luettelokohteesta kolme pistettä (...), kun haluat nähdä vaihtoehdot.</span><span class="sxs-lookup"><span data-stu-id="b0df6-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Rikastusten hallinta-asetukset rikastamisluettelossa":::

- <span data-ttu-id="b0df6-124">**Näytä** rikastuksen tiedot sekä rikastettujen asiakasprofiilien määrä.</span><span class="sxs-lookup"><span data-stu-id="b0df6-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="b0df6-125">**Muokkaa** rikastusmääritystä.</span><span class="sxs-lookup"><span data-stu-id="b0df6-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="b0df6-126">**Suorita** asiakasprofiilien rikastaminen uusimmilla tiedoilla.</span><span class="sxs-lookup"><span data-stu-id="b0df6-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="b0df6-127">**Poista aktivointi** aiemmin luodusta rikastuksesta, jolloin se ei enää päivity automaattisesti jokaisen ajoitetun päivityksen yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="b0df6-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="b0df6-128">Viimeisimmän onnistuneen päivityksen tiedot ovat edelleen käytettävissä.</span><span class="sxs-lookup"><span data-stu-id="b0df6-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="b0df6-129">**Aktivoi** passiivinen rikastus, jolloin automaattinen päivitys kunkin ajoitetun päivityksen yhteydessä aloitetaan uudelleen.</span><span class="sxs-lookup"><span data-stu-id="b0df6-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="b0df6-130">**Poista** rikastus.</span><span class="sxs-lookup"><span data-stu-id="b0df6-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="b0df6-131">Useita rikastamisia voi suorittaa tai poistaa käytöstä samanaikaisesti valitsemalla ne luettelossa.</span><span class="sxs-lookup"><span data-stu-id="b0df6-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="b0df6-132">Näyttämis- ja muokkausvaihtoehtoja ei voi käyttää joukkotoimintoja, vaan niitä voi käyttää kerralla vain yhdessä rikastamisessa.</span><span class="sxs-lookup"><span data-stu-id="b0df6-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="b0df6-133">Rikastukset ja yhteydet</span><span class="sxs-lookup"><span data-stu-id="b0df6-133">Enrichments and connections</span></span>

<span data-ttu-id="b0df6-134">Kolmannen osapuolen rikastukset määritetään käyttämällä [yhteyksiä](connections.md), jotka järjestelmänvalvoja tunnistetiedoilla ja antaa tietojen siirron hyväksynnän.</span><span class="sxs-lookup"><span data-stu-id="b0df6-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="b0df6-135">Tämän jälkeen sekä järjestelmänvalvojat että osallistujat voivat käyttää yhteyttä rikastusten määrittämiseen.</span><span class="sxs-lookup"><span data-stu-id="b0df6-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="b0df6-136">Useita samantyyppisiä rikastuksia</span><span class="sxs-lookup"><span data-stu-id="b0df6-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="b0df6-137">Rikastusmäärityksen yhteydessä määritettävä rikastettava entiteetti, joka sallii vain vain profiilien alijoukon rikastamisen.</span><span class="sxs-lookup"><span data-stu-id="b0df6-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="b0df6-138">Voit rikastaa tiedot esim. vain tiettyä segmenttiä varten.</span><span class="sxs-lookup"><span data-stu-id="b0df6-138">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="b0df6-139">Voit määrittää useita samantyyppisiä rikastuksia ja käyttää samaa yhteyttä uudelleen.</span><span class="sxs-lookup"><span data-stu-id="b0df6-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="b0df6-140">Joillakin rikastuksilla on rajansa samantyyppisten rikastusten luonnin määrälle.</span><span class="sxs-lookup"><span data-stu-id="b0df6-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="b0df6-141">Rajoitukset ja nykyinen käyttö näkyy **Rikastus**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="b0df6-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
