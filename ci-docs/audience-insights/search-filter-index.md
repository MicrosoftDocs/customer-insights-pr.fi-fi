---
title: Asiakasprofiilien hakeminen ja suodattaminen
description: Tietojen löytäminen nopeasti yhtenäisistä asiakasprofiileista ja määritettyjen määritteiden suodattaminen.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405626"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="bc1f6-103">Asiakasprofiilit: haku- ja suodatusindeksi</span><span class="sxs-lookup"><span data-stu-id="bc1f6-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="bc1f6-104">Asiakastietojen yhtenäistämisen tuloksena on asiakasprofiilientiteetti, joilla koko asiakaskannasta saadaan yhtenäinen näkymä.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="bc1f6-105">Voit [etsiä nopeasti tietoja tietystä asiakkaasta tai asiakasryhmästä](customer-profiles.md) määrittämällä **Haku**- ja **Suodatin**-ominaisuudet **Asiakkaat**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="bc1f6-106">Lue lisää siitä, miten järjestelmänvalvojat voivat muokata määritteitä **Hae ja suodata indeksi** -sivulla. Käyttäjät voivat käyttää niitä hakemiseen ja suodattamiseen.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bc1f6-107">![Hakusuodatin](media/search-filter.png "Hakusuodatin")</span><span class="sxs-lookup"><span data-stu-id="bc1f6-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="bc1f6-108">Kenttien lisääminen ja määritteiden määrittäminen</span><span class="sxs-lookup"><span data-stu-id="bc1f6-108">Add fields and specify attributes</span></span>

<span data-ttu-id="bc1f6-109">Jos määrität haettavia määritteitä ensimmäistä kertaa järjestelmänvalvojana, indeksoidut kentät on määritettävä ensin.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="bc1f6-110">Kaikki ne määritteet, joilla käyttäjät voivat hakea ja suodattaa asiakkaita **Asiakkaat**-sivulla, kannattaa valita.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="bc1f6-111">Voit määrittää vain niitä määritteitä, joita on tietojen yhtenäistämisprosessin aikana luodussa asiakasprofiilientiteetissä.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="bc1f6-112">Avaa **Asiakkaat**-sivu ja valitse **Hae ja suodata indeksi**.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="bc1f6-113">Luodaan oletushakuindeksin määritys käytettävistä määritteistä asiakasentiteetissä Yhdistämismääritys-sivulla määritettyjen seuraavien semanttisten tyyppien avulla.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="bc1f6-114">Henkilö etunimi, sukunimi, toinen nimi, koko nimi</span><span class="sxs-lookup"><span data-stu-id="bc1f6-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="bc1f6-115">Organisaation nimi</span><span class="sxs-lookup"><span data-stu-id="bc1f6-115">Organization Name</span></span>
> - <span data-ttu-id="bc1f6-116">Sähköpostiosoite</span><span class="sxs-lookup"><span data-stu-id="bc1f6-116">Email address</span></span>
> - <span data-ttu-id="bc1f6-117">Puhelin</span><span class="sxs-lookup"><span data-stu-id="bc1f6-117">Phone number</span></span>
> - <span data-ttu-id="bc1f6-118">Sijainnin tiedot</span><span class="sxs-lookup"><span data-stu-id="bc1f6-118">Location information</span></span>

2. <span data-ttu-id="bc1f6-119">Valitse **+ Lisää**, jos haluat määrittää indeksoidut kentät.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="bc1f6-120">Valitse luettelosta indeksoituina kenttinä lisättävät määritteet.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="bc1f6-121">Voit aina lisätä uusia määritteitä valitsemalla **Lisää**.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="bc1f6-122">Voit myös poistaa valitsemasi määritteet valitsemalla **Poista**-symbolin.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="bc1f6-123">Indeksoidut asiakaskentät -taulukkoon tutustuminen</span><span class="sxs-lookup"><span data-stu-id="bc1f6-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="bc1f6-124">Taulukossa on seuraavat tiedot.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="bc1f6-125">**Nimi**: ilmaisee määritteen nimen siinä muodossa kuin se näkyy asiakasprofiilientiteetissä.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="bc1f6-126">**Tietotyyppi**: määrittää, onko tietotyyppi merkkijono, numero vai päivämäärä.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="bc1f6-127">**Sisältyy hakuun**: määrittää, voidaanko määritettä käyttää asiakkaiden hakemiseen **Asiakkaat**-sivun **Haku**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="bc1f6-128">**Lisää suodatin**: ohjausobjekti, jolla määritetään, miten määritettä käytetään suodattamiseen **Asiakkaat**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="bc1f6-129">Tietyn määritteen suodatusvaihtoehtojen muokkaaminen</span><span class="sxs-lookup"><span data-stu-id="bc1f6-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="bc1f6-130">**Asiakkaat**-sivun **Suodatin**-valikossa voi olla useita määritetasoja (kuten asiakkaiden suodattamiseen käytettäviä asiakasryhmiä).</span><span class="sxs-lookup"><span data-stu-id="bc1f6-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="bc1f6-131">Valitse tietyn määritteen **Lisää suodatin** **Hae ja suodata indeksi** -sivulla.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="bc1f6-132">Voit määrittää tulosten määrän ja tavan, jolla ne järjestetään.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="bc1f6-133">Määritteen tietotyypin mukaan jokin seuraavista ruuduista avautuu.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="bc1f6-134">Merkkijonotyyppiset määritteet: Määritä tulosten määrä **Merkkijonon suodatusasetukset**-ruudussa ja käytäntö, jonka mukaan ne järjestetään.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="bc1f6-135">Numerotyyppiset määritteet: Määritä **Numeron suodatusasetukset**-ruutuun sisältyvät välit ja käytäntö, jonka mukaan ne järjestetään.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="bc1f6-136">Päivämäärätyyppiset määritteet: Määritä **Päivämäärän suodatusasetukset**-ruutuun sisältyvät välit ja käytäntö, jonka mukaan ne järjestetään.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="bc1f6-137">Ota muutokset käyttöön valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="bc1f6-138">Valitse **Suorita**, kun olet valmis ottamaan asetukset käyttöön.</span><span class="sxs-lookup"><span data-stu-id="bc1f6-138">Select **Run** once you're ready to apply your settings.</span></span>
