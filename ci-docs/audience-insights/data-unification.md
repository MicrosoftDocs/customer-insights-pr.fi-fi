---
title: Tietojen yhdistäminen
description: Tietoja käytettyjen tietojen yhdistämisestä.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405587"
---
# <a name="data-unification"></a><span data-ttu-id="ad128-103">Tietojen yhdistäminen</span><span class="sxs-lookup"><span data-stu-id="ad128-103">Data unification</span></span>

<span data-ttu-id="ad128-104">Kun [tietolähteet on määritetty](data-sources.md), tiedot voidaan yhdistää.</span><span class="sxs-lookup"><span data-stu-id="ad128-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="ad128-105">Tietojen yhdistämisessä on kolme vaihetta: **vastaavuusmääritys**, **täsmäyttäminen** ja **yhdistäminen**.</span><span class="sxs-lookup"><span data-stu-id="ad128-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="ad128-106">Tietojen yhdistämisprosessin avulla voit yhdistää erilliset tietolähteet yhdeksi päätietojoukoksi, jolla saadaan yhdistetty näkymä asiakkaista.</span><span class="sxs-lookup"><span data-stu-id="ad128-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="ad128-107">Yhdistämisvaiheet ovat pakollisia, ja ne suoritetaan seuraavassa järjestyksessä:</span><span class="sxs-lookup"><span data-stu-id="ad128-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="ad128-108">Kartta</span><span class="sxs-lookup"><span data-stu-id="ad128-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="ad128-109">Täsmäyttäminen</span><span class="sxs-lookup"><span data-stu-id="ad128-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="ad128-110">Yhdistäminen</span><span class="sxs-lookup"><span data-stu-id="ad128-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="ad128-111">Tietojen yhdistämisen jälkeen voit valinnaisesti</span><span class="sxs-lookup"><span data-stu-id="ad128-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="ad128-112">[määrittää entiteettien väliset suhteet](relationships.md), joilla luodaan edistyneitä segmenttejä</span><span class="sxs-lookup"><span data-stu-id="ad128-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="ad128-113">[rikastaa tietoja](enrichment-hub.md), joiden avulla saat merkityksellisiä tietoja asiakkaista</span><span class="sxs-lookup"><span data-stu-id="ad128-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="ad128-114">[määrittää aktiviteetteja](activities.md) joistakin käytetyistä määritteistä.</span><span class="sxs-lookup"><span data-stu-id="ad128-114">[define activities](activities.md) from some of the ingested attributes</span></span>
