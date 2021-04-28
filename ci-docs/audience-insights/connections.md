---
title: Yhteydet muihin palveluihin Customer Insightsista.
description: Tietojen jakaminen muille palveluille.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896093"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="fcdd3-103">Yhteydet (esiversio) – yleiskuvaus</span><span class="sxs-lookup"><span data-stu-id="fcdd3-103">Connections (preview) overview</span></span>

<span data-ttu-id="fcdd3-104">Yhteydet ovat avain, joka mahdollistaa tietojen jakamisen Customer Insightsiin ja ulos sieltä.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="fcdd3-105">Kukin yhteys muodostaa tietojen jakamisen tietyn palvelun kanssa.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="fcdd3-106">Yhteydet ovat perusta [kolmansien osapuolten rikastusten määrittämiselle](enrichment-hub.md) ja [viennin määrittämiselle](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="fcdd3-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="fcdd3-107">Samaa yhteyttä voidaan käyttää useita kertoja.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="fcdd3-108">Esimerkiksi yksi yhteys Dynamics 365 Marketingiin toimii useaa vientiä varten ja yhtä Leadspace-yhteyttä voi käyttää useisiin rikastuksiin.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="fcdd3-109">Luo ja tarkastele yhteyksiä kohdassa **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="fcdd3-110">**Yhteydet**-välilehdessä näkyvät kaikki aktiiviset yhteydet.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="fcdd3-111">Luettelossa näkyy rivi kutakin yhteyttä varten.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="fcdd3-112">Saat **Tutustu**-välilehdessä nopean yleiskatsauksen, kuvauksen ja tietoja siitä, mitä kullakin laajennettavuusvaihtoehdolla voi tehdä.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="fcdd3-113">Viennit</span><span class="sxs-lookup"><span data-stu-id="fcdd3-113">Exports</span></span>

<span data-ttu-id="fcdd3-114">Vain järjestelmänvalvojat voivat määrittää uusia yhteyksiä, mutta he voivat myöntää osallistujille käyttöoikeudet aiemmin luotujen yhteyksien käyttöön.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="fcdd3-115">Järjestelmänvalvojat määrittävät tietojen lähtemisen, osallistujat määrittävät tiedot ja tiheyden, joka vastaa heidän tarpeitaan.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="fcdd3-116">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="fcdd3-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="fcdd3-117">Rikastukset</span><span class="sxs-lookup"><span data-stu-id="fcdd3-117">Enrichments</span></span>

<span data-ttu-id="fcdd3-118">Vain järjestelmänvalvojat voivat määrittää uusia yhteyksiä, mutta luodut yhteydet ovat aina sekä järjestelmänvalvojien että osallistujien käytettävissä.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="fcdd3-119">Järjestelmänvalvojat hallinnoivat tunnistetietoja ja antavat hyväksyntänsä tietojen siirroille.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="fcdd3-120">Tämän jälkeen sekä järjestelmänvalvojat että osallistujat voivat käyttää yhteyksiä rikastuksiin.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="fcdd3-121">Lisää uusi yhteys</span><span class="sxs-lookup"><span data-stu-id="fcdd3-121">Add a new connection</span></span>

<span data-ttu-id="fcdd3-122">Jotta voit lisätä yhteyksiä, tarvitset [järjestelmänvalvojan käyttöoikeudet](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="fcdd3-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="fcdd3-123">Jos muodostat yhteyden muihin Microsoftin palveluihin, oletamme, että molemmat palvelut ovat samassa organisaatiossa.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="fcdd3-124">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet (esiversio)**.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="fcdd3-125">Siirry **Yhteydet**-välilehteen.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="fcdd3-126">Luo uusi yhteys valitsemalla **Lisää yhteys**.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="fcdd3-127">Valitse avattavasta valikosta luotavan yhteyden tyyppi.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="fcdd3-128">Anna **Määritä yhteys** -ruudussa tarvittavat tiedot.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="fcdd3-129">Yhteyden **Näyttönimi** ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="fcdd3-130">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="fcdd3-131">Täsmälliset kentät määräytyvät sen mukaan, mihin palveluun muodostat yhteyden.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="fcdd3-132">Saat tietoja liittyvästä yhteystyypistä kohdepalvelun artikkelista.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="fcdd3-133">luo yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="fcdd3-134">Voit myös valita **Määritä** **Tutustu**-välilehden ruudussa.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="fcdd3-135">Salli osallistujien käyttää yhteyttä vientiin</span><span class="sxs-lookup"><span data-stu-id="fcdd3-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="fcdd3-136">Kun määrität tai muokkaat vientiyhteyttä, valitse käyttäjät, joilla on oikeus käyttää tätä yhteyttä [vientien](export-destinations.md) määrittämiseen.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="fcdd3-137">Yhteys on oletusarvoisesti niiden käyttäjien käytettävissä, joilla on järjestelmänvalvojan rooli.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="fcdd3-138">Voit muuttaa tätä asetusta kohdassa **Valitse, kuka voi käyttää tätä yhteyttä** ja sallia osallistujaroolin käyttäjien käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="fcdd3-139">Osallistujat eivät voi tarkastella tai muokata yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="fcdd3-140">He näkevät vain näyttönimen tyypin ja tyypin vientiä luodessaan.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="fcdd3-141">Kun jaat yhteyden, osallistujat voivat käyttää yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="fcdd3-142">Osallistujat näkevät jaetut yhteydet vientiä määrittäessään.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="fcdd3-143">He voivat hallita jokaista tätä yhteyttä käyttävää vientiä.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="fcdd3-144">Voit muuttaa tätä asetusta niin, että säilytetään osallistujien jo määrittämät viennit.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="fcdd3-145">Yhteyden muokkaaminen</span><span class="sxs-lookup"><span data-stu-id="fcdd3-145">Edit a connection</span></span>

1. <span data-ttu-id="fcdd3-146">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet (esiversio)**.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="fcdd3-147">Siirry **Yhteydet**-välilehteen.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="fcdd3-148">Valitse muokattavan yhteyden kohdalla kolme allekkaista pistettä.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="fcdd3-149">Valitse **muokkaa**.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-149">Select **Edit**.</span></span>

1. <span data-ttu-id="fcdd3-150">Muuta päivitettävät arvot ja valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="fcdd3-151">Yhteyden poistaminen</span><span class="sxs-lookup"><span data-stu-id="fcdd3-151">Remove a connection</span></span>

<span data-ttu-id="fcdd3-152">Jos poistettavaa yhteyttä käyttävät rikastukset tai viennit, ne on ensin irrotettava tai poistettava.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="fcdd3-153">Poistoikkuna opastaa sinut liittyviin rikastuksiin tai vienteihin.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="fcdd3-154">irrotetut rikastukset ja viennit muuttuvat passiivisiksi.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="fcdd3-155">Voit aktivoida ne uudelleen lisäämällä niihin toisen yhteyden [Rikastus](enrichment-hub.md)- tai [Viennit](export-destinations.md)-sivulla.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="fcdd3-156">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet (esiversio)**.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="fcdd3-157">Siirry **Yhteydet**-välilehteen.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="fcdd3-158">Valitse poistettavan yhteyden kohdalla kolme allekkaista pistettä.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="fcdd3-159">Valitse avattavassa valikossa **Poista**.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="fcdd3-160">Vahvistusvalintaikkuna avautuu.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="fcdd3-161">Jos tätä yhteyttä käyttää jokin rikastus tai vienti, valitse painike, kun haluat nähdä, mikä käyttää yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="fcdd3-162">**Viennit:** Voit joko poistaa viennin tai katkaista yhteyden, jos haluat poistaa yhteyden.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="fcdd3-163">Järjestelmänvalvojat voivat katkaista viennin yhteyden **Katkaise yhteys** -toiminnon avulla.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="fcdd3-164">Tämä toiminto on käytettävissä yksittäisille ja useille valituille viennille.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="fcdd3-165">Kun katkaiset yhteyden, säilytät vientimäärityksen, mutta se suoritetaan vasta, kun siihen on lisätty toinen yhteys.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="fcdd3-166">**Rikastukset:** Voit joko poistaa rikastuksen tai passivoida sen, jos haluat poistaa yhteyden.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="fcdd3-167">Kun yhteydellä ei ole enää riippuvuuksia, palaa kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja yritä poistaa yhteys uudelleen.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="fcdd3-168">Vahvista poisto valitsemalla **Poista**.</span><span class="sxs-lookup"><span data-stu-id="fcdd3-168">To confirm the deletion select **Remove**.</span></span>

