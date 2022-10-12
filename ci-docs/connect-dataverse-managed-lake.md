---
title: Yhteyden muodostaminen hallinnoidun Microsoft Dataverse Data Lake -tallennustilan tietoihin
description: Tietojen tuominen Microsoft Dataversen hallitusta Data Lake -tallennustilasta.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609791"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Yhteyden muodostaminen hallinnoidun Microsoft Dataverse Data Lake -tallennustilan tietoihin

Microsoft Dataverse -käyttäjät voivat muodostaa nopeasti yhteyden Microsoft Dataversen hallitun Data Lake -tallennustilan analyysientiteetteihin. Vain yksi ympäristön tietolähde voi käyttää samanaikaisesti samaa Dataversen hallittua Data Lake -tallennustilaa.

> [!NOTE]
> Sinun täytyy olla Dataverse-organisaation järjestelmänvalvoja, jotta voit jatkaa ja tarkastella hallitussa data lakessa käytettävissä olevien entiteettien luetteloa.

## <a name="prerequisites"></a>edellytykset

- Verkkopalveluihin, kuten Azure Data Lake Storageen, tallennetut tiedot voivat tallennettuina eri sijainnissa kuin missä tietoja käsitellään tai tallennetaan Dynamics 365 Customer Insightsissa. Tuomalla verkkopalveluun tallennetut tiedot tai muodostamalla niihin yhteyden hyväksyt, että tiedot voidaan siirtää ja tallentaa yhdessä Dynamics 365 Customer Insightsin kanssa.  [Lisätietoja on Microsoftin luottamuskeskuksessa](https://www.microsoft.com/trust-center).

- Vain Dataverse-entiteetit, joissa [muutosten seuranta](/power-platform/admin/enable-change-tracking-control-data-synchronization) on otettu käyttöön, ovat näkyvissä. Nämä entiteetit voidaan viedä Dataverse-hallittuun Data Lake -tallennustilaan, ja niitä voidaan käyttää Customer Insightsissa. Käyttövalmiissa Dataverse-taulukoissa muutosten seuranta on oletusarvoisesti käytössä. Ota muutosten seuranta käyttöön mukautetuissa taulukoissa. Jos haluat tarkistaa, onko Dataverse-taulukossa otettu käyttöön muutosten seuranta, siirry kohtaan [Power Apps](https://make.powerapps.com) > **Tiedot** > **Taulukot**. Etsi kiinnostava taulukko ja valitse se. Valitse **Asetukset** > **Lisäasetukset** ja tarkista **Muutosten seuranta** asetus.

## <a name="connect-to-a-dataverse-managed-lake"></a>Yhteyden muodostaminen Dataversen hallittuun tallennustilaan

1. Valitse **Tiedot** > **Tietolähteet**.

1. Valitse **Lisää tietolähde**.

1. Valitse **Microsoft Dataverse**.

1. Anna tietolähteelle **nimi** ja valinnainen **kuvaus**

1. Anna Dataverse-organisaation **palvelinosoite** ja valitse **Kirjaudu sisään**.

1. Valitse käytettävissä olevasta luettelosta taulukot, joiden entiteettejä haluat käsitellä Customer Insightsiin.

   > [!NOTE]
   > Jos jotkin taulukot on jo valittu, muut Dynamics 365 -sovellukset (kuten Dynamics 365 Sales Insights tai Customer Service Insights) saattavat käyttää niitä. Tätä valintaa ei voi muuttaa. Nämä taulukot ovat käytettävissä entiteetteinä, kun tietolähde on luotu.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Valintaikkuna, jossa näkyy luettelo Dataverse-ympäristön entiteeteistä.":::

1. Tallenna valinta, jos haluat aloittaa valittujen taulukoiden synkronoinnin Dataversesta. Löydät juuri lisätyn yhteyden **Tietolähteet**-sivulta. Se laitetaan jonoon päivitystä varten ja se näyttää entiteetin määränä 0, kunnes kaikki valitut taulukot on synkronoitu.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Tietojen lataaminen voi viedä aikaa. Kun päivitys on onnistunut, käsiteltyjä tietoja voi tarkastella [**Entiteetit**](entities.md)-sivulla.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataversen hallitun tallennustilan tietolähteen muokkaaminen

Entiteetin valintaa voi muokata vasta tietolähteen luomisen jälkeen. Esimerkiksi silloin, jos lisäentiteettejä lisättiin Dataverseen ja haluat tuoda myös ne.
Jos haluat muodostaa yhteyden toiseen Dataverse-tietojärveen, [luo uusi tietolähde](#connect-to-a-dataverse-managed-lake).

1. Valitse **Tiedot** > **Tietolähteet**.

1. Valitse päivitettävän tietolähteen vieressä **Muokkaa**.

1. Valitse lisäentiteetit käytettävissä olevien entiteettien luettelosta.

1. Ota muutokset käyttöön ja palaa **Tietolähteet**-sivulle valitsemalla **Tallenna**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Käsittelyvirheiden tai vioittuneiden tietojen yleisiä syitä

Seuraavat tarkistukset suoritetaan, jotta näytetyt tiedot voidaan paljastaa vioittuneille tietueille:

- Kentän arvo ei vastaa sen sarakkeen tietotyyppiä.
- Kentissä on merkkejä, joiden vuoksi sarakkeet eivät vastaa odotettua rakennetta. Esimerkiksi: väärin muotoiltuja lainausmerkkejä, virheellisiä lainausmerkkejä tai uuden linjan merkkejä.
- Mahdollisten päivämäärä ja aika-, päivämäärä- tai päivämääräsiirtymäsarakkeiden muoto on määritettävä mallissa, jos se ei noudata ISO-vakiomuotoa.

### <a name="schema-or-data-type-mismatch"></a>Rakenteen tai tietotyypin ristiriita

Jos tiedot eivät ole rakenteen mukaisia, tietueet luokitellaan vioittuneiksi. Korjaa joko lähdetiedot tai rakenne ja käsittele tiedot uudelleen.

### <a name="datetime-fields-in-the-wrong-format"></a>Päivämäärä- ja aika kenttien muoto väärä

Entiteetin päivämäärä- ja aikakentät eivät ole ISO- tai en-US-muotoisia. Päivämäärän ja ajan oletusmuoto Customer Insightsissa on en-US. Kaikissa entiteetin päivämäärä- ja aikakentissä on oltava sama muoto. Customer Insights tukee muita muotoja, kunhan huomautukset tai ominaisuudet tehdään mallin tai manifest.json-tiedoston lähde- tai entiteettitasolla. Esimerkki:

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  Manifest.json-tiedostossa päivämäärä- ja aikamuoto voidaan määrittää entiteetti- tai määritetasolla. Määritä päivämäärä- ja aikamuoto käyttämällä entiteettitasolla entiteetissä exhibitsTraits-ominaisuutta *.manifest.cdm.json-tiedostossa. Käytä määritetasolla appliedTraits-ominaisuutta entityname.cdm.json-tiedoston määritteessä.

**Manifest.json entiteettitasolla**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json määritetasolla**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
