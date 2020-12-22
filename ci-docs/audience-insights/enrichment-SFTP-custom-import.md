---
title: Rikastaminen mukautetun SFTP-tuonnin avulla
description: Yleisiä tietoja mukautetusta SFTP-tuonnin rikastamisesta.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568432"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="3a6a2-103">Asiakasprofiilien rikastaminen mukautetuilla tiedoilla (esiversio)</span><span class="sxs-lookup"><span data-stu-id="3a6a2-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="3a6a2-104">Mukautetun SFTP (Secure File Transfer Protocol) -tuonnin avulla voidaan tuoda tietoja, joille ei tarvitse tehdä tietojen yhtenäistämisprosessia.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="3a6a2-105">Se on joustava, turvallinen ja helppo tapa tuoda tietoja.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="3a6a2-106">Mukautettua SFTP-tuontia voidaan käyttää yhdessä [SFTP-viennin](export-sftp.md) kanssa. Kyseisellä toiminnolla voi viedä rikastamiseen tarvittavia asiakasprofiilitietoja.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="3a6a2-107">Tiedot voidaan sitten käsitellä ja rikastaa ja mukautettua SFTP-tuontia voidaan käyttää tuomaan rikastetut tiedot takaisin Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuudella.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3a6a2-108">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="3a6a2-108">Prerequisites</span></span>

<span data-ttu-id="3a6a2-109">Mukautetun SFTP-tuonnin määritykselle on seuraavat edellytykset:</span><span class="sxs-lookup"><span data-stu-id="3a6a2-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="3a6a2-110">Sen SFTP-sijainnin käyttäjän tunnistetiedot (käyttäjänimi ja salasana), josta tiedot tuodaan.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="3a6a2-111">SFTP-isännän URL-osoite ja portin numero (yleensä 22).</span><span class="sxs-lookup"><span data-stu-id="3a6a2-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="3a6a2-112">SFTP-isäntään tuotavan tiedoston tiedostonimi ja sijainti.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="3a6a2-113">*model.json*-tiedosto, joka määrittää tuotavien tietojen rakenteen.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="3a6a2-114">Tiedoston on oltava samassa kansiossa kuin tuotava tiedosto.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="3a6a2-115">[Järjestelmänvalvojan](permissions.md#administrator) käyttöoikeus.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="3a6a2-116">Määritys</span><span class="sxs-lookup"><span data-stu-id="3a6a2-116">Configuration</span></span>

1. <span data-ttu-id="3a6a2-117">Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="3a6a2-118">Valitse **Mukautettu SFTP-tuontiruudussa** **Rikasta tietojani**.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3a6a2-119">![Mukautetun SFTP-tuontiruutu](media/SFTP_Custom_Import_tile.png "Mukautetun SFTP-tuontiruutu")</span><span class="sxs-lookup"><span data-stu-id="3a6a2-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="3a6a2-120">Valitse **Aloita** sekä anna tunnistetiedot ja SFTP-palvelimen osoite.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="3a6a2-121">Esimerkki: sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="3a6a2-122">Anna sen tiedoston nimi, jossa on tiedot ja polku tiedostoon SFTP-palvelimessa, jos se ei ole pääkansiossa.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="3a6a2-123">Vahvista kaikki syötteet valitsemalla **Yhdistä mukautettuun tuontiin**.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3a6a2-124">![Mukautetun SFTP-tuonnin määrityksen pikaikkuna](media/SFTP_Custom_Import_Configuration_flyout.png "Mukautetun SFTP-tuonnin määrityksen pikaikkuna")</span><span class="sxs-lookup"><span data-stu-id="3a6a2-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="3a6a2-125">Kenttien yhdistämismääritysten määrittäminen</span><span class="sxs-lookup"><span data-stu-id="3a6a2-125">Defining field mappings</span></span> 

<span data-ttu-id="3a6a2-126">SFTP-palvelimeen tuotavan tiedoston sisältävässä hakemistossa on oltava myös *model.json*-tiedosto.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="3a6a2-127">Tämä tiedosto määrittää rakenteen, jota käytetään tietojen tuontiin.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="3a6a2-128">Rakenteen on käytettävä [Common Data Modelia](https://docs.microsoft.com/common-data-model/) kentän yhdistämismäärityksen määrittämiseen.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="3a6a2-129">Yksinkertainen esimerkki model.json-tiedostosta:</span><span class="sxs-lookup"><span data-stu-id="3a6a2-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="3a6a2-130">Rikastamisen tulokset</span><span class="sxs-lookup"><span data-stu-id="3a6a2-130">Enrichment results</span></span>

<span data-ttu-id="3a6a2-131">Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="3a6a2-132">Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3a6a2-133">Käsittelyaika määräytyy tuotavien tietojen koon ja SFTP-palvelimen yhteyden mukaan.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="3a6a2-134">Kun rikastamisprosessi valmistuu, voit tarkistaa juuri tuodut mukautetut rikastamistiedot **Omat rikastukset** -kohdassa.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="3a6a2-135">Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="3a6a2-136">Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3a6a2-137">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="3a6a2-137">Next steps</span></span>

<span data-ttu-id="3a6a2-138">Voit hyödyntää rikastettuja asiakastietoja.</span><span class="sxs-lookup"><span data-stu-id="3a6a2-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3a6a2-139">Voit tuottaa mukautettuja kokemuksia asiakkaille luomalla [segmenttejä](segments.md) ja [mittareita](measures.md) sekä [viedä tietoja](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3a6a2-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


