---
title: Rikastaminen mukautetun SFTP-tuonnin avulla
description: Yleisiä tietoja mukautetusta SFTP-tuonnin rikastamisesta.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595851"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Asiakasprofiilien rikastaminen mukautetuilla tiedoilla (esiversio)

Mukautetun SFTP (Secure File Transfer Protocol) -tuonnin avulla voidaan tuoda tietoja, joille ei tarvitse tehdä tietojen yhtenäistämisprosessia. Se on joustava, turvallinen ja helppo tapa tuoda tietoja. Mukautettua SFTP-tuontia voidaan käyttää yhdessä [SFTP-viennin](export-sftp.md) kanssa. Kyseisellä toiminnolla voi viedä rikastamiseen tarvittavia asiakasprofiilitietoja. Tiedot voidaan sitten käsitellä ja rikastaa ja mukautettua SFTP-tuontia voidaan käyttää tuomaan rikastetut tiedot takaisin Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuudella.

## <a name="prerequisites"></a>Edellytykset

Mukautetun SFTP-tuonnin määritykselle on seuraavat edellytykset:

- Sen SFTP-sijainnin käyttäjän tunnistetiedot (käyttäjänimi ja salasana), josta tiedot tuodaan.
- SFTP-isännän URL-osoite ja portin numero (yleensä 22).
- SFTP-isäntään tuotavan tiedoston tiedostonimi ja sijainti.
- *model.json*-tiedosto, joka määrittää tuotavien tietojen rakenteen. Tiedoston on oltava samassa kansiossa kuin tuotava tiedosto.
- [Järjestelmänvalvojan](permissions.md#administrator) käyttöoikeus.

## <a name="configuration"></a>Määritys

1. Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.

1. Valitse **Mukautettu SFTP-tuontiruudussa** **Rikasta tietojani**.

   > [!div class="mx-imgBorder"]
   > ![Mukautetun SFTP-tuontiruutu](media/SFTP_Custom_Import_tile.png "Mukautetun SFTP-tuontiruutu")

1. Valitse **Aloita** sekä anna tunnistetiedot ja SFTP-palvelimen osoite. Esimerkki: sftp://mysftpserver.com:22.

1. Anna sen tiedoston nimi, jossa on tiedot ja polku tiedostoon SFTP-palvelimessa, jos se ei ole pääkansiossa.

1. Vahvista kaikki syötteet valitsemalla **Yhdistä mukautettuun tuontiin**.

   > [!div class="mx-imgBorder"]
   > ![Mukautetun SFTP-tuonnin määrityksen pikaikkuna](media/SFTP_Custom_Import_Configuration_flyout.png "Mukautetun SFTP-tuonnin määrityksen pikaikkuna")

## <a name="defining-field-mappings"></a>Kenttien yhdistämismääritysten määrittäminen 

SFTP-palvelimeen tuotavan tiedoston sisältävässä hakemistossa on oltava myös *model.json*-tiedosto. Tämä tiedosto määrittää rakenteen, jota käytetään tietojen tuontiin. Rakenteen on käytettävä [Common Data Modelia](/common-data-model/) kentän yhdistämismäärityksen määrittämiseen. Yksinkertainen esimerkki model.json-tiedostosta:

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

## <a name="enrichment-results"></a>Rikastamisen tulokset

Aloita rikastamisprosessi valitsemalla komentopalkissa **Suorita**. Voit myös antaa järjestelmän suorittaa rikastamisen automaattisesti [aikataulutetun päivityksen](system.md#schedule-tab) osana. Käsittelyaika määräytyy tuotavien tietojen koon ja SFTP-palvelimen yhteyden mukaan.

Kun rikastamisprosessi valmistuu, voit tarkistaa juuri tuodut mukautetut rikastamistiedot **Omat rikastukset** -kohdassa. Näkyvissä on myös viimeisimmän päivityksen aika ja rikastettujen profiilien määrä.

Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.

## <a name="next-steps"></a>Seuraavat vaiheet

Voit hyödyntää rikastettuja asiakastietoja. Voit tuottaa mukautettuja kokemuksia asiakkaille luomalla [segmenttejä](segments.md) ja [mittareita](measures.md) sekä [viedä tietoja](export-destinations.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]