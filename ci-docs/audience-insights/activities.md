---
title: Asiakasaktiviteetit
description: Asiakasaktiviteettien määrittäminen ja niiden näyttäminen asiakkaan aikajanalla.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596725"
---
# <a name="customer-activities"></a><span data-ttu-id="b62dd-103">Asiakasaktiviteetit</span><span class="sxs-lookup"><span data-stu-id="b62dd-103">Customer activities</span></span>

<span data-ttu-id="b62dd-104">Yhdistämällä asiakasaktiviteetteja Dynamics 365 Customer Insightsin [eri tietolähteistä](data-sources.md) voidaan luoda asiakkaan aikajana, jolla aktiviteetit ovat kronologisessa järjestyksessä.</span><span class="sxs-lookup"><span data-stu-id="b62dd-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="b62dd-105">Voit sisällyttää aikajanan Dynamics 365:n asiakkaan osallistamissovelluksiin [asiakaskortin apuohjelmalla](customer-card-add-in.md) tai Power BI -koontinäytön avulla.</span><span class="sxs-lookup"><span data-stu-id="b62dd-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="b62dd-106">Aktiviteetin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="b62dd-106">Define an activity</span></span>

<span data-ttu-id="b62dd-107">Tietolähteet sisältävät entiteettejä, joissa on tapahtuma- ja aktiviteettitietoja useita tietolähteistä.</span><span class="sxs-lookup"><span data-stu-id="b62dd-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="b62dd-108">Määritä, mitä nämä entiteetit ovat, ja valitse aktiviteetit, joita haluat tarkastella asiakkaan aikajanalla.</span><span class="sxs-lookup"><span data-stu-id="b62dd-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="b62dd-109">Valitse entiteetti, joka sisältää kohdeaktiviteetit.</span><span class="sxs-lookup"><span data-stu-id="b62dd-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="b62dd-110">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Aktiviteetit**.</span><span class="sxs-lookup"><span data-stu-id="b62dd-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="b62dd-111">Valitse **Lisää aktiviteetti**.</span><span class="sxs-lookup"><span data-stu-id="b62dd-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b62dd-112">Entiteetissä on oltava ainakin yksi määrite, jonka tyyppi on **Päivämäärä**, jotta se voidaan sisällyttää asiakkaan aikajanaa, eikä entiteettejä, joissa ei ole **Päivämäärä**-kenttiä, voi lisätä.</span><span class="sxs-lookup"><span data-stu-id="b62dd-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="b62dd-113">**Lisää aktiviteetti** -ohjausobjekti poistetaan käytöstä, jos kyseistä entiteettiä ei löydy.</span><span class="sxs-lookup"><span data-stu-id="b62dd-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="b62dd-114">Määritä **Lisää aktiviteetti** -ruudussa seuraavien kenttien arvot:</span><span class="sxs-lookup"><span data-stu-id="b62dd-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="b62dd-115">**Entiteetti**: valitse tapahtuma-tai aktiviteettitietoja sisältävä entiteetti.</span><span class="sxs-lookup"><span data-stu-id="b62dd-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="b62dd-116">**Perusavain**: Valitse kenttä, joka yksilöi tietueen.</span><span class="sxs-lookup"><span data-stu-id="b62dd-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="b62dd-117">Siinä ei saa olla arvojen kaksoiskappaleita, tyhjiä arvoja eikä puuttuvia arvoja.</span><span class="sxs-lookup"><span data-stu-id="b62dd-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="b62dd-118">**Aikaleima**: valitse kenttä, joka ilmaisee aktiviteetin aloitusajan.</span><span class="sxs-lookup"><span data-stu-id="b62dd-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="b62dd-119">**Tapahtuma**: valitse kenttä, joka on aktiviteetin tapahtuma.</span><span class="sxs-lookup"><span data-stu-id="b62dd-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="b62dd-120">**WWW-osoite**: Valitse kenttä, joka kuvaa URL-osoitetta ja sisältää tämän aktiviteetin lisätiedot.</span><span class="sxs-lookup"><span data-stu-id="b62dd-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="b62dd-121">Esimerkiksi tapahtumajärjestelmä, joka on tämän aktiviteetin aiheuttaja.</span><span class="sxs-lookup"><span data-stu-id="b62dd-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="b62dd-122">Tämä URL-osoite voi olla mikä tahansa tietolähteen kenttä, tai se voidaan muodostaa uutena kenttänä käyttämällä Power Query -muunnosta.</span><span class="sxs-lookup"><span data-stu-id="b62dd-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="b62dd-123">Nämä URL-tiedot tallennetaan Unified Activity -kohteeseen, joka voidaan käyttää siirtämällä palvelimelta ohjelmointirajapintojen avulla.</span><span class="sxs-lookup"><span data-stu-id="b62dd-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="b62dd-124">**Tiedot**: vaihtoehtoisesti voit valita lisätietoja varten lisättävän kentän.</span><span class="sxs-lookup"><span data-stu-id="b62dd-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="b62dd-125">**Kuvake**: vaihtoehtoisesti voit valita tämän aktiviteetin ilmaisevan kuvakkeen.</span><span class="sxs-lookup"><span data-stu-id="b62dd-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="b62dd-126">**Aktiviteetin tyyppi**: Määritä sellainen aktiviteetin tyypin viittaus Common Data Modeliin, joka parhaiten kuvaa aktiviteetin semanttista määritelmää.</span><span class="sxs-lookup"><span data-stu-id="b62dd-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="b62dd-127">Määritä **Määritä suhde** -osassa tiedot, jotka yhdistävät aktiviteettitiedot vastaavaan asiakkaaseen.</span><span class="sxs-lookup"><span data-stu-id="b62dd-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="b62dd-128">**Aktiviteetin entiteettikenttä**: Valitse aktiviteettikohteen kenttä, jonka avulla luodaan suhde toiseen entiteettiin.</span><span class="sxs-lookup"><span data-stu-id="b62dd-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="b62dd-129">**Asiakasentiteetti**: Valitse vastaava lähdeasiakas-entiteetti, johon aktiviteettikohde on suhteessa.</span><span class="sxs-lookup"><span data-stu-id="b62dd-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="b62dd-130">Voit liittyä vain sellaisiin lähdeasiakaskohteisiin, joita käytetään tietojen yhdistämisprosessissa.</span><span class="sxs-lookup"><span data-stu-id="b62dd-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="b62dd-131">**Asiakkaan entiteettikenttä**: Tässä kentässä näkyy lähdeasiakasentiteetin ensisijainen avain, joka on valittu yhdistämisprosessissa.</span><span class="sxs-lookup"><span data-stu-id="b62dd-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="b62dd-132">Tämän lähdeasiakaskohteen perusavainkentän avulla luodaan suhde aktiviteettientiteettiin.</span><span class="sxs-lookup"><span data-stu-id="b62dd-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="b62dd-133">**Nimi**: Jos tämän aktiviteettikohteen ja valitun lähdeasiakasentiteetin välinen suhde on jo olemassa, suhteen nimi on vain luku -tilassa.</span><span class="sxs-lookup"><span data-stu-id="b62dd-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="b62dd-134">Jos tällaista suhdetta ei ole olemassa, luodaan uusi suhde, jolla on tässä annettu nimi.</span><span class="sxs-lookup"><span data-stu-id="b62dd-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b62dd-135">![Entiteettisuhteen määrittäminen](media/activities-entities-define.png "Entiteettisuhteen määrittäminen")</span><span class="sxs-lookup"><span data-stu-id="b62dd-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="b62dd-136">Ota muutokset käyttöön valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="b62dd-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="b62dd-137">Valitse **Aktiviteetit**-sivulla **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="b62dd-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="b62dd-138">Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="b62dd-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="b62dd-139">Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="b62dd-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="b62dd-140">Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja.</span><span class="sxs-lookup"><span data-stu-id="b62dd-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="b62dd-141">Kun työn jossakin tehtävissä on valittu **Näytä tiedot**, saat lisätietoja: käsittelyajan, viimeisimmän käsittelypäivämäärän sekä kaikki tehtävään liitetyt virheet ja varoitukset.</span><span class="sxs-lookup"><span data-stu-id="b62dd-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="b62dd-142">Aktiviteetin muokkaaminen</span><span class="sxs-lookup"><span data-stu-id="b62dd-142">Edit an activity</span></span>

1. <span data-ttu-id="b62dd-143">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Aktiviteetit**.</span><span class="sxs-lookup"><span data-stu-id="b62dd-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="b62dd-144">Valitse aktiviteettientiteetti, jota haluat muokata ja valitse **Muokkaa**.</span><span class="sxs-lookup"><span data-stu-id="b62dd-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="b62dd-145">Voit myös siirtää kohdistimen entiteettirivin kohdalle ja valita **Muokkaa**-kuvakkeen.</span><span class="sxs-lookup"><span data-stu-id="b62dd-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="b62dd-146">Napsauta **Muokkaa**-kuvaketta.</span><span class="sxs-lookup"><span data-stu-id="b62dd-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="b62dd-147">Päivitä **Muokkaa aktiviteettia** -ruudussa arvot ja valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="b62dd-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="b62dd-148">Valitse **Aktiviteetit**-sivulla **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="b62dd-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="b62dd-149">Aktiviteetin poistaminen</span><span class="sxs-lookup"><span data-stu-id="b62dd-149">Delete an activity</span></span>

1. <span data-ttu-id="b62dd-150">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Aktiviteetit**.</span><span class="sxs-lookup"><span data-stu-id="b62dd-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="b62dd-151">Valitse aktiviteettientiteetti, jonka haluat poistaa ja valitse **Poista**.</span><span class="sxs-lookup"><span data-stu-id="b62dd-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="b62dd-152">Voit myös siirtää kohdistimen entiteettirivin kohdalle ja valita **Poista**-kuvakkeen.</span><span class="sxs-lookup"><span data-stu-id="b62dd-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="b62dd-153">Voit myös valita useita aktiviteettikohteita poistettavaksi kerralla.</span><span class="sxs-lookup"><span data-stu-id="b62dd-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b62dd-154">![Muokkaa tai poista entiteettisuhde](media/activities-entities-edit-delete.png "Muokkaa tai poista entiteettisuhde").</span><span class="sxs-lookup"><span data-stu-id="b62dd-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="b62dd-155">Valitse **Poista**-kuvake.</span><span class="sxs-lookup"><span data-stu-id="b62dd-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="b62dd-156">Vahvista poisto.</span><span class="sxs-lookup"><span data-stu-id="b62dd-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]