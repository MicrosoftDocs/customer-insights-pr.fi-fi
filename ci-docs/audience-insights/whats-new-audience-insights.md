---
title: Uudet ja tulevat ominaisuudet
description: Tietoja uusista ominaisuuksista, parannuksista ja virheiden korjauksista.
ms.date: 03/02/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 0e25ed4e4e25b130fda410d4ba1c78caded7f0f9
ms.sourcegitcommit: b7189b8621e66ee738e4164d4b3ce2af0def3f51
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088281"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen uudet ominaisuudet



Olemme innoissamme voidessamme ilmoittaa uusimmista päivityksistämme! Tässä artikkelissa on yhteenveto yleisen esiversion ominaisuuksista, yleisen saatavuuden parannuksista ja ominaisuuksien päivityksistä. Katso ominaisuuksien pitkäaikaiset suunnitelmat [Dynamics 365- ja Power Platform -julkaisusuunnitelmista](/dynamics365/release-plans/).

Julkaisemme päivitykset alueittain. Näin siis jotkin alueet saattavat nähdä ominaisuuksia ennen muita. Ellei toisin määritetä, sinun ei tarvitse tehdä mitään, vaan päivitämme sovelluksen automaattisesti ilman käyttökatkoja.

> [!TIP]
> Jos haluat lähettää ominaisuuspyyntöjä ja tuote-ehdotuksia tai äänestää niistä, siirry [Dynamics 365 Application Ideas -portaaliin](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="january-2022-updates"></a>Tammikuun 2022 päivitykset

Tammikuun 2022 päivitykset sisältävät uudet ominaisuudet, suorituskykypäivitykset ja ohjelmavirheiden korjaukset.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Asiakaspalautteen asenneanalyysi

Customer Insights sisältää uuden tekoälyä hyödyntävän ominaisuuden, joka syntetisoi asiakkaiden asenteita ja tunnistaa tietyt liiketoiminnan näkökohdat mahdollisuuksiksi kohdistettuihin parannuksiin. Analysoimalla asiakkaiden kirjallisen palautteen saat tarkkoja tietoja edulliseen hintaan. Luonnollisen kielen käsittelyn (NLP) mallien avulla suoritettu asenneanalyysi, jossa luodaan kaksi merkityksellistä tietoa kullekin asiakastunnukselle. Asennepisteet (–5–5) ja soveltuvien liiketoimintanäkökohtien luettelot. 

Lisätietoja on ohjeaiheessa [Asenneanalyysi asiakaspalautteessa (Esiversio)](sentiment-analysis.md).


## <a name="december-2021-updates"></a>Joulukuun 2021 päivitykset

Joulukuun 2021 päivitykset sisältävät uudet ominaisuudet, suorituskykypäivitykset ja ohjelmavirheiden korjaukset.

### <a name="forward-customer-insights-logs-to-azure-monitor"></a>Lähetä Customer Insights -lokit edelleen Azure Monitoriin

Customer Insights tarjoaa suoran integroinnin Azure Monitorin kanssa. Tämä ominaisuus sisältää seurantatapahtumat ja toimintatapahtumat. Azure Monitorin resurssilokien avulla voit valvoa ja lähettää lokeja Azure Storageen, Azure Log Analyticsiin tai virtauttaa se Azure-tapahtumakeskukseen.

Lisätietoja on ohjeaiheessa [Lokien edelleenlähetys Dynamics 365 Customer Insightsssa Azure Monitorin avulla (esiversio)](diagnostics.md).

### <a name="enrich-customer-profiles-with-engagement-data"></a>Täydennä asiakasprofiileja vuorovaikutustietojen avulla

Microsoft Office 365 -tietojen avulla voit täydentää asiakastiliprofiileja tiedoilla vuorovaikutuksista Office 365 -sovelluksissa. Seurantatiedot muodostuvat sähköposti- ja kokousaktiviteetista, jotka kootaan asiakastasolla. Esimerkiksi yritystilin sähköpostiviestien määrä tai asiakkaan tapaamisten määrän. Yksittäisten käyttäjien tietoja ei jaeta. Tämä toiminto on saatavana seuraavilla alueilla: Yhdistynyt kuningaskunta, Eurooppa, Pohjois-Amerikka.

Lisätietoja on ohjeaiheessa [Täydennä asiakasprofiileja vuorovaikutustietojen avulla (Esiversio)](enrichment-office.md).

### <a name="advanced-data-unification-features"></a>Tietojen yhdistämisen lisäominaisuudet

#### <a name="enable-conflict-resolution-policies-at-the-individual-attribute-level"></a>Ota käyttöön ristiriidan ratkaisukäytännöt yksittäisellä määritteen tasolla

Jos poistat asiakastietojen kaksoiskappaleita entiteetissä, et ehkä haluat valita voittajaksi täyttä tietuetta. Nyt voit yhdistää eri tietueiden parhaat kentät jokaisen määritteen sääntöjen perusteella. Voit esimerkiksi säilyttää uusimman sähköpostiviestin JA täydellisimmän osoitteen eri tietueista. 

Nyt voit määrittää erillisiä yhdistämissääntöjä yksittäisille määritteille samalla, kun poistat kaksoiskappaleita ja yhdistät tietueita yhdessä entiteetissä. Aiemmin voit valita vain yhden yhdistämissäännön (tietueiden säilyttäminen viimeaikaisuuden perusteella) ja sääntöä sovellettiin tietuetasolla kaikkiin määritteisiin. Se ei ole ihanteellista silloin, kun säilytettävää tietoa löytyy tietueesta A ja muita hyviä tietoja tietueesta B.

Lisätietoja on kohdassa [Vastine-entiteetin kaksoiskappaleiden poiston määrittäminen](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="custom-rules-for-matching"></a>Täsmäytyksen mukautetut säännöt

Joskus on määritettävä poikkeus yleisille säännöille, jotta tietueita EI yhdistetä. Näin voi käydä silloin, kun useat henkilöt jakavat riittävästi tietoja, jotta järjestelmä voisi täsmäyttää ne yksittäiseksi henkilöksi. Esimerkiksi kaksoset, joilla on sama sukunimi, jotka asuvat samassa kaupungissa ja joilla on sama syntymäpäivä.

Poikkeuksilla varmistetaan, että virheellinen tietojen yhdistäminen voidaan ottaa huomioon yhdistämissäännöissä. Sääntöön voi lisätä useita poikkeuksia.

Katso lisätietoja artikkelista [Poikkeuksien lisääminen sääntöön](match-entities.md#add-exceptions-to-a-rule).

#### <a name="provide-additional-conflict-resolution-policies-and-enable-grouping-of-attributes"></a>Lisää ristiriitojen ratkaisukäytäntöjä ja ota käyttöön määritteiden ryhmittely

Tämän ominaisuuden avulla voit käsitellä kenttäryhmää yhtenä yksikkönä. Jos tietueet sisältävät esimerkiksi kentät Osoite1, Osoite2, Kaupunki, Osavaltio ja Postinumero. Emme todennäköisesti halua yhdistää tietoja toiseen tietueen Osoite2-kohtaan ajatellen, että se voisi tehdä tiedoistamme täydellisempiä.

Nyt voit yhdistää toisiinsa liittyvien kenttien ryhmän ja käyttää ryhmässä yhtä yhdistämiskäytäntöä. 

Lisätietoja on ohjeaiheessa [Yhdistä kenttien ryhmä](merge-entities.md#combine-a-group-of-fields).


## <a name="november-2021-updates"></a>Marraskuun 2021 päivitykset

Marraskuun 2021 päivitykset sisältävät uudet ominaisuudet, suorituskykypäivitykset ja ohjelmavirheiden korjaukset.

### <a name="segment-membership-now-available-in-dataverse"></a>Segmentin jäsenyys on nyt käytettävissä Dataversessa

Asiakasprofiilien segmenttijäsenyystiedot ovat nyt saatavilla Dataversessa asiakasprofiilien ja oivallusten rinnalla. Dynamics 365 -toimintosovellukset ja mallipohjaiset sovellukset voivat näiden tietojen avulla etsiä tietyn asiakkaan segmenttijäsenyystiedot.

### <a name="activities-support-contact-level-details-for-business-accounts"></a>Aktiviteetit tukevat yritystilien yhteyshenkilötason tietoja

Nyt voit määrittää, näyttää ja suodattaa aktiviteetteja yhteyshenkilöille liiketoimintatilin aktiviteettiaikajanalla, jotta saat paremman käsityksen siitä, mitkä asiakkaan yhteyshenkilöt ovat tiettyihin aktiviteetteihin osallistuneet.

## <a name="october-2021-updates"></a>Lokakuun 2021 päivitykset

Lokakuun 2021 päivitykset sisältävät uudet ominaisuudet, suorituskykypäivitykset ja ohjelmavirheiden korjaukset.

### <a name="b-to-b"></a>B2B

Lokakuusta 2021 alkaen voit käyttää liiketoimintatilejä ja niihin liittyviä yhteyshenkilöitä Customer Insightsissa. Aiemmin sovellus oli räätälöity lähinnä yksittäisille kuluttajille. Useita ominaisuusalueita on päivitetty tukemaan B2B-skenaarioita uuden ympäristötyypin päällä. Jos haluat yleiskatsauksen tuetuista B2B-ominaisuuksista, katso lisätietoja [Liiketoimintatilien käyttäminen kohdeyleisötiedoissa](work-with-business-accounts.md).

Seuraavissa osissa on korostettu joitakin keskeisiä alueita, jotka on mukautettu yritystilejä ja yksittäisiä kuluttajia varten.

#### <a name="export-segments-based-on-business-accounts"></a>Liiketoimintatileihin perustuvien segmenttien vieminen

Kaikki segmenttiviennit kohdeyleisötiedoissa ovat käytettävissä liiketoimintatilien yhteydessä. Useimmat segmenttiviennit edellyttävät, että taustalla olevien segmenttien lisämääritys- ja [yhteyshenkilötiedot](segment-builder.md#create-a-new-segment) ovat voimassa yritystilien osalta. Lisätietoja: [Segmenttien vienti](export-destinations.md#export-segments).

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>LinkedIn Ads -viennin käyttö yritystilien kanssa

LinkedIn Ads -vienti on nyt käytettävissä yhteyshenkilöille ja yrityksille kohdentamisessa yritysasiakkuuksien yhteydessä. Kun valitset LinkedIn-viennin ensisijaiseksi kohdistukseksi yrityksiin kohdistamisen, voit viedä yritystileille luotuja segmenttejä ilman liitettyjä yhteystietoja. Lisätietoja on dokumentaatiossa [LinkedIn Adsin viennistä](export-linkedin-ads.md) ja [yhteyshenkilöihin kohdistamisen](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ja [yrityskohdistuksen](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) eroista. 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>Liiketoimintatileihin ja niiden hierarkiaan perustuvien mittareiden luominen

Tämän mittarin muodostimen avulla voit luoda mittareita yritystilejä varten ja käyttää tarvittaessa hierarkiatietoja. Hierarkiatietoja käytetään laskettaessa tileihin ja siihen liittyvien alatilien mittareita. Voit esimerkiksi luoda mittareita, kuten kokonaistuottoa kullekin hierarkian mukaan tunnistetulle yritysasiakasryhmälle. Lisätietoja on kohdassa [Mittarien määrittäminen ja hallinta](measures.md).

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>Liiketoimintatileihin ja niiden hierarkiaan perustuvien segmenttien luominen

Segmentin muodostimen avulla voit luoda liiketoimintatilien segmenttejä, jotka valinnaisesti sisältävät yhteyshenkilötiedot segmentin jokaiselle tilille. Jos asiakashierarkia on määritetty, voit käyttää asiakashierarkiatietoja segmentin luonnissa. Lisätietoja on kohdassa [Uuden segmentin luominen](segment-builder.md#create-a-new-segment).

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>Yritystilien säilyttäminen poistumistrendin syväanalyysin kautta

Asiakaspoistuman ennustemalli tukee nyt myös yritystilejä. Voit arvioida poistumisriskin paitsi tilille, myös tilin ja tuotteen tai palveluluokan yhdistelmälle. Tämän lisäyksen avulla voit ymmärtää, lopettaako tili todennäköisemmin ostamisen yleisesti vai vain tietyntyyppisiltä tavaroilta tai palveluluokilta. Auttaaksesi sinua käyttämään tätä tekoälymallia se listaa myös syitä siihen, miksi asiakas on todennäköisesti poistumassa. Lisätietoja on ohjeaiheessa [Tapahtumien poistumisennuste (esiversio)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Yrityksen yhteyshenkilöiden tarkasteleminen Asiakas-näkymässä

Jos liiketoimintatilit on yhdistetty liittyviin asiakkaisiin, Customer Insights -sovellus näyttää nämä liittyvät yhteyshenkilöt osana Asiakas-tietonäkymää. Lisätietoja on kohdassa [Asiakasprofiilit](customer-profiles.md).


## <a name="september-2021-updates"></a>Syyskuun 2021 päivitykset

Syyskuun 2021 päivitykset sisältävät uudet ominaisuudet, suorituskykypäivitykset ja ohjelmavirheiden korjaukset.

### <a name="activities"></a>Aktiviteetit

- **Aktiviteettiaikajanan parannukset** Olemme laajentaneet aktiviteettien aikajanan suodattimia asiakasprofiileissa. Lisäksi voit suodattaa uuden suodatinruudun avulla aktiviteettityypin ja päivämäärän mukaan. Päivämääriä voi suodattaa eri ehdoilla. Lisätietoja löytyy kohdasta [Aktiviteettiaikajanojen näyttäminen asiakasprofiileissa](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Suhteet

- **Monen siirtymän suhteiden tuki** Käytä monen siirtymän suhteita, kun määrität aktiviteetteja ja määrittelet entiteettien välisiä suhteita. Monen siirtymän suhteet käyttävät keskitason entiteettiä kahden entiteetin yhdistämiseen. Kun määrität aktiviteettia, voit käyttää monen siirtymän suhdetta muodostaaksesi yhteyden aktiviteettientiteetistä keskitason entiteettiin ja sitten asiakasentiteettiin. Voit yhdistää monen siirtymän suhteet monen polun suhteisiin. Katso lisätietoja kohdasta [Monen siirtymän suhde](relationships.md#multi-hop-relationship).

- **Monen polun suhteiden tuki** Käytä monen polun suhteita, kun määrität aktiviteetteja ja määrittelet entiteettien välisiä suhteita. Monen polun suhteet liittävät lähde-entiteetin enempään kuin yhteen entiteettiin. Kun määrität aktiviteettia, voit käyttää monen polun suhdetta muodostaaksesi yhteyden aktiviteettientiteetistä enempään kuin yhteen asiakasentiteettiin. Voit yhdistää monen polun suhteet monen siirtymän suhteisiin. Katso lisätietoja kohdasta [Monen polun suhde](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Elokuun 2021 päivitykset

Heinäkuun ja elokuun 2021 päivitykset sisältävät uuden ominaisuuden, suorituskykypäivityksiä ja ohjelmavirheiden korjauksia.

### <a name="extensibility"></a>Laajennettavuus

- **Vientisegmentit Klaviyoon** Olemme laajentaneet [vientikohteitamme sisältämään Klaviyon](export-klaviyo.md). Voit nyt tuoda segmenttejä luodaksesi kampanjoita, tehdäksesi sähköpostimarkkinointia ja käyttääksesi tiettyjä asiakasryhmiä Klaviyo-toiminnolla. 


## <a name="june-2021-updates"></a>Kesäkuun 2021 päivitykset

Kesäkuun 2021 päivitykset sisältävät useita toimintoja, suorituskykypäivityksiä ja virheiden korjauksia.

### <a name="data-ingestion"></a>Tietojen käsittely

- **Parannetut tietojen yhdistymisen edistymispäivitykset** Voit nyt tarkastella yksityiskohtaisempia ja parannettuja dynaamisia tilapäivityksiä [tietojen yhdistymisprosessin](data-unification.md) vaiheissa. Tämän ominaisuuden avulla voit seurata yksityiskohtaista edistymistä prosessivirran ymmärtämiseksi ja ryhtyä toimiin, jos jokin vaihe tarvitsee huomiota.

### <a name="extensibility"></a>Laajennettavuus

- **Segmenttien ja muiden tietojen vienti Salesforce Marketing Cloudiin** Olemme laajentaneet vientikohteitamme sisältämään [Salesforce Marketing Cloudin](export-salesforce.md). Voit nyt viedä segmenttejä ja muun tyyppisiä tietoja Salesforce Marketing Cloudiin brändätyn SFTP-viennin kautta. Tietojen tuonti voidaan automatisoida Salesforcessa täysin, ja sitä voidaan käyttää tehokkaampien markkinointikampanjoiden luomiseen.  
 
- **Vientisegmentit ActiveCampaigniin** Olemme laajentaneet vientikohteitamme sisältämään [Aktiivisen kampanjan](export-active-campaign.md). Voit nyt tuoda segmenttejä luodaksesi kampanjoita, suorittaaksesi sähköpostimarkkinointia ja työstääksesi tiettyjä asiakasryhmiä ActiveCampaign-toiminnossa.
 
- **Vientisegmentit Sendinblueen** Olemme laajentaneet vientikohteitamme sisältämään [Sendinbluen](export-sendinblue.md). Voit nyt tuoda segmenttejä luodaksesi kampanjoita, suorittaaksesi sähköpostimarkkinointia ja työstääksesi tiettyjä asiakasryhmiä Sendinblue-toiminnolla.
 
### <a name="ux-updates"></a>UX-päivitykset 

- **Uusi ja parannettu Asiakkaat-sivu ja profiilin tietosivu** Olemme uudistaneet Asiakkaat-sivun ja profiilin tietosivut käyttökokemuksen ja suorituskyvyn parantamiseksi. Näiden muutosten avulla voit tarkastella, lajitella, etsiä ja suodattaa asiakkaita. URL-osoitteessa on nyt suodattimia, joiden avulla hakutulokset voidaan jakaa saumattomasti muiden käyttäjien kanssa. Hakutulokset voidaan tallentaa myös segmenttinä.    
  Asiakasprofiilien tietosivulla on nyt ryhmitelty tiedot eri alaluokkiin, kuten väestötiedot, tunnukset ja muut profiilimääritteet luettavuuden parantamiseksi. Muut profiilin tietosivun osat ovat nyt vuorovaikutteisempia. Esimerkiksi aktiviteettien osa sallii nyt suodatuksen ja lajittelun.


## <a name="may-2021-updates"></a>Toukokuun 2021 päivityksey

Toukokuun 2021 päivityksessä on useita ominaisuuksia, suorituskykypäivityksiä ja ohjelmavirheiden korjauksia.

### <a name="data-ingestion"></a>Tietojen käsittely

- **Voit tarkastella tai muokata metatietoja tai entiteettimääritystä, kun liität tietoja Azure Data Lake Storagesta**, voit tarkastella ja muokata metatietoja tai entiteettimääritystä käyttäjäryhmän merkityksellisissä tiedoissa, kun liität tietoja Common Data Model -kansiosta Azure Data Lake Storagessa. Tämä ominaisuus tarjoaa reaaliaikaista palautetta, mallin tarkistamista ja virheiden tarkistusta. Sen avulla voit muokata sekä model.json-tiedoston että manifest.json-tiedoston saumattomasti.

### <a name="extensibility"></a>Laajennettavuus

- **Parannettu segmenttien vienti, mukautettu aikataulu ja kaksoiskappaleet** Voit nyt [nähdä luettelon tietyn segmentin kaikki viennit](export-destinations.md#view-exports-and-export-details). Tämä uusi näkymä auttaa hallitsemaan tietyn segmentin käyttötegmenttiä ja mukauttamaan olemassa olevia tai luomaan uusia vientejä.    
  Voit [määrittää mukautettuja päivitysaikatauluja](export-destinations.md#schedule-and-run-exports) yksittäiselle viennille tai usealle viennille samalla kertaa. Tähän asti kaikki viennit on nyt suoritettava jokaisen järjestelmän päivityksen yhteydessä.    
  Sen sijaan, että loisit uuden viennin alusta, voit säästää aikaa, kun aloitat aiemmin luodun viennin perusteella.

- **Vie segmentit Microsoft Advertisingiin** Olemme laajentaneet vientikohteitamme niin, että niihin sisällytetään Microsoft Advertising. Luo kohdeyleisöjä Microsoft Advertisingissa yhtenäisten asiakasprofiilitietojen avulla ja käytä näitä kohdeyleisöjä mainoskampanjoissasi. Lisätietoja on ohjeaiheessa [Segmenttien vieminen Microsoft Advertisingiin](export-microsoft-advertising.md).

- **Vie segmentit LinkedIn Adsiin** Olemme laajentaneet vientikohteitamme niin, että ne sisältävät LinkedIn Adsit, ja voit avata yhteyshenkilöiden kohdistamisen lukituksen sekä yritys kohdistamisen LinkedInin kautta viemällä yhdistetyt asiakasprofiilisi tiedot. Lisätietoja on ohjeaiheessa [Segmenttien vieminen LinkedIn Adsiin](export-linkedin-ads.md).


- **Vie segmentit Omnisendiin** Olemme laajentaneet vientikohteitamme niin, että niihin sisällytetään Omnisend. Käytä käyttäjäryhmän merkityksellisissä tiedoissa luotuja segmenttejä luodaksesi kampanjoita, tarjotaksesi sähköpostimarkkinointia ja käyttääksesi tiettyjä asiakasryhmiä Omnisend-toiminnolla. Lisätietoja on ohjeaiheessa [Segmenttien vieminen Omnisendiin](export-omnisend.md)

### <a name="predictions"></a>Ennusteet

- **Syöttötietojen käytettävyysraportti** Syöttötietojen käytettävyysraportti sisältää koosteen virheistä ja varoituksia, joita valmiit ennusteet saattavat tuottaa. Se antaa myös suosituksia mallin suorituskyvyn parantamista varten.    
  Raportti on käytettävissä sen jälkeen, kun malli on suorittanut sen koulutusprosessin. Se luodaan kullekin mallille erikseen riippumatta siitä, onnistuiko malli.
  Tämä ominaisuus on tällä hetkellä käytettävissä vain tapahtumavaihtuvuusmallissa. Lisätietoja on ohjeaiheessa [Syöttötietojen käytettävyysraportti](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Suhteet

- **Suhteen visualisointi** Suhteen visualisointinäkymässä voit nähdä kaikki olemassa olevat suhteet entiteettien välillä ja niiden kardinaalisuuden. Suhteet on nyt järjestetty ryhmiin: käyttäjän luomat, järjestelmät ja perityt suhteet. Voit myös viedä näkymän kuvana. Lisätietoja on aiheessa [Suhteiden tarkastelu](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Huhtikuun 2021 päivitykset

Huhtikuun 2021 päivityksessä on useita ominaisuuksia, suorituskykypäivityksiä ja ohjelmavirheiden korjauksia.

### <a name="data-unification"></a>Tietojen yhdistäminen
 
- **Tietojen yhdistämisen parannettu yhdistämiskokemus**    
  
   Meillä on nyt parannettu käyttökokemus tietojen yhdistämisprosessin yhdistämismääritykselle. Muutokset sisältävät yhdistettyjen kenttien intuitiivisen järjestämisen sekä yksityiskohtaiset tilastot yhdistetyistä ja yksittäisistä kentistä.

- **Entiteettien uudelleenjärjestäminen ja kaikkien lähdetietueiden määrittäminen Asiakasentiteettiin**  
      
   Entiteettejä voidaan nyt järjestää uudelleen ja poistaa olemassa olevasta yhdistämissuunnitelmasta tietojen yhdistämisprosessissa. Se antaa joustavuutta entiteettien uudelleen järjestämiseen liiketoiminnan tarpeita vastaavasti yhdistämisprosessissa. Lisäksi mahdollistamme kaikkien yhdistämättömien tietueiden lisäämisen lopulliseen *Asiakas*-entiteettiin, mikä mahdollistaa asiakasprofiilitietojoukon määrittämisen.

### <a name="enrichments"></a>Rikastukset

 - **Uusi rikastus: Parannetut osoitteet**    
  
   Olemme innoissamme voidessamme esitellä uuden rikastuksen, joka parantaa asiakastietojesi osoitteita. Tietojen osoitteet voivat olla rakenteettomia, epätäydellisiä tai virheellisiä. Tämä ominaisuus käyttää Microsoftin malleja osoitteiden normalisoimiseen ja riskastamiseen Common Data Model -muotoon tarkkuuden ja merkityksellisten tietojen parantamiseksi.
 
   Lisätietoja on kohdassa [Asiakasprofiilien rikastaminen parannetuilla osoitteilla](enrichment-enhanced-addresses.md).

- **Ohjattu määrityskokemus rikastuksille**    
  
   Suunnittelimme rikastusten määrityskokemuksen uudelleen ja teimme siitä yksinkertaisen, ohjatun kokemuksen. Sinulla on nyt selkeä vaiheittainen prosessi rikastusten luomiseen ja muokkaamiseen.
 
   Lisäksi erotimme kolmansien osapuolten rikastamisen yhteyksien määrittämisen, jotta useat rikastukset voivat käyttää samaa yhteyttä. Vain järjestelmänvalvojat voivat määrittää uusia yhteyksiä, mutta luodut yhteydet ovat sekä järjestelmänvalvojien että osallistujien käytettävissä.    

   Lisätietoja on kohdassa [Yleiskatsaus yhteyksiin](connections.md).

- **Useita samantyyppisiä rikastuksia**    
  
   Nyt annamme käyttäjille mahdollisuuden luoda ja hallita useita saman rikastustyypin rikastuksia. Voit esimerkiksi nyt luoda kaksi erillistä osoiterikastusta kahden eri asiakassegmentin rikastamista varten. Samantyyppisten rikastusten luonnille on asetettu lukumäärärajoituksia, jotka vaihtelevat rikastustyypeittäin.
  
   Lisätietoja on kohdassa [Asiakasprofiilien rikastaminen](enrichment-hub.md).

## <a name="march-2021-updates"></a>Maaliskuun 2021 päivitykset

Maaliskuun 2021 päivityksessä on useita ominaisuuksia, suorituskykypäivityksiä ja ohjelmavirheiden korjauksia.

### <a name="activities"></a>Aktiviteetit

- **Ohjattu aktiviteettitoiminto ja semanttiset tyypit**

   Aktiviteettien yhdistämiskokemusta on parannettu ja päivitetty aktiviteettien yhdistämismääritysten luonnissa opastamiseksi ja sen yksinkertaistamiseksi. Tässä uudessa käyttökokemuksessa käyttäjät saavat ohjatun käyttökokemuksen, joka auttaa prosessin jokaisen vaiheen suorittamisessa. Aktiviteettien yhdistämisvaiheessa käyttäjä voi useista aktiviteettityypeistä valinnan lisäksi yhdistää *Subscription* ja/tai *SalesOrderLine*-tiedot semanttisesti toimialan vakiorakenteisiin, joita voidaan käyttää prosessissa myöhemmin.   

   Lisätietoja on kohdassa [Asiakasaktiviteetit](activities.md).

### <a name="data-ingestion"></a>Tietojen käsittely

- **Muodosta yhteys paikallisiin tietolähteisiin käyttämällä Power Platform tietovirtoja ja yhdyskäytäviä** Olemme iloisia siitä, että voimme ilmoittaa Power Platform -tietovirtojen ja paikallisten yhteyksien esiversion Customer Insights -yhdyskäytävien käytölle yhdessä Power Platform- tai Dataverse-ympäristöjen kanssa. Kaikki linkitetyn Dataverse-ympäristön Customer Insights -ympäristössä luodut uudet tietolähteet käyttävät oletusarvon mukaan Power Platform- tietovirtoja hyödyntäen paikallisia tietojen yhteyksiä sekä monipuolisia yhdistin- ja muunnosominaisuuksia.

### <a name="extensibility"></a>Laajennettavuus

- **Yhteyksiin ja vienteihin järjestetyt viennit** Olemme muuttaneet **Vientikohteet**-sivun nimeksi **Yhteydet** ja lisänneet erillisen **Viennit**-sivun. Tässä päivityksessä siirrämme aiemmin luodut viennit yhteyden ja yhteyttä käyttävän viennin pareiksi. Järjestelmänvalvojat näkevät nyt selkeämmin lähtevät tiedot **Yhteydet**-sivulla. Kaikilla käyttäjärooleilla on **Viennit**-sivun käyttöoikeus, mutta vain järjestelmänvalvojat voivat sallia osallistujien muokata tiettyjä vientejä jaetuilla yhteyksillä.     
  Lisätietoja on ohjeaiheessa [Yhteyksien yleiskuvaus](connections.md) ja [Vientien yleiskatsaus](export-destinations.md).

- **Vie segmentit Campaign Monitoriin** Olemme laajentaneet vientikohteitamme niin, että niihin sisällytetään Campaign Monitor. Nyt voit viedä segmenttejä Customer Insightsista Campaign Monitor -luetteloihin ja käyttää niitä markkinointikampanjoiden lähtökohtana.    
   Lisätietoja on aiheessa [Vienti Campaign Monitoriin](export-campaign-monitor.md).

- **Vie segmentit Constant Contactiin** Olemme laajentaneet vientikohteitamme niin, että niihin sisällytetään Constant Contact. Nyt voit viedä segmenttejä Customer Insightsista Constant Contact -luetteloihin ja käyttää niitä markkinointikampanjoiden lähtökohtana.   
   Lisätietoja on aiheessa [Vienti Constant Contactiin](export-constant-contact.md).

- **Vie segmentit RollWorksiin** Olemme laajentaneet vientikohteitamme niin, että niihin sisällytetään RollWorks. Segmenttejä voidaan nyt viedä Customer Insightsista RollWorks-käyttäjäryhmiin, jossa niitä voidaan käyttää yritystenvälisen mainonnan perustana.    
   Lisätietoja on aiheessa [Vienti RollWorksiin](export-rollworks.md).

- **Vie segmentit Snapchatiin** Olemme laajentaneet vientikohteitamme niin, että niihin sisällytetään Snapchat. Nyt voit viedä segmenttejä Customer Insightsista Snapchat-kohdeyleisöihin ja käyttää niitä mainonnan lähtökohtana.     
   Lisätietoja on aiheessa [Vienti Snapchatiin](export-snapchat.md).

### <a name="predictions"></a>Ennusteet

- **Käytä tuotesuodattimia tuotesuositusten ennustavassa käytössä** Tuotesuositusmalliin on lisätty tuotesuodattimien käyttömahdollisuus. Nyt voit luoda ennusteen, joka käyttää vain osaa tuotteistasi.    
   Lisätietoja on ohjeaiheessa [Tuotesuodattimien määrittäminen](predict-product-recommendation.md#configure-product-filters).

- **Luo segmenttejä mallin ennusteista** Olemme lisänneet nopean tavan luoda segmenttejä käyttämällä ennustemallin tuloksia. Mallin tulossivulla voit helposti luoda uuden segmentin valitsemalla uuden **Luo segmentti** -vaihtoehdon.    
  Lisätietoja on ohjeaiheessa [Luo segmentti ennustemallin perusteella](prediction-based-segment.md).

- **Tuotesuositusten selitykset** Olemme lisänneet tietoja siitä, mitä tärkeitä tekijöitä tekoälymallissa on opittu tuotesuositusten tuottamiseksi ja missä määrin nämä tekijät vaikuttavat tuotesuosituksiin. Nämä tiedot lisätään mallin tulosnäyttöön.    
   Lisätietoja on kohdassa [Ennusteen tilan ja tulosten tarkasteleminen](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Helmikuun 2021 päivitykset

Helmikuun 2021 päivitykset sisältävät useita toimintoja, suorituskykypäivityksiä ja virheiden korjauksia.

#### <a name="extensibility"></a>Laajennettavuus

- **Segmenttien vieminen AdRoll-sovellukseen**

  Olemme laajentaneet vientikohteitamme niin, että niihin sisällytetään AdRoll. Nyt voit viedä segmenttejä Customer Insightsista AdRoll-käyttäjäryhmille ja käyttää niitä mainonnan lähtökohtana. Lisätietoja on kohdassa [AdRoll-yhdistin](export-adroll.md).

#### <a name="segments"></a>Segmentit
 
- **Kopioi segmentti**
  
  Jos haluat luoda uuden segmentin aiemmin luodun perusteella, voit nyt kopioida segmentin ja muokata sen kaksoiskappaletta, jotta voit parannella sitä tarkemmin. 

- **Lisämääritteiden lisääminen segmenttiin**

  Nyt voit lisätä määritteitä segmentin tulosteeseen, vaikka nämä määritteet eivät kuulu asiakasprofiiliin. Voit esimerkiksi sisällyttää tilaustunnukset segmenttiin, vaikka se kuuluu tilausentiteettiin, jolla on M:1-suhde asiakasentiteettiin. Jos määrite kuuluu asiakasentiteettiin liittyvään entiteettiin, voit nyt sisällyttää nämä määritteet.  

#### <a name="predictions"></a>Ennusteet

- **Ennakoivien tuotesuositusten luominen**

  Sen ymmärtäminen, mitä asiakkaat ovat kiinnostuneita ostamaan, on yksi ensimmäisistä vaiheista, joita tarvitaan liiketoiminnan tuoton parantamiseen ja asiakasuskollisuuden rakentamiseen personoinnin ja sitoutumisen avulla. Suositusten antaminen tuotteille, jotka eivät ole sopusoinnussa asiakkaasi etujen kanssa, voi katkaista asiakkaan ja yrityksesi välisen yhteyden ja lopulta rajoittaa asiakkaan potentiaalista kokonaistuloa ja kokemusta. 

  Omien tietojen avulla voit nyt luoda ennusteita siitä, mitä tuotteita asiakkaat todennäköisesti ostavat tulevaisuudessa. Lisätietoja on ohjeaiheessa [Tuotesuositusennuste](predict-product-recommendation.md).

#### <a name="system-administration"></a>Järjestelmän hallinta

- **Ympäristön kopioiminen tukee useampia tietolähteiden tyyppejä**

  Järjestelmänvalvojat voivat kopioida ympäristömäärityksiä uuteen ympäristöön samassa organisaatiossa. Tämä ominaisuus laajentaa kopiointiympäristötoimintoa tapauksissa, joissa käytetään Microsoft Dataversen hallitsemaan tietojärveen tai Common Data Model -kansioon perustuvia tietolähteitä.

## <a name="january-2021-updates"></a>Tammikuun 2021 päivitykset

Tammikuun 2021 päivitykset sisältävät useita toimintoja, suorituskykypäivityksiä ja virheiden korjauksia.

#### <a name="extensibility"></a>Laajennettavuus

- **SFTP-viennin laajennetut toiminnot ja laajennettu suorituskyky** Voit nyt viedä kaikki tulosentiteetit Customer Insightsista SFTP-isäntään. Aiemmin vienti rajoittui segmenttientiteetteihin. Lisäksi SFTP-viennin suorituskyky mahdollistaa aiempaa suuremman datamäärän käsittelemisen aiempaa lyhyemmässä ajassa SFTP-isännän suorituskyvystä riippuen.    
  Lisätietoja on kohdassa [SFTP-yhdistin (esiversio)](export-sftp.md).  

#### <a name="segments"></a>Segmentit

- **Koneoppimisen tehostamat ehdotetut segmentit mittareiden parantamiseksi** Tämä on uusi tapa segmenttien etsimiseen ja luomiseen. Järjestelmä käyttää tekoälymallia segmenttien ehdottamisessa. Tämä auttaa jo seurannassa olevien KPI-luvun (mittarin) parantamisessa. Näkyvissä on niiden määritteiden vaikutuksen määrä, jotka ovat valittavissa mittaria tai toista ensisijaista määritettä varten. Nämä tiedot auttavat nykyisten mahdollisuuksien mahdollisten segmenttien etsimisessä.    
  Lisätietoja on kohdassa [Ehdotetut segmentit (esiversio)](suggested-segments.md).

#### <a name="data-unification"></a>Tietojen yhdistäminen

- **Tehostettu vastaavuuskokemus** Vastaavuuskokemus päivitettiin tietojen yhdistämisen alueessa. Sen avulla voit määrittää ja tarkastella vastaavuussääntöjä, esimerkiksi yksityiskohtaisia tilastoja vastaavuudesta ja sen käyttämisestä. Vastaavuussäännön voi myös poistaa käytöstä, jolloin se ei ole enää aktiivinen. Samalla määrityksen ja vedä ja pudota -toiminnon vastaavuussäännöt säilytetään.
  Lisätietoja on aiheessa [Entiteettien vastaavuuden määrittäminen](match-entities.md).

- **Kaksoiskappaleiden poiston tulos vastaavuusprosessissa on käytettävissä entiteettinä** Kaksoiskappaleiden poistoprosessin tulos vastaavuusprosessissa on nyt kirjoitettu erilliseen entiteettiin lisäanalyysia varten. Tämä entiteetti sisältää kaksoiskappaleiden poistoprosessissa käytetyt kentät sekä voittaneen tietueen että vastaavat vaihtoehtoiset tietueet, jotka yhdistettiin voittaneeseen tietueeseen.
  Lisätietoja on kohdassa [Kaksoiskappaleiden poiston tulos entiteettinä](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Järjestelmän hallinta

- **Jaa tiedot saumattomasti Microsoft Dataversen kanssa** Voit nyt jakaa Customer Insightsin tuloksen Microsoft Dataverse -sovellusten kanssa käyttämällä Microsoft Dataversen hallittua Data Lakea. Kun Dataverse-ympäristö liitetään Customer Insightsiin, voit ottaa käyttöön tietojen jakamisen.
  Lisätietoja on kohdassa [Ympäristöjen hallinta](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]