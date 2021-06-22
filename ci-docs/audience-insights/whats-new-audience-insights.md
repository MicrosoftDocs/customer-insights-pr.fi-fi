---
title: Uudet ja tulevat ominaisuudet
description: Tietoja uusista ominaisuuksista, parannuksista ja virheiden korjauksista.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 355dc22ac381145b231848830cefc47eda7968f4
ms.sourcegitcommit: 6944c1592877eb92ec789df5f2e0dbecef638837
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/15/2021
ms.locfileid: "6263247"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen uudet ominaisuudet

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Olemme innoissamme voidessamme ilmoittaa uusimmista päivityksistämme! Tässä artikkelissa on yhteenveto yleisen esiversion ominaisuuksista, yleisen saatavuuden parannuksista ja ominaisuuksien päivityksistä. Katso ominaisuuksien pitkäaikaiset suunnitelmat [Dynamics 365- ja Power Platform -julkaisusuunnitelmista](/dynamics365/release-plans/).

Julkaisemme päivitykset alueittain. Näin siis jotkin alueet saattavat nähdä ominaisuuksia ennen muita. Ellei toisin määritetä, sinun ei tarvitse tehdä mitään, vaan päivitämme sovelluksen automaattisesti ilman käyttökatkoja.

> [!TIP]
> Jos haluat lähettää ominaisuuspyyntöjä ja tuote-ehdotuksia tai äänestää niistä, siirry [Dynamics 365 Application Ideas -portaaliin](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

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

- **Vie segmentit RollWorksiin** Olemme laajentaneet vientikohteitamme niin, että niihin sisällytetään RollWorks. Nyt voit viedä segmenttejä Customer Insightsista RollWorks-kohdeyleisöihin ja käyttää niitä B2B-mainonnan lähtökohtana.    
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

  Järjestelmänvalvojat voivat kopioida ympäristömäärityksiä uuteen ympäristöön samassa organisaatiossa. Tämä ominaisuus laajentaa kopiointiympäristön toimintoja niissä tapauksissa, joissa tietolähteitä käytetään Common Data Service Data Lake -tallennustilan tai Common Data Model -kansion perusteella.

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