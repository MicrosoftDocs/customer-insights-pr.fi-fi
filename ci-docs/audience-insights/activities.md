---
title: Asiakasaktiviteetit
description: Asiakasaktiviteettien määrittäminen ja niiden näyttäminen asiakkaan aikajanalla.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304922"
---
# <a name="customer-activities"></a><span data-ttu-id="8914c-103">Asiakasaktiviteetit</span><span class="sxs-lookup"><span data-stu-id="8914c-103">Customer activities</span></span>

<span data-ttu-id="8914c-104">Yhdistämällä [eri tietolähteiden](data-sources.md) asiakasaktiviteetteja Dynamics 365 Customer Insightsissa voit luoda aikajanan, jossa aktiviteetit näkyvät aikajärjestyksessä.</span><span class="sxs-lookup"><span data-stu-id="8914c-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="8914c-105">Sisällytä aikajana Dynamics 365 -sovelluksiin [Asiakaskortin-apuohjelma](customer-card-add-in.md) -ratkaisulla tai Power BI -koontinäytön avulla.</span><span class="sxs-lookup"><span data-stu-id="8914c-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="8914c-106">Aktiviteetin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="8914c-106">Define an activity</span></span>

<span data-ttu-id="8914c-107">Tietolähteet voivat sisältää entiteettejä, joissa on tapahtuma- ja aktiviteettitietoja useita tietolähteistä.</span><span class="sxs-lookup"><span data-stu-id="8914c-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="8914c-108">Määritä, mitä nämä entiteetit ovat, ja valitse aktiviteetit, joita haluat tarkastella asiakkaan aikajanalla.</span><span class="sxs-lookup"><span data-stu-id="8914c-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="8914c-109">Valitse entiteetti, joka sisältää kohdeaktiviteetit.</span><span class="sxs-lookup"><span data-stu-id="8914c-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="8914c-110">Entiteetissä on oltava ainakin yksi määrite, jonka tyyppi on **Päivämäärä**, jotta se voidaan sisällyttää asiakkaan aikajanaa, eikä entiteettejä, joissa ei ole **Päivämäärä**-kenttiä, voi lisätä.</span><span class="sxs-lookup"><span data-stu-id="8914c-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="8914c-111">**Lisää aktiviteetti** -ohjausobjekti poistetaan käytöstä, jos kyseistä entiteettiä ei löydy.</span><span class="sxs-lookup"><span data-stu-id="8914c-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="8914c-112">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Aktiviteetit**.</span><span class="sxs-lookup"><span data-stu-id="8914c-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="8914c-113">Valitse **Lisää aktiviteetti**, jos haluat aloittaa ohjatun käyttökokemuksen aktiviteetin määritysprosessille.</span><span class="sxs-lookup"><span data-stu-id="8914c-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="8914c-114">Määritä **Aktiviteettitiedot**-vaiheessa seuraavien kenttien arvot:</span><span class="sxs-lookup"><span data-stu-id="8914c-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="8914c-115">**Aktiviteetin nimi**: Valitse aktiviteetille nimi.</span><span class="sxs-lookup"><span data-stu-id="8914c-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="8914c-116">**Entiteetti**: valitse tapahtuma-tai aktiviteettitietoja sisältävä entiteetti.</span><span class="sxs-lookup"><span data-stu-id="8914c-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="8914c-117">**Perusavain**: Valitse kenttä, joka yksilöi tietueen.</span><span class="sxs-lookup"><span data-stu-id="8914c-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="8914c-118">Siinä ei saa olla arvojen kaksoiskappaleita, tyhjiä arvoja eikä puuttuvia arvoja.</span><span class="sxs-lookup"><span data-stu-id="8914c-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Määritä aktiviteettitiedot: nimi, entiteetti ja perusavain.":::

1. <span data-ttu-id="8914c-120">Siirry seuraavaan vaiheeseen valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="8914c-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="8914c-121">Määritä **Suhde**-vaiheessa tiedot, jotka yhdistät aktiviteettitiedot vastaavaan asiakkaaseen.</span><span class="sxs-lookup"><span data-stu-id="8914c-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="8914c-122">Tässä vaiheessa visualisoidaan entiteettien väliset yhteydet.</span><span class="sxs-lookup"><span data-stu-id="8914c-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="8914c-123">**Ensimmäinen**: Aktiviteettientiteetin viitekenttä, jonka avulla luodaan suhde toiseen entiteettiin.</span><span class="sxs-lookup"><span data-stu-id="8914c-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="8914c-124">**Toinen**: Vastaava lähdeasiakasentiteetti, johon aktiviteettientiteetti on suhteessa.</span><span class="sxs-lookup"><span data-stu-id="8914c-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="8914c-125">Voit liittää tietoja vain lähdeasiakasentiteetteihin, joita käytetään tietojen yhdistämisprosessissa.</span><span class="sxs-lookup"><span data-stu-id="8914c-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="8914c-126">**Kolmas**: Jos tämän aktiviteettientiteetin ja valitun lähdeasiakasentiteetin välinen suhde on jo olemassa, suhteen nimi on vain luku -tilassa.</span><span class="sxs-lookup"><span data-stu-id="8914c-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="8914c-127">Jos tällaista suhdetta ei ole, luodaan uusi suhde. Sen nimeksi tulee tähän ruutuun määritetty nimi.</span><span class="sxs-lookup"><span data-stu-id="8914c-127">If no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Entiteettisuhteen määrittäminen.":::

1. <span data-ttu-id="8914c-129">Siirry seuraavaan vaiheeseen valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="8914c-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="8914c-130">Valitse **Aktiviteetin yhdistäminen** -vaiheessa aktiviteettitapahtuma ja aktiviteetin aloitusaika.</span><span class="sxs-lookup"><span data-stu-id="8914c-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="8914c-131">**Pakolliset kentät**</span><span class="sxs-lookup"><span data-stu-id="8914c-131">**Required fields**</span></span>
      - <span data-ttu-id="8914c-132">**Tapahtuma-aktiviteetti**: kenttä, joka on tämän aktiviteetin tapahtuma.</span><span class="sxs-lookup"><span data-stu-id="8914c-132">**Event activity**: Field that is the event for this activity.</span></span>
      - <span data-ttu-id="8914c-133">**Aikaleima**: Kenttä, joka edustaa aktiviteetin aloitusaikaa.</span><span class="sxs-lookup"><span data-stu-id="8914c-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="8914c-134">**Valinnaiset kentät**</span><span class="sxs-lookup"><span data-stu-id="8914c-134">**Optional fields**</span></span>
      - <span data-ttu-id="8914c-135">**Lisätietoja**: Kenttä, jossa on tähän aktiviteettiin liittyviä tietoja.</span><span class="sxs-lookup"><span data-stu-id="8914c-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      - <span data-ttu-id="8914c-136">**Kuvake**: kuvake, joka parhaiten edustaa tätä aktiviteettityyppiä.</span><span class="sxs-lookup"><span data-stu-id="8914c-136">**Icon**: Icon that best represents this activity type.</span></span>
      - <span data-ttu-id="8914c-137">**WWW-osoite**: Kenttä, joka sisältää tätä aktiviteettia koskevat tiedot sisältävän URL-osoitteen.</span><span class="sxs-lookup"><span data-stu-id="8914c-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="8914c-138">Esimerkiksi tapahtumajärjestelmä, joka on tämän aktiviteetin aiheuttaja.</span><span class="sxs-lookup"><span data-stu-id="8914c-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="8914c-139">Tämä URL-osoite voi olla mikä tahansa tietolähteen kenttä, tai se voidaan muodostaa uutena kenttänä käyttämällä Power Query -muunnosta.</span><span class="sxs-lookup"><span data-stu-id="8914c-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="8914c-140">URL-osoitteen tiedot tallennetaan *Yhdistetty aktiviteetti* -entiteettiin, jota voidaan käyttää [ohjelmointirajapintojen](apis.md) käytön jälkeen.</span><span class="sxs-lookup"><span data-stu-id="8914c-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Määritä asiakasaktiviteetin tiedot Yhdistetty aktiviteetti -entiteetissä.":::

1. <span data-ttu-id="8914c-142">Siirry seuraavaan vaiheeseen valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="8914c-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="8914c-143">Voit tallentaa aktiviteetin nyt valitsemalla **Viimeistele ja tarkista**, kun aktiviteettityypiksi on määritetty **Muu**.</span><span class="sxs-lookup"><span data-stu-id="8914c-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="8914c-144">Valitse **Aktiviteettityyppi**-vaiheessa aktiviteetin tyyppi ja valitse tarvittaessa, haluatko yhdistää jotkin aktiviteettityypit semanttisesti käytettäväksi muissa Customer Insights -alueissa.</span><span class="sxs-lookup"><span data-stu-id="8914c-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="8914c-145">Tällä hetkellä *Subscription*- ja *SalesOrderLine*-aktiviteettityypit voidaan yhdistää semanttisesti sen jälkeen, kun on tehty päätös kenttien yhdistämisestä.</span><span class="sxs-lookup"><span data-stu-id="8914c-145">Currently, *Subscription* and *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="8914c-146">Jos aktiviteettityypillä ei ole merkitystä uudelle aktiviteetille, voit valita mukautetulle aktiviteettityypille *Muu* tai *Luo uusi*.</span><span class="sxs-lookup"><span data-stu-id="8914c-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="8914c-147">Siirry seuraavaan vaiheeseen valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="8914c-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="8914c-148">Tarkista valinnat **Tarkista**-vaiheessa.</span><span class="sxs-lookup"><span data-stu-id="8914c-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="8914c-149">Palaa mihin tahansa edellä esitettyyn vaiheeseen ja päivitä tiedot tarvittaessa.</span><span class="sxs-lookup"><span data-stu-id="8914c-149">Go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Tarkista aktiviteetin määritetyt kentät.":::
   
1. <span data-ttu-id="8914c-151">Valitse **Tallenna aktiviteetti**, jos haluat ottaa muutokset käyttöön ja palata kohtaan **Tiedot** > **Aktiviteetit** valitsemalla **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="8914c-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="8914c-152">Tässä näet aikajanalla näytettävät aktiviteetit.</span><span class="sxs-lookup"><span data-stu-id="8914c-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="8914c-153">Käsittele aktiviteetti valitsemalla **Aktiviteetit**-sivulla **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="8914c-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="8914c-154">Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="8914c-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="8914c-155">Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="8914c-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="8914c-156">Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja.</span><span class="sxs-lookup"><span data-stu-id="8914c-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="8914c-157">Kun työn jossakin tehtävissä on valittu **Näytä tiedot**, saat lisätietoja: käsittelyajan, viimeisimmän käsittelypäivämäärän sekä kaikki tehtävään liitetyt virheet ja varoitukset.</span><span class="sxs-lookup"><span data-stu-id="8914c-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="8914c-158">Aiemmin luotujen aktiviteettien hallinta</span><span class="sxs-lookup"><span data-stu-id="8914c-158">Manage existing activities</span></span>

<span data-ttu-id="8914c-159">Kohdassa **Tiedot** > **Aktiviteetit** voit tarkastella kaikkia tallennettuja aktiviteetteja ja hallita niitä.</span><span class="sxs-lookup"><span data-stu-id="8914c-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="8914c-160">Kutakin aktiviteettia edustaa rivi, joka sisältää myös lähdettä, entiteettiä ja aktiviteettityyppiä koskevat tiedot.</span><span class="sxs-lookup"><span data-stu-id="8914c-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="8914c-161">Seuraavat toiminnot ovat käytettävissä, kun valitset aktiviteetin.</span><span class="sxs-lookup"><span data-stu-id="8914c-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="8914c-162">**Muokkaa**: avaa aktiviteettiasetukset tarkistusvaiheessa.</span><span class="sxs-lookup"><span data-stu-id="8914c-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="8914c-163">Voit muuttaa mitä tahansa tai kaikkia nykyisiä määrityksiä tässä vaiheessa.</span><span class="sxs-lookup"><span data-stu-id="8914c-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="8914c-164">Kun olet muuttanut kokoonpanoa, valitse **Tallenna aktiviteetti** ja käsittele sitten muutokset valitsemalla **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="8914c-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="8914c-165">**Nimeä uudelleen**: Avaa valintaikkunan, jossa voit syöttää valitulle aktiviteetille eri nimen.</span><span class="sxs-lookup"><span data-stu-id="8914c-165">**Rename**: Opens a dialog where you can enter a different name for the selected activity.</span></span> <span data-ttu-id="8914c-166">Ota muutokset käyttöön valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="8914c-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="8914c-167">**Poista**: avaa dialogin, joka vahvistaa valitun aktiviteetin poistamisen.</span><span class="sxs-lookup"><span data-stu-id="8914c-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="8914c-168">Voit myös poistaa useita aktiviteetteja kerralla valitsemalla aktiviteetit ja valitsemalla sitten poistokuvakkeen.</span><span class="sxs-lookup"><span data-stu-id="8914c-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="8914c-169">Vahvista poisto valitsemalla **Poista**.</span><span class="sxs-lookup"><span data-stu-id="8914c-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
