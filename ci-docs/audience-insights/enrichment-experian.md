---
title: Rikastaminen kolmannen osapuolen Experian-rikastamisella
description: Yleisiä tietoja kolmannen osapuolen Experian-rikastamisesta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896369"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="8790b-103">Asiakasprofiilien rikastaminen Experianin demografiatiedoilla (esiversio)</span><span class="sxs-lookup"><span data-stu-id="8790b-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="8790b-104">Experian on maailman johtava kuluttaja- ja yritysluottojen raportointi- ja markkinointipalvelujen toimittaja.</span><span class="sxs-lookup"><span data-stu-id="8790b-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="8790b-105">Experianin tietojen rikastamispalveluilla voidaan syventää tietoja asiakkaista rikastamalla asiakasprofiileja demografiatiedoilla, kuten sillä, minkä kokoinen talous on kyseessä ja minkälaiset tulot sillä on käytettävissä.</span><span class="sxs-lookup"><span data-stu-id="8790b-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8790b-106">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="8790b-106">Prerequisites</span></span>

<span data-ttu-id="8790b-107">Experianin määrittäminen edellyttää seuraavien edellytysten toteutumista:</span><span class="sxs-lookup"><span data-stu-id="8790b-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="8790b-108">Aktiivinen Experian-tilaus.</span><span class="sxs-lookup"><span data-stu-id="8790b-108">You have an active Experian subscription.</span></span> <span data-ttu-id="8790b-109">Tilaus tehdään suoraan [Experianilta](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="8790b-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="8790b-110">[Lisätietoja Experianin tietojen rikastamisesta](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="8790b-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="8790b-111">Järjestelmänvalvoja on jo määrittänyt Experian-yhteyden *tai* sinulla on [järjestelmänvalvojan](permissions.md#administrator) käyttöoikeudet.</span><span class="sxs-lookup"><span data-stu-id="8790b-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="8790b-112">Tarvitset myös käyttäjätunnuksen, osapuolen tunnuksen ja mallinumeron sinulle luomallesi SSH-yhteensopivalle Secure Transport (ST) -tilille, jonka Experian loi.</span><span class="sxs-lookup"><span data-stu-id="8790b-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="8790b-113">Määritä rikastus</span><span class="sxs-lookup"><span data-stu-id="8790b-113">Configure the enrichment</span></span>

1. <span data-ttu-id="8790b-114">Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.</span><span class="sxs-lookup"><span data-stu-id="8790b-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="8790b-115">Valitse Experian-ruudussa **Rikasta tietojani**.</span><span class="sxs-lookup"><span data-stu-id="8790b-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8790b-116">![Experian-ruutu](media/experian-tile.png "Experian-ruutu")</span><span class="sxs-lookup"><span data-stu-id="8790b-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="8790b-117">Valitse [yhteys](connections.md) avattavasta luettelosta.</span><span class="sxs-lookup"><span data-stu-id="8790b-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="8790b-118">Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.</span><span class="sxs-lookup"><span data-stu-id="8790b-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="8790b-119">Jos olet järjestelmänvalvoja, voit luoda yhteyden valitsemalla **Lisää yhteys** ja valitsemalla avattavasta valikosta Experian.</span><span class="sxs-lookup"><span data-stu-id="8790b-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="8790b-120">Vahvista valinta valitsemalla **Yhdistä Experianiin**.</span><span class="sxs-lookup"><span data-stu-id="8790b-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="8790b-121">Valitse **Seuraava** ja valitse **Asiakastietojoukko**, jonka haluat rikastaa Experianin demografiatiedoilla.</span><span class="sxs-lookup"><span data-stu-id="8790b-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="8790b-122">Voit valita **asiakasentiteetin**, joka rikastaa kaikkia asiakasprofiileja, tai segmenttientiteetin, joka rikastaa vain segmenttiin sisältyviä asiakasprofiileja.</span><span class="sxs-lookup"><span data-stu-id="8790b-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Näyttökuva asiakastietojoukon valitsemisesta.":::

1. <span data-ttu-id="8790b-124">Valitse **Seuraava** ja määritä, mitä yhtenäisten profiilien kenttätyyppejä pitäisi käyttää Experianin vastaavien demografiatietojen etsimiseen.</span><span class="sxs-lookup"><span data-stu-id="8790b-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="8790b-125">Vähintään yksi kenttä seuraavista vaaditaan: **Nimi ja osoite**, **Puhelin** tai **Sähköposti**.</span><span class="sxs-lookup"><span data-stu-id="8790b-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="8790b-126">Jotta vastineen tarkkuus olisi suurempi, voit lisätä enintään kaksi muuta kenttää.</span><span class="sxs-lookup"><span data-stu-id="8790b-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="8790b-127">Valinta vaikuttaa seuraavassa vaiheessa käytettävissä oleviin yhdistämiskenttiin.</span><span class="sxs-lookup"><span data-stu-id="8790b-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="8790b-128">Mitä enemmän avaintunnisteiden määritteitä lähetetään Experianiin, sitä korkeampi vastaavuusaste on.</span><span class="sxs-lookup"><span data-stu-id="8790b-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="8790b-129">Aloita kentän vastaavuusmääritys valitsemalla **Seuraava**.</span><span class="sxs-lookup"><span data-stu-id="8790b-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="8790b-130">Määritä, mitä yhtenäisten profiilien kenttiä pitäisi käyttää Experianin vastaavien demografiatietojen etsimiseen.</span><span class="sxs-lookup"><span data-stu-id="8790b-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="8790b-131">Pakolliset kentät on merkitty.</span><span class="sxs-lookup"><span data-stu-id="8790b-131">Required fields are marked.</span></span>

1. <span data-ttu-id="8790b-132">Anna rikastuksen ja tulosentiteetin nimi.</span><span class="sxs-lookup"><span data-stu-id="8790b-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="8790b-133">Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.</span><span class="sxs-lookup"><span data-stu-id="8790b-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="8790b-134">Experian-yhteyden määrittäminen</span><span class="sxs-lookup"><span data-stu-id="8790b-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="8790b-135">Yhteyksien määrittämiseen tarvitaan järjestelmänvalvojan oikeudet.</span><span class="sxs-lookup"><span data-stu-id="8790b-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="8790b-136">Valitse rikastusta määritettäessä **Lisää yhteys** *tai* siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja valitse Experian-ruudussa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="8790b-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="8790b-137">Valitse **Aloita**.</span><span class="sxs-lookup"><span data-stu-id="8790b-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="8790b-138">Kirjoita yhteyden nimi **Näyttönimi**-ruutuun.</span><span class="sxs-lookup"><span data-stu-id="8790b-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="8790b-139">Anna Experianin Secure Transport -tilisi voimassa oleva käyttäjätunnus, osapuolitunnus ja mallinumero.</span><span class="sxs-lookup"><span data-stu-id="8790b-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="8790b-140">Tarkista tiedot ja hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu</span><span class="sxs-lookup"><span data-stu-id="8790b-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="8790b-141">Tarkista määritys valitsemalla **Tarkista**.</span><span class="sxs-lookup"><span data-stu-id="8790b-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="8790b-142">Kun tarkistus on suoritettu, valitse **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="8790b-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian-yhteyden määritysruutu.":::

## <a name="enrichment-results"></a><span data-ttu-id="8790b-144">Rikastamisen tulokset</span><span class="sxs-lookup"><span data-stu-id="8790b-144">Enrichment results</span></span>

<span data-ttu-id="8790b-145">Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="8790b-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="8790b-146">Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana.</span><span class="sxs-lookup"><span data-stu-id="8790b-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8790b-147">Käsittelyaika määräytyy asiakastietojen koon ja Experianin tilille määrittämän rikastamisprosessin perusteella.</span><span class="sxs-lookup"><span data-stu-id="8790b-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="8790b-148">Kun rikastamisprosessi on valmis, voit tarkastella juuri rikastettujen asiakasprofiilien tietoja valitsemalla **Omat rikastukset**.</span><span class="sxs-lookup"><span data-stu-id="8790b-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="8790b-149">Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.</span><span class="sxs-lookup"><span data-stu-id="8790b-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="8790b-150">Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.</span><span class="sxs-lookup"><span data-stu-id="8790b-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8790b-151">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="8790b-151">Next steps</span></span>

<span data-ttu-id="8790b-152">Voit hyödyntää rikastettuja asiakastietoja.</span><span class="sxs-lookup"><span data-stu-id="8790b-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="8790b-153">Voit antaa asiakkaille mukautettuja kokemuksia luomalla [segmenttejä](segments.md) ja [mittoja](measures.md) sekä [viemällä tietoja](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8790b-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8790b-154">Tietojen yksityisyys ja vaatimustenmukaisuus</span><span class="sxs-lookup"><span data-stu-id="8790b-154">Data privacy and compliance</span></span>

<span data-ttu-id="8790b-155">Kun tietojen lähetys Experianiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja.</span><span class="sxs-lookup"><span data-stu-id="8790b-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8790b-156">Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Experian noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita.</span><span class="sxs-lookup"><span data-stu-id="8790b-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8790b-157">Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8790b-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8790b-158">Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.</span><span class="sxs-lookup"><span data-stu-id="8790b-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
