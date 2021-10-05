---
title: Customer Insightsin kokeiluversion luominen ja määrittäminen
description: Vaiheet Dynamics 365 Customer Insights -tilauksen kokeiluversion saamiseen ja määrittämiseen.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3a235e924395a606b9332de3d205289288a597a9
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558819"
---
# <a name="set-up-a-trial-environment"></a>Kokeiluympäristön määrittäminen 

Dynamics 365 Customer Insightsin kokeiluversion avulla voit tarkastella avainominaisuuksia ja oppia lisää eri ominaisuuksista. Kokeilutilaus poistetaan vanhenemisen jälkeen. Kokeiluympäristöt ovat yksittäisten käyttäjien luomia, ja heistä tulee kokeiluympäristöjensä järjestelmänvalvojia. He voivat kutsua lisää käyttäjiä kokeiluversioon ja määrittää eri ominaisuudet.

## <a name="create-a-trial-environment"></a>Kokeiluympäristön luominen

Voit rekisteröityä kokeiluversioon [kokeiluversion rekisteröitymissivulla](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Valitse ensin **Rekisteröidy ilmaisen kokeiluversion käyttäjäksi** ja sitten **Rekisteröidy nyt**.

1. Anna työ- tai koulusi sähköpostiosoite, kerro lisää itsestäsi ja valitse **Aloita**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Valintaikkuna kokeiluesiintymään rekisteröitymistä varten":::

1. Tutustu ehtoihin ja valitse hyväksyäksesi **Jatka**.

1. Anna uudelle ympäristölle **nimi**. 

1. Määritä ympäristön **tyypiksi** **Kokeiluversio**.

1. **Toimialan esittely** -kentässä voit halutessasi valita toimialakohtaisen tietojoukon. Voit myös [vaihtaa toimialan esittelyyn](#use-industry-specific-demo-data-sets-in-audience-insights) myöhemmin ja aloittaa oletustietosarjasta.

1. Valitse ympäristön **alue**.

1. Vaihtoehtoisesti, jos olet Dynamics 365 -organisaation järjestelmänvalvoja: Valitse **Lisäasetukset** ja anna organisaation URL-osoite, käyttääksesi ennusteominaisuuksia, kuten asiakasvaihtuvuuden ennuste. 

1. Valitse **Luo**. 

Ympäristön asennuksen valmistuminen kestää vain hetken. Valmistuttuasi sinut ohjataan demoympäristöön tai alan esittelyyn, jonka valitset yllä olevassa vaiheessa. Voit nyt tutustua sovellukseen vain luku -demotietojen avulla. Lisätietoja omien tietojen lisäämiseksi ympäristöön on kohdassa [Skenaariokohtaisten esittelytietojen luominen omassa ympäristössäsi](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Näyttökuva juuri luodusta kokeiluympäristöstä.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Toimialakohtaisten esittelytietokokonaisuuksien käyttö käyttäjäryhmän tiedoissa

Toteutujen tietolähteiden yhdistäminen on yksi Customer Insightsin käytön kriittisistä vaiheista. Jos haluat kokeilla ominaisuuksia häiritsemättä omia tietojasi, voit halutessasi käyttää toimialakohtaisia esittelytietoja. Esittelytietojoukkoja on saatavilla seuraaville toimialoille: 

-   Autot
-   Pankit
-   Kuluttajatuotteet
-   Julkishallinto
-   Terveydenhuolto
-   Hotelli- ja ravintola-ala
-   Vakuutus
-   Valmistava teollisuus
-   Asiantuntijapalvelut
-   Vähittäiskauppa

### <a name="see-industry-specific-demo-data-in-trials"></a>Katso toimialakohtaiset esittelytiedot kokeiluversioissa

Jos Customer Insights -versio on vain luku -versio, joka on räätälöity tietylle toimialalle tai skenaariolle, aloita Demo-ympäristöstä. 
 
1.  Valitse kohdeyleisö oivalluksista **Demo**-ympäristö ympäristövalitsin.

2.  Valitse **Aloitus**-kohdassa vaihtoehto avattavasta Valitse toimialan esittely -valikosta.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Valitse kokeiluympäristön toimiala.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Skenaariokohtaisten esittelytietojen luominen omassa ympäristössäsi

Jos olet Järjestelmänvalvoja, luo uusi ympäristö valitsemalla ympäristövalitsin sovelluksen ylätunnisteessa. Uudessa ympäristössä voit määrittää omat tietolähteesi ja määrittää sovelluksen tarpeitasi noudattaen. 

1.  Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.

2.  Jos haluat tuoda omat tietolähteesi, siirry [tietojenkäsittelyoppaaseen](data-sources.md).     
   Jos haluat käyttää mallitietoja, joiden avulla voit kokeilla tietojen käsittelyä, voit käsitellä alan demotiedot ympäristössäsi. Valitse **Tuo Datahubista** -vaihtoehto ja noudata alla olevia ohjeita.

3.  Valitse skenaarioon sopiva alan kortti. 

4.  Tarkista ja päivitä halutessasi ehdotetun nimen tietolähde. 

5.  Valitse **Seuraava**, jos haluat käsitellä mallitietoja. 

Voit nyt käyttää näitä tietoja Customer Insightsin räätälöintiin skenaariosi mukaan. Jos haluat nähdä ympäristökohtaiset esittelytiedot, valitse **<Industry>-demo** -vaihtoehto ympäristövalitsimesta.

## <a name="limitations-in-trials"></a>Kokeiluversioiden rajoitukset

- Kokeiluversiot ovat oletusarvoisesti aktiivisia 30 päivän ajan. Voit kuitenkin jatkaa niitä päivän 23 jälkeen, kun kirjaudut kokeiluversioon.
- Et voi käyttää omaa Azure Data Lake -tallennustiliäsi tulostustietojen tallentamiseen kokeilun aikana. Data Laken tallennustililtä voi kuitenkin saada tietoja.
- Voit tallentaa Dataverse-ympäristöön enintään kolme gigatavua tietoja, jotka valmistellaan automaattisesti, kun käynnistät Customer Insights -kokeiluversion.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Tietojen kopioiminen kokeiluversiosta maksettuun tilaukseen

Yleensä suosittelemme, että aloitat alusta omilla tiedoillasi päivittäessäsi Customer Insightsin maksulliseen versioon. 

Voit halutessasi kopioida tietosi kokeiluympäristöstä, jos ostat Customer Insightsin. Sinun on oltava Customer Insights -kokeiluversion järjestelmänvalvoja ja Microsoft 365 -vuokraajan yleinen järjestelmänvalvoja tai organisaatiosi Dynamics 365:n järjestelmänvalvoja, jotta voit siirtää asetukset kokeiluympäristöstä maksulliseen ympäristöön. 

Kun olet kirjautunut maksullisen Customer Insights -esiintymääsi ensimmäistä kertaa, sinua pyydetään luomaan uusi ympäristö. Tässä prosessissa voit kopioida konfiguraation aiemmin luodusta ympäristöstä ja siirtää suurimman osan asetuksista. Jos sinulla on edellä mainitut käyttöoikeudet, kokeiluympäristö näkyy tässä luettelossa. Lisätietoja on kohdassa [Ympäristön määritysten kopioiminen](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Seuraavat vaiheet

Seuraavien artikkelien avulla voit aloittaa Customer Insightsin määrittämisen. 

- [Lisää käyttäjiä ja määritä käyttöoikeuksia](permissions.md).
- [Käytä tietolähteitäsi](data-sources.md) ja suorita ne [tietojen yhdistämisprosessin](data-unification.md) avulla [yhtenäisten asiakasprofiilien](customer-profiles.md) aikaansaamiseksi.
- [Rikastuta yhtenäisiä asiakasprofiileja](enrichment-hub.md) tai [suorita ennustavia malleja](predictions-overview.md).
- Luo [segmenttejä](segments.md) ryhmitelläksesi asiakkaita ja [mittoja](measures.md) KPI-arvosteluille.
- Määritä [yhteydet](connections.md) ja [vienti](export-destinations.md), jotta voit käsitellä tietojen alijoukkoja muissa sovelluksissa.
