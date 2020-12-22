---
title: Microsoft Teams -botti
description: Yhtenäistettyjen asiakasprofiilien hakeminen Microsoft Teamsissa botin avulla.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405612"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="87fee-103">Dynamics 365 Customer Insightsin Teams-botti (esiversio)</span><span class="sxs-lookup"><span data-stu-id="87fee-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="87fee-104">Botti käyttää Microsoft Teams -yhteyttä yhtenäistettyjen asiakasprofiilien etsimiseen Teams-kanavissa.</span><span class="sxs-lookup"><span data-stu-id="87fee-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="87fee-105">![Teams-botti, jossa näkyy asiakastietue](media/teams-bot.png "Teams-botti, jossa näkyy asiakastietue")</span><span class="sxs-lookup"><span data-stu-id="87fee-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="87fee-106">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="87fee-106">Prerequisites</span></span>

<span data-ttu-id="87fee-107">Botin asennus ja määritys edellyttää seuraavaa:</span><span class="sxs-lookup"><span data-stu-id="87fee-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="87fee-108">Vähintään yksi [tietolähde on lisättynä](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="87fee-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="87fee-109">[Yhdistämisprosessi](data-unification.md) on valmis.</span><span class="sxs-lookup"><span data-stu-id="87fee-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="87fee-110">Kenttiä on lisätty [haku- ja suodatusindeksiin ](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="87fee-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="87fee-111">Customer Insights ja Teams ovat samassa organisaatiossa.</span><span class="sxs-lookup"><span data-stu-id="87fee-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="87fee-112">Botin määritys</span><span class="sxs-lookup"><span data-stu-id="87fee-112">Configure the bot</span></span>

1. <span data-ttu-id="87fee-113">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="87fee-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="87fee-114">Valitse Microsoft Teams -ruudussa **Asenna**.</span><span class="sxs-lookup"><span data-stu-id="87fee-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="87fee-115">Sinut ohjataan Teamsin **Sovellukset**-alueelle.</span><span class="sxs-lookup"><span data-stu-id="87fee-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="87fee-116">Voit myös avata Teamsin ja valita **Sovellukset** vasemmasta alakulmasta tai [hankkia sen AppSourcesta](https://go.microsoft.com/fwlink/?linkid=2124104) suoraan.</span><span class="sxs-lookup"><span data-stu-id="87fee-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="87fee-117">Hae **Customer Insights** ja valitse sovellus.</span><span class="sxs-lookup"><span data-stu-id="87fee-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="87fee-118">Valitse **Lisää**.</span><span class="sxs-lookup"><span data-stu-id="87fee-118">Select **Add**.</span></span>
1. <span data-ttu-id="87fee-119">Kun olet kirjautunut Customer Insightsiin Teamsissä, näet tervetuloviestin ja voit aloittaa.</span><span class="sxs-lookup"><span data-stu-id="87fee-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="87fee-120">Asioita, joihin voit käyttää bottia</span><span class="sxs-lookup"><span data-stu-id="87fee-120">Things you can do with the bot</span></span>

<span data-ttu-id="87fee-121">Botti tarjoaa yhdistettyjen asiakasprofiilien hakumahdollisuuksia.</span><span class="sxs-lookup"><span data-stu-id="87fee-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="87fee-122">Syötä **haku** ja sen jälkeen nimi, sähköpostiosoite tai mikä muu yhdistetyn asiakasprofiilin kenttä, joka lisätään haku- ja suodatusindeksiin.</span><span class="sxs-lookup"><span data-stu-id="87fee-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="87fee-123">Saat kortin, joka sisältää jopa 15 kenttää tuloksena olevasta asiakasprofiilista.</span><span class="sxs-lookup"><span data-stu-id="87fee-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="87fee-124">Useat vastaavuudet palauttavat tulosluettelon, josta voit valita profiilin.</span><span class="sxs-lookup"><span data-stu-id="87fee-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="87fee-125">Lisäämällä hakutermiin lainausmerkit voit hakea tarkkaa vastaavuutta.</span><span class="sxs-lookup"><span data-stu-id="87fee-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="87fee-126">Jos organisaatiolla on samassa organisaatiossa useita Customer Insights -ympäristöjä, antamalla **switchinstance** voit valita, mihin ympäristöön botti yhdistetään.</span><span class="sxs-lookup"><span data-stu-id="87fee-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="87fee-127">Kirjoita **ohje**, kun haluat nähdä luettelon käytettävissä olevista bottikomennoista.</span><span class="sxs-lookup"><span data-stu-id="87fee-127">Enter **help** to see a list of available commands for the bot.</span></span>  
