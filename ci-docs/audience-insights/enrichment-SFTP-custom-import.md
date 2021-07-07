---
title: Rikastaminen mukautetun SFTP-tuonnin avulla
description: Yleisiä tietoja mukautetusta SFTP-tuonnin rikastamisesta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304646"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="5a298-103">Asiakasprofiilien rikastaminen mukautetuilla tiedoilla (esiversio)</span><span class="sxs-lookup"><span data-stu-id="5a298-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="5a298-104">Mukautetun SFTP (Secure File Transfer Protocol) -tuonnin avulla voidaan tuoda tietoja, joille ei tarvitse tehdä tietojen yhtenäistämisprosessia.</span><span class="sxs-lookup"><span data-stu-id="5a298-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="5a298-105">Se on joustava, turvallinen ja helppo tapa tuoda tietoja.</span><span class="sxs-lookup"><span data-stu-id="5a298-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="5a298-106">Mukautettua SFTP-tuontia voidaan käyttää yhdessä [SFTP-viennin](export-sftp.md) kanssa. Kyseisellä toiminnolla voi viedä rikastamiseen tarvittavia asiakasprofiilitietoja.</span><span class="sxs-lookup"><span data-stu-id="5a298-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="5a298-107">Tiedot voidaan tämän jälkeen käsitellä ja rikastaa. Rikastetut tiedot voidaan tuoda takaisin Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuuteen mukautetun SFTP-tuonnin avulla.</span><span class="sxs-lookup"><span data-stu-id="5a298-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5a298-108">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="5a298-108">Prerequisites</span></span>

<span data-ttu-id="5a298-109">Mukautetun SFTP-tuonnin määritykselle on seuraavat edellytykset:</span><span class="sxs-lookup"><span data-stu-id="5a298-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="5a298-110">Tiedossa on SFTP-isäntään tuotavan tiedoston nimi ja sijainti (polku).</span><span class="sxs-lookup"><span data-stu-id="5a298-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="5a298-111">*model.json*-tiedosto määrittää tuotavien tietojen [Common Data Model -rakenteen](/common-data-model/).</span><span class="sxs-lookup"><span data-stu-id="5a298-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="5a298-112">Tiedoston on oltava samassa kansiossa kuin tuotava tiedosto.</span><span class="sxs-lookup"><span data-stu-id="5a298-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="5a298-113">Järjestelmänvalvoja on jo määrittänyt SFTP-yhteyden *tai* sinulla on [järjestelmänvalvojan](permissions.md#administrator) käyttöoikeudet.</span><span class="sxs-lookup"><span data-stu-id="5a298-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="5a298-114">Tarvitset sen SFTP-sijainnin käyttäjän tunnistetiedot, URL-osoitteen ja portin numeron, josta haluat tuoda tietoja.</span><span class="sxs-lookup"><span data-stu-id="5a298-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="5a298-115">Määritä tuonti</span><span class="sxs-lookup"><span data-stu-id="5a298-115">Configure the import</span></span>

1. <span data-ttu-id="5a298-116">Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.</span><span class="sxs-lookup"><span data-stu-id="5a298-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="5a298-117">Valitse **Mukautettu SFTP-tuonti** -ruudussa **Rikasta tietojani** ja valitse **Aloita**.</span><span class="sxs-lookup"><span data-stu-id="5a298-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Mukautettu SFTP-tuonti -ruutu.":::

1. <span data-ttu-id="5a298-119">Valitse [yhteys](connections.md) avattavasta luettelosta.</span><span class="sxs-lookup"><span data-stu-id="5a298-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="5a298-120">Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.</span><span class="sxs-lookup"><span data-stu-id="5a298-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="5a298-121">Jos olet järjestelmänvalvoja, voit luoda yhteyden valitsemalla **Lisää yhteys** -kohdan ja valitsemalla sitten avattavasta luettelosta **Mukautettu SFTP-tuonti** -kohdan.</span><span class="sxs-lookup"><span data-stu-id="5a298-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="5a298-122">Vahvista valittu yhteys valitsemalla **Yhdistä mukautettuun tuontiin**.</span><span class="sxs-lookup"><span data-stu-id="5a298-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="5a298-123">Valitse **Seuraava** ja syötä tuotavan datatiedoston **polku** ja **tiedostonimi**.</span><span class="sxs-lookup"><span data-stu-id="5a298-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Näyttökuva tietojen sijainnin syöttämisestä.":::

1. <span data-ttu-id="5a298-125">Valitse **Seuraava** ja anna rikastuksen ja tulosentiteetin nimi.</span><span class="sxs-lookup"><span data-stu-id="5a298-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="5a298-126">Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.</span><span class="sxs-lookup"><span data-stu-id="5a298-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="5a298-127">Yhteyden määrittäminen mukautettua SFTP-tuontia varten</span><span class="sxs-lookup"><span data-stu-id="5a298-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="5a298-128">Yhteyksien määrittämiseen tarvitaan järjestelmänvalvojan oikeudet.</span><span class="sxs-lookup"><span data-stu-id="5a298-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="5a298-129">Valitse rikastusta määritettäessä **Lisää yhteys** *tai* siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja valitse Mukautettu tuonti -ruudussa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="5a298-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="5a298-130">Kirjoita yhteyden nimi **Näyttönimi**-ruutuun.</span><span class="sxs-lookup"><span data-stu-id="5a298-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="5a298-131">Anna sen SFTP-palvelimen sallittu käyttäjänimi, salasana ja isännän URL-osoite, jossa tuotavat tiedot ovat.</span><span class="sxs-lookup"><span data-stu-id="5a298-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="5a298-132">Tarkista tiedot ja hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu.</span><span class="sxs-lookup"><span data-stu-id="5a298-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="5a298-133">Tarkista määritys valitsemalla **Tarkista**.</span><span class="sxs-lookup"><span data-stu-id="5a298-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="5a298-134">Kun tarkistus on tehty, yhteys tallennetaan valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="5a298-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5a298-135">![Experian-yhteyden määrityssivu](media/enrichment-SFTP-connection.png "Experian-yhteyden määrityssivu")</span><span class="sxs-lookup"><span data-stu-id="5a298-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="5a298-136">Kenttien yhdistämismääritysten määrittäminen</span><span class="sxs-lookup"><span data-stu-id="5a298-136">Defining field mappings</span></span> 

<span data-ttu-id="5a298-137">SFTP-palvelimeen tuotavan tiedoston sisältävässä hakemistossa on oltava myös *model.json*-tiedosto.</span><span class="sxs-lookup"><span data-stu-id="5a298-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="5a298-138">Tämä tiedosto määrittää rakenteen, jota käytetään tietojen tuontiin.</span><span class="sxs-lookup"><span data-stu-id="5a298-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="5a298-139">Rakenteessa on oltava käytössä [Common Data Model](/common-data-model/), jotta voidaan määrittää kentän vastaavuusmääritys.</span><span class="sxs-lookup"><span data-stu-id="5a298-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="5a298-140">Yksinkertainen esimerkki model.json-tiedostosta:</span><span class="sxs-lookup"><span data-stu-id="5a298-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="5a298-141">Rikastamisen tulokset</span><span class="sxs-lookup"><span data-stu-id="5a298-141">Enrichment results</span></span>

<span data-ttu-id="5a298-142">Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="5a298-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="5a298-143">Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana.</span><span class="sxs-lookup"><span data-stu-id="5a298-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5a298-144">Käsittelyaika määräytyy tuotavien tietojen koon ja SFTP-palvelimen yhteyden mukaan.</span><span class="sxs-lookup"><span data-stu-id="5a298-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="5a298-145">Kun rikastamisprosessi valmistuu, voit tarkistaa juuri tuodut mukautetut rikastamistiedot **Omat rikastukset** -kohdassa.</span><span class="sxs-lookup"><span data-stu-id="5a298-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="5a298-146">Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.</span><span class="sxs-lookup"><span data-stu-id="5a298-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="5a298-147">Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.</span><span class="sxs-lookup"><span data-stu-id="5a298-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5a298-148">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="5a298-148">Next steps</span></span>

<span data-ttu-id="5a298-149">Voit hyödyntää rikastettuja asiakastietoja.</span><span class="sxs-lookup"><span data-stu-id="5a298-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="5a298-150">Voit luoda [segmenttejä](segments.md) ja [mittareita](measures.md) ja [viedä tietoja](export-destinations.md), jos haluat tarjota asiakkaille mukautettuja käyttökokemuksia.</span><span class="sxs-lookup"><span data-stu-id="5a298-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
