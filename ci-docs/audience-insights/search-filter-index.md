---
title: Asiakasprofiilien hakeminen ja suodattaminen
description: Tietojen löytäminen nopeasti yhtenäisistä asiakasprofiileista ja määritettyjen määritteiden suodattaminen.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597139"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="8fe7f-103">Asiakasprofiilit: haku- ja suodatusindeksi</span><span class="sxs-lookup"><span data-stu-id="8fe7f-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="8fe7f-104">Asiakastietojen yhtenäistämisen tuloksena on asiakasprofiilientiteetti, joilla koko asiakaskannasta saadaan yhtenäinen näkymä.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="8fe7f-105">Voit [etsiä nopeasti tietoja tietystä asiakkaasta tai asiakasryhmästä](customer-profiles.md) määrittämällä **Haku**- ja **Suodatin**-ominaisuudet **Asiakkaat**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="8fe7f-106">Lue lisää siitä, miten järjestelmänvalvojat voivat muokata määritteitä **Hae ja suodata indeksi** -sivulla. Käyttäjät voivat käyttää niitä hakemiseen ja suodattamiseen.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8fe7f-107">![Hakusuodatin](media/search-filter.png "Hakusuodatin")</span><span class="sxs-lookup"><span data-stu-id="8fe7f-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="8fe7f-108">Kenttien lisääminen ja määritteiden määrittäminen</span><span class="sxs-lookup"><span data-stu-id="8fe7f-108">Add fields and specify attributes</span></span>

<span data-ttu-id="8fe7f-109">Jos määrität haettavia määritteitä ensimmäistä kertaa järjestelmänvalvojana, indeksoidut kentät on määritettävä ensin.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="8fe7f-110">Kaikki ne määritteet, joilla käyttäjät voivat hakea ja suodattaa asiakkaita **Asiakkaat**-sivulla, kannattaa valita.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="8fe7f-111">Voit määrittää vain niitä määritteitä, joita on tietojen yhtenäistämisprosessin aikana luodussa asiakasprofiilientiteetissä.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="8fe7f-112">Avaa **Asiakkaat**-sivu ja valitse **Hae ja suodata indeksi**.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="8fe7f-113">Valitse **+ Lisää**, jos haluat määrittää indeksoidut kentät.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="8fe7f-114">Valitse luettelosta indeksoituina kenttinä lisättävät määritteet.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="8fe7f-115">Voit aina lisätä uusia määritteitä valitsemalla **Lisää**.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="8fe7f-116">Voit myös poistaa valitsemasi määritteet valitsemalla **Poista**-symbolin.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="8fe7f-117">Indeksoidut asiakaskentät -taulukkoon tutustuminen</span><span class="sxs-lookup"><span data-stu-id="8fe7f-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="8fe7f-118">Taulukossa on seuraavat tiedot.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="8fe7f-119">**Nimi**: ilmaisee määritteen nimen siinä muodossa kuin se näkyy asiakasprofiilientiteetissä.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="8fe7f-120">**Tietotyyppi**: määrittää, onko tietotyyppi merkkijono, numero vai päivämäärä.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="8fe7f-121">**Sisältyy hakuun**: määrittää, voidaanko määritettä käyttää asiakkaiden hakemiseen **Asiakkaat**-sivun **Haku**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="8fe7f-122">**Lisää suodatin**: ohjausobjekti, jolla määritetään, miten määritettä käytetään suodattamiseen **Asiakkaat**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="8fe7f-123">Tietyn määritteen suodatusvaihtoehtojen muokkaaminen</span><span class="sxs-lookup"><span data-stu-id="8fe7f-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="8fe7f-124">**Asiakkaat**-sivun **Suodatin**-valikossa voi olla useita määritetasoja (kuten asiakkaiden suodattamiseen käytettäviä asiakasryhmiä).</span><span class="sxs-lookup"><span data-stu-id="8fe7f-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="8fe7f-125">Valitse tietyn määritteen **Lisää suodatin** **Hae ja suodata indeksi** -sivulla.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="8fe7f-126">Voit määrittää tulosten määrän ja tavan, jolla ne järjestetään.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="8fe7f-127">Määritteen tietotyypin mukaan jokin seuraavista ruuduista avautuu.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="8fe7f-128">Merkkijonotyyppiset määritteet: Määritä tulosten määrä **Merkkijonon suodatusasetukset**-ruudussa ja käytäntö, jonka mukaan ne järjestetään.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="8fe7f-129">Numerotyyppiset määritteet: Määritä **Numeron suodatusasetukset**-ruutuun sisältyvät välit ja käytäntö, jonka mukaan ne järjestetään.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="8fe7f-130">Päivämäärätyyppiset määritteet: Määritä **Päivämäärän suodatusasetukset**-ruutuun sisältyvät välit ja käytäntö, jonka mukaan ne järjestetään.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="8fe7f-131">Ota muutokset käyttöön valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="8fe7f-132">Valitse **Suorita**, kun olet valmis ottamaan asetukset käyttöön.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8fe7f-133">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="8fe7f-133">Next steps</span></span>

<span data-ttu-id="8fe7f-134">Siirry **Asiakkaat**-sivulle, jos haluat etsiä asiakasprofiileja tai käyttää indeksoituja kenttiä ja katsoa kaikkien asiakasprofiilien osajoukkoa.</span><span class="sxs-lookup"><span data-stu-id="8fe7f-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]