---
title: Tietojen yhtenäistäminen yhdistämällä entiteettejä
description: Yhtenäisten asiakasprofiilien luominen tietoja yhdistämällä.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267031"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="5a1a8-103">Entiteettien ja määritteiden yhdistäminen</span><span class="sxs-lookup"><span data-stu-id="5a1a8-103">Map entities and attributes</span></span>

<span data-ttu-id="5a1a8-104">**Yhdistäminen** on käyttäjäryhmän merkityksellisten tietojen tietojen yhtenäistämisen ensimmäisen vaihe.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="5a1a8-105">Yhdistäminen koostuu kolmesta vaiheesta:</span><span class="sxs-lookup"><span data-stu-id="5a1a8-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="5a1a8-106">*Entiteetin valinta*: Määritä yhdisteltävät entiteetit, jotka muodostavat aiempaa täydellisemmän tietojoukon asiakkaiden tiedoista.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="5a1a8-107">*Määritteen valinta*: Määritä jokaiselle entiteetille sarakkeet, jotka haluat yhdistää, ja täsmäytä *vastaavuus*- ja *yhdistämisvaiheet*.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="5a1a8-108">Näitä sarakkeita kutsutaan *määritteiksi*.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="5a1a8-109">*Perusavaimen ja semanttisen tyypin valinta*: Määritä kullekin entiteetille määrite, jonka haluat määrittää entiteetin perusavaimeksi, ja määritä kullekin määritteelle semanttinen tyyppi, joka parhaiten kuvaa kyseistä määritettä.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="5a1a8-110">Lisätietoja tietojen yhdistämisen yleisprosessista on kohdassa [Yhdistäminen](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="5a1a8-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="5a1a8-111">Valitse ensimmäiset entiteetit</span><span class="sxs-lookup"><span data-stu-id="5a1a8-111">Select the first entities</span></span>

1. <span data-ttu-id="5a1a8-112">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Yhtenäistä** > **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="5a1a8-113">Aloita yhdistämisvaihe valitsemalla **Valitse entiteettejä** -kohta.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="5a1a8-114">Valitse entiteetit ja määritteet, joita haluat käyttää vaiheissa *vastaavuuksien etsiminen* ja *yhdistäminen*.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="5a1a8-115">Voit valita tarvittavat määritteet yksitellen entiteetistä tai lisätä kaikki entiteetin määritteet valitsemalla **Sisällytä kaikki kentät** -valintaruutu entiteettitasolla.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="5a1a8-116">Kannattaa valita ainakin kaksi entiteettiä, jotta tietojen yhdistämisprosessista on hyötyä.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5a1a8-117">![Entiteettien lisääminen, esimerkki](media/data-manager-configure-map-add-entities-example.png "Entiteettien lisääminen, esimerkki")</span><span class="sxs-lookup"><span data-stu-id="5a1a8-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="5a1a8-118">Tässä esimerkissä lisätään entiteetit **eCommerceContacts** ja **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="5a1a8-119">Valitsemalla nämä entiteetit voit johtaa tietoja siitä, ketkä verkkoliiketoiminnan asiakkaista kuuluvat kanta-asiakasohjelman piiriin.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="5a1a8-120">Voit hakea avainsanoilla kaikista määritteistä ja entiteeteistä ja valita tarvittavat määritteet, jotka haluat yhdistää.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5a1a8-121">![Esimerkki hakukentästä](media/data-manager-configure-map-search-fields-example.png "Esimerkki hakukentästä")</span><span class="sxs-lookup"><span data-stu-id="5a1a8-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="5a1a8-122">Vahvista valintasi valitsemalla **Käytä**.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="5a1a8-123">Valitse määritteille perusavain ja semanttinen tyyppi</span><span class="sxs-lookup"><span data-stu-id="5a1a8-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="5a1a8-124">Kun olet valinnut entiteetit, valitut entiteetit tulevat tarkasteltavaksi **Yhdistä**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="5a1a8-125">Määritä entiteetin perusavain ja määritä entiteetin määritteelle semanttinen tyyppi.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="5a1a8-126">**Perusavain**: Valitse jokaiselle entiteetille yksi määrite perusavaimeksi.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="5a1a8-127">Jotta määrite olisi kelvollinen perusavain, se ei saa sisältää arvojen kaksoiskappaleita, siitä ei saa puuttua arvoja eikä siinä saa olla tyhjiä arvoja.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="5a1a8-128">Merkkijonon, kokonaisluvun ja GUID-tunnusten tietotyyppimääritteitä tuetaan perusavaimina, ja ne näytetään kentässä, josta voit valita ne.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="5a1a8-129">**Määritteen semanttinen tyyppi**: Määritteiden luokat, kuten sähköpostiosoite tai nimi.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="5a1a8-130">Määritä **Älykäs yhdistämismääritys** -asetukseksi **Käytössä**, jos haluat käyttää semantiikan älykkääseen ennakointiin, ajan säästämiseen ja tarkkuuden parantamiseen tekoälymalleja.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="5a1a8-131">Älykäs yhdistämismääritys korostaa tekoälyyn perustuvat semanttiset suositukset **Tyyppi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="5a1a8-132">Jos asetukseksi määritetään **Pois käytöstä**, tavalliset yhdistämismäärityssuositukset tulevat näkyviin.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="5a1a8-133">Voit valita minkä tahansa vaihtoehtoluettelossa olevan semanttisen tyypin ja ohittaa ehdotetun valinnan.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5a1a8-134">![Määritetyyppi ja semanttinen ennuste](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Määritetyyppi ja semanttinen ennuste")</span><span class="sxs-lookup"><span data-stu-id="5a1a8-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="5a1a8-135">Myös mukautetun semantiikkatyypin voi lisätä.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="5a1a8-136">Valitse määritteen tyypin kenttä ja kirjoita mukautetun semanttisen tyypin nimi.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="5a1a8-137">Tällä tavoin voit myös vaihtaa määritetyyppejä, jotka järjestelmä on tunnistanut.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="5a1a8-138">Kaikki määritteet, joiden semanttinen tyyppi tunnistetaan automaattisesti, kootaan **Tarkista yhdistetyt kentät** -osaan.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="5a1a8-139">Tarkista nämä määritteet ja niiden semanttiset tyypit, koska niitä käytetään entiteettien yhdistelemiseen tietojen yhtenäistämisen yhdistämisvaiheessa.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="5a1a8-140">Määritteet, joita ei yhdistetä automaattisesti semanttiseen tyyppiin, kootaan **Määritä yhdistämättömien kenttien tiedot** -osaan.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="5a1a8-141">Valitse yhdistämättömien määritteiden semanttisen tyypin kenttä tai syötä mukautetun määritetyyppisi nimi.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5a1a8-142">![Perusavain ja määritetyyppi](media/data-manager-configure-map-add-attributes.png "Perusavain ja määritetyyppi")</span><span class="sxs-lookup"><span data-stu-id="5a1a8-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="5a1a8-143">Yhden kentän pitäisi yhdistyä semanttiseen tyyppiin Person.FullName, jotta asiakkaan nimi täytetään asiakaskortissa.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="5a1a8-144">Muussa tapauksessa asiakaskortit näkyvät nimettöminä.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="5a1a8-145">Määritteiden ja entiteettien lisääminen ja poistaminen</span><span class="sxs-lookup"><span data-stu-id="5a1a8-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="5a1a8-146">Valitse kohdassa **Yhtenäistä** > **Yhdistä** valinta **Muokkaa kenttiä**.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="5a1a8-147">Lisää tai poista määritteitä ja entiteettejä **Muokkaa kenttiä** -ruudussa.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="5a1a8-148">Etsi ja valitse haluamasi määritteet ja entiteetit haun tai vierityksen avulla.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="5a1a8-149">Yhdistettyjä määritteitä tai entiteettejä ei voi poistaa.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5a1a8-150">![Määritteiden lisääminen tai poistaminen](media/configure-data-map-edit.png "Määritteiden lisääminen tai poistaminen")</span><span class="sxs-lookup"><span data-stu-id="5a1a8-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="5a1a8-151">Valitse **Käytä**.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="5a1a8-152">Kuvien lisääminen profiileihin</span><span class="sxs-lookup"><span data-stu-id="5a1a8-152">Add images to profiles</span></span>

<span data-ttu-id="5a1a8-153">Jos entiteetti sisältää URL-osoitteita julkisesti saatavilla oleviin profiilikuviin tai logoihin, voit lisätä ne yhdistettyyn asiakasprofiiliin.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="5a1a8-154">Valitse entiteetti ja etsi kenttä, joka sisältää URL-osoitteen profiilikuvaan.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="5a1a8-155">Kirjoita **Tyyppi**-kenttään manuaalisesti seuraava arvo:</span><span class="sxs-lookup"><span data-stu-id="5a1a8-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="5a1a8-156">Henkilölle: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="5a1a8-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="5a1a8-157">Organisaatiolle: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="5a1a8-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="5a1a8-158">Jatka yhtenäistämisvaiheita ja varmista, että myös kuvan URL-osoitteen sisältävä määrite lisätään [yhdistämisvaiheessa](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="5a1a8-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="5a1a8-159">Määritä organisaatioiden määritteet</span><span class="sxs-lookup"><span data-stu-id="5a1a8-159">Set attributes for organizations</span></span>

<span data-ttu-id="5a1a8-160">Organisaatioiden (esikatselu) määritetyypin vastaavuus on määritettävä Organization.Name-kohteeseen</span><span class="sxs-lookup"><span data-stu-id="5a1a8-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="5a1a8-161">![Perusavain ja määritetyyppi, yritysten välinen](media/configure-data-map-edit-b2b.png "Perusavain ja määritetyyppi, yritysten välinen")</span><span class="sxs-lookup"><span data-stu-id="5a1a8-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="5a1a8-162">Seuraava vaihe</span><span class="sxs-lookup"><span data-stu-id="5a1a8-162">Next step</span></span>

<span data-ttu-id="5a1a8-163">Tietojen yhdistämisprosessiin kuuluu myös **Täsmäyttäminen**-sivulle siirtyminen.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="5a1a8-164">Saat lisätietoja tästä vaiheesta [**Täsmäyttäminen**](match-entities.md)-sivulta.</span><span class="sxs-lookup"><span data-stu-id="5a1a8-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="5a1a8-165">Katso seuraava video: [Aloittaminen: Yhdistetyn asiakasprofiilin luominen](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="5a1a8-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]