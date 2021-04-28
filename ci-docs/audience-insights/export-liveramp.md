---
title: LiveRamp-yhdistin
description: Tietoja yhteyden määrittämisestä ja viennistä LiveRampiin.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760323"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="d6ed2-103">Segmenttien vieminen LiveRampiin&reg; (esiversio)</span><span class="sxs-lookup"><span data-stu-id="d6ed2-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="d6ed2-104">Aktivoi tiedot LiveRampissa, jotta voit muodostaa yhteyden yli 500 ympäristöön digitaalisissa kanavissa, yhteisöpalveluissa ja televisioissa.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="d6ed2-105">Työstä tietojasi LiveRampissa kohdistaaksesi, estääksesi ja yksilöllistääksesi mainoskampanjoita.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="d6ed2-106">Yhteyden edellytykset</span><span class="sxs-lookup"><span data-stu-id="d6ed2-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="d6ed2-107">Tämän yhdistimen käyttö edellyttää LiveRamp-tilausta.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="d6ed2-108">Hanki tilaus [ottamalla suoraan yhteyttä LiveRampiin](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="d6ed2-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="d6ed2-109">[Lisätietoja LiveRamp-käyttöönotosta](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="d6ed2-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="d6ed2-110">Määritä yhteys LiveRampiin</span><span class="sxs-lookup"><span data-stu-id="d6ed2-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="d6ed2-111">Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d6ed2-112">Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **LiveRamp**.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="d6ed2-113">Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d6ed2-114">Yhteyden nimi ja tyyppi kuvaavat yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d6ed2-115">On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d6ed2-116">Valitse, kuka voi käyttää tätä yhteyttä.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-116">Choose who can use this connection.</span></span> <span data-ttu-id="d6ed2-117">Jos et tee mitään, oletusarvo on Järjestelmänvalvojat.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d6ed2-118">Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d6ed2-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d6ed2-119">Anna LiveRamp Secure FTP (SFTP) -tilillesi **Käyttäjänimi** ja **Salasana**.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="d6ed2-120">Nämä tunnistetiedot voivat erota LiveRamp-käyttöönoton tunnistetiedoista.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="d6ed2-121">Testaa yhteys LiveRampiin valitsemalla **Tarkista**.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="d6ed2-122">Kun yhteys on tarkistettu, hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="d6ed2-123">Viimeistele yhteys valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d6ed2-124">Viennin määrittäminen</span><span class="sxs-lookup"><span data-stu-id="d6ed2-124">Configure an export</span></span>

<span data-ttu-id="d6ed2-125">Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d6ed2-126">Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d6ed2-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d6ed2-127">Siirry kohtaan **Tiedot** > **Viennit**.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d6ed2-128">Luo uusi vienti valitsemalla **Lisää kohde**.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d6ed2-129">Valitse **Yhteys vientiä varten** -kentässä yhteys LiveRamp-osasta.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="d6ed2-130">Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d6ed2-131">Valitse **Valitse avaintunniste** -kentässä **Sähköposti**, **Nimi ja osoite** tai **Puhelin** lähetettäväksi LiveRampille käyttäjätietojen ratkaisemiseksi.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d6ed2-132">![LiveRamp-yhdistin ja määritteiden yhdistämismääritys](media/export-liveramp-segments.png "LiveRamp-yhdistin ja määritteiden yhdistämismääritys")</span><span class="sxs-lookup"><span data-stu-id="d6ed2-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="d6ed2-133">Yhdistä yhdistetyn asiakasentiteetin vastaavat määritteet valittua avaintunnistetta varten.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="d6ed2-134">Valitse **Lisää määrite**, jos haluat yhdistää lisää määritteitä lähetettäväksi LiveRampiin.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="d6ed2-135">Useiden avaintunnistemääritteiden lähettäminen LiveRampille tuottaa todennäköisesti suuremman vastaavuuden.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="d6ed2-136">Valitse segmentit, jotka haluat viedä LiveRampiin.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="d6ed2-137">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-137">Select **Save**.</span></span>

<span data-ttu-id="d6ed2-138">Viennin tallentaminen ei suorita vientiä heti.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d6ed2-139">Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d6ed2-140">Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d6ed2-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d6ed2-141">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="d6ed2-141">Data privacy and compliance</span></span>

<span data-ttu-id="d6ed2-142">Kun tietojen lähetys Liverampiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d6ed2-143">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Liveramp noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d6ed2-144">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d6ed2-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d6ed2-145">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="d6ed2-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
