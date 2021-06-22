---
title: Entiteettien entiteettipolkujen väliset suhteet
description: Useita lähteistä peräisin olevien entiteettien keskinäisten suhteiden luominen ja hallinta.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171160"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="3b2ef-103">Entiteettien väliset suhteet</span><span class="sxs-lookup"><span data-stu-id="3b2ef-103">Relationships between entities</span></span>

<span data-ttu-id="3b2ef-104">Suhteet yhdistää entiteetit ja määrittää kaavion tiedoista, kun entiteeteille on yhteinen tunnus, viiteavain.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="3b2ef-105">Tähän viiteavaimeen voidaan viitata entiteetistä toiseen.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="3b2ef-106">Yhdistetyt entiteetit mahdollistavat segmenttien ja mittojen määrittelyn useiden tietolähteiden perusteella.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="3b2ef-107">Suhteita on kolmea tyyppiä:</span><span class="sxs-lookup"><span data-stu-id="3b2ef-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="3b2ef-108">Ei-muokattavissa olevat järjestelmäsuhteet, jonka järjestelmä luo tietojenyhdistämisprosessin yhteydessä</span><span class="sxs-lookup"><span data-stu-id="3b2ef-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="3b2ef-109">Ei-muokattavissa olevat perityt suhteet, jotka luodaan automaattisesti tietolähteestä</span><span class="sxs-lookup"><span data-stu-id="3b2ef-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="3b2ef-110">Muokattavat mukautetut suhteet, jotka käyttäjät ovat luoneet ja määrittäneet</span><span class="sxs-lookup"><span data-stu-id="3b2ef-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="3b2ef-111">Ei-muokattavissa olevat järjestelmäsuhteet</span><span class="sxs-lookup"><span data-stu-id="3b2ef-111">Non-editable system relationships</span></span>

<span data-ttu-id="3b2ef-112">Tietojen yhdistämisen aikana järjestelmäsuhteet luodaan automaattisesti älykkään vastaavuuden perusteella.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="3b2ef-113">Nämä suhteet auttavat liittämään asiakasprofiilitietueet vastaaviin tietueisiin.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="3b2ef-114">Seuraavassa kaaviossa on kuvattu kolmen järjestelmäpohjaisen suhteen luonti.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="3b2ef-115">Asiakasentiteetti on yhdistetty muihin entiteetteihin, jotta saadaan aikaan yhtenäinen *Asiakas*-entiteetti.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Kaavio kolmen 1-n-suhteen sisältävän asiakasyksikön suhdepoluista.":::

- <span data-ttu-id="3b2ef-117">***CustomerToContact* -suhde** luotiin *asiakas*-entiteetin ja *yhteyshenkilö*-entiteetin välille.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="3b2ef-118">*Asiakas*-entiteetti saa avainkentän **Contact_contactId**, joka liitetään *yhteyshenkilö*-entiteetin avainkenttään **contactId**.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="3b2ef-119">\***CustomerToAccount\*-suhde** luotiin *asiakas*-entiteetin ja *tili*-entiteetin välille.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="3b2ef-120">*Asiakas*-entiteetti saa avainkentän **Account_accountId**, joka liitetään *tili*-entiteetin avainkenttään **accountId**.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="3b2ef-121">\***CustomerToWebAccount\*-suhde** luotiin *asiakas*-entiteetin ja *verkkotili*-entiteetin välille.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="3b2ef-122">*Asiakas*-entiteetti saa avainkentän **WebAccount_webaccountId**, joka liitetään *verkkotili*-entiteetin avainkenttään **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="3b2ef-123">Ei-muokattavissa olevat perityt suhteet</span><span class="sxs-lookup"><span data-stu-id="3b2ef-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="3b2ef-124">Tietojen käytön aikana järjestelmä tarkistaa, onko tietolähteitä olemassa oleville suhteille.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="3b2ef-125">Jos suhdetta ei ole, järjestelmä luo ne automaattisesti.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="3b2ef-126">Näitä suhteita käytetään myös jatkoprosesseissa.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="3b2ef-127">Luo muokattu suhde</span><span class="sxs-lookup"><span data-stu-id="3b2ef-127">Create a custom relationship</span></span>

<span data-ttu-id="3b2ef-128">Suhde koostuu *lähde-entiteetistä*, joka sisältää viiteavaimen ja *kohde-entiteetistä*, johon lähde-entiteetin viite-avain osoittaa.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="3b2ef-129">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Suhteet**.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="3b2ef-130">Valitse **Uusi suhde**.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="3b2ef-131">Kirjoita **Uusi suhde** -ruutuun seuraavat tiedot:</span><span class="sxs-lookup"><span data-stu-id="3b2ef-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Uusi suhdesivuruutu, jossa on tyhjät syöttökentät.":::

   - <span data-ttu-id="3b2ef-133">**Suhteen nimi**: Nimi, joka vastaa suhteen tarkoitusta.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="3b2ef-134">Esimerkki: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="3b2ef-135">**Kuvaus**: Suhteen kuvaus.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="3b2ef-136">**Lähde-entiteetti**: Entiteetti, jota käytetään suhteen lähteenä.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="3b2ef-137">Esimerkki: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="3b2ef-138">**Kohde-entiteetti**: Entiteetti, jota käytetään kohteen lähteenä.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="3b2ef-139">Esimerkki: Asiakas.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-139">Example: Customer.</span></span>
   - <span data-ttu-id="3b2ef-140">**Lähteen kardinaliteetti**: Määritä lähde-entiteetin kardinaliteetti.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="3b2ef-141">Kardinaliteetti kuvaa joukon mahdollisten elementtien määrää.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="3b2ef-142">Se liittyy aina kohdekardinaliteettiin.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="3b2ef-143">Voit valita **yhden** tai **usean** välillä.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="3b2ef-144">Vain monta yhteen- ja yksi yhteen -suhteita tuetaan.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="3b2ef-145">Monta yhteen: useat lähdetietueet voivat liittyä yhteen kohdetietueeseen.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="3b2ef-146">Esimerkki: yhden asiakkaan tukitapauksia on useita.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="3b2ef-147">Yksi yhteen: yksi lähdetietue liittyy yhteen kohdetietueeseen.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="3b2ef-148">Esimerkki: yksi uskollisuustunnus yhdelle asiakkaalle.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="3b2ef-149">Monta moneen -suhteet voidaan luoda käyttämällä kahta monta-yhteen-suhdetta ja linkitysentiteettiä, joka yhdistää lähde-entiteetin ja kohde-entiteetin.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="3b2ef-150">**Kohdekardinaliteetti**: Valitse kohde-entiteettitietueiden kardinaliteetti.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="3b2ef-151">**Lähdeavainkenttä**: lähde-entiteetin viiteavainkenttä.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="3b2ef-152">Esimerkki: SupportCase voi käyttää CaseID-tunnusta viiteavaimena.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="3b2ef-153">**Kohdeavainkenttä**: Kohde-entiteetin avainkenttä.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="3b2ef-154">Esimerkiksi Asiakas voi käyttää **CustomerID**-avainkenttä.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="3b2ef-155">Valitse **Tallenna** luodaksesi asiakassuhteen.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="3b2ef-156">Tarkastele suhteita</span><span class="sxs-lookup"><span data-stu-id="3b2ef-156">View relationships</span></span>

<span data-ttu-id="3b2ef-157">Tässä Suhteet-sivulla on kaikki luodut suhteet.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="3b2ef-158">Kullakin rivillä on suhde, joka sisältää myös tietoja lähde-entiteetistä, kohde-entiteetistä ja suhteesta.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Luettelo suhteista ja asetuksista suhteet-sivun toimintopalkissa.":::

<span data-ttu-id="3b2ef-160">Tämä sivu tarjoaa joukon vaihtoehtoja nykyisille ja uusille suhteille:</span><span class="sxs-lookup"><span data-stu-id="3b2ef-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="3b2ef-161">**Uusi suhde**: Valitse [Luo mukautettu suhde](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="3b2ef-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="3b2ef-162">**Visualisointi**: [Tutustu suhteeseen visualisointitehosteen](#explore-the-relationship-visualizer) avulla, niin näet verkkokaavion aiemmin luoduista suhteista ja niiden kardinaliteetista.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="3b2ef-163">**Suodatus**: Valitse suhdetyyppi, jonka haluat näyttää luettelossa.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="3b2ef-164">**Hae suhteet**: Käytä suhdeominaisuuksien tekstipohjaista hakua.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="3b2ef-165">Tutustu suhteeseen visualisointitehosteena</span><span class="sxs-lookup"><span data-stu-id="3b2ef-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="3b2ef-166">Suhteen visualisointi näyttää verkkokaavion yhdistettyjen entiteettien välisistä suhteista ja niiden kardinaliteetista.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="3b2ef-167">Jos haluat mukauttaa näkymää, voit muuttaa ruutujen sijaintia vetämällä ne kaavioon.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Näyttökuva suhdevisualisointiverkkokaaviosta, johon on liitetty toisiinsa liittyviä kokonaisuuksia.":::

<span data-ttu-id="3b2ef-169">Käytettävissä olevat asetukset:</span><span class="sxs-lookup"><span data-stu-id="3b2ef-169">Available options:</span></span> 
- <span data-ttu-id="3b2ef-170">**Vie kuvana**: Tallenna nykyinen näkymä kuvatiedostona.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="3b2ef-171">**Vaihda vaaka- tai pystysuuntaiseksi asetteluksi**: muuta entiteettien ja suhteiden asettelu.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="3b2ef-172">**Muokkaa**: Päivitä mukautettuja suhteita muokkausruudussa ja tallenna muutokset.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="3b2ef-173">Olemassa olevien suhteiden hallinta</span><span class="sxs-lookup"><span data-stu-id="3b2ef-173">Manage existing relationships</span></span> 

<span data-ttu-id="3b2ef-174">Suhteet-sivulla kutakin suhdetta edustaa rivi.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="3b2ef-175">Valitse suhde ja valitse jokin seuraavista vaihtoehdoista:</span><span class="sxs-lookup"><span data-stu-id="3b2ef-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="3b2ef-176">**Muokkaa**: Päivitä mukautettuja suhteita muokkausruudussa ja tallenna muutokset.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="3b2ef-177">**Poista**: Poista mukautetut suhteet.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="3b2ef-178">**Näkymä**: Näytä järjestelmän luomat ja perityt suhteet.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="3b2ef-179">Seuraava vaihe</span><span class="sxs-lookup"><span data-stu-id="3b2ef-179">Next step</span></span>

<span data-ttu-id="3b2ef-180">Järjestelmän suhteita ja mukautettuja suhteita käytetään [luotaessa segmenttejä](segments.md) sellaisten useiden tietolähteiden perusteella, jotka eivät ole enää siilossa.</span><span class="sxs-lookup"><span data-stu-id="3b2ef-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
