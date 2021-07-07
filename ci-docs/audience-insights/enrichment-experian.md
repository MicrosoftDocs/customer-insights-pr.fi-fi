---
title: Rikastaminen kolmannen osapuolen Experian-rikastamisen avulla
description: Yleisiä tietoja kolmannen osapuolen Experian-rikastamisesta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309816"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="b8b76-103">Rikasta asiakasprofiileja Experian-ratkaisun demografisten tietojen avulla (esiversio)</span><span class="sxs-lookup"><span data-stu-id="b8b76-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="b8b76-104">Experian on maailmanlaajuinen johtaja asiakas- ja yritysluottojen raportointi- ja markkinointipalveluiden tarjoamisessa.</span><span class="sxs-lookup"><span data-stu-id="b8b76-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="b8b76-105">Experian-ratkaisun tietojen rikastamisen palvelujen avulla voit parantaa tietämystä asiakkaista rikastamalla asiakasprofiileja käyttämällä demografisia tietoja, kuten talouden kokoa ja tuloja.</span><span class="sxs-lookup"><span data-stu-id="b8b76-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b8b76-106">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="b8b76-106">Prerequisites</span></span>

<span data-ttu-id="b8b76-107">Jotta voit määrittää Experian-ratkaisun, seuraavien edellytysten on täytyttävä:</span><span class="sxs-lookup"><span data-stu-id="b8b76-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b8b76-108">Tarvitset aktiivisen Experian-tilauksen.</span><span class="sxs-lookup"><span data-stu-id="b8b76-108">You have an active Experian subscription.</span></span> <span data-ttu-id="b8b76-109">Jos haluat tehdä tilauksen, [ota yhteyttä suoraan Experian-ratkaisuun](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="b8b76-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="b8b76-110">[Lisätietoja Experian-ratkaisun tietojen rikastamisesta](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="b8b76-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="b8b76-111">Järjestelmänvalvoja on jo määrittänyt Experian-yhteyden *tai* sinulla on [järjestelmänvalvojan](permissions.md#administrator) oikeudet.</span><span class="sxs-lookup"><span data-stu-id="b8b76-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="b8b76-112">Experian-ratkaisun luomaa SSH:ta käyttävää Secure Transport (ST) -tiliä varten tarvitaan käyttäjätunnus, osapuolen tunnus ja mallinumero.</span><span class="sxs-lookup"><span data-stu-id="b8b76-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="b8b76-113">Tuetut maat ja alueet</span><span class="sxs-lookup"><span data-stu-id="b8b76-113">Supported countries/regions</span></span>

<span data-ttu-id="b8b76-114">Tällä hetkellä tuemme asiakasprofiilien rikastamista vain Yhdysvalloissa.</span><span class="sxs-lookup"><span data-stu-id="b8b76-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="b8b76-115">Määritä rikastus</span><span class="sxs-lookup"><span data-stu-id="b8b76-115">Configure the enrichment</span></span>

1. <span data-ttu-id="b8b76-116">Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.</span><span class="sxs-lookup"><span data-stu-id="b8b76-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="b8b76-117">Valitse **Rikasta omat tiedot** Experian-ruudussa.</span><span class="sxs-lookup"><span data-stu-id="b8b76-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b8b76-118">![Experian muokkausta](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="b8b76-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="b8b76-119">Valitse [yhteys](connections.md) avattavasta luettelosta.</span><span class="sxs-lookup"><span data-stu-id="b8b76-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="b8b76-120">Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.</span><span class="sxs-lookup"><span data-stu-id="b8b76-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="b8b76-121">Jos olet järjestelmänvalvoja, voit luoda yhteyden valitsemalla **Lisää yhteys** ja valitsemalla sitten avattavasta luettelosta Experian-kohdan.</span><span class="sxs-lookup"><span data-stu-id="b8b76-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="b8b76-122">Valitse **Muodosta yhteys Experianiin**, jos haluat vahvistaa yhteyden valinnan.</span><span class="sxs-lookup"><span data-stu-id="b8b76-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="b8b76-123">Valitse **Seuraava** ja valitse sitten **Asiakkaan tietojoukko**, jos haluat rikastaa Experianin demografisia tietoja.</span><span class="sxs-lookup"><span data-stu-id="b8b76-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="b8b76-124">Voit valita **asiakasentiteetin**, joka rikastaa kaikkia asiakasprofiileja, tai segmenttientiteetin, joka rikastaa vain segmenttiin sisältyviä asiakasprofiileja.</span><span class="sxs-lookup"><span data-stu-id="b8b76-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Näyttökuva asiakastietojoukon valitsemisesta.":::

1. <span data-ttu-id="b8b76-126">Valitse **Seuraava** ja määritä, mitkä kenttätyyppejä yhdistetyistä profiileista käytetään etsittäessä vastaavia demografisia tietoja Experianista.</span><span class="sxs-lookup"><span data-stu-id="b8b76-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="b8b76-127">Vähintään yksi kenttä seuraavista vaaditaan: **Nimi ja osoite**, **Puhelin** tai **Sähköposti**.</span><span class="sxs-lookup"><span data-stu-id="b8b76-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="b8b76-128">Jotta vastineen tarkkuus olisi suurempi, voit lisätä enintään kaksi muuta kenttää.</span><span class="sxs-lookup"><span data-stu-id="b8b76-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="b8b76-129">Valinta vaikuttaa seuraavassa vaiheessa käytettävissä oleviin yhdistämiskenttiin.</span><span class="sxs-lookup"><span data-stu-id="b8b76-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="b8b76-130">Lisää Experianiin lähetetyt avaimen tunnisteen määritteet, jotka todennäköisesti tuottavat parhaan tuloksen.</span><span class="sxs-lookup"><span data-stu-id="b8b76-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="b8b76-131">Aloita kentän vastaavuusmääritys valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="b8b76-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="b8b76-132">Määritä, mitkä kenttätyyppejä yhdistetyistä profiileista käytetään etsittäessä vastaavia demografisia tietoja Experianista.</span><span class="sxs-lookup"><span data-stu-id="b8b76-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="b8b76-133">Pakolliset kentät on merkitty.</span><span class="sxs-lookup"><span data-stu-id="b8b76-133">Required fields are marked.</span></span>

1. <span data-ttu-id="b8b76-134">Anna rikastuksen ja tulosentiteetin nimi.</span><span class="sxs-lookup"><span data-stu-id="b8b76-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="b8b76-135">Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.</span><span class="sxs-lookup"><span data-stu-id="b8b76-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="b8b76-136">Yhteyden määrittäminen Experianiin</span><span class="sxs-lookup"><span data-stu-id="b8b76-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="b8b76-137">Yhteyksien määrittämiseen tarvitaan järjestelmänvalvojan oikeudet.</span><span class="sxs-lookup"><span data-stu-id="b8b76-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="b8b76-138">Valitse **Lisää yhteys**, kun rikastamista määritetään, *tai* siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja valitse **Määritä** Experian-ruudussa.</span><span class="sxs-lookup"><span data-stu-id="b8b76-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="b8b76-139">Valitse **Aloita**.</span><span class="sxs-lookup"><span data-stu-id="b8b76-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="b8b76-140">Kirjoita yhteyden nimi **Näyttönimi**-ruutuun.</span><span class="sxs-lookup"><span data-stu-id="b8b76-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="b8b76-141">Anna sallittu käyttäjätunnus, osapuolen tunnus ja mallinumero Experianin Secure Transport -tiliä varten.</span><span class="sxs-lookup"><span data-stu-id="b8b76-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="b8b76-142">Tarkista **Tietojen yksityisyys ja vaatimustenmukaisuus** -kohta ja hyväksy se valitsemalla **Hyväksyn**.</span><span class="sxs-lookup"><span data-stu-id="b8b76-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="b8b76-143">Tarkista määritys valitsemalla **Tarkista**.</span><span class="sxs-lookup"><span data-stu-id="b8b76-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="b8b76-144">Kun tarkistus on suoritettu, valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="b8b76-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian-yhteyden määritysruutu.":::

## <a name="enrichment-results"></a><span data-ttu-id="b8b76-146">Rikastamisen tulokset</span><span class="sxs-lookup"><span data-stu-id="b8b76-146">Enrichment results</span></span>

<span data-ttu-id="b8b76-147">Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="b8b76-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="b8b76-148">Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana.</span><span class="sxs-lookup"><span data-stu-id="b8b76-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b8b76-149">Käsittelyaika riippuu asiakastietojen koosta ja Experianin tilille määrittämistä rikastusprosesseista.</span><span class="sxs-lookup"><span data-stu-id="b8b76-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="b8b76-150">Kun rikastamisprosessi on valmis, voit tarkastella juuri rikastettujen asiakasprofiilien tietoja valitsemalla **Omat rikastukset**.</span><span class="sxs-lookup"><span data-stu-id="b8b76-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="b8b76-151">Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.</span><span class="sxs-lookup"><span data-stu-id="b8b76-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="b8b76-152">Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.</span><span class="sxs-lookup"><span data-stu-id="b8b76-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b8b76-153">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="b8b76-153">Next steps</span></span>

<span data-ttu-id="b8b76-154">Voit hyödyntää rikastettuja asiakastietoja.</span><span class="sxs-lookup"><span data-stu-id="b8b76-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b8b76-155">Voit luoda [segmenttejä](segments.md) ja [mittareita](measures.md) ja jopa [viedä tietoja](export-destinations.md), jos haluat tarjota asiakkaille mukautettuja käyttökokemuksia.</span><span class="sxs-lookup"><span data-stu-id="b8b76-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b8b76-156">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="b8b76-156">Data privacy and compliance</span></span>

<span data-ttu-id="b8b76-157">Kun otat käyttöön Dynamics 365 Customer Insightsin tietojen siirtämiseksi Experianiin, sallit tietojen siirtämisen säännöstenmukaisuuden rajan ulkopuolelle Dynamics 365 Customer Insightsissa, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilökohtaiset tiedot.</span><span class="sxs-lookup"><span data-stu-id="b8b76-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b8b76-158">Microsoft siirtää nämä tiedot pyyntösi mukaisesti, mutta olet vastuussa siitä, että Experian täyttää kaikki liiketoimintaasi koskevat tietosuoja- tai tietoturvavelvoitteet.</span><span class="sxs-lookup"><span data-stu-id="b8b76-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b8b76-159">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b8b76-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b8b76-160">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.</span><span class="sxs-lookup"><span data-stu-id="b8b76-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
