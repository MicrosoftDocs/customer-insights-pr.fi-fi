---
title: Customer Insightsin tietojen vieminen Facebookin mainosten hallintaan
description: Tietoja yhteyden määrittämisestä ja viennistä Facebook Ads Manageriin.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e20c7b7fd3989d7621cb7765f38b85c8ab4adfcb
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305106"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="86c92-103">Segmenttiluettelon vieminen Facebook Ads Manageriin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="86c92-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="86c92-104">Voit luoda kampanjoita Facebookissa ja Instagramissaa viemällä yhdistettyjen asiakasprofiilien segmenttejä Facebook Ads Manageriin.</span><span class="sxs-lookup"><span data-stu-id="86c92-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="86c92-105">Yhteyden edellytykset</span><span class="sxs-lookup"><span data-stu-id="86c92-105">Prerequisites for connection</span></span>

- <span data-ttu-id="86c92-106">Tarvitset [**Facebook Ads -tilin**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), joka sisältää [**Facebookin yritystilin**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="86c92-106">You need to have a [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="86c92-107">Sinun on oltava [**Facebook Ads -tilin**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) järjestelmänvalvoja.</span><span class="sxs-lookup"><span data-stu-id="86c92-107">You need to be an administrator on the [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="86c92-108">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="86c92-108">Known limitations</span></span>

- <span data-ttu-id="86c92-109">Jopa 10 miljoonaa asiakasprofiilia vientiä kohden Facebook Ads -ratkaisun hallinnassa.</span><span class="sxs-lookup"><span data-stu-id="86c92-109">Up to 10 million customer profiles per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="86c92-110">Vienti Facebook Ads Manageriin on rajoitettu segmentteihin.</span><span class="sxs-lookup"><span data-stu-id="86c92-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="86c92-111">Voit luoda tai päivittää Facebookissa mukautettuja kohderyhmiä vain *asiakasluettelo*-tyypeille.</span><span class="sxs-lookup"><span data-stu-id="86c92-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="86c92-112">Yhteensä 10 miljoonan profiilin segmenttien vienti voi kestää 90 minuuttia.</span><span class="sxs-lookup"><span data-stu-id="86c92-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="86c92-113">Määritä yhteys Facebook Ads Manageriin</span><span class="sxs-lookup"><span data-stu-id="86c92-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="86c92-114">Ennen kuin käyttäjät voivat luoda viennin, järjestelmänvalvojan on määritettävä yhteys palveluun ja sallittava osallistujien käyttää yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="86c92-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="86c92-115">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="86c92-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="86c92-116">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="86c92-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="86c92-117">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="86c92-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="86c92-118">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="86c92-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="86c92-119">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="86c92-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="86c92-120">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="86c92-120">Choose who can use this connection.</span></span> <span data-ttu-id="86c92-121">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="86c92-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="86c92-122">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="86c92-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="86c92-123">Todenna Facebook Adsin avulla:</span><span class="sxs-lookup"><span data-stu-id="86c92-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="86c92-124">Valitse **Jatka Facebookilla**, jos haluat kirjautua sisään Facebook Ads -tilillä.</span><span class="sxs-lookup"><span data-stu-id="86c92-124">Select **Continue with Facebook** to sign in to your Facebook Ads account.</span></span>

   1. <span data-ttu-id="86c92-125">Salli **ads_management**-oikeus Facebook-todennuksen jälkeen.</span><span class="sxs-lookup"><span data-stu-id="86c92-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="86c92-126">Valitse **Facebook Ad -tili**, jota haluat käyttää.</span><span class="sxs-lookup"><span data-stu-id="86c92-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="86c92-127">Valitse **aiemmin luotu mukautettu käyttäjäryhmä** avattavasta luettelosta tai luo **uusi mukautettu käyttäjäryhmä**.</span><span class="sxs-lookup"><span data-stu-id="86c92-127">Select an **Existing custom audience** from the dropdown list or create a **New custom audience**.</span></span> <span data-ttu-id="86c92-128">Lisätietoja on kohdassa [**Kohdeyleisöt Facebook Ads Managerissa**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="86c92-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="86c92-129">Voit luoda tai päivittää Facebookissa mukautettuja kohderyhmiä vain *asiakasluettelo*-tyypille tämän viennin yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="86c92-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="86c92-130">Joissakin tapauksissa avattavassa luettelossa ovat eri tyyppiset mukautetut käyttäjäryhmät.</span><span class="sxs-lookup"><span data-stu-id="86c92-130">In some cases, you see custom audiences of different types in the dropdown list.</span></span> <span data-ttu-id="86c92-131">Jos valitset jonkin toisen tyypin kuin *asiakasluettelo*, vienti epäonnistuu.</span><span class="sxs-lookup"><span data-stu-id="86c92-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="86c92-132">Tarkista tietojen **Tietosuoja ja vaatimustenmukaisuus** ja valitse **Hyväksyn**.</span><span class="sxs-lookup"><span data-stu-id="86c92-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="86c92-133">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="86c92-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="86c92-134">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="86c92-134">Configure an export</span></span>

<span data-ttu-id="86c92-135">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="86c92-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="86c92-136">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="86c92-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="86c92-137">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="86c92-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="86c92-138">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="86c92-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="86c92-139">Valitse **Yhteys vientiä varten** -kentässä yhteys **Facebook Ads Manager** -osasta.</span><span class="sxs-lookup"><span data-stu-id="86c92-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="86c92-140">Jos et näe tämän osan nimeä, nämä yhteystyypit eivät ole käytettävissä.</span><span class="sxs-lookup"><span data-stu-id="86c92-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="86c92-141">Valitse **Choose your key identifier** -kentässä **Email**, **Name and address** tai **Phone**, jonka avulla lähetetään Facebook Ads Manageriin.</span><span class="sxs-lookup"><span data-stu-id="86c92-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="86c92-142">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="86c92-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="86c92-143">Yhdistä yhdistetyn asiakasentiteetin vastaavat määritteet valittua avaintunnistetta varten.</span><span class="sxs-lookup"><span data-stu-id="86c92-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > [!TIP]
   > <span data-ttu-id="86c92-144">Parhaat vastaavuudet saat, jos valitset avaintunnisteeksi **sähköpostin**.</span><span class="sxs-lookup"><span data-stu-id="86c92-144">The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="86c92-145">Lisätunnusten lisääminen voi parantaa vastaavuutta.</span><span class="sxs-lookup"><span data-stu-id="86c92-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="86c92-146">Valitse **Lisää määrite**, jos haluat yhdistää lisää määritteitä lähetettäväksi Facebook Ads Manageriin.</span><span class="sxs-lookup"><span data-stu-id="86c92-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="86c92-147">Facebook Ads -ratkaisun hallinnan määritteiden vastaavuus määritetään seuraaviin käyttäjän määrittämiin kutsumanimiin: **FN** = **etunimi**, **LN** = **sukunimi**, **FI** = **ensimmäinen alkukirjain**, **PHONE** = **puhelin**, **GEN** = **sukupuoli**, **DOB** = **syntymäaika**, **ST** = **osavaltio**, **CT** = **kaupunki**, **ZIP** = **postinumero**, **COUNTRY** = **maa tai alue**</span><span class="sxs-lookup"><span data-stu-id="86c92-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / ZIP Code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="86c92-148">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="86c92-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="86c92-149">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="86c92-149">Select **Save**.</span></span>

<span data-ttu-id="86c92-150">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="86c92-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="86c92-151">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="86c92-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="86c92-152">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="86c92-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="86c92-153">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="86c92-153">Data privacy and compliance</span></span>

<span data-ttu-id="86c92-154">Kun tietojen lähetys Facebookin mainosten hallintaan otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="86c92-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="86c92-155">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Facebook Ads noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="86c92-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="86c92-156">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="86c92-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="86c92-157">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="86c92-157">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
