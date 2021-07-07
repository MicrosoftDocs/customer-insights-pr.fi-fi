---
title: Customer Insights -tietojen vieminen Salesforce Marketing Cloud -sovellukseen
description: Lisätietoja yhteyden ja viemisen määrittämisestä Salesforce Marketing Cloud -sovellukseen
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314603"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="7f594-103">Segmenttien ja muiden tietojen vieminen Salesforce Marketing Cloud -sovellukseen (esiversio)</span><span class="sxs-lookup"><span data-stu-id="7f594-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="7f594-104">Käytä Salesforce Marketing Cloud -sovelluksen asiakastietoja viemällä ne suojatun tiedostonsiirtoprotokollan (SFTP) sijainnin kautta.</span><span class="sxs-lookup"><span data-stu-id="7f594-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="7f594-105">Yhteyden edellytykset</span><span class="sxs-lookup"><span data-stu-id="7f594-105">Prerequisites for connection</span></span>

- <span data-ttu-id="7f594-106">SFTP-isännän ja vastaavien järjestelmänvalvojan valtuustietojen käytettävyys.</span><span class="sxs-lookup"><span data-stu-id="7f594-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="7f594-107">Salesforce Marketing Cloud -sovelluksen SFTP-sijaintien määrittäminen</span><span class="sxs-lookup"><span data-stu-id="7f594-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="7f594-108">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="7f594-108">Known limitations</span></span>

- <span data-ttu-id="7f594-109">Viennin suoritusaika määräytyy järjestelmän suorituskyvyn mukaan.</span><span class="sxs-lookup"><span data-stu-id="7f594-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="7f594-110">Suosittelemme, että palvelimen käytössä on vähintään kaksi suoritinydintä ja yksi gigatavu muistia.</span><span class="sxs-lookup"><span data-stu-id="7f594-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="7f594-111">100 miljoonan asiakasprofiilin vieminen voi kestää 90 minuuttia, kun käytössä on suositeltu vähimmäismääritys.</span><span class="sxs-lookup"><span data-stu-id="7f594-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="7f594-112">Yhteyden määrittäminen Salesforce Marketing Cloud -sovellukseen</span><span class="sxs-lookup"><span data-stu-id="7f594-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="7f594-113">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="7f594-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7f594-114">Määritä yhteys valitsemalla **Lisää yhteys**. Valitse lopuksi **Salesforce Marketing Cloud**.</span><span class="sxs-lookup"><span data-stu-id="7f594-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="7f594-115">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="7f594-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7f594-116">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="7f594-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7f594-117">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="7f594-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7f594-118">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="7f594-118">Choose who can use this connection.</span></span> <span data-ttu-id="7f594-119">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="7f594-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7f594-120">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7f594-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7f594-121">Anna SFTP-tilille **Käyttäjänimi**, **Salasana**, **Isäntänimi** ja **Vientikansio**.</span><span class="sxs-lookup"><span data-stu-id="7f594-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="7f594-122">Valitse **Tarkista** yhteyden testausta varten.</span><span class="sxs-lookup"><span data-stu-id="7f594-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="7f594-123">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="7f594-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7f594-124">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="7f594-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="7f594-125">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="7f594-125">Configure an export</span></span>

<span data-ttu-id="7f594-126">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="7f594-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7f594-127">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="7f594-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7f594-128">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="7f594-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7f594-129">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="7f594-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7f594-130">Valitse **Yhteys vientiä varten** -kentässä yhteys SFTP-osasta.</span><span class="sxs-lookup"><span data-stu-id="7f594-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="7f594-131">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="7f594-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7f594-132">Valitse, haluatko viedä tiedot **gzip**-muodossa vai **pakkaamattomina** sekä vietävien tiedostojen **kenttäerotin**.</span><span class="sxs-lookup"><span data-stu-id="7f594-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="7f594-133">Valitse vietävät entiteetit, esimerkiksi segmentit.</span><span class="sxs-lookup"><span data-stu-id="7f594-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7f594-134">Kukin valittu kohde jaetaan enintään viiteen tulostiedostoon vietäessä.</span><span class="sxs-lookup"><span data-stu-id="7f594-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="7f594-135">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="7f594-135">Select **Save**.</span></span>

<span data-ttu-id="7f594-136">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="7f594-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7f594-137">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="7f594-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7f594-138">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="7f594-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="7f594-139">Customer Insights -tietojen tuominen SFTP-sijainnista Salesforce Marketing Cloud -sovellukseen</span><span class="sxs-lookup"><span data-stu-id="7f594-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="7f594-140">Luo [tietolaajennukset Salesforce Marketing Cloud -sovellukseen](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5), jotta voit tuoda Customer Insightsin datatiedoston SFTP-sijainnista.</span><span class="sxs-lookup"><span data-stu-id="7f594-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="7f594-141">[Tuo tiedot SFTP-sijainnista](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) Salesforce Marketing Cloud -sovelluksen tietolaajennukseen.</span><span class="sxs-lookup"><span data-stu-id="7f594-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="7f594-142">Määritä tietojen automaattinen tuominen tietolaajennuksiin.</span><span class="sxs-lookup"><span data-stu-id="7f594-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="7f594-143">Lisätietoja [tiedoston pudottamisen automatisoinneista ja ajoitetuista automatisoinneista](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="7f594-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="7f594-144">Määritä [tiedoston pudottamisen automatisointi](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) tai [ajoitettu automatisointi](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="7f594-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="7f594-145">Tässä on esimerkki [automatisoinnista SFTP:n avulla](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="7f594-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7f594-146">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="7f594-146">Data privacy and compliance</span></span>

<span data-ttu-id="7f594-147">Kun tietojen lähetys SFTP:n kautta otetaan käyttöön Dynamics 365 Customer Insightsissa, tietojen siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="7f594-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7f594-148">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että vientikohde noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="7f594-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7f594-149">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7f594-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7f594-150">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="7f594-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
