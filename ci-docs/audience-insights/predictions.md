---
title: Osittaisten tietojen viimeisteleminen ennusteiden avulla
description: Puutteellisten asiakastietojen täydentäminen ennusteiden avulla.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3100acf383d85c00a6ff0a8ebc54e038bd813427
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732400"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Osittaisten tietojen täydentäminen ennusteilla (vanhentunut)

> [!IMPORTANT]
> Tämä ominaisuus **vanhentuu** **5.11.2021** alkaen. Nykyiset toteutukset toimivat, kunnes toiminto poistetaan, mutta uusia integrointeja ei voi luoda alla olevan ohjeen mukaisesti.

Ennusteiden avulla voit helposti luoda ennustettuja arvoja, jotka auttavat ymmärtämään asiakasta aiempaa paremmin. Valitsemalla **Analytiikka** > **Ennusteet**-sivulla **Omat ennusteet** näkyviin tulee ennusteet, jotka on määritetty toisaalla käyttäjäryhmän merkityksellisissä tiedoissa ja joiden avulla ennusteita voi mukauttaa entisestään.

> [!NOTE]
> Et voi käyttää tätä toimintoa, jos ympäristössä on käytössä Azure Data Lake Gen 2 -tallennustila.
>
> Ennustetoiminto käyttää automaattisia ominaisuuksia tietojen arvioinnissa ja se tekee ennusteet näiden tietojen perusteella. Sen vuoksi sitä voi käyttää profiloinnissa. Tämä termi on määritetty yleisissä tietosuoja-asetuksissa (GDPR). Asiakkaat käyttävät tätä toimintoa tietojen käsittelyyn. GDPR tai muut lait tai säädökset saattavat ohjata toiminnon käyttöä. Olet vastuussa siitä, että Dynamics 365 Customer Insightsin käyttäminen, myös ennusteiden käyttäminen, on kaikkien lakien ja säädösten mukaista. Näihin kuuluvat yksityisyyteen, henkilökohtaisiin tietoihin, biometrisiin tietoihin, tietosuojaan ja viestintäsalaisuuteen liittyvät lait.

## <a name="prerequisites"></a>Edellytykset

Ennen kuin organisaatio voi käyttää ennustetoimintoa, seuraavien edellytykset on toteuduttava:

1. Organisaatiossasi on esiintymä, joka on [määritetty Microsoft Dataversessä](/ai-builder/build-model#prerequisites) ja se on samassa organisaatiossa kuin Customer Insights.

2. Käyttäjäryhmäsi tiedot on liitetty Dataverse-esiintymääsi.

Lisätietoja on kohdassa [Uuden ympäristön luominen](create-environment.md).

## <a name="create-a-prediction-in-the-customer-entity"></a>Ennusteen luominen asiakasentiteetissä

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Entiteetit**.

2. Valitse **asiakasentiteetti**.

3. Valitse **Asiakas: CustomerInsights** -entiteetissä **Kentät**-välilehti.

4. Etsi sen määritteen nimi, jolle haluat ennustaa arvot, ja valitse sitten **Yleiskatsaus**-kuvake **Yhteenveto**-sarakkeessa.
   > [!div class="mx-imgBorder"]
   > ![Yleiskatsaus-kuvake.](media/intelligence-overviewicon.png "Yleiskatsaus-kuvake")

5. Jos määritteeltä puuttuu paljon arvoja, valitse **Ennusta puuttuvat arvot** ja jatka ennusteen määrittämistä.
   > [!div class="mx-imgBorder"]
   > ![Yleiskatsauksen tila ja ennusteen puuttuvat arvot -painike näkyvissä.](media/intelligence-overviewpredictmissingvalues.png "Yleiskatsauksen tila ja ennusteen puuttuvat arvot -painike näkyvissä")

6. Anna **näyttönimi** ja **tulosentiteetin nimi** ennusteen tuloksia varten.

7. Näkyviin tulee valmiiksi määritetty asetusluettelo, jossa voit yhdistää arvot ennustettua luokkaa varten. Tässä tapauksessa luokan asetuksia ovat vain 0 ja 1, koska ne vastaavat tosi-/epätosi-arvoja tai ennusteen binaarista luonnetta. Yhdistä Luokka-sarakkeessa kentän arvot, jotka haluat luokitella arvolla 0 lopullisessa ennusteessa, ja nimikkeet, jotka haluat luokitella arvolla 1 lopullisessa ennusteessa.
   > [!div class="mx-imgBorder"]
   > ![Esimerkki kentän arvojen ja luokkien yhdistämisestä.](media/intelligence-categorymapping.png "Esimerkki kentän arvojen ja luokkien yhdistämisestä")

8. Valitse **Valmis**. Ennustetta aletaan käsitellä. Käsittelyn kesto riippuu tietojen koosta ja monimuotoisuudesta. Tulokset ovat käytettävissä uudessa entiteetissä luodun ennusteen **tulosentiteetin nimen** perusteella.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Luo ennuste segmentin luomisen aikana

Tietyn määritteen puuttuvien arvojen ennustaminen valinnaisesti on mahdollista myös segmentin luomisen aikana. Erityisesti silloin, kun luot segmentin nopeasti yhdistetyn asiakasentiteetin tai asiakasmittarientiteetin perusteella.

Tämän prosessin osana valitaan tietty määrite, johon segmentti perustuu. Se voi olla vaikkapa asiakastyytyväisyys tai ostojen summa. Segmenttiä luotaessa järjestelmä ehdottaa tapaa, jolla kyseisen määritteen puuttuvat arvot ennustetaan.

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Segmentit** ja valitse sitten **Profiilit**-ruutu.

2. Valitse **Kenttä**, jos haluat luoda segmentin, ja valitse sitten **Operaattori**. Valitse lopuksi **Tarkista**.

3. Anna segmentille **nimi** ja **näyttönimi**.

4. Valitse **Tallenna**.

5. Jos luodun segmentin lähdekentän tiedot ovat vaillinaiset, voit valita puuttuvien arvojen ennustamisen.
   > [!div class="mx-imgBorder"]
   > ![Ennuste-painike.](media/segments-predictoption.png "Ennuste-painike")

6. Anna **näyttönimi** ja **tulosentiteetin nimi** ennusteen tuloksia varten.

7. Valitse **Valmis**. Ennuste luodaan pian uudessa entiteetissä, jonka nimenä on **Tulosentiteetin nimi** -kohdassa antamasi nimi.

## <a name="view-a-prediction"></a>Tarkastele ennustetta

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Analytiikka** > **Ennusteet** > **Omat ennusteet**.

2. Valitse ennuste, jota haluat tarkastella.

3. Valitse **Toiminnot**-sarakkeen kolme pistettä ja valitse sitten **Tarkastele**.

4. Näkyviin tulee arvopisteiden määrä ennustenäkymässä.
   > [!div class="mx-imgBorder"]
   > ![Ennusteet-sivu.](media/intelligence-predictionsviewpage.png "Ennusteet-sivu")

   - **Ennustetut arvot** osoittavat täsmäytyksen, joka luotiin kentän arvon ja luokan täsmäytysvaiheessa. Ne ovat tietojoukon arvoja, jotka on yhdistetty tiettyyn luokkaan.
   -**Tärkeimmät vaikuttajat** ovat tietojoukon tekijöitä, jotka todennäköisimmin vaikuttavat ennusteen luotettavuuteen kentän arvon ja tietyn luokan täsmäytyksessä.
   - **Suorituskyky** osoittaa, miten ennusteet onnistuvat. Valitse tämä linkki, jos haluat lisätietoja.
   - **Esikatselu**-kohdassa on esimerkkejä ennusteen tulostietojoukosta ja ennustetun arvon todennäköisyys tai luotettavuus. 0 tarkoittaa epävarmaa ja 1 varmaa.

## <a name="update-a-prediction"></a>Päivitä ennuste

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Analytiikka** > **Ennusteet** > **Omat ennusteet**.

2. Valitse päivitettävä ennuste ja valitse sitten **Päivitä**-kuvake.

3. Ennuste ajoitetaan käsittelyä varten. Näet edellisen päivitysajankohdan **Päivitetty**-sarakkeessa **Ennusteet**-sivulla.

## <a name="edit-a-prediction"></a>Muokkaa ennustetta

Kun olet luonut ennusteen, voit mukauttaa mallia AI Builderissa ja tehostaa mallin toimintaa.  

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Analytiikka** > **Ennusteet** > **Omat ennusteet**.

2. Valitse ennuste, jota haluat muokata.

3. Valitse **Toiminnot**-sarakkeen kolme pistettä ja valitse sitten **Tarkastele**.

4. Valitse **Mukauta AI Builderissa**.

5. Päivitä malli AI Builderissa. [Lisätietoja mallien hallinnasta AI builderissa](/ai-builder/manage-model#retrain-and-republish-existing-models).

Ennusteen seuraava suoritus käyttää luomaasi päivitettyä mallia.

> [!NOTE]
> AI Builderissa luodut uudet mallit eivät näy käyttäjäryhmän merkityksellisissä tiedoissa, ellei mallia luotu edellä mainituista kokemuksista.

## <a name="remove-a-prediction"></a>Poista ennuste

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Analytiikka** > **Ennusteet** > **Omat ennusteet**.

2. Valitse poistettava ennuste.

3. Valitse **Toiminnot**-sarakkeen kolme pistettä ja valitse sitten **Poista**.

4. Vahvista poisto.

## <a name="troubleshooting"></a>Vianmääritys

Jos Dataversen liittämisprosessia ei voi suorittaa virheen vuoksi, voit yrittää suorittaa prosessin manuaalisesti. Liittämisprosessissa voi esiintyä kaksi tunnettua ongelmaa:

- Asiakaskortin apuohjelmaratkaisua ei ole asennettu.
    1. [Asenna ja määritä ratkaisu noudattamalla ohjeita](customer-card-add-in.md).

- Sovellusoikeuksia ei myönnetä.
    1. Siirry [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com)en.
    1. Valitse **Ympäristöt**.
    1. Valitse sen ympäristön vieressä oleva kolme pistettä, johon haluat lisätä oikeudet, ja valitse sitten **Asetukset**.
    1. Laajenna **Käyttäjät ja oikeudet** ja valitse **Käyttäjät**.
    1. Valitse **+ Uusi** ja valitse sitten **Käyttäjä**.
    1. Valitse **Sovelluksen käyttäjä**, jos sitä ei ole jo valittu, ja anna seuraavat tiedot:
        - **Käyttäjänimi:** cihelp@microsoft.com
        - **Sovellustunnus:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Etunimi:** Customer
        - **Sukunimi:** Insights
        - **Ensisijainen sähköposti:** cihelp@microsoft.com
    1. Valitse **Tallenna ja sulje**.
    1. Valitse juuri luotu käyttäjä.
    1. Valitse yläosan valikkopalkista **Hallitse rooleja**.
    1. Valitse **Järjestelmänvalvoja** ja valitse sitten **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
