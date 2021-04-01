---
title: Rekisteröityjen oikeuksien (DSR) pyynnöt GDPR:n mukaan | Microsoft Docs
description: Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuuden rekisteröidyn pyyntöön vastaaminen.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9c453c9b416bff0e6362a8ccf7ff534f4efa1e00
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597507"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="9bc05-103">Rekisteröityjen oikeuksien (DSR) pyynnöt GDPR:n mukaan</span><span class="sxs-lookup"><span data-stu-id="9bc05-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="9bc05-104">Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuuden rekisteröityjen poistopyyntöihin vastaaminen GDPR:n mukaisesti.</span><span class="sxs-lookup"><span data-stu-id="9bc05-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="9bc05-105">Oikeus poistaa henkilökohtaisia tietoja organisaation asiakastiedoista on yleisen tietosuoja-asetuksen (GDPR) tärkeä osa.</span><span class="sxs-lookup"><span data-stu-id="9bc05-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="9bc05-106">Henkilökohtaisten tietojen poistaminen sisältää kaikkien henkilökohtaisten tietojen sekä järjestelmän luomien lokien poistaminen. Tähän eivät kuulu seurantalokien tiedot.</span><span class="sxs-lookup"><span data-stu-id="9bc05-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="9bc05-107">Rekisteröityjen poistopyyntöjen hallinta</span><span class="sxs-lookup"><span data-stu-id="9bc05-107">Manage data subject delete requests</span></span>

<span data-ttu-id="9bc05-108">Käyttäjäryhmän merkitykselliset tiedot sisältävät seuraavat ominaisuudet, joilla voi poistaa tietyn asiakkaan tai käyttäjän henkilökohtaisia tietoja:</span><span class="sxs-lookup"><span data-stu-id="9bc05-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="9bc05-109">**Asiakastietojen poistopyyntöjen hallinta**: Customer Insightsin asiakastiedot käsitellään alkuperäisistä tietolähteistä Customer Insightsin ulkopuolelta.</span><span class="sxs-lookup"><span data-stu-id="9bc05-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="9bc05-110">Kaikki GDPR-poistopyynnöt on suoritettava alkuperäisessä tietolähteessä.</span><span class="sxs-lookup"><span data-stu-id="9bc05-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="9bc05-111">**Customer Insightsin käyttäjätietojen poistopyyntöjen hallinta**:Customer Insightsin luo käyttäjien tiedot.</span><span class="sxs-lookup"><span data-stu-id="9bc05-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="9bc05-112">Kaikki GDPR-poistopyynnöt on suoritettava Customer Insightsissa.</span><span class="sxs-lookup"><span data-stu-id="9bc05-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="9bc05-113">Asiakastietojen poistopyyntöjen hallinta</span><span class="sxs-lookup"><span data-stu-id="9bc05-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="9bc05-114">Customer Insightsin järjestelmänvalvoja voi seurata näitä vaiheita ja poistaa asiakastiedot, jotka on poistettu tietolähteestä seuraavalla tavalla:</span><span class="sxs-lookup"><span data-stu-id="9bc05-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="9bc05-115">Kirjaudu Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9bc05-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="9bc05-116">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**</span><span class="sxs-lookup"><span data-stu-id="9bc05-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="9bc05-117">Jokainen luettelon tietolähde, joka sisältää poistetut asiakastiedot:</span><span class="sxs-lookup"><span data-stu-id="9bc05-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="9bc05-118">Valitse (...) ja valitse sitten **Päivitä**.</span><span class="sxs-lookup"><span data-stu-id="9bc05-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="9bc05-119">Tarkista tietolähteen tila **Tila**-kohdassa.</span><span class="sxs-lookup"><span data-stu-id="9bc05-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="9bc05-120">Valintamerkki osoittaa, että päivitys onnistui.</span><span class="sxs-lookup"><span data-stu-id="9bc05-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="9bc05-121">Varoituskolmio osoittaa, että päivitys ei onnistunut.</span><span class="sxs-lookup"><span data-stu-id="9bc05-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="9bc05-122">Jos varoituskolmion näkyy, ota yhteys osoitteen D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="9bc05-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9bc05-123">![Asiakastietojen GDPR-poistopyyntöjen käsittely](media/gdpr-data-sources.png "Asiakastietojen GDPR-poistopyyntöjen käsittely")</span><span class="sxs-lookup"><span data-stu-id="9bc05-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="9bc05-124">Käyttäjätietojen poistopyyntöjen hallinta</span><span class="sxs-lookup"><span data-stu-id="9bc05-124">Manage delete requests for user data</span></span>

<span data-ttu-id="9bc05-125">Customer Insightsin järjestelmänvalvoja voi poistaa Customer Insightsin käyttäjätiedot seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="9bc05-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="9bc05-126">Kirjaudu Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9bc05-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="9bc05-127">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Käyttöoikeudet**</span><span class="sxs-lookup"><span data-stu-id="9bc05-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="9bc05-128">Valitse poistettavan käyttäjän valintaruutu.</span><span class="sxs-lookup"><span data-stu-id="9bc05-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="9bc05-129">Valitse **Poista**.</span><span class="sxs-lookup"><span data-stu-id="9bc05-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9bc05-130">![Käyttäjätietojen poistopyyntöjen käsittely GDPR:n mukaisesti](media/gdpr-permissions.png "Käyttäjätietojen poistopyyntöjen käsittely GDPR:n mukaisesti")</span><span class="sxs-lookup"><span data-stu-id="9bc05-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="9bc05-131">Rekisteröityjen vientipyyntöihin vastaaminen GDPR:n mukaisesti</span><span class="sxs-lookup"><span data-stu-id="9bc05-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="9bc05-132">Osana sitoumustamme toimia kumppaninasi yleisen tietosuoja-asetuksen (GDPR) noudattamisessa olemme kehittäneet ohjeistuksen, joka auttaa valmistautumisessa.</span><span class="sxs-lookup"><span data-stu-id="9bc05-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="9bc05-133">Tässä dokumentaatiossa on ohjeet, jotka tekemällä voidaan tukea GDPR:n vaatimustenmukaisuutta käyttäjäryhmän merkityksellisiä tietoja käytettäessä.</span><span class="sxs-lookup"><span data-stu-id="9bc05-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="9bc05-134">Vienti- ja tarkastelupyyntöjen hallinta</span><span class="sxs-lookup"><span data-stu-id="9bc05-134">Manage export and view requests</span></span>

<span data-ttu-id="9bc05-135">Oikeus tietojen siirrettävyyteen mahdollistaa sen, että rekisteröidyt voivat pyytää kopiota henkilökohtaisista tiedoistaan sähköisessä muodossa (rakenteellisena, usein käytettynä, koneellisesti luettavissa olevana ja yhteentoimivassa muodossa olevana), joka voidaan toimittaa toiselle tiedonkäsittelijälle.</span><span class="sxs-lookup"><span data-stu-id="9bc05-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="9bc05-136">Asiakastietojen vieminen (vuokraajan järjestelmänvalvoja)</span><span class="sxs-lookup"><span data-stu-id="9bc05-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="9bc05-137">Vuokraajan järjestelmänvalvoja voi viedä tiedot seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="9bc05-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="9bc05-138">Lähetä osoitteeseen D365CI@microsoft.com sähköposti, jossa määritetään asiakkaan pyynnössä oleva sähköpostiosoite.</span><span class="sxs-lookup"><span data-stu-id="9bc05-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="9bc05-139">Customer Insights -ryhmä lähettää sähköpostin rekisteröidyn vuokraajan järjestelmänvalvojan sähköpostiosoitteeseen ja pyytää vahvistamaan tietojen viennin.</span><span class="sxs-lookup"><span data-stu-id="9bc05-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="9bc05-140">Kuittaa pyydetyn asiakkaan tietojen vientivahvistus.</span><span class="sxs-lookup"><span data-stu-id="9bc05-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="9bc05-141">Saat viedyt tiedot vuokraajan järjestelmänvalvojan sähköpostiosoitteen kautta.</span><span class="sxs-lookup"><span data-stu-id="9bc05-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="9bc05-142">Käyttäjätietojen vieminen (vuokraajan järjestelmänvalvoja)</span><span class="sxs-lookup"><span data-stu-id="9bc05-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="9bc05-143">Lähetä osoitteeseen D365CI@microsoft.com sähköposti, jossa määritetään käyttäjän pyynnössä oleva sähköpostiosoite.</span><span class="sxs-lookup"><span data-stu-id="9bc05-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="9bc05-144">Customer Insights -ryhmä lähettää sähköpostin rekisteröidyn vuokraajan järjestelmänvalvojan sähköpostiosoitteeseen ja pyytää vahvistamaan tietojen viennin.</span><span class="sxs-lookup"><span data-stu-id="9bc05-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="9bc05-145">Kuittaa pyydetyn käyttäjän tietojen vientivahvistus.</span><span class="sxs-lookup"><span data-stu-id="9bc05-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="9bc05-146">Saat viedyt tiedot vuokraajan järjestelmänvalvojan sähköpostiosoitteen kautta.</span><span class="sxs-lookup"><span data-stu-id="9bc05-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]