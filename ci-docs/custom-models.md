---
title: Mukautetut koneoppimisen mallit | Microsoft-dokumentit
description: Azuren automaattianalyysipalvelujen mukautettujen mallien käyttäminen Dynamics 365 Customer Insightsissa.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609742"
---
# <a name="custom-machine-learning-models"></a>Mukautetut koneoppimisen mallit

> [!NOTE]
> Machine Learning Studion (perinteinen) tuki päättyy 31.8.2024. On suositeltavaa siirtyä [Azure Machine Learningiin](/azure/machine-learning/overview-what-is-azure-machine-learning) tähän päivämäärään mennessä.
>
> 1.12.2021 jälkeen et voi luoda uusia Machine Learning Studion (perinteinen) resursseja. Voit käyttää 31.8.2024 asti aiemmin luotuja Machine Learning Studion (classic) resursseja. Lisätietoja on ohjeaiheessa [Siirtyminen Azure Machine Learningiin](/azure/machine-learning/migrate-overview).

Mukautettujen mallien avulla voidaan hallita Azuren automaattianalyysipalvelumalleihin perustuvia työnkulkuja. Työnkulut auttavat valitsemaan tiedot, joista halutaan muodostaa merkityksellisiä tietoja, ja yhdistää tulokset yhtenäistettyihin asiakastietoihin. Lisätietoja mukautettujen koneoppimismallien muodostamisesta on kohdassa [Azuren automaattianalyysipalveluihin perustuvien mallien käyttäminen](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>edellytykset

- [Azuren automaattianalyysipalvelujen eräputkien](/azure/machine-learning/concept-ml-pipelines) kautta julkaistut verkkopalvelut.
- Putki on julkaistava [putken päätepisteessä](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- Azure Studio -esiintymään liitetty [Azure Data Lake Gen2 -tallennustili](/azure/storage/blobs/data-lake-storage-quickstart-create-account).
- Putkia sisältäviä Azuren automaattianalyysipalvelujen työtiloja varten tarvitaan Azuren automaattianalyysipalvelujen työtilan omistajan tai järjestelmänvalvojan käyttöoikeudet.

  > [!NOTE]
  > Tiedot siirretään Customer Insights -ilmentymien ja työnkulun valittujen Azure-verkkopalveluiden tai -putkien välillä. Kun siirrät tietoja Azure-palveluun, varmista, että palvelu on määritetty käsittelemään tietoja tavalla ja sijainnilla, jotka ovat organisaatiotasi tai näitä tietoja koskevien juridisten tai lakisääteisten vaatimusten mukaisia.

## <a name="add-a-new-workflow"></a>Uuden työnkulun lisääminen

1. Valitse **Analytiikka** > **Mukautetut mallit** ja valitse **Uusi työnkulku**.

1. Anna tunnistettava **nimi**.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Näyttökuva Uusi työnkulku -ruudusta.":::

1. Valitse organisaatio, joka sisältää verkkopalvelun **Vuokraaja, joka sisältää verkkopalvelun** -kohdassa.

1. Jos Azuren koneoppimispalvelun tilaus on eri vuokraajassa kuin Customer Insights, valitse **sisäänkirjaus** valtuustiedoilla valitussa organisaatiossa.

1. Valitse verkkopalveluun liitetyt **työtilat**.

1. Valitse avattavassa **WWW-palvelu, joka sisältää mallin** -valikossa Azure Machine Learning -putki. Valitse sitten **Seuraava**.
   Lisätietoja [jakson julkaisemisesta Azuren automaattianalyysipalveluissa suunnitteluohjelman](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) tai [SDK:n](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) avulla.

1. Valitse kullekin **verkkopalvelun syötteelle** vastaava **Entiteetti** Customer Insightsissa. Valitse sitten **Seuraava**.
   > [!NOTE]
   > Mukautettu mallityönkulku käyttää heuristiikkaa verkkopalvelun syöttökenttien yhdistämisessä entiteettimääritteisiin kentän nimen ja tietotyypin perusteella. Näkyviin tulee virhe, jos verkkopalvelun kenttää ei voi yhdistää entiteettiin.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Työnkulun määrittäminen.":::

1. Määritä seuraavat ominaisuudet **Mallin tulosteparametrit** -kohdassa:
   - Putken tulosten **entiteetin nimi**
   - Eräputken **Tulostetietosäilön parametrin nimi**
   - Eräputken **Tulostepolun parametrin nimi**

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Mallin tulosteparametri -ruutu.":::

1. Valitse vastaava määrite asiakkaat määrittävässä **Asiakastunnus tuloksissa** -kohdassa ja valitse sitten **Tallenna**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Tulosten liittäminen Asiakastiedot-ruutuun.":::

   Avautuvassa **Työnkulku tallennettu** -ikkunassa on työnkulun tiedot. Jos määritit Azuren automaattianalyysipalvelun putken, Customer Insights liittää sen putken sisältävään työtilaan. Customer Insights saa **osallistuja**-roolin Azure-työtilassa.

1. Valitse **Valmis**. **Mukautetut mallit** -sivu avautuu.

1. Valitse työnkulun kohdalla kolme pystysuuntaista pistettä (&vellip;) ja valitse sitten **Suorita**. Työnkulku suoritetaan automaattisesti myös jokaisen [ajoitetun päivityksen](schedule-refresh.md) yhteydessä.

## <a name="manage-an-existing-workflow"></a>Aiemmin luodun työnkulun hallinta

Luotuja työnkulkuja voi tarkastella valitsemalla **Älykäs toiminto** > **Mukautetut mallit**.

Käytettävissä olevia toimintoja voi tarkastella valitsemalla työnkulun.

- Työnkulun **muokkaaminen**
- Työnkulun **suorittaminen**
- Työnkulun [**poistaminen**](#delete-a-workflow)

### <a name="edit-a-workflow"></a>Työnkulun muokkaaminen

1. Valitse **Älykäs toiminto** > **Mukautetut mallit**.

1. Valitse ensin päivitettävän työnkulun vieressä vertikaalinen kolme pistettä (&vellip;) ja valitse sitten **Muokkaa**.

1. Vaihda **Näyttönimi** tarvittaessa ja valitse **Seuraava**.

1. Päivitä kunkin **verkkopalvelun syötteen** vastaava **entiteetti** tarvittaessa Customer Insightsissa. Valitse sitten **Seuraava**.

1. Seuraavia voidaan muuttaa **Mallin tulosteparametrit** -kohdassa:
   - Putken tulosten **entiteetin nimi**
   - Eräputken **Tulostetietosäilön parametrin nimi**
   - Eräputken **Tulostepolun parametrin nimi**

1. Määritä asiakkaat valitsemalla vastaava määrite **Asiakkaan tunnus tuloksissa** -kohdassa. Päättelytulosteesta on valittava määrite, jossa on samankaltaiset arvot kuin asiakasentiteetin Asiakastunnus-sarakkeessa. Jos tietojoukossa ei ole kyseistä saraketta, valitse määrite, joka määrittää rivin yksilöivästi.

1. Valitse **Tallenna**

### <a name="delete-a-workflow"></a>Työnkulun poistaminen

1. Valitse **Älykäs toiminto** > **Mukautetut mallit**.

1. Valitse ensin poistettavan työnkulun vieressä vertikaalinen kolme pistettä (&vellip;) ja valitse sitten **Poista**.

1. Vahvista poisto.

Työnkulku poistetaan. [Entiteetti](entities.md), joka luotiin työnkulun yhteydessä, on yhä olemassa ja sitä voi sitä tarkastella valitsemalla **Tiedot** > **Entiteetit**-sivu.

## <a name="view-the-results"></a>Tulosten näyttäminen

Työnkulun tulokset tallennetaan entiteettiin, jonka nimi määritettiin **Mallin tulosteparametrit** -kohdassa. Näitä tietoja voi käyttää valitsemalla [**Tiedot** > **Entiteetit**-sivu](entities.md) tai [käyttämällä ohjelmointirajapintaa](apis.md).

### <a name="api-access"></a>Ohjelmointirajapinnan käyttö

Jos haluat saada tietoja mukautetusta mallientiteetistä, käytä tiettyä OData-kyselyä seuraavassa muodossa:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Korvaa `<your instance id>` Customer Insights -ympäristön tunnuksella, joka näkyy selaimen osoiterivillä Customer Insights -tietoja käytettäessä.

1. Korvaa `<custom model output entity>` entiteetin nimellä , joka annettiin **Mallin tulosteparametrit** -kohdassa.

1. Korvaa `<guid value>` sen asiakkaan asiakastunnuksella, jota halutaan käyttää. Tämä tunnus näkyy [asiakasprofiilisivun](customer-profiles.md) CustomerID-kentässä.

## <a name="frequently-asked-questions"></a>Usein kysytyt kysymykset

- Miksi en näe myyntiputkea mukautetun mallin työnkulun määrittämisen aikana?
  Tämä ongelma johtuu usein putken määritysongelmasta. Varmista, että [syöteparametri on määritetty](azure-machine-learning-experiments.md#dataset-configuration) ja [tulostetietosäilö ja polkuparametrit](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) on myös määritetty.

- Mitä "Älykkään toiminnon työnkulkua ei voi tallentaa" -virhe tarkoittaa? 
  Käyttäjät näkevät tämän virhesanoman yleensä silloin, kun heillä ei ole työtilan omistajan tai käyttäjän järjestelmänvalvojakäyttöoikeuksia. Käyttäjä tarvitsee korkeamman käyttöoikeustason, jotta Customer Insights voi käsitellä työnkulkua palveluna sen sijaan, että hän voi käyttää käyttäjätietoja työnkulun myöhemmissä vaiheissa.

- Tuetaanko mukautetun mallityönkulun yksityistä päätepistettä tai yksityistä linkkiä?
  Customer Insightsissa ei ole tällä hetkellä käyttövalmista mukautettujen mallien yksityisen päätepisteen tukea, mutta siihen on manuaalinen ratkaisu. Lisätietoja voi kysyä tuesta.

## <a name="responsible-ai"></a>Tekoälyn vastuullinen käyttö

Ennusteiden ominaisuuksilla voi luoda parempia asiakaskokemuksia sekä parantaa liiketoimintaominaisuuksia ja tulovirtoja. On erittäin suositeltavaa tasapainottaa eettisesti ennusteen arvo sekä sen vaikutukset ja mahdolliset puolueellisuudet. Lisätietoja tavasta, jolla Microsoft [ottaa tekoälyn vastuullisen käytön huomioon](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Saat myös lisätietoja Azuren automaattianalyysipalveluja koskevista [vastuullisten automaattianalyysipalvelujen tekniikoista ja prosesseista](/azure/machine-learning/concept-responsible-ml).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
