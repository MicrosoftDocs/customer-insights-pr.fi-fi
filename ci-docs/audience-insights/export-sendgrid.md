---
title: Customer Insights -tietojen vieminen SendGridiin
description: Tietoja yhteyden määrittämisestä SendGridiin.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268728"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="0668b-103">SendGrid-yhdistin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="0668b-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="0668b-104">Vie yhdistettyjen asiakasprofiilien segmentit SendGridin yhteyshenkilöluetteloihin ja käytä niitä SendGridin kampanjoissa ja sähköpostimarkkinoinnissa.</span><span class="sxs-lookup"><span data-stu-id="0668b-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="0668b-105">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="0668b-105">Prerequisites</span></span>

-   <span data-ttu-id="0668b-106">[SendGrid-tili](https://sendgrid.com/) ja vastaavat järjestelmänvalvojan tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="0668b-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0668b-107">SendGridissa on aiemmin luotuja yhteyshenkilöluetteloja ja vastaavia tunnuksia.</span><span class="sxs-lookup"><span data-stu-id="0668b-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="0668b-108">Lisätietoja on kohdassa [SendGrid - yhteyshenkilöiden hallinta](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="0668b-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="0668b-109">Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).</span><span class="sxs-lookup"><span data-stu-id="0668b-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="0668b-110">Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.</span><span class="sxs-lookup"><span data-stu-id="0668b-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="0668b-111">Yhteyden muodostaminen SendGridiin</span><span class="sxs-lookup"><span data-stu-id="0668b-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="0668b-112">Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="0668b-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0668b-113">Valitse **SendGrid**-kohdassa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="0668b-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="0668b-114">Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="0668b-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGridin viennin määritysruutu.":::

1. <span data-ttu-id="0668b-116">Anna **SendGridin ohjelmointirajapinnan avain** [SendGridin ohjelmointirajapinnan avain](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="0668b-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="0668b-117">Anna **[SendGrid-luettelon tunnus](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="0668b-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="0668b-118">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="0668b-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0668b-119">Käynnistä SendGrid-yhteys valitsemalla **Yhdistä**.</span><span class="sxs-lookup"><span data-stu-id="0668b-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="0668b-120">Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.</span><span class="sxs-lookup"><span data-stu-id="0668b-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0668b-121">Määritä vienti valitsemalla **Next**.</span><span class="sxs-lookup"><span data-stu-id="0668b-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="0668b-122">Yhdistimen määrittäminen</span><span class="sxs-lookup"><span data-stu-id="0668b-122">Configure the connector</span></span>

1. <span data-ttu-id="0668b-123">Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="0668b-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0668b-124">Toimi samalla tavalla muiden valinnaisten kenttien osalta. Näitä kenttiä ovat esimerkiksi **Etunimi**, **Sukunimi**, **Maa/alue**, **Osavaltio**, **Kaupunki** ja **Postinumero**.</span><span class="sxs-lookup"><span data-stu-id="0668b-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="0668b-125">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="0668b-125">Select the segments you want to export.</span></span> <span data-ttu-id="0668b-126">On erittäin **suositeltavaa, että asiakastietueita viedään enintään 100 000** SendGridiin.</span><span class="sxs-lookup"><span data-stu-id="0668b-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="0668b-127">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="0668b-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0668b-128">Tietojen vieminen</span><span class="sxs-lookup"><span data-stu-id="0668b-128">Export the data</span></span>

<span data-ttu-id="0668b-129">Voit [viedä tietoja tarvittaessa](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0668b-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0668b-130">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="0668b-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0668b-131">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="0668b-131">Known limitations</span></span>

- <span data-ttu-id="0668b-132">Yhteensä enintään 100 000 profiilia SendGridiin.</span><span class="sxs-lookup"><span data-stu-id="0668b-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="0668b-133">SendGrid-vienti on rajoitettu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="0668b-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="0668b-134">100 000 profiilin vieminen SendGridiin voi kestää muutaman tunnin.</span><span class="sxs-lookup"><span data-stu-id="0668b-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="0668b-135">SendGridiin vietävien profiilien määrä määräytyy SendGrid-sopimuksen mukaan, joka myös rajoittaa profiilien määrää.</span><span class="sxs-lookup"><span data-stu-id="0668b-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0668b-136">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="0668b-136">Data privacy and compliance</span></span>

<span data-ttu-id="0668b-137">Kun tietojen lähetys SendGridiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="0668b-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0668b-138">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että SendGrid noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="0668b-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="0668b-139">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0668b-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0668b-140">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="0668b-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]