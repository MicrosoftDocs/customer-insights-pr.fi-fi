---
title: Jaetut tehtävät ennusteskenaarioita varten
description: Opettele hallitsemaan, määrittämään vikoja ja hiomaan ennusteita.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315874"
---
# <a name="manage-predictions"></a><span data-ttu-id="3e5c6-103">Hallitse ennusteita</span><span class="sxs-lookup"><span data-stu-id="3e5c6-103">Manage predictions</span></span>

<span data-ttu-id="3e5c6-104">Tässä artikkelissa käsitellään joitakin tehtäviä, jotka useimmat ennusteskenaariot jakavat.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="3e5c6-105">Epäonnistuneen ennusteen vianmääritys</span><span class="sxs-lookup"><span data-stu-id="3e5c6-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="3e5c6-106">Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="3e5c6-107">Valitse kolme allekkain olevaa pistettä sen ennusteen vieressä, jonka virhelokeja haluat tarkastella.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="3e5c6-108">Valitse **Lokit**.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-108">Select **Logs**.</span></span>

1. <span data-ttu-id="3e5c6-109">Tarkastele kaikkia virheitä.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-109">Review all the errors.</span></span> <span data-ttu-id="3e5c6-110">Mahdollisia virhe tyyppejä on useita. Ne osoittavat, mikä ehto aiheutti virheen.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="3e5c6-111">Esimerkiksi virhe, joka osoittaa olemassa olevien tietojen olevan riittämättömät tarkan ennusteen luomiseksi, ratkaistaan yleensä lataamalla lisää tietoja Customer Insightsiin.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="3e5c6-112">Syötetietojen käytettävyysraportti</span><span class="sxs-lookup"><span data-stu-id="3e5c6-112">Input data usability report</span></span>

<span data-ttu-id="3e5c6-113">Syöttötietojen käytettävyysraportti tarjoaa konsolidoidun kuvan virheistä ja varoituksista, joita valmiit ennusteet saattavat tuottaa.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="3e5c6-114">Se antaa myös suosituksia mallin suorituskyvyn parantamista varten.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="3e5c6-115">Raportti on käytettävissä sen jälkeen, kun malli on suorittanut sen koulutusprosessin.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="3e5c6-116">Se luodaan kullekin mallille erikseen riippumatta siitä, onnistuiko malli.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="3e5c6-117">Näytä syötetietojen käytettävyysraportti</span><span class="sxs-lookup"><span data-stu-id="3e5c6-117">View the input data usability report</span></span>

<span data-ttu-id="3e5c6-118">Kun valmiin mallin koulutusvaihe on valmis, tarkastele raporttia:</span><span class="sxs-lookup"><span data-stu-id="3e5c6-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="3e5c6-119">Valitse mallin nimen vierestä kolme pistettä ja valitse sitten **Syötetietojen käytettävyysraportti**.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="3e5c6-120">Valitse mallin tila valitsemalla sivuruudusta **Näytä tietojen käytettävyysraportti**.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="3e5c6-121">Valitse luettelosta jokin malleista ja valitse komentopalkissa **Tietojen käytettävyysraportti**.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="3e5c6-122">Avaa mallien tulossivu ja valitse komentopalkissa **Tietojen käytettävyysraportti**.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="3e5c6-123">Tiedot syötetietojen käytettävyysraportissa</span><span class="sxs-lookup"><span data-stu-id="3e5c6-123">Information in the input data usability report</span></span>

<span data-ttu-id="3e5c6-124">Seuraavissa raportin sarakkeissa on hyödyllisiä tietoja mallin tietojen parantamiseksi.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Esimerkki syöttötietojen käytettävyysraportista, jossa näkyy taulukko, jossa on virheitä, varoituksia ja suosituksia.":::

- <span data-ttu-id="3e5c6-126">Nimi: virheen, varoituksen tai suosituksen kuvaileva nimi.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="3e5c6-127">Vaihe: mallivaihe, kouluttaa tai pisteyttää, tietoihin viitataan.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="3e5c6-128">Tila: tietojen vakavuus (virhe, varoitus, suositus).</span><span class="sxs-lookup"><span data-stu-id="3e5c6-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="3e5c6-129">Sarakkeen nimi: Entiteetin sarake, jota on muutettava mallin suorituskyvyn parantamiseksi.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="3e5c6-130">Entiteetin nimi: Entiteetin nimi, jota on muutettava mallin suorituskyvyn parantamiseksi.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="3e5c6-131">Tiedot: Tietoja virheestä, varoituksesta tai suosituksista.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="3e5c6-132">Ennusteen päivittäminen</span><span class="sxs-lookup"><span data-stu-id="3e5c6-132">Refresh a prediction</span></span>

<span data-ttu-id="3e5c6-133">Ennusteet päivittyvät automaattisesti saman [aikataulun mukaan kuin tiedot päivitetään](system.md#schedule-tab) asetuksissa määritetyllä tavalla.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="3e5c6-134">Voit päivittää ne myös manuaalisesti.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="3e5c6-135">Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="3e5c6-136">Valitse päivitettävän ennusteen vieressä olevat allekkaiset pisteet.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="3e5c6-137">Valitse **Päivitä**.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="3e5c6-138">Ennusteen poistaminen</span><span class="sxs-lookup"><span data-stu-id="3e5c6-138">Delete a prediction</span></span>

<span data-ttu-id="3e5c6-139">Ennusteen poistaminen poistaa myös sen tuloste-entiteetin.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="3e5c6-140">Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="3e5c6-141">Valitse poistettavan ennusteen vieressä olevat allekkaiset pisteet.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="3e5c6-142">Valitse **Poista**.</span><span class="sxs-lookup"><span data-stu-id="3e5c6-142">Select **Delete**.</span></span>
