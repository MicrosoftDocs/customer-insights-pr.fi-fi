---
title: Customer Insightsin tietojen vieminen DotDigitaliin
description: Tietoja yhteyden määrittämisestä ja viennistä DotDigitaliin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d08504856e1c673ef32433b83bf491d7f4e8cee4
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976842"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="19e65-103">Segmenttiluetteloiden vieminen DotDigitaliin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="19e65-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="19e65-104">Vie yhtenäistettyjen asiakasprofiilien segmentit DotDigital-osoitekirjoihin ja käytä niitä kampanjoissa, sähköpostimarkkinoinnissa ja asiakassegmenttien muodostamisessa DotDigitalin kanssa.</span><span class="sxs-lookup"><span data-stu-id="19e65-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="19e65-105">Yhteyden edellytykset</span><span class="sxs-lookup"><span data-stu-id="19e65-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="19e65-106">[DotDigital-tili](https://dotdigital.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="19e65-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="19e65-107">DotDigitalissa on aiemmin luotuja osoitekirjoja ja vastaavia tunnuksia.</span><span class="sxs-lookup"><span data-stu-id="19e65-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="19e65-108">Tunnus saadaan URL-osoitteesta, kun valitset ja avaat osoitekirjan.</span><span class="sxs-lookup"><span data-stu-id="19e65-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="19e65-109">Lisätietoja on kohdassa [DotDigital-osoitekirjat](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="19e65-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="19e65-110">Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).</span><span class="sxs-lookup"><span data-stu-id="19e65-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="19e65-111">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="19e65-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="19e65-112">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="19e65-112">Known limitations</span></span>

- <span data-ttu-id="19e65-113">Enintään 1 miljoona profiilia kussakin DotDigital-viennissä.</span><span class="sxs-lookup"><span data-stu-id="19e65-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="19e65-114">DotDigital-vienti on rajoitettu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="19e65-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="19e65-115">Yhteensä 1 miljoonan profiilin segmenttien vienti voi kestää 3 tuntia palveluntoimittajan rajoitusten vuoksi.</span><span class="sxs-lookup"><span data-stu-id="19e65-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="19e65-116">DotDigitaliin vietävien profiilien määrä määräytyy DotDigital-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.</span><span class="sxs-lookup"><span data-stu-id="19e65-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="19e65-117">Määritä yhteys DotDigitaliin</span><span class="sxs-lookup"><span data-stu-id="19e65-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="19e65-118">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="19e65-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="19e65-119">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="19e65-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="19e65-120">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="19e65-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="19e65-121">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="19e65-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="19e65-122">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="19e65-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="19e65-123">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="19e65-123">Choose who can use this connection.</span></span> <span data-ttu-id="19e65-124">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="19e65-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="19e65-125">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="19e65-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="19e65-126">Anna **DotDigitalin käyttäjänimi ja salasana**.</span><span class="sxs-lookup"><span data-stu-id="19e65-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="19e65-127">Anna **[DotDigital-osoitekirjan tunnus](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="19e65-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="19e65-128">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="19e65-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="19e65-129">Käynnistä DotDigital-yhteys valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="19e65-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="19e65-130">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="19e65-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="19e65-131">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="19e65-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="19e65-132">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="19e65-132">Configure an export</span></span>

<span data-ttu-id="19e65-133">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="19e65-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="19e65-134">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="19e65-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="19e65-135">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="19e65-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="19e65-136">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="19e65-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="19e65-137">Valitse **Yhteys vientiä varten** -kentässä yhteys DotDigital-osasta.</span><span class="sxs-lookup"><span data-stu-id="19e65-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="19e65-138">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="19e65-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="19e65-139">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="19e65-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="19e65-140">Toimi samalla tavalla muiden valinnaisten kenttien osalta. Näitä kenttiä ovat esimerkiksi **Etunimi**, **Sukunimi**, **Koko nimi**, **Sukupuoli** ja **Postinumero**.</span><span class="sxs-lookup"><span data-stu-id="19e65-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="19e65-141">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="19e65-141">Select the segments you want to export.</span></span> <span data-ttu-id="19e65-142">Voit viedä yhteensä enintään 1 000 000 asiakasprofiilia DotDigitaliin.</span><span class="sxs-lookup"><span data-stu-id="19e65-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="19e65-143">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="19e65-143">Select **Save**.</span></span>

<span data-ttu-id="19e65-144">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="19e65-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="19e65-145">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="19e65-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="19e65-146">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="19e65-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="19e65-147">DotDigitalissa voi etsiä nyt segmenttejä [DotDigital-osoitekirjoissa](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="19e65-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="19e65-148">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="19e65-148">Data privacy and compliance</span></span>

<span data-ttu-id="19e65-149">Kun tietojen lähetys DotDigitaliin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="19e65-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="19e65-150">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että DotDigital noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="19e65-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="19e65-151">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="19e65-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="19e65-152">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="19e65-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
