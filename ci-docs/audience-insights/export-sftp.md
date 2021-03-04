---
title: Customer Insightsin tietojen vieminen SFTP-isäntiin
description: Opettele määrittämään yhteys SFTP-palvelimeen.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267994"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="7776a-103">SFTP-yhdistin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="7776a-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="7776a-104">Asiakastietojen käyttäminen kolmansien osapuolten sovelluksissa viemällä ne SFTP (Secure File Transfer Protocol) -isäntään.</span><span class="sxs-lookup"><span data-stu-id="7776a-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7776a-105">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="7776a-105">Prerequisites</span></span>

- <span data-ttu-id="7776a-106">SFTP-isännän ja vastaavien valtuustietojen käytettävyys.</span><span class="sxs-lookup"><span data-stu-id="7776a-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="7776a-107">Muodosta yhteys SFTP:hen</span><span class="sxs-lookup"><span data-stu-id="7776a-107">Connect to SFTP</span></span>

1. <span data-ttu-id="7776a-108">Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="7776a-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7776a-109">Valitse kohdassa **SFTP** **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="7776a-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="7776a-110">Anna kohteelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="7776a-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="7776a-111">Anna SFTP-tilille **Käyttäjänimi**, **Salasana**, **Isäntänimi** ja **Vientikansio**.</span><span class="sxs-lookup"><span data-stu-id="7776a-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="7776a-112">Valitse **Tarkista** yhteyden testausta varten.</span><span class="sxs-lookup"><span data-stu-id="7776a-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="7776a-113">Kun tarkistus on tehty, määritä, viedäänkö tiedot **Gzip-pakattuina** vai **purettuina**. Valitse sitten vietyjen tiedostojen **kentän erotin**.</span><span class="sxs-lookup"><span data-stu-id="7776a-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="7776a-114">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="7776a-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7776a-115">Aloita viennin määrittäminen valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="7776a-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="7776a-116">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="7776a-116">Configure the export</span></span>

1. <span data-ttu-id="7776a-117">Valitse vietävät entiteetit, esimerkiksi segmentit.</span><span class="sxs-lookup"><span data-stu-id="7776a-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7776a-118">Kukin valittu entiteetti sisältää enintään viisi tulostetiedostoa vietäessä.</span><span class="sxs-lookup"><span data-stu-id="7776a-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="7776a-119">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="7776a-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7776a-120">Tietojen vieminen</span><span class="sxs-lookup"><span data-stu-id="7776a-120">Export the data</span></span>

<span data-ttu-id="7776a-121">Voit [viedä tietoja tarvittaessa](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="7776a-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="7776a-122">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="7776a-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7776a-123">Tunnetut rajoitukset</span><span class="sxs-lookup"><span data-stu-id="7776a-123">Known limitations</span></span>

- <span data-ttu-id="7776a-124">Viennin suoritusaika määräytyy järjestelmän suorituskyvyn mukaan.</span><span class="sxs-lookup"><span data-stu-id="7776a-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="7776a-125">Suosittelemme, että palvelimen käytössä on vähintään kaksi suoritinydintä ja yksi gigatavu muistia.</span><span class="sxs-lookup"><span data-stu-id="7776a-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="7776a-126">Entiteettien vieminen enintään 100 miljoonalle asiakasprofiilille voi kestää 90 minuuttia, kun käytössä on suositeltu vähimmäismääritys eli kaksi suoritinydintä ja yksi gigatavu muistia.</span><span class="sxs-lookup"><span data-stu-id="7776a-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7776a-127">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="7776a-127">Data privacy and compliance</span></span>

<span data-ttu-id="7776a-128">Kun tietojen lähetys SFTP:n kautta otetaan käyttöön Dynamics 365 Customer Insightsissa, tietojen siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="7776a-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7776a-129">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että vientikohde noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="7776a-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7776a-130">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7776a-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7776a-131">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="7776a-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]