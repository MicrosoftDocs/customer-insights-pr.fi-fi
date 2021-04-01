---
title: Entiteettien entiteettipolkujen väliset suhteet
description: Useita lähteistä peräisin olevien entiteettien keskinäisten suhteiden luominen ja hallinta.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595208"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="ab5b5-103">Entiteettien väliset suhteet</span><span class="sxs-lookup"><span data-stu-id="ab5b5-103">Relationships between entities</span></span>

<span data-ttu-id="ab5b5-104">Suhteiden avulla voit yhdistää entiteettejä ja luoda kaavion tiedoista, kun entiteetit jakavat yhteisen tunnuksen (viiteavaimen), johon entiteetit voivat viitata.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="ab5b5-105">Yhdistettyjen entiteettien avulla voit määrittää segmentit ja mittarit useiden tietolähteiden avulla.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="ab5b5-106">Suhdetyyppejä on kaksi.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-106">There are two types of relationships.</span></span> <span data-ttu-id="ab5b5-107">Ei-muokattavat järjestelmän suhteet, jotka luodaan automaattisesti, ja käyttäjien luomat ja määrittämät mukautetut suhteet.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="ab5b5-108">Tärsmäytys- ja yhdistämisprosessien aikana taustalla luodaan järjestelmän suhteet älykkään täsmäytystoiminnon perusteella.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="ab5b5-109">Nämä suhteet auttavat liittämään asiakasprofiilitietueet muihin vastaaviin entiteettitietueisiin.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="ab5b5-110">Seuraavassa kaaviossa on kuva, jossa esitetään kolmen järjestelmän suhteen luominen, kun asiakasentiteetti täsmäytetään lisäentiteetteihin lopullisen asiakasprofiilientiteetin muodostamista varten.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ab5b5-111">![Suhteen luominen](media/relationships-entities-merge.png "Suhteen luominen")</span><span class="sxs-lookup"><span data-stu-id="ab5b5-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="ab5b5-112">\***CustomerToContact\*-suhde** luotiin asiakasentiteetin ja yhteyshenkilöentiteetin välille.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="ab5b5-113">Asiakasentiteetti saa avainkentän **Contact_contactId**, joka liitetään yhteyshenkilöentiteetin avainkenttään **contactId**.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="ab5b5-114">\***CustomerToAccount\*-suhde** luotiin asiakasentiteetin ja tilientiteetin välille.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="ab5b5-115">Asiakasentiteetti saa avainkentän **Account_accountId**, joka liitetään tilientiteetin avainkenttään **accountId**.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="ab5b5-116">\***CustomerToWebAccount\*-suhde** luotiin asiakasentiteetin ja verkkotilientiteetin välille.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="ab5b5-117">Asiakasentiteetti saa avainkentän **WebAccount_webaccountId**, joka liitetään verkkotilientiteetin avainkenttään **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="ab5b5-118">Suhteen luominen</span><span class="sxs-lookup"><span data-stu-id="ab5b5-118">Create a relationship</span></span>

<span data-ttu-id="ab5b5-119">Määritä mukautetut suhteet **Suhteet**-sivulla.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="ab5b5-120">Jokainen suhde sisältää lähde-entiteetin (entiteetti, jossa on viiteavain) ja kohde-entiteetin (entiteetti, johon lähde-entiteetin viiteavain osoittaa).</span><span class="sxs-lookup"><span data-stu-id="ab5b5-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="ab5b5-121">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Suhteet**.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="ab5b5-122">Valitse **Uusi suhde**.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="ab5b5-123">Anna **Lisää suhde** -ruutuun seuraavat tiedot:</span><span class="sxs-lookup"><span data-stu-id="ab5b5-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ab5b5-124">![Anna suhteen tiedot](media/relationships-add.png "Anna suhteen tiedot")</span><span class="sxs-lookup"><span data-stu-id="ab5b5-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="ab5b5-125">**Suhteen nimi**: Nimi, joka vastaa suhteen tarkoitusta (esimerkiksi **Tilin verkkolokit**).</span><span class="sxs-lookup"><span data-stu-id="ab5b5-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="ab5b5-126">**Kuvaus**: Suhteen kuvaus.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="ab5b5-127">**Lähde-entiteetti**: Valitse entiteetti, jota käytetään suhteen lähteenä (esimerkiksi verkkoloki).</span><span class="sxs-lookup"><span data-stu-id="ab5b5-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="ab5b5-128">**Kardinaliteetti**: Valitse lähde-entiteettitietueiden kardinaliteetti.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="ab5b5-129">Esimerkiksi "useita" tarkoittaa, että yhteen verkkotiliin liittyy useita verkkolokitietueita.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="ab5b5-130">**Lähteen avainkenttä**: Tämä kuvaa lähde-entiteetin viiteavainkenttää.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="ab5b5-131">Esimerkiksi verkkolokilla on **accountId**-viiteavainkenttä.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="ab5b5-132">**Kohde-entiteetti**: Valitse entiteetti, jota käytetään suhteen kohteena (esimerkiksi verkkotili).</span><span class="sxs-lookup"><span data-stu-id="ab5b5-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="ab5b5-133">**Kohdekardinaliteetti**: Valitse kohde-entiteettitietueiden kardinaliteetti.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="ab5b5-134">Esimerkiksi "yksi" tarkoittaa, että yhteen verkkotiliin liittyy useita verkkolokitietueita.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="ab5b5-135">**Kohdeavainkenttä**: Tämä kenttä edustaa kohde-entiteetin avainkenttää.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="ab5b5-136">Esimerkiksi verkkotilillä on **accountId**-avainkenttä.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="ab5b5-137">Vain monta yhteen- ja yksi yhteen -suhteita tuetaan.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="ab5b5-138">Monta moneen -suhteita voi luoda käyttämällä kahta monta yhteen -suhdetta ja linkittämällä entiteetin (joka on sama, jota käytettiin lähde- ja kohde-entiteetin yhdistämisessä).</span><span class="sxs-lookup"><span data-stu-id="ab5b5-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="ab5b5-139">Poista suhde</span><span class="sxs-lookup"><span data-stu-id="ab5b5-139">Delete a relationship</span></span>

1. <span data-ttu-id="ab5b5-140">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Suhteet**.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="ab5b5-141">Valitse sen suhteen valintaruudut, jonka haluat poistaa.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="ab5b5-142">Valitse **Poista** **Suhteet**-taulukon yläosassa.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="ab5b5-143">Vahvista poisto.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="ab5b5-144">Seuraava vaihe</span><span class="sxs-lookup"><span data-stu-id="ab5b5-144">Next step</span></span>

<span data-ttu-id="ab5b5-145">Järjestelmän suhteita ja mukautettuja suhteita käytetään luotaessa segmenttejä sellaisten useiden tietolähteiden perusteella, jotka eivät ole enää siilossa.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="ab5b5-146">Lisätietoja on kohdassa [Segmentit](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ab5b5-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]