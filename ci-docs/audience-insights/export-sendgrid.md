---
title: Customer Insights -tietojen vieminen SendGridiin
description: Tietoja yhteyden määrittämisestä ja viennistä SendGridiin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759761"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="eb01a-103">Segmenttien vieminen SendGridiin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="eb01a-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="eb01a-104">Vie yhdistettyjen asiakasprofiilien segmentit SendGridin yhteyshenkilöluetteloihin ja käytä niitä SendGridin kampanjoissa ja sähköpostimarkkinoinnissa.</span><span class="sxs-lookup"><span data-stu-id="eb01a-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="eb01a-105">Yhteyden edellytykset</span><span class="sxs-lookup"><span data-stu-id="eb01a-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="eb01a-106">[SendGrid-tili](https://sendgrid.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="eb01a-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="eb01a-107">SendGridissa on aiemmin luotuja yhteyshenkilöluetteloja ja vastaavia tunnuksia.</span><span class="sxs-lookup"><span data-stu-id="eb01a-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="eb01a-108">Lisätietoja on kohdassa [SendGrid - yhteyshenkilöiden hallinta](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="eb01a-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="eb01a-109">Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).</span><span class="sxs-lookup"><span data-stu-id="eb01a-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="eb01a-110">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="eb01a-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="eb01a-111">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="eb01a-111">Known limitations</span></span>

- <span data-ttu-id="eb01a-112">Yhteensä enintään 100 000 profiilia SendGridiin.</span><span class="sxs-lookup"><span data-stu-id="eb01a-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="eb01a-113">SendGrid-vienti on rajoitettu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="eb01a-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="eb01a-114">100 000 profiilin vieminen SendGridiin voi kestää muutaman tunnin.</span><span class="sxs-lookup"><span data-stu-id="eb01a-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="eb01a-115">SendGridiin vietävien profiilien määrä määräytyy SendGrid-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.</span><span class="sxs-lookup"><span data-stu-id="eb01a-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="eb01a-116">Määritä yhteys SendGridiin</span><span class="sxs-lookup"><span data-stu-id="eb01a-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="eb01a-117">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="eb01a-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="eb01a-118">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **SendGrid**.</span><span class="sxs-lookup"><span data-stu-id="eb01a-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="eb01a-119">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="eb01a-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="eb01a-120">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="eb01a-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="eb01a-121">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="eb01a-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="eb01a-122">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="eb01a-122">Choose who can use this connection.</span></span> <span data-ttu-id="eb01a-123">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="eb01a-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="eb01a-124">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="eb01a-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="eb01a-125">Anna **SendGridin ohjelmointirajapinnan avain** [SendGridin ohjelmointirajapinnan avain](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="eb01a-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="eb01a-126">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="eb01a-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="eb01a-127">Käynnistä SendGrid-yhteys valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="eb01a-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="eb01a-128">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="eb01a-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="eb01a-129">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="eb01a-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="eb01a-130">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="eb01a-130">Configure an export</span></span>

<span data-ttu-id="eb01a-131">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="eb01a-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="eb01a-132">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="eb01a-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="eb01a-133">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="eb01a-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="eb01a-134">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="eb01a-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="eb01a-135">Valitse **Yhteys vientiä varten** -kentässä yhteys SendGrid-osasta.</span><span class="sxs-lookup"><span data-stu-id="eb01a-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="eb01a-136">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="eb01a-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="eb01a-137">Anna **[SendGrid-luettelon tunnus](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="eb01a-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="eb01a-138">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="eb01a-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="eb01a-139">Toimi samalla tavalla muiden valinnaisten kenttien osalta. Näitä kenttiä ovat esimerkiksi **Etunimi**, **Sukunimi**, **Maa/alue**, **Osavaltio**, **Kaupunki** ja **Postinumero**.</span><span class="sxs-lookup"><span data-stu-id="eb01a-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="eb01a-140">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="eb01a-140">Select the segments you want to export.</span></span> <span data-ttu-id="eb01a-141">On erittäin **suositeltavaa, että asiakastietueita viedään enintään 100 000** SendGridiin.</span><span class="sxs-lookup"><span data-stu-id="eb01a-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="eb01a-142">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="eb01a-142">Select **Save**.</span></span>

<span data-ttu-id="eb01a-143">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="eb01a-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="eb01a-144">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="eb01a-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="eb01a-145">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="eb01a-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="eb01a-146">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="eb01a-146">Data privacy and compliance</span></span>

<span data-ttu-id="eb01a-147">Kun tietojen lähetys SendGridiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="eb01a-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="eb01a-148">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että SendGrid noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="eb01a-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="eb01a-149">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="eb01a-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="eb01a-150">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="eb01a-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]