---
title: Yleiskatsaus tuetuista ennusteskenaarioista
description: Dynamics 365 Customer Insights -sovelluksen kattamia ennusteskenaarioita ja vaihtoehtoja.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095703"
---
# <a name="predictions-overview"></a><span data-ttu-id="57b41-103">Ennusteiden yleiskatsaus</span><span class="sxs-lookup"><span data-stu-id="57b41-103">Predictions overview</span></span>

<span data-ttu-id="57b41-104">Dynamics 365 Customer Insightsissa on erilaisia vaihtoehtoja, joilla voit hyödyntää tekoälyä ja koneoppimista tietojen ennustamiseen.</span><span class="sxs-lookup"><span data-stu-id="57b41-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="57b41-105">Valmiit mallit</span><span class="sxs-lookup"><span data-stu-id="57b41-105">Out-of-box models</span></span>

<span data-ttu-id="57b41-106">Helpoin tapa aloittaa tietojen ennustaminen on esimääritetyt mallit, joita kutsutaan usein valmiiksi malleiksi.</span><span class="sxs-lookup"><span data-stu-id="57b41-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="57b41-107">Ne edellyttävät vain tiettyjä tietoja ja rakennetta, jotta saat nopeasti tietoja.</span><span class="sxs-lookup"><span data-stu-id="57b41-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="57b41-108">Tällä hetkellä käytettävissä ovat seuraavat mallit:</span><span class="sxs-lookup"><span data-stu-id="57b41-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="57b41-109">[Asiakkaan elinkaariarvo](predict-customer-lifetime-value.md): Ennustaa asiakkaan potentiaalisen tuoton koko ajan, jonka se on vuorovaikutuksessa yrityksen kanssa.</span><span class="sxs-lookup"><span data-stu-id="57b41-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="57b41-110">[Tuotesuositus](predict-product-recommendation.md): ehdottaa ostokäyttäytymiseen perustuvia ennakoivia tuotesuosituksia ja asiakkaita, joilla on samanlaiset ostomallit.</span><span class="sxs-lookup"><span data-stu-id="57b41-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="57b41-111">[Tilausvaihtuvuus](predict-subscription-churn.md): Ennustaa, onko asiakkaalla riski lakata käyttämästä yrityksesi tilaustuotteita tai palveluja.</span><span class="sxs-lookup"><span data-stu-id="57b41-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="57b41-112">[Liiketapahtumien vaihtuminen](predict-transactional-churn.md): Ennustaa, jos asiakas ei enää osta tuotteitasi tai palveluitasi tietyllä aikavälillä.</span><span class="sxs-lookup"><span data-stu-id="57b41-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="57b41-113">Azuren automaattianalyysipalvelujen integraatio</span><span class="sxs-lookup"><span data-stu-id="57b41-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="57b41-114">Jos organisaatio käyttää jo koneoppimisen skenaarioita, jotka perustuvat Azure-koneoppimisen kokeiluihin, Customer Insightsin mukautetut mallit -ominaisuus auttaa yhdistämään pisteet.</span><span class="sxs-lookup"><span data-stu-id="57b41-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="57b41-115">Luo työnkulkuja, jotka auttavat valitsemaan tiedot, joista haluat saada tietoja, ja yhdistä tulokset yhtenäisiksi asiakasprofiileiksi.</span><span class="sxs-lookup"><span data-stu-id="57b41-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="57b41-116">Lisätietoja on aiheessa [Mukautetut koneoppimismallit](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="57b41-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="57b41-117">AI Builderin ennuste</span><span class="sxs-lookup"><span data-stu-id="57b41-117">AI Builder prediction</span></span>

<span data-ttu-id="57b41-118">Joskus tietojoukot ovat puutteellisia ja joitakin arvoja puuttuu.</span><span class="sxs-lookup"><span data-stu-id="57b41-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="57b41-119">Customer Insights voi auttaa ennustamaan puuttuvat arvot Asiakas-entiteetistä ja segmentistä.</span><span class="sxs-lookup"><span data-stu-id="57b41-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="57b41-120">Lisätietoja on ohjeaiheessa [Osittaisten tietojen täydentäminen ennusteilla](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="57b41-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
