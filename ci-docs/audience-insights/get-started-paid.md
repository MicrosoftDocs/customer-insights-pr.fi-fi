---
title: Customer Insightsin maksullisen käyttöoikeuden luominen ja määrittäminen
description: Vaiheet lisensoidun Dynamics 365 Customer Insights -tilauksen saaminen ja määrittäminen.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f8cf1be97ee8af46145a450009fd278b1821f8fe
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650464"
---
# <a name="get-started-with-a-paid-subscription"></a>Maksullisen tilauksen käytön aloittaminen

Tässä artikkelissa kerrotaan, miten luodaan uusi ympäristö sen jälkeen, kun organisaatio on ostanut Dynamics 365 Customer Insights -tilauksen. Jos haluat ostaa Customer Insightsin, yhteydenottovaihtoehtomme näkyvät [Dynamics 365 Customer Insights -verkkosivustolla](https://dynamics.microsoft.com/ai/customer-insights/). 

Jos haluat kokeilla palvelua ja ominaisuuksia, katso lisätietoja kohdasta [Kokeiluympäristön määrittäminen](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Ympäristön luominen aiemmin luodussa organisaatiossa

Kun asiakas on hankkinut tilauslisenssin Customer Insightsiin, Microsoft 365 -vuokraajan yleinen järjestelmänvalvoja saa sähköpostiviestin, jossa häntä kehotetaan luomaan ympäristö. Mene osoitteeseen [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) aloittaaksesi. 

Customer Insightsia ei ole lisensoitu käyttäjää kohden, joten se ei näy Käyttöoikeudet-alueessa. Jos etsit käyttöoikeutta Microsoft 365 -hallintakeskuksesta, siirry **Tuotteesi** -sivustoon. 

> [!NOTE]
> Organisaatiot voivat luoda *kaksi* ympäristöä jokaista Customer Insights -käyttöoikeutta varten. Jos organisaatiosi ostaa useamman kuin yhden käyttöoikeuden, [ota yhteyttä tukiryhmäämme](https://go.microsoft.com/fwlink/?linkid=2079641), jotta käytettävissä olevien ympäristöjen määrää voidaan lisätä. Saat lisätietoja kapasiteetista ja lisäkapasiteetista lataamalla [Dynamics 365 -käyttöoikeusoppaan](https://go.microsoft.com/fwlink/?LinkId=866544).

Ympäristön luominen:

1. Valitse **Luo ympäristö** -valintaikkunassa **Uusi ympäristö**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Valintaikkuna uuden ympäristön luomisesta Customer Insightsiin.":::

   Suosittelemme, että aloitat ympäristön määrittämisen alusta. Jos kuitenkin olet kokeiluympäristön järjestelmänvalvoja tai jäsen, voit [kopioida tietoja toisesta ympäristöstä](manage-environments.md#copy-the-environment-configuration) valitsemalla **Kopioi aiemmin luodusta ympäristöstä**. Näkyviin tulee luettelo kaikista organisaation käytettävissä olevista ympäristöistä, joista voit kopioida tietoja.

1. Anna seuraavat tiedot:
   - **Nimi**: Ympäristön nimi. Tämä kenttä on jo täytetty, jos kopioit tietoja aiemmin luodusta ympäristöstä, mutta voit muuttaa sitä.
   - **Alue**: Alue, jossa palvelu otetaan käyttöön ja jossa sitä isännöidään.
   - **Tyyppi**: Määritä, haluatko luoda tuotanto- vai eristysympäristön. Eristysympäristöt eivät salli ajoitettua tietojen päivittämistä, ja ne on tarkoitettu esikäyttöä ja testausta varten.
   
1. Valinnaisesti voit valita **Lisäasetukset**:

   - **Tallenna kaikki tiedot kohteeseen**: Määrittää, minne haluat tallentaa Customer Insightsin tulostiedot. Käytettävissä on kaksi vaihtoehtoa: **Customer Insights -tallennustila** (Customer Insights -ryhmä hallinnoi Azure Data Lake -ratkaisussa) ja **Azure Data Lake Storage** (oma Azure Data Lake Storage). Oletusarvoisesi Customer Insights -tallennustila -vaihtoehto on valittu.

     > [!NOTE]
     > Tallentamalla tiedot Azure Data Lake Storageen hyväksyt, että tiedot siirretään ja tallennetaan kyseisen Azure-tallennustilin asianmukaiseen maantieteelliseen sijaintiin. Tämä sijainti voi olla eri kuin sijainti, johon tiedot on tallennettu Dynamics 365 Customer Insightsissa. [Lisätietoja on Microsoftin luottamuskeskuksessa.](https://www.microsoft.com/trust-center)
     >
     > Tällä hetkellä käsitellyt entiteetit Power BIn tietovoista tallennetaan Microsoft Dataversen hallitsemaan Data Lake -tallennustilaan. 
     > 
     > Vain ympäristön luomisen aikana käytetyn Azure-alueen Azure Data Lake Storage -tilejä tuetaan. 
     > 
     > Vain niitä Azure Data Lake Storage -tilejä tuetaan, joille on valittu hierarkkinen nimitila.


   - Voit valita Azure Data Lake Storage -asetukselle resurssi- tai tilausperustaisen asetuksen todentamista varten. Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md). **Säilön** nimeä ei voi muuttaa, ja se tulee olemaan `customerinsights`.
   
   - Jos haluat käyttää [valmiita malleja](predictions-overview.md#out-of-box-models), määrittää tietojen jakamisen Microsoft Dataverse -järjestelmän kanssa tai ottaa käyttöön paikallisten tietolähteiden tietojen käyttämisen, anna Microsoft Dataverse -ympäristön URL-osoite kohdassa **Tietojen jakamisen määrittäminen Microsoft Dataversessä ja lisäominaisuuksien ottaminen käyttöön**. Valitse **Ota käyttöön tietojen jakaminen**, jos haluat jakaa Customer Insightsin tulostiedot Microsoft Dataversen hallitun Data Laken kanssa.

     > [!NOTE]
     > - Tietojen jakamista Microsoft Dataversen hallitun Data Laken kanssa ei tueta tällä hetkellä, jos kaikki tiedot tallennetaan omaan Azure Data Lake Storage -ratkaisuun.
     > - [Entiteettien puuttuvien arvojen ennustetta](predictions.md) ei tueta tällä hetkellä, kun otat tietojen jakamisen käyttöön Microsoft Dataversen hallitun Data Laken kanssa.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Määritysvalinnat tietojen jakamista varten Microsoft Dataversen kanssa.":::

   Kun järjestelmäprosessit, kuten tietojenkäsitteleminen, ovat valmiit, järjestelmä luo vastaavat kansiot määrittämällesi tallennustilille. Datatiedostot ja model.json-tiedostot luodaan ja lisätään kansioihin prosessin nimen perusteella.

   Jos luot useita Customer Insights -ympäristöjä ja valitset kyseisten ympäristöjen tuloste-entiteettien tallentamisen tallennustilille, kullekin ympäristölle luodaan erilliset kansiot siten, että säilössä on ci_<environmentid>.

1. Valitse **Luo** määrittääksesi ympäristön. 

## <a name="configure-an-environment"></a>Ympäristön määrittäminen

Seuraavien artikkelien avulla voit aloittaa Customer Insightsin määrittämisen. 

- [Lisää käyttäjiä ja määritä käyttöoikeuksia](permissions.md).
- [Käytä tietolähteitäsi](data-sources.md) ja suorita ne [tietojen yhdistämisprosessin](data-unification.md) avulla [yhtenäisten asiakasprofiilien](customer-profiles.md) aikaansaamiseksi.
- [Rikastuta yhtenäisiä asiakasprofiileja](enrichment-hub.md) tai [suorita ennustavia malleja](predictions-overview.md).
- Luo [segmenttejä](segments.md) ryhmitelläksesi asiakkaita ja [mittoja](measures.md) KPI-arvosteluille.
- Määritä [yhteydet](connections.md) ja [vienti](export-destinations.md), jotta voit käsitellä tietojen alijoukkoja muissa sovelluksissa.
