---
title: Dynamics 365 -sovellusten asiakaskortin apuohjelma (sisältää videon)
description: Näytä Customer Insightsin asiakasprofiilitiedot Dynamics 365 -sovelluksissa tämän apuohjelman avulla.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 2dfa6c643cbe9a8531a085d8ce01b0f64776476f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646033"
---
# <a name="customer-card-add-in-preview"></a>Asiakaskortin apuohjelma (esiversio)



Saat kokonaisvaltainen näkymän asiakkaista suoraan Dynamics 365 -sovelluksissa. Kun asiakaskortin apuohjelma on asennettu tuettuun Dynamics 365 -sovellukseen, voit valita, näytetäänkö asiakasprofiilin kentät, tiedot ja aktiviteetin aikajana. Apuohjelma hakee tietoja Customer Insights -sovelluksesta vaikuttamatta yhdistetyn Dynamics 365 -sovelluksen tietoihin.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Edellytykset

- Apuohjelma toimii vain Dynamics 365 - mallipohjaisissa sovelluksissa, kuten Salesissa tai Customer Servicen versiossa 9.0 ja uudemmissa.
- Dynamics 365 -tietojen yhdistäminen Customer Insightsin asiakasprofiileihin kannattaa tehdä [käsittelemällä ne Dynamics 365 -sovelluksessa Microsoft Dataverse -yhdistimen avulla](connect-power-query.md). Jos Dynamics 365 -yhteystietoja (tai -asiakkaita) käsitellään jollain muulla tavalla, on varmistettava, että `contactid`- (tai `accountid`) -kenttä on määritetty [kyseisen tietolähteen perusavaimeksi tietojen yhtenäistämisprosessin yhdistämisvaiheessa](map-entities.md#select-primary-key-and-semantic-type-for-attributes). 
- Kaikki asiakaskortin lisäosan Dynamics 365 -käyttäjät on [lisättävä käyttäjinä](permissions.md) Customer Insights -tietoihin, jotta he näkevät tiedot.
- Customer Insightsin [määritetyt haku- ja suodatusominaisuudet](search-filter-index.md) ovat pakollisia, jotta tietojen valinta toimisi.
- Kukin apuohjelman ohjausobjekti perustuu tiettyihin tietoihin Customer Insightsissa. Jotkin tiedot ja ohjausobjektit ovat käytettävissä vain tietyntyyppisissä ympäristöissä. Apuohjelman kokoonpano antaa ilmoituksen, jos jokin ohjausobjekti ei ole käytettävissä valitun ympäristötyypin vuoksi. Lisätietoja [ympäristön käyttötapauksista](work-with-business-accounts.md).
  - **Mittarin ohjausobjekti**: Vaatii asiakasmääritetyyppisiä [määritettyjä mittareita](measures.md).
  - **Älykkyyden hallinta**: Edellyttää [ennusteiden tai mukautettujen mallien](predictions-overview.md) avulla luotuja tietoja.
  - **Asiakkaan tietojen ohjausobjekti**: Profiilin kaikki kentät ovat käytettävissä yhtenäisessä asiakasprofiilissa.
  - **Rikastus-ohjausobjekti**: edellyttää aktiivisia [rikastuksia](enrichment-hub.md), joita käytetään asiakasprofiileihin. Korttilisäosa tukee seuraavia rikastuksia: Microsoftin tuottamat [tuotemerkit](enrichment-microsoft.md), [kiinnostuksen kohteet](enrichment-microsoft.md) ja [Office-vuorovaikutustiedot](enrichment-office.md).
  - **Yhteyshenkilöiden ohjausobjekti**: Edellyttää yhteyshenkilötyyppisen semanttisen entiteetin määrittelemistä.
  - **Aikajanan ohjausobjekti**: Edellyttää [määritettyjä aktiviteetteja](activities.md).

## <a name="install-the-customer-card-add-in"></a>Asiakaskortin apuohjelman asentaminen

Asiakaskortin apuohjelma on Dynamics 365:n Customer Engagement -sovellusten ratkaisu. Jos haluat asentaa ratkaisun, siirry AppSourceen ja hae sanalla **Dynamics Customer Card**. Valitse [Customer Card Add-in AppSourcessa](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) ja sitten **Hanki nyt**.

Ratkaisun asentaminen voi edellyttää kirjautumista Dynamics 365 -sovelluksen järjestelmänvalvojan tunnistetiedoilla. Ratkaisun asentaminen ympäristöön voi kestää jonkin aikaa.

## <a name="configure-the-customer-card-add-in"></a>Asiakaskortin apuohjelman määrittäminen

1. Siirry järjestelmänvalvojana Dynamics 365:n **Asetukset**-osaan ja valitse **Ratkaisut**.

1. Valitse **Näyttönimi**-linkki **Dynamics 365 Customer Insights – Asiakaskortti-apuohjelma (esiversio)** -ratkaisulle.

   > [!div class="mx-imgBorder"]
   > ![Näyttönimen valinta.](media/select-display-name.png "Valitse näyttönimi.")

1. Valitse **Kirjaudu sisään** ja anna sen järjestelmänvalvojatilin tunniste tiedot, jota käytät Customer Insightsin määrittämiseen.

   > [!NOTE]
   > Tarkista, että selaimen ponnahdusikkunoiden estotoiminto ei estä todennusikkunan avautumista, kun valitset **Kirjaudu sisään**-painikkeen.

1. Valitse se Customer Insights -ympäristö, josta haluat noutaa tietoja.

1. Määritä Dynamics 365 -sovelluksen tietueiden kenttien yhdistämismääritys. Customer Insights -tiedoistasi riippuen voit valita seuraavista yhdistämisvaihtoehdoista:
   - Yhteyshenkilö yhdistetään valitsemalla asiakasentiteetissä kenttä, joka vastaa yhteyshenkilöentiteetin tunnusta.
   - Tili yhdistetään valitsemalla asiakasentiteetissä kenttä, joka vastaa tilientiteetin tunnusta.

   > [!div class="mx-imgBorder"]
   > ![Yhteyshenkilön tunnus -kenttä.](media/contact-id-field.png "Yhteyshenkilön tunnus -kenttä.")

1. Tallenna asetukset valitsemalla **Tallenna määritys**.

1. Seuraavaksi sinun täytyy määrittää käyttöoikeusroolit Dynamics 365:ssä, jotta käyttäjät voivat mukauttaa ja nähdä asiakaskortin. Valitse Dynamics 365:ssä **Asetukset** > **Suojaus** > **Käyttäjät**. Valitse käyttäjät, joiden käyttäjärooleja haluat muokata, ja valitse **Roolien hallinta**.

1. Delegoi **Customer Insights -kortin mukauttaja** -rooli käyttäjille, jotka mukauttavat koko organisaation kortissa näkemää sisältöä.

## <a name="add-customer-card-controls-to-forms"></a>Asiakaskortin ohjausobjektien lisääminen lomakkeisiin

Skenaariosta riippuen voit valita ohjausobjekteja joko **Yhteyshenkilö**-lomakkeeseen tai **Tili**-lomakkeeseen. Jos Customer Insights -ympäristösi on yritystilejä varten, on suositeltavaa lisätä ohjausobjektit Tili-lomakkeeseen. Korvaa tässä tapauksessa "yhteyshenkilö" alla olevissa vaiheessa tunnuksella "tili".

1. Voit lisätä Asiakaskortti-ohjausobjekteja Yhteyshenkilö-lomakkeeseen siirtymällä Dynamics 365 -järjestelmässä kohtaan **Asetukset** > **Mukautukset**.

1. Valitse **Mukauta järjestelmää**.

1. Siirry **Yhteyshenkilö**-entiteettiin, laajenna se ja valitse sitten **Lomakkeet**.

1. Valitse yhteyshenkilölomake, jonka haluat lisätä asiakaskortin ohjausobjekteihin.

    > [!div class="mx-imgBorder"]
    > ![Yhteyshenkilölomakkeen valitseminen.](media/contact-active-forms.png "Valitse yhteyshenkilölomake.")

1. Voit lisätä ohjausobjektin vetämällä kentän lomake-editorissa **kenttien hallinnasta** kohtaan, johon haluat sijoittaa ohjausobjektin.

1. Valitse juuri lisätty lomakkeen kenttä ja valitse sitten **Muuta ominaisuuksia**.

1. Valitse **Ohjausobjektit**-välilehdessä **Lisää ohjausobjekti**. Valitse jokin käytettävissä olevista mukautetuista ohjausobjekteistä ja valitse sitten **Lisää**.

1. Poista **Kentän ominaisuudet** -valintaikkunassa **Näytä otsikko lomakkeessa** -valintaruudun valinta.

1. Valitse ohjausobjektille asetus **WWW**. Jos kyseessä on rikastusohjausobjekti, valitse näytettävä rikastustyyppi määrittämällä **enrichmentType**-kenttä. Lisää jokaiselle rikastustyypille erillinen rikastusohjausobjekti.

1. Julkaise päivitetty yhteyshenkilölomake valitsemalla **Tallenna** ja **Julkaise**.

1. Siirry julkaistuun yhteyshenkilölomakkeeseen. Näet juuri lisätyn ohjausobjektin. Kirjautuminen voi olla välttämätöntä, kun sitä käytetään ensimmäisen kerran.

1. Voit mukauttaa mukautetussa ohjausobjektissa näkyviä tietoja valitsemalla muokkauspainikkeen oikeassa yläkulmassa.

## <a name="upgrade-customer-card-add-in"></a>Asiakaskortin apuohjelman päivittäminen

Asiakaskortin apuohjelmaa ei päivitetä automaattisesti. Jos haluat päivittää uusimpaan versioon, toimi seuraavasti Dynamics 365 -sovelluksessa, johon apuohjelma on asennettu.

1. Siirry Dynamics 365 -sovelluksissa kohtaan **Asetukset** > **Mukauttaminen** ja valitse **Ratkaisut**.

1. Etsi apuohjelmien taulukosta **CustomerInsightsCustomerCard** ja valitse rivi.

1. Valitse **Ota ratkaisun päivitys käyttöön** toimintorivillä.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Ratkaisun päivittäminen Dynamics 365 -sovellusten Mukauttaminen-alueella.":::

1. Kun olet käynnistänut päivityksen, latausilmaisin näkyy päivityksen valmistumiseen asti. Jos uudempia versioja ei ole, päivitys näyttää virhesanoman.

## <a name="troubleshooting"></a>Vianmääritys

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Asiakaskortin apuohjelman ohjausobjektit eivät löydä tietoja

**Ongelma:**

Vaikka tunnuskentät olisi määritetty oikein, ohjausobjektit eivät löydä tietoja asiakkailta.  

**Ratkaisu:**

1. Varmista, että olet määrittänyt kortin apuohjelman ohjeiden mukaisesti: [Asiakaskortin apuohjelman määrittäminen](#configure-the-customer-card-add-in) 

1. Tarkista tietojen käytön konfiguraatio. Muokkaa Dynamics 365 -järjestelmän tietolähdettä, joka sisältää yhteyshenkilön tunnuksen GUID-tunnuksen. Jos Power Query -editorissa näkyy yhteyshenkilön tunnuksen GUID-tunnus ja siinä on isoja kirjaimia, kokeile seuraavia: 
    1. Muokkaa tietolähdettä ja avaa tietolähde Power Query -editorissa.
    1. Valitse yhteyshenkilön tunnussarake.
    1. Valitse **Muunna** otsikkoriviltä nähdäksesi saatavilla olevat toiminnot.
    1. Valitse **pieni kirjain**. Tarkista, ovatko taulukon GUID-tunnukset nyt pieniä kirjaimia.
    1. Tallenna tietolähde.
    1. Suorita tietojen käsittely, yhdistäminen ja jatkoprosessit, jotta muutokset välitetään GUID-tunnukseen. 

Kun täydellinen päivitys on suoritettu, odotettujen tietojen pitäisi näkyä asiakaskortin apuohjelman ohjausobjekteissa. 

[!INCLUDE [footer-include](includes/footer-banner.md)]
