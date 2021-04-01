---
title: Koneoppimisstudion (perinteinen) kokeileminen
description: (Perinteisen) koneoppimisstudion mallien käyttäminen Dynamics 365 Customer Insightsissa.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 71881f7e1f9448fe0a7d6d92b8102b8b42de7c2a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598335"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Azuren koneoppimisstudioon (perinteinen) perustuvien mallien käyttäminen

Dynamics 365 Customer Insightsin yhtenäistetyt tiedot ovat sellaisten koneoppimismallien muodostamisen lähde, joilla voidaan luoda lisää merkityksellisiä liiketoimintatietoja. Integroituneet Customer Insights ja koneoppimisstudio (perinteinen) käyttävät käyttäjän mukautettuja malleja Lisätietoja Azuren automaattianalyysipalveluissa kehitettyjen mallien integroinnista Customer Insightsiin on kohdassa [Azuren automaattianalyysipalvelujen kokeileminen](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Edellytykset

- Customer Insightsin käyttöoikeus
- Aktiivinen Azure Enterprise -tilaus
- [Yhdistetyt asiakasprofiilit](data-unification.md)
- Määritetty [entiteetin vienti Azure Blob -säilöön ](export-azure-blob-storage.md)

## <a name="set-up-machine-learning-studio-classic"></a>Perinteisen koneoppimisstudion määrittäminen

Ensimmäisessä vaiheessa luodaan koneoppimisstudiolle (perinteinen) työtila ja avataan studio.

1. Siirry [https://www.portal.azure.comen](https://www.portal.azure.com/) ja kirjaudu sisään.

1. Valitse **Luo resurssi**.

1. Hae **Koneoppimisstudion työtila** ja valitse **Luo**.

1. Anna [työtilan luontiin](/azure/machine-learning/studio/create-workspace) tarvittavat tiedot. Valitse **Verkkopalvelusuunnitelman hinnoittelutaso** sen perusteella, kuinka paljon tietoja suunnittelet tuovasi. Paras tulos saadaan valitsemalla maantieteellisesti lähin **sijainti**.

1. Koneoppimisstudion työtilan koontinäyttö avautuu, kun resurssi on luotu. Valitse **Käynnistä koneoppimisstudio**.

   ![Azuren koneoppimisstudion käyttöliittymä](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Azuren koneoppimisstudion käyttäminen

Voit nyt luoda uuden kokeilun tai tuoda aiemmin luodun kokeilumallin esimerkkivalikoimasta. Käytössä on näytekokeiluja kolmeen vakioskenaarioon:

- [Vaihtuvuusennuste](#churn-analysis)

- [Asiakkaan elinkaaren arvo](#customer-lifetime-value-prediction)

- [Tuotesuositus tai seuraava paras toiminto](#productrecommendation-or-next-best-action)

1. Jos luot uuden kokeilun tai käytät valikoiman kokeilumallia, **Tuo tiedot** -ominaisuudet on määritettävä. Siirry tietosi sisältävään Azure Blob -säilöön käyttämällä ohjattua kokemusta tai antamalla tiedot suoraan.  

   ![Azuren koneoppimisstudion kokeilu](media/azure-machine-learning-studio-experiment.png)

1. Voit luoda muodostaa mukautetun käsittelyjakson, joka siistii ja esikäsittelee tiedot, poimii ominaisuudet ja kouluttaa sopivan mallin.

1. Testaa ja optimoi mallin toiminta.

1. Kun olet tyytyväinen malliin, valitse **Määritä verkkopalvelu** > **Ennakoiva verkkopalvelu**. Tämä vaihtoehto tuo koulutetun mallin ja ominaisuuksien kehitysjakson koulutuskokeilusta ennakoivaan palveluun. Ennakoiva palvelu voi tehdä ennusteita ottamalla käyttöön toisen syötetietojoukon, jossa on koulutuskokeilussa käytetty rakenne.

   ![Ennakoivan verkkopalvelun määrittäminen](media/predictive-webservice-control.png)

1. Kun ennakoiva verkkokokeilu toimii oikein, se voidaan ottaa käyttöön automaattisessa aikataulutuksessa. Verkkopalvelun käyttäminen Customer Insightsin kanssa määritetään valitsemalla **Ota verkkopalvelu käyttöön** > **Ota verkkopalvelu käyttöön [uusi] – esiversio**. [Lisätietoja verkkopalvelun käyttöönottamisesta](/azure/machine-learning/studio/deploy-a-machine-learning-web-service)

   ![Ennakoivan verkkopalvelun käyttöönottaminen](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Valikoiman esimerkkimallit

Tässä artikkelissa malleissa käytetään kuvitteellista Contoso Hotel -skenaariota. Contoso Hotel kerää seuraavat tiedot:

- Hotelliyöpymisaktiviteetista koostuvat CRM-tiedot. Tietojoukko sisältää tietojen kunkin rekisteröityneen asiakkaan yöpymispäivämäärät. Siinä on myös tietoja esimerkiksi varauksesta, huonetyypistä ja rahankäytöstä. Tiedot ovat neljän vuoden ajalta tammikuusta 2014 tammikuuhun 2018.
- Hotellivieraiden asiakasprofiilit. Näissä profiileissa on tietoja kustakin asiakkaasta, kuten nimi, syntymäaika, postiosoite, sukupuoli ja puhelinnumero.
- Hotellin tarjoamien palvelujen käyttö, joita ovat esimerkiksi kylpyläpalvelut, pesula, WiFi tai kuriiripalvelut. Nämä tiedot kirjataan kunkin rekisteröityneen asiakkaan osalta. Yleensä palveluiden käyttö on linkitetään yöpymiseen. Joissakin tapauksissa myös sellaiset asiakkaat voivat käyttää palveluja, jotka eivät yövy hotellissa.

## <a name="churn-analysis"></a>Vaihtuvuusanalyysi

Vaihtuvuusanalyysia käytetään liiketoiminnan eri alueilla. Tässä esimerkissä tarkastellaan palvelun vaihtuvuutta edellä kuvattujen hotellipalvelujen osalta. Näin saadaan toimiva esimerkki kattavasta mallijaksosta, jonka perusteella voidaan luoda muun tyyppisiä vaihtuvuusmalleja.

### <a name="definition-of-churn"></a>Vaihtuvuuden määritelmä

Vaihtuvuuden määritelmä voi olla erilainen eri skenaarioissa. Tässä esimerkissä vieras, joka ei ole yöpynyt hotellissa kuluneen vuoden aikana, on katsottava vaihtuneeksi.  

Kokeilumalli voidaan tuoda valikoimasta. Varmista ensin, että tuot Azure Blob -säilöstä **Hotelliyöpymisaktiviteetti**-, **Asiakastiedot**- ja **Palvelun käyttötiedot** -tiedot.

   ![Vaihtuvuusmallin tietojen tuominen](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Ominaisuuksien kehitys

Vaihtuvuuden perusteella määritetään ensin raakaominaisuudet, jotka vaikuttavat selitteeseen. Sen jälkeen nämä raakaominaisuudet käsitellään ominaisuuksiksi, joita voidaan käyttää koneoppimismalleissa. Tiedot integroidaan Customer Insights, joten nämä taulukot voidaan liittää käyttämällä *asiakastunnusta*.

   ![Tuotujen tietojen liittäminen](media/join-imported-data.png)

Vaihtuvuusanalyysimallin muodostamisessa käytettävä ominaisuuksien kehitys voi olla jonkin verran haastavaa. Tieto on aikafunktio, jossa uusi hotelliaktiviteetti kirjataan päivittäin. Ominaisuuksien kehityksen aikana halutaan luoda staattisia ominaisuuksia dynaamisista tiedoista. Tässä tapauksessa hotelliaktiviteetista luodaan useita ominaisuuksista ja liukuvana aikaikkunana on yksi vuosi. Lisäksi laajennetaan luokitellut ominaisuudet, kuten huonetyyppi tai varaustyyppi, erillisiksi ominaisuuksiksi käyttämällä one-hot-koodausta.  

Lopullinen ominaisuusluettelo:

| **Luku**  | **Alkuperäinen_sarake**          | **Johdetut ominaisuudet**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Huonetyyppi                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Varaustyyppi                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Matkustusluokka              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Käytetty rahamäärä                | TotalDollarSpent                                                                                                                          |
| 5           | Tulo- ja lähtöpäivämäärät  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Palvelun käyttö                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Mallin valinta

Seuraavaksi valitaan optimaalinen algoritmi. Tässä tapauksessa useimmat ominaisuudet perustuvat luokitteluominaisuuksiin. Yleensä päätöspuuhun perustuvat mallit toimivat hyvin. Jos kyse on vain numeerisista ominaisuuksista, neuraaliverkot voivat olla parempi vaihtoehto. Myös tukivektorikone (SVM) on hyvä vaihtoehto tällaisissa tilanteissa, joskin niiden tehokas toiminta edellyttää aika paljon säätämistä. Ensimmäiseksi mallivaihtoehdoksi valitaan **Kaksiluokkainen tehostettu päätöspuu** ja sen jälkeen toiseksi malliksi **Kaksiluokkainen SVM**. Azure koneoppimisstudion avulla voit tehdä A/B-testausta, joten alussa kannattaa käyttää kahta mallia yhden mallin sijaan.

Seuraava kuvassa näkyy Azuren koneoppimisstudion mallin kouluttaminen ja arviointijakso:

![Azuren koneoppimisstudion vaihtuvuusmalli](media/azure-machine-learning-model.png)

Lisäksi käytetään **permutaatio-ominaisuuden tärkeys** -tekniikkaa, mikä on tärkeä osa mallin optimointia. Valmiissa malleissa ei ole juuri käsitystä siitä, millainen vaikutus tietyllä ominaisuudella on lopulliseen ennusteeseen. Ominaisuuden tärkeyslaskin laskee mukautetulla algoritmilla yksittäisten ominaisuuksien vaikutuksen tietyn mallin lopputulokseen. Ominaisuuden tärkeys normalisoidaan arvojen +1ja -1 välille. Negatiivinen vaikutus tarkoittaa, että vastaava ominaisuus vaikuttaa yleisen käsityksen vastaisesti tulokseen, minkä vuoksi se pitäisi poistaa mallista. Positiivinen vaikutus ilmaisee, että ominaisuus vaikuttaa merkittävästi ennusteen suuntaan. Nämä arvot eivät ole korrelaatiokertoimia, sillä ne ovat erilaisia mittareita. Lisätietoja on kohdassa [Permutaatio-ominaisuuden tärkeys](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Koko [vaihtuvuuskokemus on saatavana Azure AI Galleryssä](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Asiakkaan elinkaaren arvon ennuste

Asiakkaan elinkaari arvo (CLTV) on yksi tärkeimmistä mittareista, jonka avulla yritys voi arvioida ja segmentoida asiakkaitaan. Hotellitoiminnassa asiakkaiden tuntemus on välttämätöntä. Esimerkiksi tietoisuus siitä, mistä tekijöistä hyvät asiakkaat muodostuvat, on välttämätön tieto. Se auttaa hotellin johtoa arvioimaan, mihin ominaisuuksiin on keskityttävä ja mitä on parannettava, jotta paljon kuluttavat asiakkaat olisivat tyytyväisiä. Nämä päätökset vaikuttavat suoraan myyntiin ja tuloihin.  

### <a name="definition-of-cltv"></a>Asiakkaan elinkaaren arvon määritelmä

Tässä esimerkissä asiakkaan elinkaaren arvo määritetään siksi kokonaissummaksi, jonka asiakkaan odotetaan käyttävän seuraavan 365 päivän aikana. Tämän arvon ennustamiseen käytetään kaikkien asiakkaiden tietoja kuluneen kolmen vuoden ajalta.

### <a name="featurization"></a>Ominaisuuksien kehitys

Tässä tapauksessa ominaisuuksien kehitys muistuttaa vaihtuvuusskenaariota. Selitteet ja ennustetut arvot kuitenkin poikkeavat edellä kuvatuista arvoista.

### <a name="model-selection"></a>Mallin valinta

Asiakkaan elinkaaren arvon ennustaminen on regressiotehtävä, sillä ennustettu arvo on arvoltaan positiivinen jatkuva muuttuja. Ominaisuuden ominaisuuksien perusteella valitaan yhdeksi algoritmiksi **Tehostetun päätöspuun regressio** ja **Neuraaliverkon regressio** toiseksi mallia kouluttavaksi algoritmiksi.

## <a name="product-recommendation-or-next-best-action"></a>Tuotesuositus tai seuraava paras toiminto

Tuotesuositus tarkoittaa hotelliskenaariossa hotellin asiakkaille tarjoamien palvelujen suosittelua. Tavoitteena on valita asiakkaille sopivia palveluja siten, että palvelujen käyttö maksimoidaan. Se vastaa videoiden suoratoistopalvelujen käyttäjille tehtäviä elokuvasuosituksia.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Tuotesuosituksen tai seuraavan parhaan toiminnon määritelmä

Tavoitteeksi määritetään palvelun käytöstä saatavan summan maksimointi tarjoamalla hotellin asiakkaille heidän kiinnostuksen kohteitaan parhaiten vastaavia palveluja.

### <a name="featurization"></a>Ominaisuuksien kehitys

Vaihtuvuusmallin tavoin hotellin ServiceCustomerID ja asiakastunnus yhdistetään, jotta asiakastunnuksen perusteella voidaan muodostaa yhdenmukaisia suosituksia.

![Suositusmallin ominaisuuksien kehitys](media/azure-machine-learning-model-featurization.png)

Tiedot hankitaan kolmesta eri entiteetistä ja ominaisuudet johdetaan niistä. Suositusongelman ominaisuuksien kehitys on erilaista kuin vaihtuvuus- tai CLTV-skenaarioissa. Suositusmalliin tarvitaan tietoja kolmena ominaisuusjoukkona.

### <a name="model-selection"></a>Mallin valinta

Tuotteita tai palveluja ennustetaan käyttämällä **Train Matchbox Recommender**-algoritmia suositusmallin kouluttamiseen.

![Tuotesuositusalgoritmi](media/azure-machine-learning-model-recommendation-algorithm.png)

**Train Matchbox Recommender** -mallin kolmeen syöttöporttiin syötetään koulutuspalvelun käyttötiedot, asiakkaan kuvaus (valinnainen) ja palvelun kuvaus. Malli voidaan pisteyttää kolmella eri tavalla. Yhtä tapaa käytetään arvioimaan mallia, jossa arvioidut nimikkeet sijoitetaan järjestykseen laskemalla NDCG (Normalized Discounted Cumulative Gain) -pistemäärä. Tässä kokeilussa NDCG-pistemäärä on 0,97. Kahdessa muussa vaihtoehdossa malli pisteytetään koko suositeltavan palveluluettelon perusteella tai vain ne nimikkeet pisteytetään, joita käyttäjät eivät ole aiemmin käyttäneet.

Kun koko palveluluettelon suositusten jakautumista tarkastellaan lähemmin, eniten suositeltavia palveluja ovat puhelin-, WiFi- ja kuriiripalvelut. Tämä vastaa sitä, mitä on havaittu palvelujen kulutustietojen jakautumisessa:

![Suositusmallin tulokset](media/azure-machine-learning-model-output.png)

Koko [tuotesuosituskokeilu on saatavana Azure AI Galleryssä.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Mukautettujen mallien integrointi

Näiden ennusteiden käyttö Customer Insightsissa edellyttää, että ennusteet ja asiakastunnukset **viedään**. [Vie ne samaan Azure Blob -säilösijaintiin](/azure/storage/common/storage-import-export-data-from-blobs), johon veit lähdetiedot. Ennakoiva verkkopalvelu voidaan aikatauluttaa päivittämään pistemäärät säännöllisesti.

Mukautetun mallin luomia tietoja voidaan käyttää rikastuttamaan asiakastietoja entisestään. Lisätietoja on aiheessa [Mukautetut koneoppimismallit](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]