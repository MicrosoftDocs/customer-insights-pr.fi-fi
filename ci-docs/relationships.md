---
title: Entiteettien entiteettipolkujen väliset suhteet
description: Useita lähteistä peräisin olevien entiteettien keskinäisten suhteiden luominen ja hallinta.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: a7b10d985d5cba64b25595a3d7c101d6cb5c62a5
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646390"
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

1. Siirry kohtaan **Tiedot** > **Suhteet**.

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

## <a name="set-up-account-hierarchies"></a>Tilihierarkioiden määrittäminen

Ympäristöt, jotka on määritetty käyttämään yritystilejä ensisijaisena kohdekäyttäjäryhmänä, voivat määrittää tilihierarkiat liittyviä yritystilejä varten. Esimerkiksi yritys, jolla on erilliset liiketoimintayksiköt. 

Organisaatiot luovat tilihierarkioita, joiden avulla voidaan hallita tilejä ja niiden välisiä suhteita paremmin. Customer Insights tukee pääkohde-alikohde-tilihierarkioita, jotka ovat jo olemassa käytettävissä asiakastiedoissa. Esimerkiksi tilit Dynamics 365 Salesista. Nämä hierarkiat voidaan määrittää **Suhteet**-sivulla.

1. Siirry kohtaan **Tiedot** > **Suhteet**.
1. Valitse **Tilihierarkia**-välilehti.
1. Valitse **Uusi tilihierarkia**. 
1. Anna **Tilihierarkia**-ruudussa hierarkian nimi. Järjestelmä luo tuloste-entiteetille nimen. Voit muuttaa tuloste-entiteetin nimeä.
1. Valitse entiteetti, joka sisältää tilihierarkian. Se on yleensä samassa entiteetissä, joka sisältää tilit.
1. Valitse **Tilin tunnus** ja **Tilin päätunnus** valitusta entiteetistä 
1. Valitse **Tallenna**, jotta voit ottaa asetukset käyttöön ja viimeistellä tilihierarkian.

## <a name="view-relationships"></a>Tarkastele suhteita

Tässä Suhteet-sivulla on kaikki luodut suhteet. Kullakin rivillä on suhde, joka sisältää myös tietoja lähde-entiteetistä, kohde-entiteetistä ja suhteesta. 

:::image type="content" source="media/relationships-list.png" alt-text="Luettelo suhteista ja asetuksista suhteet-sivun toimintopalkissa.":::

Tämä sivu tarjoaa joukon vaihtoehtoja nykyisille ja uusille suhteille: 
- **Uusi suhde**: Valitse [Luo mukautettu suhde](#create-a-custom-relationship).
- **Visualisointi**: [Tutustu suhteeseen visualisointitehosteen](#explore-the-relationship-visualizer) avulla, niin näet verkkokaavion aiemmin luoduista suhteista ja niiden kardinaliteetista.
- **Suodatus**: Valitse suhdetyyppi, jonka haluat näyttää luettelossa.
- **Hae suhteet**: Käytä suhdeominaisuuksien tekstipohjaista hakua.

### <a name="explore-the-relationship-visualizer"></a>Tutustu suhteeseen visualisointitehosteena

Suhteen visualisointi näyttää verkkokaavion yhdistettyjen entiteettien välisistä suhteista ja niiden kardinaliteetista. Se myös visualisoi suhdepolun.

Jos haluat mukauttaa näkymää, voit muuttaa ruutujen sijaintia vetämällä ne kaavioon.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Näyttökuva suhdevisualisointiverkkokaaviosta, johon on liitetty toisiinsa liittyviä kokonaisuuksia.":::

Käytettävissä olevat asetukset: 
- **Vie kuvana**: Tallenna nykyinen näkymä kuvatiedostona.
- **Vaihda vaaka- tai pystysuuntaiseksi asetteluksi**: muuta entiteettien ja suhteiden asettelu.
- **Muokkaa**: Päivitä mukautettuja suhteita muokkausruudussa ja tallenna muutokset.

## <a name="relationship-paths"></a>Suhdepolut

Suhdepolku kuvaa entiteettejä, jotka liittyvät lähde-entiteetin ja kohde-entiteetin välisiin suhteisiin. Sitä käytetään luotaessa segmenttiä tai mittayksikköä, joka sisältää muita entiteettejä kuin yhdistetyn profiilin entiteetin, ja yhdistetyn profiilin entiteetin tavoittamisessa on useita vaihtoehtoja. 

Suhdepolku ilmoittaa järjestelmälle mistä suhteesta yhdistettyyn profiilientiteettiin on pääsy. Eri suhdepolut voivat tuottaa erilaisia tuloksia.

Esimerkiksi entiteetillä *eCommerce_eCommercePurchases* on seuraavat suhteet yhdistettynä *Asiakas*-entiteettiin:

- eCommerce_eCommercePurchases > Asiakas
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Asiakas
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Asiakas 

Suhdepolku määrittää entiteetit, joita voi käyttää luotaessa yksiköitä tai segmenttejä koskevia sääntöjä. Jos valitset vaihtoehdon, jolla on pisin suhdepolku, tulokset ovat todennäköisesti pienempiä, koska vastaavien tietueiden on kuuluttava kaikkiin entiteetteihin. Tässä esimerkissä asiakkaan on ostettava tavaroita sähköisen kaupankäynnin (eCommerce_eCommercePurchases) kautta myyntipisteestä (POS_posPurchases) ja osallistuttava kanta-asiakasohjelmaamme (loyaltyScheme_loyCustomers). Kun valitset ensimmäisen vaihtoehdon, saat todennäköisesti enemmän tuloksia, koska asiakkaiden on oltava vain yhdessä lisäentiteetissä.

### <a name="direct-relationship"></a>Suora suhde

Suhde luokitellaan **suoraksi suhteeksi**, kun lähde-entiteetti liittyy kohde-entiteettiin, jolla on vain yksi suhde.

Jos esimerkiksi aktiviteettientiteetti nimeltään *eCommerce_eCommercePurchases*, muodostaa yhteyden kohde-entiteettiin *eCommerce_eCommerceContacts* vain *ContactId*:n kautta, se on suora suhde.

:::image type="content" source="media/direct_Relationship.png" alt-text="Lähde-entiteetti muodostaa yhteyden suoraan kohde-entiteettiin.":::

#### <a name="multi-path-relationship"></a>Monipolkuinen suhde

**Monipolkuinen suhde** on suora suhdetyyppi, joka yhdistää lähde-entiteetin useaan kohde-entiteettiin.

Jos esimerkiksi aktiviteettientiteetti nimeltään *eCommerce_eCommercePurchases*, liittyy kahteen kohde-entiteettiin, *eCommerce_eCommerceContacts* ja *loyaltyScheme_loyCustomers*, se on monipolkuinen suhde.

:::image type="content" source="media/multi-path_relationship.png" alt-text="Lähde-entiteetti muodostaa yhteyden suoraan useaan kohde-entiteettiin monipolkuisen suhteen kautta.":::

### <a name="indirect-relationship"></a>Epäsuora suhde

Suhde luokitellaan **epäsuoraksi suhteeksi**, kun lähde-entiteetti liittyy yhteen tai useampaan entiteettiin ennen kuin liittyy kohde-entiteettiin.

#### <a name="multi-hop-relationship"></a>Monivaiheinen suhde

*Monivaiheinen suhde* on *epäsuora suhde*, jonka avulla lähde-entiteetti voidaan yhdistää kohde-entiteettiin yhden tai usean muun välittäjäentiteetin kautta.

Jos esimerkiksi *eCommerce_eCommercePurchasesWest*-niminen aktiviteettientiteetti muodostaa yhteyden *eCommerce_eCommercePurchasesEast*-nimiseen välittäjäentiteettiin ja muodostaa sitten yhteyden *eCommerce_eCommerceContacts*-nimiseen kohde-entiteettiin, se on monivaiheinen suhde.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Lähde-entiteetti muodostaa yhteyden suoraan kohde-entiteettiin välittäjäentiteetin kanssa.":::

### <a name="multi-hop-multi-path-relationship"></a>Monivaiheinen, monipolkuinen suhde

Monivaiheisia ja monipolkuisia suhteita voidaan käyttää yhdessä **monivaiheisten monipolkuisten suhteiden** luomiseen. Tämä erikoistyyppi yhdistää **monivaiheiset** ja **monipolkuiset suhteet**. Sen avulla voit muodostaa yhteyden useampaan kuin yhteen kohde-entiteettiin käytettäessä välittäjäentiteettejä.

Jos esimerkiksi *eCommerce_eCommercePurchasesWest*-niminen aktiviteettientiteetti muodostaa yhteyden *eCommerce_eCommercePurchasesEast*-nimiseen välittäjäentiteettiin ja muodostaa sitten yhteyden kahteen kohde-entiteettiin, sekä *eCommerce_eCommerceContacts*-nimiseen että *loyaltyScheme_loyCustomers* kohde-entiteettiin, se on monivaiheinen, monipolkuinen suhde.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Lähde-entiteetti muodostaa yhteyden suoraan yhteen kohde-entiteettiin ja muodostaa yhteyden toiseen kohde-entiteettiin välittäjäentiteetin kautta.":::

## <a name="manage-existing-relationships"></a>Olemassa olevien suhteiden hallinta 

Suhteet-sivulla kutakin suhdetta edustaa rivi. 

Valitse suhde ja valitse jokin seuraavista vaihtoehdoista: 
 
- **Muokkaa**: Päivitä mukautettuja suhteita muokkausruudussa ja tallenna muutokset.
- **Poista**: Poista mukautetut suhteet.
- **Näkymä**: Näytä järjestelmän luomat ja perityt suhteet. 

## <a name="next-step"></a>Seuraava vaihe

Järjestelmän ja suhteiden avulla [luodaan segmenttejä](segments.md) ja [mittatietoja](measures.md), jotka perustuvat useisiin tietolähteisiin, joita ei enää toimiteta.

[!INCLUDE [footer-include](includes/footer-banner.md)]
