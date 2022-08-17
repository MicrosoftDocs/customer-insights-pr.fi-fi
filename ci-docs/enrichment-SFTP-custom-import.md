---
title: Asiakasprofiilien rikastaminen mukautetun SFTP-tuonnin avulla (esiversio)
description: Yleisiä tietoja mukautetusta SFTP-tuonnin rikastamisesta.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 831d1d3d3045379bbc5bcdcd4b05b8a147221f31
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237762"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Asiakasprofiilien rikastaminen mukautetun SFTP-tuonnin avulla (esiversio)

Mukautetun SFTP (Secure File Transfer Protocol) -tuonnin avulla voidaan tuoda tietoja, joille ei tarvitse tehdä tietojen yhtenäistämisprosessia. Se on joustava, turvallinen ja helppo tapa tuoda tietoja. Mukautettua SFTP-tuontia voidaan käyttää yhdessä [SFTP-viennin](export-sftp.md) kanssa. Kyseisellä toiminnolla voi viedä rikastamiseen tarvittavia asiakasprofiilitietoja. Tietoja voidaan käsitellä ja täydentää, ja SFTP:n mukautetun tuonnin avulla rikastetun tiedon voi palauttaa Dynamics 365 Customer Insightsiin.

## <a name="prerequisites"></a>edellytykset

- SFTP-isännässä tuotavan tiedoston tiedostonimi ja sijainti (polku) tiedetään.

- Tuotavien tietojen Common Data Model -rakenteen määrittävä *model.json*-tiedosto on käytettävissä. Tiedoston on oltava samassa kansiossa kuin tuotava tiedosto.

- SFTP-[yhteys](connections.md) on [määritetty](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Tiedoston rakenne-esimerkki

SFTP-palvelimeen tuotavan tiedoston sisältävässä hakemistossa on oltava myös *model.json*-tiedosto. Tämä tiedosto määrittää rakenteen, jota käytetään tietojen tuontiin. Rakenteessa on oltava käytössä [Common Data Model](/common-data-model/), jotta voidaan määrittää kentän vastaavuusmääritys. Yksinkertainen esimerkki model.json-tiedostosta:

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Yhteyden määrittäminen mukautettua SFTP-tuontia varten

Määrittäjällä on oltava Customer Insightsin [järjestelmänvalvoja](permissions.md#admin), jolla on sen SFTP-sijainnin käyttäjän tunnistetiedot, URL-osoite ja portin numero, josta tiedot tuodaan.

1. Valitse rikastusta määritettäessä **Lisää yhteys** tai valitse **Järjestelmänvalvoja** > **Yhteydet** ja valitse siten Mukautettu tuonti -ruudussa **Määritä**.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Mukautetun tuontiyhteyden määrittämissivu":::

1. Anna yhteyden nimi.

1. Anna sen SFTP-palvelimen sallittu käyttäjänimi, salasana ja isännän URL-osoite, jossa tuotavat tiedot ovat.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Tarkista määritys valitsemalla **Vahvista** ja valitse sitten **Tallenna**.

## <a name="configure-the-import"></a>Määritä tuonti

1. Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.

1. Valitse **Rikasta tiedot** **Mukautetut SFTP-tiedot** -ruudussa.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Mukautettu SFTP-tuonti -ruutu.":::

1. Tutustu yleiskatsaukseen ja valitse **Seuraava**.

1. Valitse yhteys. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Valitse ensin **Asiakkaan tietojoukko** ja sitten rikastettava profiili tai segmentti. *Asiakas*-entiteetti rikastaa kaikkia asiakasprofiileja, kun taas segmentti rikastaa vain segmenttiin sisältyviä asiakasprofiileja.

1. Valitse **Seuraava**.

1. Anna tuotavan datatiedoston **polku** ja **tiedostonimi**.

1. Valitse **Seuraava**.

1. Anna **Nimi** rikastamista varten ja **Tulosentiteetin nimi**.

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.

1. Aloita rikastamisprosessi valitsemalla **Suorita** tai sulje ja palaa **Rikastukset**-sivulle.

## <a name="view-enrichment-results"></a>Rikastamisen tulosten tarkasteleminen

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Seuraavat vaiheet

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
