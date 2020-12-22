---
title: Power Query -pohjaisten tietolähteiden lisäävä päivitys
description: Power Queryyn perustuvien suurten tietolähteiden uusien ja päivitettyjen tietojen päivittäminen.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405614"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="64f01-103">Power Queryyn perustuvien tietolähteiden lisäävä päivitys</span><span class="sxs-lookup"><span data-stu-id="64f01-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="64f01-104">Tietolähteiden lisäävän päivityksen edut:</span><span class="sxs-lookup"><span data-stu-id="64f01-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="64f01-105">**Päivitysten nopeutuminen** – Vain muuttuneet tiedot päivitetään.</span><span class="sxs-lookup"><span data-stu-id="64f01-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="64f01-106">Esimerkiksi historiallisessa tietojoukossa päivitetään vain viisi viimeisintä päivää.</span><span class="sxs-lookup"><span data-stu-id="64f01-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="64f01-107">**Parantuntu luotettavuus** – koska päivitykset ovat pienempiä, yhteyksiä epävakaisiin lähdejärjestelmiin ei tarvitse ylläpitää yhtä pitkään, mikä vähentää yhteysongelmien riskiä.</span><span class="sxs-lookup"><span data-stu-id="64f01-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="64f01-108">**Resurssin kulutus vähenee** – vain kaikkien tietojen alijoukon päivittäminen tehostaa laskentaresurssien käyttöä ja vähentää ympäristön rasitusta.</span><span class="sxs-lookup"><span data-stu-id="64f01-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="64f01-109">Määritä lisäävä päivitys</span><span class="sxs-lookup"><span data-stu-id="64f01-109">Configure incremental refresh</span></span>

<span data-ttu-id="64f01-110">Käyttäjäryhmän merkityksellisissä tiedoissa on mahdollista tehdä sellaisten Power Queryn kautta tuotujen tietolähteiden lisäävä päivitys, jotka tukevat lisäävää käyttöä.</span><span class="sxs-lookup"><span data-stu-id="64f01-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="64f01-111">Esimerkiksi Azure SQL -tietokannat, joiden päivämäärä- ja aikakentät ilmaisevat, milloin tietotietueet päivitettiin viimeksi.</span><span class="sxs-lookup"><span data-stu-id="64f01-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="64f01-112">[Luo uusi Power Queryyn perustuva tietolähde](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="64f01-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="64f01-113">Anna tietolähteelle nimi.</span><span class="sxs-lookup"><span data-stu-id="64f01-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="64f01-114">Valitse lisäävää päivitystä tukeva tietolähde, kuten Azure SQL -tietokanta.</span><span class="sxs-lookup"><span data-stu-id="64f01-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="64f01-115">Valitse käsiteltävät entiteetit tai taulukot.</span><span class="sxs-lookup"><span data-stu-id="64f01-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="64f01-116">Tee muunnoksen vaiheet ja valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="64f01-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="64f01-117">Avaa **Lisäävän päivityksen asetukset** valitsemalla **Määritä lisäävä päivitys** -valintaikkunassa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="64f01-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="64f01-118">Jos valitset **Ohita**, tietolähde päivittää koko tietojoukon.</span><span class="sxs-lookup"><span data-stu-id="64f01-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="64f01-119">Voit käyttää lisäävää päivitystä myös myöhemmin muokkaamalla aiemmin luotua tietolähdettä.</span><span class="sxs-lookup"><span data-stu-id="64f01-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="64f01-120">**Lisäävän päivityksen asetukset** -kohdassa määritetään kaikkien tietolähdettä luotaessa valittujen entiteettien lisäävä päivitys.</span><span class="sxs-lookup"><span data-stu-id="64f01-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64f01-121">![Tietolähteen entiteettien määrittäminen lisäävää päivitystä varten](media/incremental-refresh-settings.png "Tietolähteen entiteettien määrittäminen lisäävää päivitystä varten")</span><span class="sxs-lookup"><span data-stu-id="64f01-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="64f01-122">Valitse entiteetti ja anna seuraavat tiedot:</span><span class="sxs-lookup"><span data-stu-id="64f01-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="64f01-123">**Valitse ensisijainen avain**: valitse entiteetin tai taulukon perusavain.</span><span class="sxs-lookup"><span data-stu-id="64f01-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="64f01-124">**Määritä viimeksi päivitetty -kenttä**: Tässä kentässä näytetään vain päivämäärä- ja aikatyypin määritteitä.</span><span class="sxs-lookup"><span data-stu-id="64f01-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="64f01-125">Valitse määrite, joka ilmaisee, milloin tietueet viimeksi päivitettiin.</span><span class="sxs-lookup"><span data-stu-id="64f01-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="64f01-126">Sen avulla määritetään tietueet, jotka sijoittuvat lisäävän päivityksen aikavälille.</span><span class="sxs-lookup"><span data-stu-id="64f01-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="64f01-127">**Etsi päivityksiä joka**: määritä, kuinka pitkä lisäävän päivityksen aikaväli on.</span><span class="sxs-lookup"><span data-stu-id="64f01-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="64f01-128">Viimeistele tietolähteen luonti valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="64f01-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="64f01-129">Ensimmäinen tietojen päivitys on täydellinen päivitys.</span><span class="sxs-lookup"><span data-stu-id="64f01-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="64f01-130">Sen jälkeen tietojen lisäävä päivitys tapahtuu edellisessä vaiheessa määritetyllä tavalla.</span><span class="sxs-lookup"><span data-stu-id="64f01-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>
