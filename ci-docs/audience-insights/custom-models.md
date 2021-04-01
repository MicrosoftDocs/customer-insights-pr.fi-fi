---
title: Mukautetut koneoppimisen mallit | Microsoft-dokumentit
description: Azuren automaattianalyysipalvelujen mukautettujen mallien käyttäminen Dynamics 365 Customer Insightsissa.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 87fb517e9f0b380f9721f77470dceb3bcb7e5616
ms.sourcegitcommit: 55c00ea61c78db7b3b54894c01afb3246dff31c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2021
ms.locfileid: "5700664"
---
# <a name="custom-machine-learning-models"></a>Mukautetut koneoppimisen mallit

Valitsemalla **Analytiikka** > **Mukautetut mallit** voit hallita Azuren automaattianalyysipalvelumalleihin perustuvia työnkulkuja. Työnkulut auttavat valitsemaan tiedot, joista halutaan muodostaa merkityksellisiä tietoja, ja yhdistää tulokset yhtenäistettyihin asiakastietoihin. Lisätietoja mukautettujen koneoppimismallien muodostamisesta on kohdassa [Azuren automaattianalyysipalveluihin perustuvien mallien käyttäminen](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Tekoälyn vastuullinen käyttö

Ennusteiden ominaisuuksilla voi luoda parempia asiakaskokemuksia sekä parantaa liiketoimintaominaisuuksia ja tulovirtoja. On erittäin suositeltavaa tasapainottaa eettisesti ennusteen arvo sekä sen vaikutukset ja mahdolliset puolueellisuudet. Lisätietoja tavasta, jolla Microsoft [ottaa tekoälyn vastuullisen käytön huomioon](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Saat myös lisätietoja Azuren automaattianalyysipalveluja koskevista [vastuullisten automaattianalyysipalvelujen tekniikoista ja prosesseista](/azure/machine-learning/concept-responsible-ml).

## <a name="prerequisites"></a>Edellytykset

- Tämä toiminto tukee tällä hetkellä verkkopalveluja, jotka on julkaistu [koneoppimisstudiossa (perinteinen)](https://studio.azureml.net) ja [Azuren automaattianalyysipalvelujen eräjaksoissa](/azure/machine-learning/concept-ml-pipelines).

- Tämän toiminnon käyttöä varten tarvitaan Azure Data Lake Gen2 -tallennustilin, joka on liitetty Azure-studioesiintymään. Lisätietoja on kohdassa [Azure Data Lake Storage Gen2 -tallennustilatilin luominen](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Azure-automaattianalyysin työtiloja, joissa on putkia varten tarvitset Azure-automaattianalyysin työtilan omistajan tai järjestelmänvalvojan käyttöoikeudet.

   > [!NOTE]
   > Tiedot siirretään Customer Insights -ilmentymien ja työnkulun valittujen Azure-verkkopalveluiden tai -putkien välillä. Kun siirrät tietoja Azure-palveluun, varmista, että palvelu on määritetty käsittelemään tietoja tavalla ja sijainnilla, jotka ovat organisaatiotasi tai näitä tietoja koskevien juridisten tai lakisääteisten vaatimusten mukaisia.

## <a name="add-a-new-workflow"></a>Uuden työnkulun lisääminen

1. Valitse **Analytiikka** > **Mukautetut mallit** ja valitse **Uusi työnkulku**.

1. Anna mukautetulle mallille tunnistettava nimi **Nimi**-kentässä.

   > [!div class="mx-imgBorder"]
   > ![Näyttökuva Uusi työnkulku -ruudusta](media/new-workflowv2.png "Näyttökuva Uusi työnkulku -ruudusta")

1. Valitse organisaatio, joka sisältää verkkopalvelun **Vuokraaja, joka sisältää verkkopalvelun** -kohdassa.

1. Jos Azuren koneoppimispalvelun tilaus on eri vuokraajassa kuin Customer Insights, valitse **sisäänkirjaus** valtuustiedoilla valitussa organisaatiossa.

1. Valitse verkkopalveluun liitetyt **työtilat**. Luettelossa on kaksi osaa: toinen on Azuren automaattianalyysipalvelujen v1 (koneoppimisstudio (perinteinen)) ja toinen Azuren automaattianalyysipalvelut v2 (Azuren automaattianalyysipalvelut). Jos ole varma, mikä työtila sopii omaan Koneoppimisstudio (perinteinen) -työtilaan, valitse **Mikä tahansa**.

1. Valitse Koneoppimisstudio (perinteinen) -verkkopalvelu tai Azuren automaattianalyysipalvelut -putki avattavassa **WWW-palvelu, joka sisältää mallin** -luettelossa. Valitse sitten **Seuraava**.
   - Lisätietoja [verkkopalvelun julkaisemisesta koneoppimisstudiossa (perinteinen)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Lisätietoja [jakson julkaisemisesta Azuren automaattianalyysipalveluissa suunnitteluohjelman](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) tai [SDK:n](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) avulla. Jakso on julkaistava [jakson päätepisteessä](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Valitse kullekin **verkkopalvelun syötteelle** vastaava **Entiteetti** käyttäjäryhmän merkityksellisissä tiedoissa ja valitse sitten **Seuraava**.
   > [!NOTE]
   > Mukautettu mallityönkulku käyttää heuristiikkaa verkkopalvelun syöttökenttien yhdistämisessä entiteettimääritteisiin kentän nimen ja tietotyypin perusteella. Näkyviin tulee virhe, jos verkkopalvelun kenttää ei voi yhdistää entiteettiin.

   > [!div class="mx-imgBorder"]
   > ![Työnkulun määrittäminen](media/intelligence-screen2-updated.png "Työnkulun määrittäminen")

1. Määritä seuraavat ominaisuudet **Mallin tulosteparametrit** -vaiheessa:
   - Koneoppimisstudio (perinteinen)
      1. Anna sen tulosteen **entiteetin nimi**, johon haluat verkkopalvelun tulosten siirtyvän.
   - Azuren automaattianalyysipalvelut
      1. Anna sen tulosteen **entiteetin nimi**, johon haluat jakson tulosten siirtyvän.
      1. Valitse avattavassa luettelossa eränjakson **Tulostetietosäilön parametrin nimi**.
      1. Valitse avattavassa luettelossa eränjakson **Tulostepolun parametrin nimi**.

      > [!div class="mx-imgBorder"]
      > ![Mallin tulosteparametri -ruutu](media/intelligence-screen3-outputparameters.png "Mallin tulosteparametri -ruutu")

1. Valitse vastaava määrite siinä avattavassa **Asiakastunnus tuloksissa** -luettelossa, joka määrittää asiakkaat, ja valitse **Tallenna**.

   > [!div class="mx-imgBorder"]
   > ![Tulosten liittäminen Asiakastiedot-ruutuun](media/intelligence-screen4-relatetocustomer.png "Tulosten liittäminen Asiakastiedot-ruutuun")

1. Näkyviin tulee **Työnkulku tallennettu** -näyttö, jossa ovat työnkulun tiedot.    
   Azuren automaattianalyysipalvelut -jaksolle määritettiin työnkulku, käyttäjäryhmän merkitykselliset tiedot liitetään jakson sisältävään työtilaan. Käyttäjäryhmän merkityksellisten tietojen rooli Azure-työtilassa on **Osallistuja**.

1. Valitse **Valmis**.

1. Työnkulku voidaan nyt suorittaa **Mukautetut mallit** -sivulta.

## <a name="edit-a-workflow"></a>Työnkulun muokkaaminen

1. Valitse **Mukautetut mallit** -sivulla **Toiminnot**-sarakkeen pystysuorat kolme pistettä aiemmin luodun työnkulun vieressä ja valitse **Muokkaa**.

1. Vaikka voit päivittää työnkulun tunnistettavan nimen **Näyttönimi**-kentässä, et voi muuttaa määritettyä verkkopalvelua tai jaksoa. Valitse **Seuraava**.

1. Kullekin **verkkopalvelun syötteelle** voidaan päivittää vastaava **Entiteetti** käyttäjäryhmän merkityksellisissä tiedoissa. Valitse sitten **Seuraava**.

1. Määritä seuraavat ominaisuudet **Mallin tulosteparametrit** -vaiheessa:
   - Koneoppimisstudio (perinteinen)
      1. Anna sen tulosteen **entiteetin nimi**, johon haluat verkkopalvelun tulosten siirtyvän.
   - Azuren automaattianalyysipalvelut
      1. Anna sen tulosteen **entiteetin nimi**, johon haluat jakson tulosten siirtyvän.
      1. Valitse testijaksolle **Tulostetietosäilön parametrin nimi**.
      1. Valitse testijaksolle **Tulostepolun parametrin nimi**.

1. Valitse vastaava määrite siinä avattavassa **Asiakastunnus tuloksissa** -luettelossa, joka määrittää asiakkaat, ja valitse **Tallenna**.
   Päättelytulosteesta on valittava määrite, jossa on samankaltaiset arvot kuin asiakasentiteetin Asiakastunnus-sarakkeessa. Jos tietojoukossa ei ole kyseistä saraketta, valitse määrite, joka määrittää rivin yksilöivästi.

## <a name="run-a-workflow"></a>Työnkulun suorittaminen

1. Valitse **Mukautetut mallit** -sivulla **Toiminnot**-sarakkeen pystysuorat kolme pistettä aiemmin luodun työnkulun vieressä ja valitse Muokkaa.

1. Valitse **Suorita**.

Työnkulku suoritetaan myös automaattisesti jokaisen ajoitetun päivityksen yhteydessä. Lisätietoja [aikataulutettujen päivitysten määrittämisestä](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Työnkulun poistaminen

1. Valitse **Mukautetut mallit** -sivulla **Toiminnot**-sarakkeen pystysuorat kolme pistettä aiemmin luodun työnkulun vieressä ja valitse Muokkaa.

1. Valitse **Poista** ja vahvista poistaminen.

Työnkulku poistetaan. [Entiteetti](entities.md), joka luotiin työnkulun yhteydessä, on yhä olemassa. Voit tarkastella sitä **Entiteetit**-sivulla.

## <a name="results"></a>Tulokset

Työnkulun tulokset tallennetaan mallituotoksen parametrivaiheen aikana määritettyön entiteettiin. Voit käyttää näitä tietoja [entiteettisivulta](entities.md) tai [API-liittymän](apis.md) kautta.

### <a name="api-access"></a>Ohjelmointirajapinnan käyttö

Jos haluat saada tietoja mukautetusta mallientiteetistä, käytä tiettyä OData-kyselyä seuraavassa muodossa:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Korvaa `<your instance id>` Customer Insights -ympäristön tunnuksella, jonka löydät selaimen osoiterivillä, kun käytät Customer Insights -tietoja.

1. Korvaa `<custom model output entity>` mukautetun mallin määrityksen mallitulosteparametrien vaiheessa annetulla entiteetin nimellä.

1. Korvaa `<guid value>` sen asiakkaan asiakastunnuksella, jonka tietuetta haluat käyttää. Tämä tunnus löytyy yleensä [Asiakasprofiilit-sivun](customer-profiles.md) CustomerID-kentästä.

## <a name="frequently-asked-questions"></a>Usein kysyttyjä kysymyksiä

- Miksi en näe myyntiputkea mukautetun mallin työnkulun määrittämisen aikana?    
  Tämä ongelma johtuu usein putken määritysongelmasta. Varmista, että [syöteparametri on määritetty](azure-machine-learning-experiments.md#dataset-configuration) ja [tulostetietosäilö ja polkuparametrit](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) on myös määritetty.

- Mitä "Älykkään toiminnon työnkulkua ei voi tallentaa" -virhe tarkoittaa?    
  Käyttäjät näkevät tämän virhesanoman yleensä silloin, kun heillä ei ole työtilan omistajan tai käyttäjän järjestelmänvalvojakäyttöoikeuksia. Käyttäjä tarvitsee korkeamman käyttöoikeustason, jotta Customer Insights voi käsitellä työnkulkua palveluna sen sijaan, että hän voi käyttää käyttäjätietoja työnkulun myöhemmissä vaiheissa.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
