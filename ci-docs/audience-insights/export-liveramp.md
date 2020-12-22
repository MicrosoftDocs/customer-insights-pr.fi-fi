---
title: LiveRamp-yhdistin
description: Tietoja tietojen viennistä LiveRampiin.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667180"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="483a5-103">LiveRamp&reg; yhdistin (esikatselu)</span><span class="sxs-lookup"><span data-stu-id="483a5-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="483a5-104">Aktivoi tietosi LiveRampissa muodostaaksesi yhteyden yli 500 ympäristöön digitaalisissa, yhteisöllisissä ja television ekosysteemeissä.</span><span class="sxs-lookup"><span data-stu-id="483a5-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="483a5-105">Työstä tietojasi LiveRampissa kohdistaaksesi, estääksesi ja yksilöllistääksesi mainoskampanjoita.</span><span class="sxs-lookup"><span data-stu-id="483a5-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="483a5-106">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="483a5-106">Prerequisites</span></span>

- <span data-ttu-id="483a5-107">Tämän yhdistimen käyttö edellyttää LiveRamp-tilausta.</span><span class="sxs-lookup"><span data-stu-id="483a5-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="483a5-108">Hanki tilaus [ottamalla suoraan yhteyttä LiveRampiin](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="483a5-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="483a5-109">[Lisätietoja LiveRamp-käyttöönotosta](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="483a5-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="483a5-110">LiveRampiin yhdistäminen</span><span class="sxs-lookup"><span data-stu-id="483a5-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="483a5-111">Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.</span><span class="sxs-lookup"><span data-stu-id="483a5-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="483a5-112">Valitse **LiveRamp**-ruudussa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="483a5-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="483a5-113">Anna kohteelle tunnistettava nimi **Näyttönimi**-kentässä.</span><span class="sxs-lookup"><span data-stu-id="483a5-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="483a5-114">Anna LiveRamp Secure FTP (SFTP) -tilillesi **Käyttäjänimi** ja **Salasana**.</span><span class="sxs-lookup"><span data-stu-id="483a5-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="483a5-115">Nämä tunnistetiedot voivat erota LiveRamp-käyttöönoton tunnistetiedoista.</span><span class="sxs-lookup"><span data-stu-id="483a5-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="483a5-116">Testaa yhteys LiveRampiin valitsemalla **Tarkista**.</span><span class="sxs-lookup"><span data-stu-id="483a5-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="483a5-117">Kun yhteys on tarkistettu, hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu.</span><span class="sxs-lookup"><span data-stu-id="483a5-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="483a5-118">Määritä LiveRamp-yhdistin valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="483a5-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="483a5-119">Yhdistimen määrittäminen</span><span class="sxs-lookup"><span data-stu-id="483a5-119">Configure the connector</span></span>

1. <span data-ttu-id="483a5-120">Valitse **Valitse avaintunniste** -kentässä **Sähköposti**, **Nimi ja osoite** tai **Puhelin** lähetettäväksi LiveRampille käyttäjätietojen ratkaisemiseksi.</span><span class="sxs-lookup"><span data-stu-id="483a5-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="483a5-121">Yhdistä yhdistetyn asiakasentiteetin vastaavat määritteet valittua avaintunnistetta varten.</span><span class="sxs-lookup"><span data-stu-id="483a5-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="483a5-122">Valitse **Lisää määrite**, jos haluat yhdistää lisää määritteitä LiveRampille lähetettäväksi.</span><span class="sxs-lookup"><span data-stu-id="483a5-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="483a5-123">Useiden avaintunnistemääritteiden lähettäminen LiveRampille tuottaa todennäköisesti suuremman vastaavuuden.</span><span class="sxs-lookup"><span data-stu-id="483a5-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="483a5-124">Valitse segmentit, jotka haluat viedä LiveRampiin.</span><span class="sxs-lookup"><span data-stu-id="483a5-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="483a5-125">Valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="483a5-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="483a5-126">![LiveRamp-yhdistin ja määritteiden yhdistämismääritys](media/export-liveramp-segments.png "LiveRamp-yhdistin ja määritteiden yhdistämismääritys")</span><span class="sxs-lookup"><span data-stu-id="483a5-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="483a5-127">Tietojen vieminen</span><span class="sxs-lookup"><span data-stu-id="483a5-127">Export the data</span></span>

<span data-ttu-id="483a5-128">Vienti käynnistyy pian, jos kaikki viennin edellytykset täyttyvät.</span><span class="sxs-lookup"><span data-stu-id="483a5-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="483a5-129">Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="483a5-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="483a5-130">Kun vienti on suoritettu onnistuneesti, voit kirjautua LiveRampin käyttöönottoon tietojesi aktivointia ja jakelu varten.</span><span class="sxs-lookup"><span data-stu-id="483a5-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="483a5-131">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="483a5-131">Data privacy and compliance</span></span>

<span data-ttu-id="483a5-132">Kun tietojen lähetys Liverampiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="483a5-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="483a5-133">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Liveramp noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="483a5-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="483a5-134">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="483a5-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="483a5-135">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.</span><span class="sxs-lookup"><span data-stu-id="483a5-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>