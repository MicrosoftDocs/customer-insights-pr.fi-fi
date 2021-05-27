---
title: Customer Insightsin tietojen vieminen SFTP-isäntiin
description: Tietoja yhteyden määrittämisestä ja viennistä SFTP-sijaintiin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3663a48955f0b1db8a96e25403e5f8947bc6a220
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976889"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="39fb9-103">Segmenttiluetteloiden ja muiden tietojen vieminen SFTP-sijaintiin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="39fb9-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="39fb9-104">Käytä asiakastietojasi kolmansien osapuolten sovelluksissa viemällä ne Secure File Transfer Protocol (SFTP) -sijaintiin.</span><span class="sxs-lookup"><span data-stu-id="39fb9-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="39fb9-105">Yhteyden edellytykset</span><span class="sxs-lookup"><span data-stu-id="39fb9-105">Prerequisites for connection</span></span>

- <span data-ttu-id="39fb9-106">SFTP-isännän ja vastaavien valtuustietojen käytettävyys.</span><span class="sxs-lookup"><span data-stu-id="39fb9-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="39fb9-107">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="39fb9-107">Known limitations</span></span>

- <span data-ttu-id="39fb9-108">Viennin suoritusaika määräytyy järjestelmän suorituskyvyn mukaan.</span><span class="sxs-lookup"><span data-stu-id="39fb9-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="39fb9-109">Suosittelemme, että palvelimen käytössä on vähintään kaksi suoritinydintä ja yksi gigatavu muistia.</span><span class="sxs-lookup"><span data-stu-id="39fb9-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="39fb9-110">Entiteettien vieminen enintään 100 miljoonalle asiakasprofiilille voi kestää 90 minuuttia, kun käytössä on suositeltu vähimmäismääritys eli kaksi suoritinydintä ja yksi gigatavu muistia.</span><span class="sxs-lookup"><span data-stu-id="39fb9-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="39fb9-111">Määritä SFTP-yhteydet</span><span class="sxs-lookup"><span data-stu-id="39fb9-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="39fb9-112">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="39fb9-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="39fb9-113">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **SFTP**.</span><span class="sxs-lookup"><span data-stu-id="39fb9-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="39fb9-114">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="39fb9-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="39fb9-115">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="39fb9-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="39fb9-116">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="39fb9-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="39fb9-117">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="39fb9-117">Choose who can use this connection.</span></span> <span data-ttu-id="39fb9-118">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="39fb9-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="39fb9-119">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="39fb9-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="39fb9-120">Anna SFTP-tilille **Käyttäjänimi**, **Salasana**, **Isäntänimi** ja **Vientikansio**.</span><span class="sxs-lookup"><span data-stu-id="39fb9-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="39fb9-121">Valitse **Tarkista** yhteyden testausta varten.</span><span class="sxs-lookup"><span data-stu-id="39fb9-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="39fb9-122">Valitse, haluatko viedä tiedot **gzip**-muodossa vai **pakkaamattomina** sekä vietävien tiedostojen **kenttäerotin**.</span><span class="sxs-lookup"><span data-stu-id="39fb9-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="39fb9-123">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="39fb9-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="39fb9-124">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="39fb9-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="39fb9-125">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="39fb9-125">Configure an export</span></span>

<span data-ttu-id="39fb9-126">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="39fb9-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="39fb9-127">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="39fb9-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="39fb9-128">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="39fb9-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="39fb9-129">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="39fb9-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="39fb9-130">Valitse **Yhteys vientiä varten** -kentässä yhteys SFTP-osasta.</span><span class="sxs-lookup"><span data-stu-id="39fb9-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="39fb9-131">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="39fb9-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="39fb9-132">Valitse vietävät entiteetit, esimerkiksi segmentit.</span><span class="sxs-lookup"><span data-stu-id="39fb9-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="39fb9-133">Kukin valittu kohde jaetaan enintään viiteen tulostiedostoon vietäessä.</span><span class="sxs-lookup"><span data-stu-id="39fb9-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="39fb9-134">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="39fb9-134">Select **Save**.</span></span>

<span data-ttu-id="39fb9-135">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="39fb9-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="39fb9-136">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="39fb9-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="39fb9-137">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="39fb9-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="39fb9-138">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="39fb9-138">Data privacy and compliance</span></span>

<span data-ttu-id="39fb9-139">Kun tietojen lähetys SFTP:n kautta otetaan käyttöön Dynamics 365 Customer Insightsissa, tietojen siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="39fb9-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="39fb9-140">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että vientikohde noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="39fb9-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="39fb9-141">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="39fb9-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="39fb9-142">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="39fb9-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
