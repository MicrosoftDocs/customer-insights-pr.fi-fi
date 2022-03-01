---
title: Entiteettien entiteettipolkujen väliset suhteet
description: Useita lähteistä peräisin olevien entiteettien keskinäisten suhteiden luominen ja hallinta.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171160"
---
# <a name="relationships-between-entities"></a>Entiteettien väliset suhteet

Suhteet yhdistää entiteetit ja määrittää kaavion tiedoista, kun entiteeteille on yhteinen tunnus, viiteavain. Tähän viiteavaimeen voidaan viitata entiteetistä toiseen. Yhdistetyt entiteetit mahdollistavat segmenttien ja mittojen määrittelyn useiden tietolähteiden perusteella.

Suhteita on kolmea tyyppiä: 
- Ei-muokattavissa olevat järjestelmäsuhteet, jonka järjestelmä luo tietojenyhdistämisprosessin yhteydessä
- Ei-muokattavissa olevat perityt suhteet, jotka luodaan automaattisesti tietolähteestä 
- Muokattavat mukautetut suhteet, jotka käyttäjät ovat luoneet ja määrittäneet

## <a name="non-editable-system-relationships"></a>Ei-muokattavissa olevat järjestelmäsuhteet

Tietojen yhdistämisen aikana järjestelmäsuhteet luodaan automaattisesti älykkään vastaavuuden perusteella. Nämä suhteet auttavat liittämään asiakasprofiilitietueet vastaaviin tietueisiin. Seuraavassa kaaviossa on kuvattu kolmen järjestelmäpohjaisen suhteen luonti. Asiakasentiteetti on yhdistetty muihin entiteetteihin, jotta saadaan aikaan yhtenäinen *Asiakas*-entiteetti.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Kaavio kolmen 1-n-suhteen sisältävän asiakasyksikön suhdepoluista.":::

- ***CustomerToContact* -suhde** luotiin *asiakas*-entiteetin ja *yhteyshenkilö*-entiteetin välille. *Asiakas*-entiteetti saa avainkentän **Contact_contactId**, joka liitetään *yhteyshenkilö*-entiteetin avainkenttään **contactId**.
- ***CustomerToAccount*-suhde** luotiin *asiakas*-entiteetin ja *tili*-entiteetin välille. *Asiakas*-entiteetti saa avainkentän **Account_accountId**, joka liitetään *tili*-entiteetin avainkenttään **accountId**.
- ***CustomerToWebAccount*-suhde** luotiin *asiakas*-entiteetin ja *verkkotili*-entiteetin välille. *Asiakas*-entiteetti saa avainkentän **WebAccount_webaccountId**, joka liitetään *verkkotili*-entiteetin avainkenttään **webaccountId**.

## <a name="non-editable-inherited-relationships"></a>Ei-muokattavissa olevat perityt suhteet

Tietojen käytön aikana järjestelmä tarkistaa, onko tietolähteitä olemassa oleville suhteille. Jos suhdetta ei ole, järjestelmä luo ne automaattisesti. Näitä suhteita käytetään myös jatkoprosesseissa.

## <a name="create-a-custom-relationship"></a>Luo muokattu suhde

Suhde koostuu *lähde-entiteetistä*, joka sisältää viiteavaimen ja *kohde-entiteetistä*, johon lähde-entiteetin viite-avain osoittaa. 

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Suhteet**.

2. Valitse **Uusi suhde**.

3. Kirjoita **Uusi suhde** -ruutuun seuraavat tiedot:

   :::image type="content" source="media/relationship-add.png" alt-text="Uusi suhdesivuruutu, jossa on tyhjät syöttökentät.":::

   - **Suhteen nimi**: Nimi, joka vastaa suhteen tarkoitusta. Esimerkki: CustomerToSupportCase.
   - **Kuvaus**: Suhteen kuvaus.
   - **Lähde-entiteetti**: Entiteetti, jota käytetään suhteen lähteenä. Esimerkki: SupportCase.
   - **Kohde-entiteetti**: Entiteetti, jota käytetään kohteen lähteenä. Esimerkki: Asiakas.
   - **Lähteen kardinaliteetti**: Määritä lähde-entiteetin kardinaliteetti. Kardinaliteetti kuvaa joukon mahdollisten elementtien määrää. Se liittyy aina kohdekardinaliteettiin. Voit valita **yhden** tai **usean** välillä. Vain monta yhteen- ja yksi yhteen -suhteita tuetaan.  
     - Monta yhteen: useat lähdetietueet voivat liittyä yhteen kohdetietueeseen. Esimerkki: yhden asiakkaan tukitapauksia on useita.
     - Yksi yhteen: yksi lähdetietue liittyy yhteen kohdetietueeseen. Esimerkki: yksi uskollisuustunnus yhdelle asiakkaalle.

     > [!NOTE]
     > Monta moneen -suhteet voidaan luoda käyttämällä kahta monta-yhteen-suhdetta ja linkitysentiteettiä, joka yhdistää lähde-entiteetin ja kohde-entiteetin.

   - **Kohdekardinaliteetti**: Valitse kohde-entiteettitietueiden kardinaliteetti. 
   - **Lähdeavainkenttä**: lähde-entiteetin viiteavainkenttä. Esimerkki: SupportCase voi käyttää CaseID-tunnusta viiteavaimena.
   - **Kohdeavainkenttä**: Kohde-entiteetin avainkenttä. Esimerkiksi Asiakas voi käyttää **CustomerID**-avainkenttä.

4. Valitse **Tallenna** luodaksesi asiakassuhteen.

## <a name="view-relationships"></a>Tarkastele suhteita

Tässä Suhteet-sivulla on kaikki luodut suhteet. Kullakin rivillä on suhde, joka sisältää myös tietoja lähde-entiteetistä, kohde-entiteetistä ja suhteesta. 

:::image type="content" source="media/relationships-list.png" alt-text="Luettelo suhteista ja asetuksista suhteet-sivun toimintopalkissa.":::

Tämä sivu tarjoaa joukon vaihtoehtoja nykyisille ja uusille suhteille: 
- **Uusi suhde**: Valitse [Luo mukautettu suhde](#create-a-custom-relationship).
- **Visualisointi**: [Tutustu suhteeseen visualisointitehosteen](#explore-the-relationship-visualizer) avulla, niin näet verkkokaavion aiemmin luoduista suhteista ja niiden kardinaliteetista.
- **Suodatus**: Valitse suhdetyyppi, jonka haluat näyttää luettelossa.
- **Hae suhteet**: Käytä suhdeominaisuuksien tekstipohjaista hakua.

### <a name="explore-the-relationship-visualizer"></a>Tutustu suhteeseen visualisointitehosteena

Suhteen visualisointi näyttää verkkokaavion yhdistettyjen entiteettien välisistä suhteista ja niiden kardinaliteetista.

Jos haluat mukauttaa näkymää, voit muuttaa ruutujen sijaintia vetämällä ne kaavioon.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Näyttökuva suhdevisualisointiverkkokaaviosta, johon on liitetty toisiinsa liittyviä kokonaisuuksia.":::

Käytettävissä olevat asetukset: 
- **Vie kuvana**: Tallenna nykyinen näkymä kuvatiedostona.
- **Vaihda vaaka- tai pystysuuntaiseksi asetteluksi**: muuta entiteettien ja suhteiden asettelu.
- **Muokkaa**: Päivitä mukautettuja suhteita muokkausruudussa ja tallenna muutokset.

## <a name="manage-existing-relationships"></a>Olemassa olevien suhteiden hallinta 

Suhteet-sivulla kutakin suhdetta edustaa rivi. 

Valitse suhde ja valitse jokin seuraavista vaihtoehdoista: 
 
- **Muokkaa**: Päivitä mukautettuja suhteita muokkausruudussa ja tallenna muutokset.
- **Poista**: Poista mukautetut suhteet.
- **Näkymä**: Näytä järjestelmän luomat ja perityt suhteet. 

## <a name="next-step"></a>Seuraava vaihe

Järjestelmän suhteita ja mukautettuja suhteita käytetään [luotaessa segmenttejä](segments.md) sellaisten useiden tietolähteiden perusteella, jotka eivät ole enää siilossa.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
