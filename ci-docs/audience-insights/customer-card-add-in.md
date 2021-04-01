---
title: Asiakaskortin apuohjelman asentaminen ja määrittäminen
description: Dynamics 365 Customer Insightsin asiakaskortin apuohjelman asentaminen ja määrittäminen.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597323"
---
# <a name="customer-card-add-in-preview"></a>Asiakaskortin apuohjelma (esiversio)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Saat kokonaisvaltainen näkymän asiakkaista suoraan Dynamics 365 -sovelluksissa. Tarkastele demografiatietoja, näkemyksiä ja aktiviteettiaikajanoja asiakaskortin apuohjelman avulla.

## <a name="prerequisites"></a>Edellytykset

- Dynamics 365 -sovellus (kuten myyntikeskus tai asiakaspalvelukeskus), versio 9.0 tai uudempi, jossa Unified Interface käytössä.
- Asiakasprofiilit [käsitellään Dynamics 365 -sovelluksessa Common Data Servicen avulla](connect-power-query.md).
- Asiakaskortin lisäosan käyttäjät on [lisättävä käyttäjinä](permissions.md) käyttäjäryhmän merkityksellisissä tiedoissa.
- [Määritetyt haku- ja suodatusominaisuudet ](search-filter-index.md).
- Demografiatietojen ohjausobjekti: demografiset kentät (kuten ikä tai sukupuoli), ovat käytettävissä yhdistetyssä asiakasprofiilissa.
- Rikastus-ohjausobjekti: edellyttää aktiivisia [rikastuksia](enrichment-hub.md), joita käytetään asiakasprofiileihin.
- Analytiikan ohjausobjekti: edellyttää tietoja, jotka on luotu käyttämällä Azuren automaattianalyysipalveluita ([ennusteet](predictions.md) tai [mukautetut mallit](custom-models.md))
- Mittarin ohjausobjekti: edellyttää [määritettyjä mittareita](measures.md).
- Aikajanan ohjausobjekti: edellyttää [määritettyjä aktiviteetteja](activities.md).

## <a name="install-the-customer-card-add-in"></a>Asiakaskortin apuohjelman asentaminen

Asiakaskortin apuohjelma on Dynamics 365:n Customer Engagement -sovellusten ratkaisu. Jos haluat asentaa ratkaisun, siirry AppSourceen ja hae sanalla **Dynamics Customer Card**. Valitse [Customer Card Add-in AppSourcessa](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) ja sitten **Hanki nyt**.

Ratkaisun asentaminen voi edellyttää kirjautumista Dynamics 365 -sovelluksen järjestelmänvalvojan tunnistetiedoilla.

Ratkaisun asentaminen ympäristöön voi kestää jonkin aikaa.

## <a name="configure-the-customer-card-add-in"></a>Asiakaskortin apuohjelman määrittäminen

1. Siirry järjestelmänvalvojana Dynamics 365:n **Asetukset**-osaan ja valitse **Ratkaisut**.

1. Valitse **Näyttönimi**-linkki **Dynamics 365 Customer Insights – Asiakaskortti-apuohjelma (esiversio)** -ratkaisulle.

   > [!div class="mx-imgBorder"]
   > ![Näyttönimen valinta](media/select-display-name.png "Näyttönimen valinta")

1. Valitse **Kirjaudu sisään** ja anna sen järjestelmänvalvojatilin tunniste tiedot, jota käytät Customer Insightsin määrittämiseen.

   > [!NOTE]
   > Tarkista, että selaimen ponnahdusikkunoiden estotoiminto ei estä todennusikkunan avautumista, kun valitset **Kirjaudu sisään**-painikkeen.

1. Valitse ympäristö, josta tietoja noudetaan.

1. Määritä, mikä kenttä yhdistetään tietueisiin Dynamics 365 -sovelluksessa.
   - Yhteyshenkilö yhdistetään valitsemalla asiakasentiteetissä kenttä, joka vastaa yhteyshenkilöentiteetin tunnusta.
   - Tili yhdistetään valitsemalla asiakasentiteetissä kenttä, joka vastaa tilientiteetin tunnusta.

   > [!div class="mx-imgBorder"]
   > ![Yhteyshenkilön tunnus -kenttä](media/contact-id-field.png "Yhteyshenkilön tunnus -kenttä")

1. Tallenna asetukset valitsemalla **Tallenna määritys**.

1. Seuraavaksi sinun täytyy määrittää käyttöoikeusroolit Dynamics 365:ssä, jotta käyttäjät voivat mukauttaa ja nähdä asiakaskortin. Valitse Dynamics 365:ssä **Asetukset** > **Suojaus** > **Käyttäjät**. Valitse käyttäjät, joiden käyttäjärooleja haluat muokata, ja valitse **Roolien hallinta**.

1. Delegoi **Customer Insights -kortin mukauttaja** -rooli käyttäjille, jotka mukauttavat koko organisaation kortissa näkemää sisältöä.

## <a name="add-customer-card-controls-to-forms"></a>Asiakaskortin ohjausobjektien lisääminen lomakkeisiin
  
1. Voit lisätä Asiakaskortti-ohjausobjekteja Yhteyshenkilö-lomakkeeseen siirtymällä Dynamics 365 -järjestelmässä kohtaan **Asetukset** > **Mukautukset**.

1. Valitse **Mukauta järjestelmää**.

1. Siirry **Yhteyshenkilö**-entiteettiin, laajenna se ja valitse sitten **Lomakkeet**.

1. Valitse yhteyshenkilölomake, jonka haluat lisätä asiakaskortin ohjausobjekteihin.

    > [!div class="mx-imgBorder"]
    > ![Yhteyshenkilölomakkeen valitseminen](media/contact-active-forms.png "Yhteyshenkilölomakkeen valitseminen")

1. Voit lisätä ohjausobjektin vetämällä kentän lomake-editorissa **kenttien hallinnasta** kohtaan, johon haluat sijoittaa ohjausobjektin.

1. Valitse juuri lisätty lomakkeen kenttä ja valitse sitten **Muuta ominaisuuksia**.

1. Valitse **Ohjausobjektit**-välilehdessä **Lisää ohjausobjekti**. Valitse jokin käytettävissä olevista mukautetuista ohjausobjekteistä ja valitse sitten **Lisää**.

1. Poista **Kentän ominaisuudet** -valintaikkunassa **Näytä otsikko lomakkeessa** -valintaruudun valinta.

1. Valitse ohjausobjektille asetus **WWW**. Jos kyseessä on rikastusohjausobjekti, valitse näytettävä rikastustyyppi määrittämällä **enrichmentType**-kenttä. Lisää jokaiselle rikastustyypille erillinen rikastusohjausobjekti.

1. Julkaise päivitetty yhteyshenkilölomake valitsemalla **Tallenna** ja **Julkaise**.

1. Siirry julkaistuun yhteyshenkilölomakkeeseen. Näet juuri lisätyn ohjausobjektin. Kirjautuminen voi olla välttämätöntä, kun sitä käytetään ensimmäisen kerran.

1. Voit mukauttaa mukautetussa ohjausobjektissa näkyviä tietoja valitsemalla muokkauspainikkeen oikeassa yläkulmassa.

## <a name="upgrade-customer-card-add-in"></a>Asiakaskortin apuohjelman päivittäminen
Asiakaskortin apuohjelmaa ei päivitetä automaattisesti. Voit päivittää uusimman version toimimalla seuraavasti Dynamics 365 -sovelluksessa, johon apuohjelma on asennettu.

1. Siirry Dynamics 365 -sovelluksissa kohtaan **Asetukset** > **Mukauttaminen** ja valitse **Ratkaisut**.

1. Etsi apuohjelmien taulukosta **CustomerInsightsCustomerCard** ja valitse rivi.

1. Valitse **Ota ratkaisun päivitys käyttöön** toimintorivillä.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Ratkaisun päivittäminen Dynamics 365 -sovellusten Mukauttaminen-alueella":::

1. Kun olet käynnistänut päivityksen, latausilmaisin näkyy päivityksen valmistumiseen asti. Jos uudempia versioja ei ole, päivitys näyttää virhesanoman.


[!INCLUDE[footer-include](../includes/footer-banner.md)]