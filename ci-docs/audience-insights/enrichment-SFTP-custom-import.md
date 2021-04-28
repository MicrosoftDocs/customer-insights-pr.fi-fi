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
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Asiakasprofiilien rikastaminen mukautetuilla tiedoilla (esiversio)

Mukautetun Secure File Transfer Protocol (SFTP) -tuonnin avulla voit tuoda tietoja, joita ei tarvitse käyttää tietojen yhdistämisprosessissa. Se on joustava, turvallinen ja helppo tapa tuoda tietoja. Mukautettua SFTP-tuontia voidaan käyttää yhdessä [SFTP-viennin](export-sftp.md) kanssa. Kyseisellä toiminnolla voi viedä rikastamiseen tarvittavia asiakasprofiilitietoja. Tiedot voidaan sitten käsitellä ja rikastaa ja mukautettua SFTP-tuontia voidaan käyttää tuomaan rikastetut tiedot takaisin Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen ominaisuudella.

## <a name="prerequisites"></a>Edellytykset

Mukautetun SFTP-tuonnin määritykselle on seuraavat edellytykset:

- Sinulla on tuotavan tiedoston tiedostonimi ja sijainti (polku) SFTP-palvelimella.
- *model.json*-tiedosto määrittää tuotavien tietojen [Common Data Model -rakenteen](/common-data-model/). Tiedoston on oltava samassa kansiossa kuin tuotava tiedosto.
- Järjestelmänvalvoja on jo määrittänyt SFTP-yhteyden *tai* sinulla on [järjestelmänvalvojan](permissions.md#administrator) käyttöoikeudet. Tarvitset sen SFTP-sijainnin käyttäjän tunnistetiedot, URL-osoitteen ja portin numeron, josta haluat tuoda tietoja.


## <a name="configure-the-import"></a>Määritä tuonti

1. Valitse **Tiedot** > **Rikastaminen** ja valitse sitten **Tutustu**-välilehti.

1. Valitse **Mukautettu SFTP-tuonti** -ruudussa **Rikasta tietojani** ja valitse **Aloita**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Mukautettu SFTP-tuonti -ruutu.":::

1. Valitse [yhteys](connections.md) avattavasta luettelosta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä. Jos olet järjestelmänvalvoja, voit luoda yhteyden valitsemalla **Lisää yhteys** ja valitsemalla avattavasta valikosta **Mukautettu SFTP-tuonti**.

1. Vahvista valittu yhteys valitsemalla **Yhdistä mukautettuun tuontiin**.

1.  Valitse **Seuraava** ja kirjoita tuodun datatiedoston **Tiedostonimi** ja **Polku**.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Näyttökuva tietojen sijainnin syöttämisestä.":::

1. Valitse **Seuraava** ja anna rikastuksen ja tulosentiteetin nimi. 

1. Valitse **Tallenna rikastus**, kun olet tarkistanut vaihtoehdot.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Yhteyden määrittäminen mukautettua SFTP-tuontia varten 

Yhteyksien määrittämiseen tarvitaan järjestelmänvalvojan oikeudet. Valitse rikastusta määritettäessä **Lisää yhteys** *tai* siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja valitse Mukautettu tuonti -ruudussa **Määritä**.

1. Kirjoita yhteyden nimi **Näyttönimi**-ruutuun.

1. Anna tuotavien tietojen SFTP-palvelimen kelvollinen käyttäjänimi, salasana ja URL-osoite.

1. Tarkista tiedot ja hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu.

1. Tarkista määritys valitsemalla **Tarkista**.

1. Kun tarkistus on valmis, yhteys voidaan tallentaa valitsemalla **Tallenna**.

> [!div class="mx-imgBorder"]
   > ![Experian-yhteyden määrityssivu](media/enrichment-SFTP-connection.png "Experian-yhteyden määrityssivu")


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
