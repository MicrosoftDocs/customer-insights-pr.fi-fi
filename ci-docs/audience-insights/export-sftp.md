---
title: Customer Insightsin tietojen vieminen SFTP-isäntiin
description: Opettele määrittämään yhteys SFTP-palvelimeen.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643499"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="bc43f-103">SFTP-yhdistin (esiversio)</span><span class="sxs-lookup"><span data-stu-id="bc43f-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="bc43f-104">Asiakastietojen käyttäminen kolmansien osapuolten sovelluksissa viemällä ne SFTP (Secure File Transfer Protocol) -isäntään.</span><span class="sxs-lookup"><span data-stu-id="bc43f-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bc43f-105">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="bc43f-105">Prerequisites</span></span>

- <span data-ttu-id="bc43f-106">SFTP-isännän ja vastaavien tunnistetietojen käytettävyys.</span><span class="sxs-lookup"><span data-stu-id="bc43f-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="bc43f-107">Yhdistäminen SFTP-palvelimeen</span><span class="sxs-lookup"><span data-stu-id="bc43f-107">Connect to SFTP</span></span>

1. <span data-ttu-id="bc43f-108">Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="bc43f-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="bc43f-109">Valitse kohdassa **SFTP** **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="bc43f-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="bc43f-110">Anna kohteelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="bc43f-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="bc43f-111">Anna SFTP-tilin **Käyttäjänimi**, **Salasana** ja **Isäntänimi**.</span><span class="sxs-lookup"><span data-stu-id="bc43f-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="bc43f-112">Esimerkki: jos SFTP-palvelimen pääkansio on /root/folder ja haluat, että tiedot viedään kansioon /root/folder/ci_export_destination_folder, isännän on silloin oltava sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="bc43f-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="bc43f-113">Valitse **Tarkista** yhteyden testausta varten.</span><span class="sxs-lookup"><span data-stu-id="bc43f-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="bc43f-114">Kun tarkistus on onnistunut, valitse, haluatko viedä tiedot **pakattuina** vai **purettuina**, ja valitse sitten vietyjen tiedostojen **kenttäerotin**.</span><span class="sxs-lookup"><span data-stu-id="bc43f-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="bc43f-115">Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).</span><span class="sxs-lookup"><span data-stu-id="bc43f-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bc43f-116">Aloita viennin määrittäminen valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="bc43f-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="bc43f-117">Yhteyden määrittäminen</span><span class="sxs-lookup"><span data-stu-id="bc43f-117">Configure the connection</span></span>

1. <span data-ttu-id="bc43f-118">Valitse vietävät **asiakkaan määritteet**.</span><span class="sxs-lookup"><span data-stu-id="bc43f-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="bc43f-119">Voit viedä yhden tai useita määritteitä.</span><span class="sxs-lookup"><span data-stu-id="bc43f-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="bc43f-120">Valitse **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="bc43f-120">Select **Next**.</span></span>

1. <span data-ttu-id="bc43f-121">Valitse segmentit, jotka haluat viedä.</span><span class="sxs-lookup"><span data-stu-id="bc43f-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="bc43f-122">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="bc43f-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="bc43f-123">Tietojen vieminen</span><span class="sxs-lookup"><span data-stu-id="bc43f-123">Export the data</span></span>

<span data-ttu-id="bc43f-124">Voit [viedä tietoja tarvittaessa](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="bc43f-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="bc43f-125">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="bc43f-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bc43f-126">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="bc43f-126">Data privacy and compliance</span></span>

<span data-ttu-id="bc43f-127">Kun tietojen lähetys SFTP:n kautta otetaan käyttöön Dynamics 365 Customer Insightsissa, tietojen siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="bc43f-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bc43f-128">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että vientikohde noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="bc43f-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bc43f-129">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bc43f-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bc43f-130">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="bc43f-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
