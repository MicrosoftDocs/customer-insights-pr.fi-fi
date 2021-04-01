---
title: Common Data Servicen hallittujen Data Lake -tallennustilan entiteetteihin yhdistäminen
description: Tietojen tuominen Common Data Servicen hallitusta Data Lake -tallennustilasta.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596955"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="a0a56-103">Yhteyden muodostaminen hallinnoidun Common Data Service Data Lake -tallennustilan tietoihin</span><span class="sxs-lookup"><span data-stu-id="a0a56-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a0a56-104">Tässä artikkelissa on tietoja siitä, miten nykyiset Dynamics 365 -asiakkaat voivat yhdistää nopeasti analytiikkaentiteetit Common Data Servicen hallitussa Data Lake -tallennustilassa.</span><span class="sxs-lookup"><span data-stu-id="a0a56-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="a0a56-105">Vain Common Data Service -organisaation järjestelmänvalvojat voivat jatkaa tarkastelemaan hallitussa Data Lake -tallennustilassa käytettävissä olevia entiteettejä.</span><span class="sxs-lookup"><span data-stu-id="a0a56-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="a0a56-106">Tärkeitä huomioon otettavia seikkoja</span><span class="sxs-lookup"><span data-stu-id="a0a56-106">Important considerations</span></span>

<span data-ttu-id="a0a56-107">Verkkopalveluihin, kuten Azure Data Lake Storageen, tallennetut tiedot voivat tallennettuina eri sijainnissa kuin missä tietoja käsitellään tai tallennetaan Dynamics 365 Customer Insightsissa.</span><span class="sxs-lookup"><span data-stu-id="a0a56-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="a0a56-108"> Tuomalla verkkopalveluun tallennetut tiedot tai muodostamalla niihin yhteyden hyväksyt, että tiedot voidaan siirtää ja tallentaa yhdessä Dynamics 365 Customer Insightsin kanssa.  [Lisätietoja on Microsoftin luottamuskeskuksessa.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="a0a56-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="a0a56-109">Yhteyden muodostaminen Common Data Servicen hallittuun tallennustilaan</span><span class="sxs-lookup"><span data-stu-id="a0a56-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="a0a56-110">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.</span><span class="sxs-lookup"><span data-stu-id="a0a56-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="a0a56-111">Valitse **Lisää tietolähde**.</span><span class="sxs-lookup"><span data-stu-id="a0a56-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="a0a56-112">Valitse **Yhdistä Common Data Serviceeen** ja sitten **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="a0a56-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="a0a56-113">Anna tietolähteen **nimi** ja valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="a0a56-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="a0a56-114">Nimen ohjeet:</span><span class="sxs-lookup"><span data-stu-id="a0a56-114">Name guidelines:</span></span> 
   - <span data-ttu-id="a0a56-115">Alussa on oltava kirjain.</span><span class="sxs-lookup"><span data-stu-id="a0a56-115">Start with a letter.</span></span>
   - <span data-ttu-id="a0a56-116">Käytä vain kirjaimia ja numeroita.</span><span class="sxs-lookup"><span data-stu-id="a0a56-116">Use letters and numbers only.</span></span> <span data-ttu-id="a0a56-117">Erikoismerkit ja välilyönnit eivät ole sallittuja.</span><span class="sxs-lookup"><span data-stu-id="a0a56-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="a0a56-118">Käytä 3–64 merkkiä.</span><span class="sxs-lookup"><span data-stu-id="a0a56-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="a0a56-119">Anna Common Data Service -organisaatiosi **Palvelinosoite** ja valitse **Kirjaudu sisään**.</span><span class="sxs-lookup"><span data-stu-id="a0a56-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a0a56-120">![Valintaruutu Common Data Servicen palvelinosoitteen syöttämiselle](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="a0a56-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="a0a56-121">Valitse luettelosta käytettävä entiteetti.</span><span class="sxs-lookup"><span data-stu-id="a0a56-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="a0a56-122">Jos joitakin entiteettejä on jo valittuna, muut Dynamics 365- sovellukset (kuten Dynamics 365 Sales Insights tai Customer Service Insights) saattavat käyttää niitä.</span><span class="sxs-lookup"><span data-stu-id="a0a56-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="a0a56-123">Tätä valintaa ei voi muuttaa.</span><span class="sxs-lookup"><span data-stu-id="a0a56-123">You can't change the selection.</span></span> <span data-ttu-id="a0a56-124">Nämä kohteet ovat käytettävissä, kun tietolähde on luotu.</span><span class="sxs-lookup"><span data-stu-id="a0a56-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a0a56-125">![Valintaikkuna, jossa näkyy Common Data Service -organisaation entiteettiluettelo](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="a0a56-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="a0a56-126">Tallenna valintasi, jos haluat aloittaa valittujen entiteettien synkronoinnin Common Data Servicen hallittuun tallennustilaan.</span><span class="sxs-lookup"><span data-stu-id="a0a56-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="a0a56-127">Löydät juuri lisätyn yhteyden **Tietolähteet**-sivulta.</span><span class="sxs-lookup"><span data-stu-id="a0a56-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="a0a56-128">Se asetetaan päivitysjonoon, ja entiteettimääränä näkyy 0, kunnes kaikki entiteetit on synkronoitu.</span><span class="sxs-lookup"><span data-stu-id="a0a56-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="a0a56-129">Vain yksi ympäristön tietolähde voi käyttää samanaikaisesti samaa Common Data Servicen hallittua Data Lake -tallennustilaa.</span><span class="sxs-lookup"><span data-stu-id="a0a56-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="a0a56-130">Common Data Servicen hallitun tallennustilan tietolähteen muokkaaminen</span><span class="sxs-lookup"><span data-stu-id="a0a56-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="a0a56-131">Entiteetin valintaa voi muokata vasta tietolähteen luomisen jälkeen.</span><span class="sxs-lookup"><span data-stu-id="a0a56-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="a0a56-132">Esimerkiksi silloin, jos lisäentiteettejä lisättiin Common Data Serviceen ja haluat tuoda myös ne.</span><span class="sxs-lookup"><span data-stu-id="a0a56-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="a0a56-133">Jos haluat muodostaa yhteyden eri Common Data Serviceen, [luo uusi tietolähde](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="a0a56-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="a0a56-134">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.</span><span class="sxs-lookup"><span data-stu-id="a0a56-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="a0a56-135">Valitse päivitettävän tietolähteen vieressä kolme pistettä.</span><span class="sxs-lookup"><span data-stu-id="a0a56-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="a0a56-136">Valitse luettelossa **Muokkaa**-vaihtoehto.</span><span class="sxs-lookup"><span data-stu-id="a0a56-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="a0a56-137">Valitse lisäentiteetit käytettävissä olevien entiteettien luettelosta ja valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="a0a56-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]