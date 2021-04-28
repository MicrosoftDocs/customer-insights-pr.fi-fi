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
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896277"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="d9869-103">Asiakasprofiilien rikastaminen mukautetuilla tiedoilla (esiversio)</span><span class="sxs-lookup"><span data-stu-id="d9869-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="d9869-104">Mukautetun Secure File Transfer Protocol (SFTP) -tuonnin avulla voit tuoda tietoja, joita ei tarvitse käyttää tietojen yhdistämisprosessissa.</span><span class="sxs-lookup"><span data-stu-id="d9869-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="d9869-105">Se on joustava, turvallinen ja helppo tapa tuoda tietoja.</span><span class="sxs-lookup"><span data-stu-id="d9869-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="d9869-106">Mukautettua SFTP-tuontia voidaan käyttää yhdessä [SFTP-viennin](export-sftp.md) kanssa. Kyseisellä toiminnolla voi viedä rikastamiseen tarvittavia asiakasprofiilitietoja.</span><span class="sxs-lookup"><span data-stu-id="d9869-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="d9869-107">Tiedot voidaan sitten käsitellä ja rikastaa ja mukautettua SFTP-tuontia voidaan käyttää tuomaan rikastetut tiedot takaisin Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuudella.</span><span class="sxs-lookup"><span data-stu-id="d9869-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d9869-108">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="d9869-108">Prerequisites</span></span>

<span data-ttu-id="d9869-109">Mukautetun SFTP-tuonnin määritykselle on seuraavat edellytykset:</span><span class="sxs-lookup"><span data-stu-id="d9869-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d9869-110">Sinulla on tuotavan tiedoston tiedostonimi ja sijainti (polku) SFTP-palvelimella.</span><span class="sxs-lookup"><span data-stu-id="d9869-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="d9869-111">*model.json*-tiedosto määrittää tuotavien tietojen [Common Data Model -rakenteen](/common-data-model/).</span><span class="sxs-lookup"><span data-stu-id="d9869-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="d9869-112">Tiedoston on oltava samassa kansiossa kuin tuotava tiedosto.</span><span class="sxs-lookup"><span data-stu-id="d9869-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="d9869-113">Järjestelmänvalvoja on jo määrittänyt SFTP-yhteyden *tai* sinulla on [järjestelmänvalvojan](permissions.md#administrator) käyttöoikeudet.</span><span class="sxs-lookup"><span data-stu-id="d9869-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="d9869-114">Tarvitset sen SFTP-sijainnin käyttäjän tunnistetiedot, URL-osoitteen ja portin numeron, josta haluat tuoda tietoja.</span><span class="sxs-lookup"><span data-stu-id="d9869-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="d9869-115">Määritä tuonti</span><span class="sxs-lookup"><span data-stu-id="d9869-115">Configure the import</span></span>

1. <span data-ttu-id="d9869-116">Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.</span><span class="sxs-lookup"><span data-stu-id="d9869-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="d9869-117">Valitse **Mukautettu SFTP-tuonti** -ruudussa **Rikasta tietojani** ja valitse **Aloita**.</span><span class="sxs-lookup"><span data-stu-id="d9869-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Mukautettu SFTP-tuonti -ruutu.":::

1. <span data-ttu-id="d9869-119">Valitse [yhteys](connections.md) avattavasta luettelosta.</span><span class="sxs-lookup"><span data-stu-id="d9869-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="d9869-120">Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.</span><span class="sxs-lookup"><span data-stu-id="d9869-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="d9869-121">Jos olet järjestelmänvalvoja, voit luoda yhteyden valitsemalla **Lisää yhteys** ja valitsemalla avattavasta valikosta **Mukautettu SFTP-tuonti**.</span><span class="sxs-lookup"><span data-stu-id="d9869-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="d9869-122">Vahvista valittu yhteys valitsemalla **Yhdistä mukautettuun tuontiin**.</span><span class="sxs-lookup"><span data-stu-id="d9869-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="d9869-123">Valitse **Seuraava** ja kirjoita tuodun datatiedoston **Tiedostonimi** ja **Polku**.</span><span class="sxs-lookup"><span data-stu-id="d9869-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Näyttökuva tietojen sijainnin syöttämisestä.":::

1. <span data-ttu-id="d9869-125">Valitse **Seuraava** ja anna rikastuksen ja tulosentiteetin nimi.</span><span class="sxs-lookup"><span data-stu-id="d9869-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="d9869-126">Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.</span><span class="sxs-lookup"><span data-stu-id="d9869-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="d9869-127">Yhteyden määrittäminen mukautettua SFTP-tuontia varten</span><span class="sxs-lookup"><span data-stu-id="d9869-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="d9869-128">Yhteyksien määrittämiseen tarvitaan järjestelmänvalvojan oikeudet.</span><span class="sxs-lookup"><span data-stu-id="d9869-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="d9869-129">Valitse rikastusta määritettäessä **Lisää yhteys** *tai* siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja valitse Mukautettu tuonti -ruudussa **Määritä**.</span><span class="sxs-lookup"><span data-stu-id="d9869-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="d9869-130">Kirjoita yhteyden nimi **Näyttönimi**-ruutuun.</span><span class="sxs-lookup"><span data-stu-id="d9869-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="d9869-131">Anna tuotavien tietojen SFTP-palvelimen kelvollinen käyttäjänimi, salasana ja URL-osoite.</span><span class="sxs-lookup"><span data-stu-id="d9869-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="d9869-132">Tarkista tiedot ja hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu.</span><span class="sxs-lookup"><span data-stu-id="d9869-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="d9869-133">Tarkista määritys valitsemalla **Tarkista**.</span><span class="sxs-lookup"><span data-stu-id="d9869-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="d9869-134">Kun tarkistus on valmis, yhteys voidaan tallentaa valitsemalla **Tallenna**.</span><span class="sxs-lookup"><span data-stu-id="d9869-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="d9869-135">![Experian-yhteyden määrityssivu](media/enrichment-SFTP-connection.png "Experian-yhteyden määrityssivu")</span><span class="sxs-lookup"><span data-stu-id="d9869-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="d9869-136">Kenttien yhdistämismääritysten määrittäminen</span><span class="sxs-lookup"><span data-stu-id="d9869-136">Defining field mappings</span></span> 

<span data-ttu-id="d9869-137">SFTP-palvelimeen tuotavan tiedoston sisältävässä hakemistossa on oltava myös *model.json*-tiedosto.</span><span class="sxs-lookup"><span data-stu-id="d9869-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="d9869-138">Tämä tiedosto määrittää rakenteen, jota käytetään tietojen tuontiin.</span><span class="sxs-lookup"><span data-stu-id="d9869-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="d9869-139">Rakenteen on käytettävä [Common Data Modelia](/common-data-model/) kentän yhdistämismäärityksen määrittämiseen.</span><span class="sxs-lookup"><span data-stu-id="d9869-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="d9869-140">Yksinkertainen esimerkki model.json-tiedostosta:</span><span class="sxs-lookup"><span data-stu-id="d9869-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="d9869-141">Rikastamisen tulokset</span><span class="sxs-lookup"><span data-stu-id="d9869-141">Enrichment results</span></span>

<span data-ttu-id="d9869-142">Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="d9869-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="d9869-143">Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana.</span><span class="sxs-lookup"><span data-stu-id="d9869-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d9869-144">Käsittelyaika määräytyy tuotavien tietojen koon ja SFTP-palvelimen yhteyden mukaan.</span><span class="sxs-lookup"><span data-stu-id="d9869-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="d9869-145">Kun rikastamisprosessi valmistuu, voit tarkistaa juuri tuodut mukautetut rikastamistiedot **Omat rikastukset** -kohdassa.</span><span class="sxs-lookup"><span data-stu-id="d9869-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="d9869-146">Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.</span><span class="sxs-lookup"><span data-stu-id="d9869-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="d9869-147">Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.</span><span class="sxs-lookup"><span data-stu-id="d9869-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d9869-148">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="d9869-148">Next steps</span></span>

<span data-ttu-id="d9869-149">Voit hyödyntää rikastettuja asiakastietoja.</span><span class="sxs-lookup"><span data-stu-id="d9869-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d9869-150">Voit tuottaa mukautettuja kokemuksia asiakkaille luomalla [segmenttejä](segments.md) ja [mittareita](measures.md) sekä [viedä tietoja](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d9869-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
