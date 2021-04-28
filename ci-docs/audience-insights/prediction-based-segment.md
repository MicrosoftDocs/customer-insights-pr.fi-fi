---
title: Ennusteen tulokseen perustuvat segmentit
description: Luo segmentit ennustemallin tulosentiteetin perusteella.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741425"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="00dfc-103">Luo segmentti ennustemallin perusteella (esiversio)</span><span class="sxs-lookup"><span data-stu-id="00dfc-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="00dfc-104">Ennusteiden tulokset koskevat joskus vain asiakkaiden alijoukkoa.</span><span class="sxs-lookup"><span data-stu-id="00dfc-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="00dfc-105">Lisää suositusten mukauttamista luomalla segmenttejä ennustemallin tuloksista.</span><span class="sxs-lookup"><span data-stu-id="00dfc-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="00dfc-106">Voit esimerkiksi antaa tiettyjä suosituksia asiakkaille, jotka haluavat tietyntyyppistä palvelua.</span><span class="sxs-lookup"><span data-stu-id="00dfc-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="00dfc-107">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="00dfc-107">Prerequisites</span></span>

- <span data-ttu-id="00dfc-108">Vähintään [osallistujan oikeudet](permissions.md) Customer Insightsissa.</span><span class="sxs-lookup"><span data-stu-id="00dfc-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="00dfc-109">Customer Insightsissa määritetty tuotesuositus, tapahtumaperusteisen asiakaspoistuman, tilausten asiakaspoistuman tai asiakkaan elinkaaren arvon malli.</span><span class="sxs-lookup"><span data-stu-id="00dfc-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="00dfc-110">Tarkista eri mallien määrityksen edellytykset:</span><span class="sxs-lookup"><span data-stu-id="00dfc-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="00dfc-111">Tuotesuositusmalli</span><span class="sxs-lookup"><span data-stu-id="00dfc-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="00dfc-112">Tilausten vaihtuvuus -malli</span><span class="sxs-lookup"><span data-stu-id="00dfc-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="00dfc-113">Tapahtumaperusteinen vaihtuvuus -malli</span><span class="sxs-lookup"><span data-stu-id="00dfc-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="00dfc-114">Asiakkaan elinkaaren arvo -malli</span><span class="sxs-lookup"><span data-stu-id="00dfc-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="00dfc-115">Ennusteisiin perustuvan asiakassegmentin luominen</span><span class="sxs-lookup"><span data-stu-id="00dfc-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="00dfc-116">Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.</span><span class="sxs-lookup"><span data-stu-id="00dfc-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="00dfc-117">Valitse tarkasteltavan mallin vieressä pystysuuntaiset kolme pistettä ja valitse sitten **Näytä**.</span><span class="sxs-lookup"><span data-stu-id="00dfc-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="00dfc-118">Valitse tulossivulla **Luo segmentti**.</span><span class="sxs-lookup"><span data-stu-id="00dfc-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="00dfc-119">Lisätietoja tulossivusta on malliin liittyvässä artikkelissa.</span><span class="sxs-lookup"><span data-stu-id="00dfc-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Näyttökuva ennusteen tulossivusta korostaen Luo segmentti -toimintoa.":::

1. <span data-ttu-id="00dfc-121">Luo uusi segmentti valitun mallin tulosentiteetin perusteella.</span><span class="sxs-lookup"><span data-stu-id="00dfc-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="00dfc-122">Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).</span><span class="sxs-lookup"><span data-stu-id="00dfc-122">For more information, see [Create and manage segments](segments.md).</span></span>