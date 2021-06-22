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
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095704"
---
# <a name="manage-predictions"></a><span data-ttu-id="511f7-103">Hallitse ennusteita</span><span class="sxs-lookup"><span data-stu-id="511f7-103">Manage predictions</span></span>

<span data-ttu-id="511f7-104">Tässä artikkelissa käsitellään joitakin tehtäviä, jotka useimmat ennusteskenaariot jakavat.</span><span class="sxs-lookup"><span data-stu-id="511f7-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="511f7-105">Epäonnistuneen ennusteen vianmääritys</span><span class="sxs-lookup"><span data-stu-id="511f7-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="511f7-106">Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.</span><span class="sxs-lookup"><span data-stu-id="511f7-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="511f7-107">Valitse kolme allekkain olevaa pistettä sen ennusteen vieressä, jonka virhelokeja haluat tarkastella.</span><span class="sxs-lookup"><span data-stu-id="511f7-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="511f7-108">Valitse **Lokit**.</span><span class="sxs-lookup"><span data-stu-id="511f7-108">Select **Logs**.</span></span>

1. <span data-ttu-id="511f7-109">Tarkastele kaikkia virheitä.</span><span class="sxs-lookup"><span data-stu-id="511f7-109">Review all the errors.</span></span> <span data-ttu-id="511f7-110">Mahdollisia virhe tyyppejä on useita. Ne osoittavat, mikä ehto aiheutti virheen.</span><span class="sxs-lookup"><span data-stu-id="511f7-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="511f7-111">Esimerkiksi virhe, joka osoittaa olemassa olevien tietojen olevan riittämättömät tarkan ennusteen luomiseksi, ratkaistaan yleensä lataamalla lisää tietoja Customer Insightsiin.</span><span class="sxs-lookup"><span data-stu-id="511f7-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="511f7-112">Syötetietojen käytettävyysraportti</span><span class="sxs-lookup"><span data-stu-id="511f7-112">Input data usability report</span></span>

<span data-ttu-id="511f7-113">Syöttötietojen käytettävyysraportti tarjoaa konsolidoidun kuvan virheistä ja varoituksista, joita valmiit ennusteet saattavat tuottaa.</span><span class="sxs-lookup"><span data-stu-id="511f7-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="511f7-114">Se antaa myös suosituksia mallin suorituskyvyn parantamista varten.</span><span class="sxs-lookup"><span data-stu-id="511f7-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="511f7-115">Raportti on käytettävissä sen jälkeen, kun malli on suorittanut sen koulutusprosessin.</span><span class="sxs-lookup"><span data-stu-id="511f7-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="511f7-116">Se luodaan kullekin mallille erikseen riippumatta siitä, onnistuiko malli.</span><span class="sxs-lookup"><span data-stu-id="511f7-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="511f7-117">Tällä hetkellä tämä ominaisuus toimii vain tapahtumavaihtuvuusmallissa.</span><span class="sxs-lookup"><span data-stu-id="511f7-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="511f7-118">Näytä syötetietojen käytettävyysraportti</span><span class="sxs-lookup"><span data-stu-id="511f7-118">View the input data usability report</span></span>

<span data-ttu-id="511f7-119">Kun valmiin mallin koulutusvaihe on valmis, tarkastele raporttia:</span><span class="sxs-lookup"><span data-stu-id="511f7-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="511f7-120">Valitse mallin nimen vierestä kolme pistettä ja valitse sitten **Syötetietojen käytettävyysraportti**.</span><span class="sxs-lookup"><span data-stu-id="511f7-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="511f7-121">Valitse mallin tila valitsemalla sivuruudusta **Näytä tietojen käytettävyysraportti**.</span><span class="sxs-lookup"><span data-stu-id="511f7-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="511f7-122">Valitse luettelosta jokin malleista ja valitse komentopalkissa **Tietojen käytettävyysraportti**.</span><span class="sxs-lookup"><span data-stu-id="511f7-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="511f7-123">Avaa mallien tulossivu ja valitse komentopalkissa **Tietojen käytettävyysraportti**.</span><span class="sxs-lookup"><span data-stu-id="511f7-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="511f7-124">Tiedot syötetietojen käytettävyysraportissa</span><span class="sxs-lookup"><span data-stu-id="511f7-124">Information in the input data usability report</span></span>

<span data-ttu-id="511f7-125">Seuraavissa raportin sarakkeissa on hyödyllisiä tietoja mallin tietojen parantamiseksi.</span><span class="sxs-lookup"><span data-stu-id="511f7-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Esimerkki syöttötietojen käytettävyysraportista, jossa näkyy taulukko, jossa on virheitä, varoituksia ja suosituksia.":::

- <span data-ttu-id="511f7-127">Nimi: virheen, varoituksen tai suosituksen kuvaileva nimi.</span><span class="sxs-lookup"><span data-stu-id="511f7-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="511f7-128">Vaihe: mallivaihe, kouluttaa tai pisteyttää, tietoihin viitataan.</span><span class="sxs-lookup"><span data-stu-id="511f7-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="511f7-129">Tila: tietojen vakavuus (virhe, varoitus, suositus).</span><span class="sxs-lookup"><span data-stu-id="511f7-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="511f7-130">Sarakkeen nimi: Entiteetin sarake, jota on muutettava mallin suorituskyvyn parantamiseksi.</span><span class="sxs-lookup"><span data-stu-id="511f7-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="511f7-131">Entiteetin nimi: Entiteetin nimi, jota on muutettava mallin suorituskyvyn parantamiseksi.</span><span class="sxs-lookup"><span data-stu-id="511f7-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="511f7-132">Tiedot: Tietoja virheestä, varoituksesta tai suosituksista.</span><span class="sxs-lookup"><span data-stu-id="511f7-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="511f7-133">Ennusteen päivittäminen</span><span class="sxs-lookup"><span data-stu-id="511f7-133">Refresh a prediction</span></span>

<span data-ttu-id="511f7-134">Ennusteet päivittyvät automaattisesti saman [aikataulun mukaan kuin tiedot päivitetään](system.md#schedule-tab) asetuksissa määritetyllä tavalla.</span><span class="sxs-lookup"><span data-stu-id="511f7-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="511f7-135">Voit päivittää ne myös manuaalisesti.</span><span class="sxs-lookup"><span data-stu-id="511f7-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="511f7-136">Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.</span><span class="sxs-lookup"><span data-stu-id="511f7-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="511f7-137">Valitse päivitettävän ennusteen vieressä olevat allekkaiset pisteet.</span><span class="sxs-lookup"><span data-stu-id="511f7-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="511f7-138">Valitse **Päivitä**.</span><span class="sxs-lookup"><span data-stu-id="511f7-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="511f7-139">Ennusteen poistaminen</span><span class="sxs-lookup"><span data-stu-id="511f7-139">Delete a prediction</span></span>

<span data-ttu-id="511f7-140">Ennusteen poistaminen poistaa myös sen tuloste-entiteetin.</span><span class="sxs-lookup"><span data-stu-id="511f7-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="511f7-141">Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.</span><span class="sxs-lookup"><span data-stu-id="511f7-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="511f7-142">Valitse poistettavan ennusteen vieressä olevat allekkaiset pisteet.</span><span class="sxs-lookup"><span data-stu-id="511f7-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="511f7-143">Valitse **Poista**.</span><span class="sxs-lookup"><span data-stu-id="511f7-143">Select **Delete**.</span></span>
