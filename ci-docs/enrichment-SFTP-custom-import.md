---
title: Rikastaminen mukautetun SFTP-tuonnin avulla
description: Yleisiä tietoja mukautetusta SFTP-tuonnin rikastamisesta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f52d24cbe793bee7948ad2af31059cd3edf40f94
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645998"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Asiakasprofiilien rikastaminen mukautetuilla tiedoilla (esiversio)

Mukautetun SFTP (Secure File Transfer Protocol) -tuonnin avulla voidaan tuoda tietoja, joille ei tarvitse tehdä tietojen yhtenäistämisprosessia. Se on joustava, turvallinen ja helppo tapa tuoda tietoja. Mukautettua SFTP-tuontia voidaan käyttää yhdessä [SFTP-viennin](export-sftp.md) kanssa. Kyseisellä toiminnolla voi viedä rikastamiseen tarvittavia asiakasprofiilitietoja. Tietoja voidaan käsitellä ja täydentää, ja SFTP:n mukautetun tuonnin avulla rikastetun tiedon voi palauttaa Dynamics 365 Customer Insightsiin.

## <a name="prerequisites"></a>edellytykset

Mukautetun SFTP-tuonnin määritykselle on seuraavat edellytykset:

- Tiedossa on SFTP-isäntään tuotavan tiedoston nimi ja sijainti (polku).
- *model.json*-tiedosto määrittää tuotavien tietojen [Common Data Model -rakenteen](/common-data-model/). Tiedoston on oltava samassa kansiossa kuin tuotava tiedosto.
- Järjestelmänvalvoja on jo määrittänyt SFTP-yhteyden *tai* sinulla on [järjestelmänvalvojan](permissions.md#admin) käyttöoikeudet. Tarvitset sen SFTP-sijainnin käyttäjän tunnistetiedot, URL-osoitteen ja portin numeron, josta haluat tuoda tietoja.


## <a name="configure-the-import"></a>Määritä tuonti

1. Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.

1. Valitse **Mukautettu SFTP-tuonti** -ruudussa **Rikasta tietojani** ja valitse **Aloita**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Mukautettu SFTP-tuonti -ruutu.":::

1. Valitse [yhteys](connections.md) avattavasta luettelosta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä. Jos olet järjestelmänvalvoja, voit luoda yhteyden valitsemalla **Lisää yhteys** -kohdan ja valitsemalla sitten avattavasta luettelosta **Mukautettu SFTP-tuonti** -kohdan.

1. Vahvista valittu yhteys valitsemalla **Yhdistä mukautettuun tuontiin**.

1.  Valitse **Seuraava** ja syötä tuotavan datatiedoston **polku** ja **tiedostonimi**.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Näyttökuva tietojen sijainnin syöttämisestä.":::

1. Valitse **Seuraava** ja valitse asiakastietojoukko. Se voi sisältää joko kaikki asiakasprofiilit tai segmentin.

1. Valitse **Seuraava** ja anna rikastuksen ja tulosentiteetin nimi. 

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Yhteyden määrittäminen mukautettua SFTP-tuontia varten 

Yhteyksien määrittämiseen tarvitaan järjestelmänvalvojan oikeudet. Valitse rikastusta määritettäessä **Lisää yhteys** *tai* siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja valitse Mukautettu tuonti -ruudussa **Määritä**.

1. Kirjoita yhteyden nimi **Näyttönimi**-ruutuun.

1. Anna sen SFTP-palvelimen sallittu käyttäjänimi, salasana ja isännän URL-osoite, jossa tuotavat tiedot ovat.

1. Tarkista tiedot ja hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu.

1. Tarkista määritys valitsemalla **Tarkista**.

1. Kun tarkistus on tehty, yhteys tallennetaan valitsemalla **Tallenna**.

   > [!div class="mx-imgBorder"]
   > ![Experian-yhteyden määrityssivu.](media/enrichment-SFTP-connection.png "Experian-yhteyden määrityssivu")


## <a name="defining-field-mappings"></a>Kenttien yhdistämismääritysten määrittäminen 

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

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
