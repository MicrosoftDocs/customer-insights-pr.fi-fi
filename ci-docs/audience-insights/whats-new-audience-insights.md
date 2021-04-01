---
title: Uudet ja tulevat ominaisuudet
description: Tietoja uusista ominaisuuksista, parannuksista ja virheiden korjauksista.
ms.date: 03/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 96c0b871eeaaf0976e5c718f37f883f4410977dc
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598427"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insightsin käyttäjäryhmän merkityksellisten tietojen uudet ominaisuudet

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Olemme innoissamme voidessamme ilmoittaa uusimmista päivityksistämme! Tässä artikkelissa on yhteenveto yleisen esiversion ominaisuuksista, yleisen saatavuuden parannuksista ja ominaisuuksien päivityksistä. Katso ominaisuuksien pitkäaikaiset suunnitelmat [Dynamics 365- ja Power Platform -julkaisusuunnitelmista](/dynamics365/release-plans/).

Lisäksi seuraavassa videossa on tietoja kuluneille kuudelle kuukaudelle suunnitelluista ominaisuuksista.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Julkaisemme päivitykset alueittain. Näin siis jotkin alueet saattavat nähdä ominaisuuksia ennen muita. Ellei toisin määritetä, sinun ei tarvitse tehdä mitään, vaan päivitämme sovelluksen automaattisesti ilman käyttökatkoja.

> [!TIP]
> Jos haluat lähettää ominaisuuspyyntöjä ja tuote-ehdotuksia tai äänestää niistä, siirry [Dynamics 365 Application Ideas -portaaliin](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

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


## <a name="december-2020-updates"></a>Joulukuun 2020 päivitykset

Joulukuun 2020 päivitykset sisältävät useita ominaisuuksia, suorituskykypäivityksiä ja virheiden korjauksia.

### <a name="new-and-updated-features-in-december-2020"></a>Uudet ja päivitetyt ominaisuudet joulukuussa 2020

#### <a name="data-enrichment"></a>Tietojen rikastaminen

- **Parannettu tuotemerkin ja kiinnostusten kohteiden affiniteettien rikastamisetf**
  
  Affiniteettipisteitä yksinkertaistettiin, jotta niitä olisi aiempaa helpompi ymmärtää ja käyttää. Nyt voit nopeasti tunnistaa asiakkaat sen perusteella, kuinka paljon affiniteettia näillä on tiettyä tuotemerkkiä tai kiinnostuksen kohdetta kohtaan.

  Lisäksi olemme lisänneet uusia määritysvaihtoehtoja, jotka ohjaavat paremmin asiakasprofiilien rikastamista. 

  Lisätietoja on kohdassa [Asiakasprofiilien rikastaminen brändin ja kiinnostuksen kohteiden affiniteeteillä](enrichment-microsoft-graph.md).

- **Rikastettavien profiilien määrittäminen**

  Nyt voit rikastaa vain asiakasprofiilien alijoukkoa ja valita segmenttientiteetin oletusasiakasentiteetin sijaan. Luo segmentti, joka sisältää rikastettavat asiakasprofiilit, ja valitse se asiakastietojoukon rikastuksen määrityksessä.
  Tämä ominaisuus on tällä hetkellä käytettävissä vain Experian- ja HERE Technologies -rikastuksille. Tätä ominaisuutta rikastetaan pian.

  Lisätietoja on kohdassa [Asiakasprofiilien rikastaminen Experianin demografiatiedoilla](enrichment-experian.md) tai [Asiakasprofiilien rikastaminen HERE Technologies -tiedoilla](enrichment-here.md).

#### <a name="extensibility"></a>Laajennettavuus

- **Segmenttien aktivointi Autopilotin kautta**

  Vie segmenttejä Autopilotiin ja käytä niitä markkinointiin. Lisätietoja on kohdassa [Autopilot-yhdistin (esiversio)](export-autopilot.md).

- **Segmenttien aktivointi SendGridin kautta**

  Vie segmenttejä SendGridiin ja käytä niitä markkinointiin. Lisätietoja on kohdassa [SendGrid-yhdistin](export-sendgrid.md).

#### <a name="system-administration"></a>Järjestelmän hallinta

- **Päivitetty ympäristön hallintakokemus**
  
  Nyt voit luoda, muokata, poistaa ja palauttaa ympäristöjä suoraan sovelluksen otsikon ympäristön valitsijasta. 
  
  Lisäksi käytössäsi olevan ympäristön kiinnitetty ympäristö on ympäristöpaneelin yläosassa, joten sitä ei enää tarvitse hakea.

  Lisätietoja on kohdassa [Ympäristöjen hallinta](manage-environments.md).

## <a name="november-2020-updates"></a>Marraskuun 2020 päivitykset

Marraskuun 2020 päivitykset sisältävät useita ominaisuuksia, suorituskykypäivityksiä ja virheiden korjauksia.

### <a name="new-and-updated-features-in-november-2020"></a>Uudet ja päivitetyt ominaisuudet marraskuussa 2020

#### <a name="data-enrichment"></a>Tietojen rikastaminen

- **Omien mukautettujen rikastustietojen tuominen suojatun tiedostonsiirtoprotokollan (SFTP) välityksellä**
  
  Mukautetun SFTP-tuonnin avulla voi tuoda rikastustietoja, joille ei tarvitse tietojen yhtenäistämistä. Lisätietoja mukautetusta SFTP-tuonnista.

  Lisätietoja on kohdassa [Asiakasprofiilien rikastaminen mukautetuilla tiedoilla (esiversio)](enrichment-SFTP-custom-import.md).
 
- **Asiakastietojen rikastaminen HERE Technologiesin sijaintitiedoilla**

  HERE Technologiesin tietojen rikastamispalveluilla voi muodostaa tarkemman asiakkaiden sijaintitietoisuuden esimerkiksi osoitteen normalisoinnin sekä leveys- ja pituusastetietojen poiminnan avulla. Lisätietoja HERE Technologiesin käyttämisestä rikastamiseen.

  Lisätietoja on kohdassa [Asiakasprofiilien rikastaminen HERE Technologiesin avulla](enrichment-here.md).

#### <a name="data-unification"></a>Tietojen yhdistäminen

- **Tietojen profiloinnin ottaminen joustavasti käyttöön valituissa entiteeteissä ja kentissä tallennustilillä**

  Voit ilmaista, missä Azure Data Lake -tallennustilin Common Data Model -kansion tietoentiteeteissä ja kentissä haluat ottaa tietojen profiloinnin käyttöön tietojen käsittelyprosessin osana.

  Lisätietoja on kohdassa [Yhteyden muodostaminen Common Data Model -kansioon](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Laajennettavuus

- **Segmenttien aktivointi Google Adsin kautta**

  Vie segmentit Google Adsin käyttäjäryhmäluetteloihin ja käytä näitä luetteloita mainontaan Google Haussa, Google Display-verkostossa, YouTubessa ja Gmailissa. Lisätietoja segmenttien aktivoinnista Google Adsin avulla.

  Lisätietoja on kohdassa [Google Ads -yhdistin](export-google-ads.md).

- **Segmenttien aktivointi Marketon kautta**

  Vie segmentit Marketo-käyttäjäryhmiin ja käytä näitä käyttäjäryhmiä markkinoinnin automatisointiin. Lisätietoja segmenttien aktivoinnista Marketon avulla. 

  Lisätietoja on kohdassa [Marketo-yhdistin](export-marketo.md).

- **Segmenttien aktivointi DotDigitalin kautta**

  Vie segmenttejä DotDigitaliin ja käytä niitä markkinointiin. Lisätietoja segmenttien aktivoinnista DotDigitalin avulla. 

  Lisätietoja on kohdassa [DotDigital-yhdistin](export-dotdigital.md).

#### <a name="predictions"></a>Ennusteet

- **Tapahtuman vaihtuvuuden ennakointi**

  Tapahtuman vaihtuvuuden ennakointitoiminnon avulla ennustaa itse ilman data-asiantuntija apua, kuinka todennäköisesti asiakas lopettaa tuotteiden tai palvelujen ostamisen.  Voit yhdistää ennakoivan pisteytyksen avulla muita asiakkaita koskevia tietoja, kuten asiakkaan arvon, ja luoda suuren vaihtuvuusriskin ja arvoltaan suurien asiakkaiden segmenttejä. Tämän segmentin avulla asiakkaiden vaihtuvuusriskiä voidaan vähentää kohdistamalla heille suoraan markkinointiaktiviteetteja, asiakastukea ja muita skenaarioita.
 
  Määritä vaihtuvuuden määritys liiketoimintakohtaiseksi aikaan perustuvaksi ikkunaksi. Määritä sitten, milloin asiakas katsotaan vaihtuneeksi. Esimerkiksi elintarvikemyymälä voi katsoa asiakkaan vaihtuneeksi, jos he eivät ole ostaneet mitään 30 päivään.
 
  Kun ennusteen luontia jatketaan, saat tietää, mitä tietoja tarvitaan. Lisäksi pystyt yhdistämään liiketoimintaa koskevia tietoja kenttiin, joita tarvitaan asiakkaiden vaihtuvuuden ennustamiseen. Voit myös määrittää aikataulun, jonka perusteella malli koulutetaan järjestelmän uusilla tiedoilla sopeutumaan muuttuvaan liiketoimintaympäristöön.
 
  Lisätietoja on kohdassa [Tapahtuman vaihtuvuusennuste (esiversio)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Järjestelmän hallinta

- **Palauta ympäristön oletusasetukset**

  Aloita alusta palauttamalla kaikki valitun esiintymän ympäristössä.

  Lisätietoja on kohdassa [Aiemmin luodun ympäristön palauttaminen](manage-environments.md#reset-an-existing-environment).


- **Yhteyden muodostaminen Azure Data Lake -tallennustiliin palveluobjektin avulla**

  Kirjoita tietojen tuloste tallennustilille ja lue tietoja tallennustililtä Azure-palveluobjektin avulla. Aiemmin luodut tallennustilin yhteydet voivat jatkaa tiliavaimen käyttöä. Niissä on myös päivitysvaihtoehto, jolla palveluobjektia voidaan käyttää jatkossa. Uudet yhteydet perustuvat tallennustilin palveluobjektin todennusmenetelmään.

  Lisätietoja on kohdassa [Yhteyden muodostaminen Azure Data Lake Storage Gen2 -tiliin käyttäjäryhmän merkityksellisten tietojen Azure-palveluobjektilla](connect-service-principal.md).

## <a name="october-2020-updates"></a>Lokakuun 2020 päivitykset

Lokakuun 2020 päivitykset sisältävät useita ominaisuuksia, suorituskykypäivityksiä ja virheiden korjauksia.

### <a name="new-and-updated-features-in-october-2020"></a>Uudet ja päivitetyt ominaisuudet lokakuussa 2020

#### <a name="extensibility"></a>Laajennettavuus

- **Vienti kohteeseen Mailchimp**

Viemällä segmenttejä aiemmin luotuihin Mailchimp-käyttäjäryhmäluetteloihin voit antaa asiakkaille mukautetun sähköpostikokemuksen.

Lisätietoja on kohdassa [Mailchimp-yhdistin](export-mailchimp.md).

#### <a name="data-enrichment"></a>Tietojen rikastaminen

- **Lähdetietueiden kaksoiskappaleiden poistaminen vastine-entiteetissä**

Määritä kaksoiskappaleiden poistosäännöt entiteeteissä, joiden avulla etsitään vastine tietueiden kaksoiskappaleita määritettäessä. Yhdistä ne yhdeksi tietueeksi ja linkitä kaikki lähdetietueet tähän yhdistettyyn tietueeseen. Tätä kaksoiskappaleiden poistotietuetta käytetään sitten entiteettien välisessä vastaavuusprosessissa.

Lisätietoja on kohdassa [Vastine-entiteetin kaksoiskappaleiden poiston määrittäminen](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Järjestelmän hallinta

- **Orkestrointi: uusi yhdistämisen päivitysvaihtoehto**

Tähän saakka yhdistämisprosessia suoritettaessa järjestelmä suoritti kaikki seuraavat prosessit, jotka ovat riippuvaisia yhdistämisestä ja sitä seuraavista prosesseista. Voit nyt tarkistaa, että yhdistämisprosessin tuloksen (yhtenäistetyn asiakasentiteetin), ennen kuin sitä käytetään seuraavissa käsittelyissä, kuten segmentissä tai mittareissa.
Yhdistämissivulla voidaan nyt valita vain yhdistämisvaiheen suorittaminen ja suorittaa vain tämä prosessi. Kaikki seuraavat prosessit voidaan päivittää valitsemalla yhdistämisen ja seuraavien prosessien suorittaminen. 

## <a name="september-2020-updates"></a>Syyskuun 2020 päivitykset

Syyskuun 2020 päivitykset sisältävät useita toimintoja, suorituskykypäivityksiä ja ohjelmavirheiden korjauksia.

### <a name="new-and-updated-features-in-september-2020"></a>Uudet ja päivitetyt toiminnot syyskuussa 2020

#### <a name="activities"></a>Toiminnat

- **Älykäs määritteen semanttinen ennuste**

Tämä uusi toiminto ennustaa tietojen yhdistämisprosessiin siirrettävien syötemääritteiden semanttisen tyypin. Se käyttää tarkkuutta parantavia ja aikaa säästäviä koneoppimismalleja.

#### <a name="enrichments"></a>Rikastukset

- **Experianin demografiatietojen rikastaminen**

Demografiatietojen rikastaminen Experianista on saatava esiversiona. Experian on maailman johtava kuluttaja- ja yritysluottojen raportointi- ja markkinointipalvelujen toimittaja. [Experianin tietojen rikastamispalveluilla](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) voidaan syventää tietoja asiakkaista rikastamalla asiakasprofiileja demografiatiedoilla, kuten sillä, minkä kokoinen talous on kyseessä ja minkälaiset tulot sillä on käytettävissä.

Tämän toiminnon käyttö edellyttää aktiivista Experian-tilausta.

Lisätietoja on kohdassa [Asiakasprofiilien rikastaminen Experianin demografiatiedoilla](enrichment-experian.md)


#### <a name="system-administration"></a>Järjestelmän hallinta

- **Tehtävän tietoruutu**

Tehtävän tietoruudussa on tietoja järjestelmän suorittamista tehtävistä. Se on kätevä tapa selvittää määrityksessä olevia ongelmia ja etsiä ratkaisuja.
Virhesanomia tarkastelemalla saa ohjeita mahdollisten ongelmien korjaamiseen.
 
- **Useille sivuille lisättyjen tietojen käsitteleminen**

Tämä parannus lisää tietoja **Entiteetit**- ja **Asiakkaat**-sivulla olevien entiteettien tilasta.
 
Voit lisäksi etsiä kummaltakin sivulta tietoja prosessien edistymisestä sekä tietoja tehtävistä.

- **Järjestelmän tilasivun parannukset**

**Järjestelmä** > **Tila** -valinnalla saatavan tilatietotaulukon rakennetta on parannettu tietojen vientejä tarkasteltaessa.
 
Lisäksi **Tiedot**-sarakkeessa ovat virheet ovat nyt entistä tarkempia ja niiden perusteella voi toimia. 
 
- **Peruuttaminen palauttaa työn edelliseen tilaan**

Kun työ peruutetaan esimerkiksi täsmäytysprosessissa, se palautuu takaisin viimeisimpään tilaan. Jos esimerkiksi täsmäytysprosessi suoritettiin eilen ja se peruutettiin tänään, se palautuu eilisen onnistuneeseen tilaan.


## <a name="august-2020-updates"></a>Elokuun 2020 päivitykset

Elokuun 2020 päivitykset sisältävät useita toimintoja, suorituskykypäivityksiä ja ohjelmavirheiden korjauksia.

### <a name="new-and-updated-features-in-august-2020"></a>Uudet ja päivitetyt toiminnot elokuussa 2020

#### <a name="data-unification"></a>Tietojen yhdistäminen

- **Parannettu yhdistämisvaiheen kokemus tietojen yhdistämisen aikana**

  Tietojen yhdistämisprosessin yhdistämisvaihekokemuksessa voi valita entiteettejä ja määritteitä sekä määrittää semantiikan aiempaa sujuvammin.

  Muutoksia:
  
  - Entiteettien ja kenttien lisäämiseen tarvitaan vähemmän toimintoja
  - Yhdistämissivun parannetut hakuominaisuudet
  - Ehdotetun kenttätyypin visuaalinen ja helppo tunnistus

#### <a name="enrichment"></a>Rikastus

- **Kiinnostuksen kohteiden affiniteettien rikastaminen käytettävissä useilla markkinoilla**

  Olemme laajentamassa kiinnostuksen kohteiden affiniteettien rikastamisen saatavuutta Yhdysvaltojen ulkopuolelle viidelle markkina-alueelle: Kanada, Australia, Yhdistynyt kuningaskunta, Ranska ja Saksa. Tämän laajennuksen avulla voit rikastaa asiakastietoja niin, että ne ottavat huomioon nämä markkinat aiempaa paremmin. Lisäksi rikastetaan näillä markkinoilla sijaitsevia asiakasprofiileja käyttämällä Microsoft Graphin paikallisia tietoja.
  Lisätietoja on kohdassa [Asiakasprofiilien rikastaminen brändin ja kiinnostuksen kohteiden affiniteeteillä](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>Heinäkuun 2020 päivitykset

Heinäkuun 2020 päivitykset sisältävät useita toimintoja, suorituskykypäivityksiä ja virheiden korjauksia.

### <a name="new-and-updated-features-in-july-2020"></a>Uudet ja päivitetyt toiminnot heinäkuussa 2020

#### <a name="extensibility"></a>Laajennettavuus

- **Power Automate -käynnistin valmistuneelle yhdistämisprosessille**

  Power Automate -käynnistimiä on laajennettu ja on annettu mahdollisuus luoda ilmoitus tai toiminto, kun jonkin yhdistämisprosessin päivitys on valmis.    
  Lisätietoja on kohdassa [Power Automate -yhdistin](export-power-automate.md).

#### <a name="enrichment"></a>Rikastus

- **Tuotemerkin affiniteettien rikastaminen käytettävissä useilla markkinoilla**

  Olemme laajentamassa tuotemerkin affiniteettien rikastamisen saatavuutta Yhdysvaltojen ulkopuolelle viidelle markkina-alueelle: Kanada, Australia, Yhdistynyt kuningaskunta, Ranska ja Saksa. Tämän laajennuksen avulla asiakastietoja voi rikastaa näiden markkinoiden paikallisilla tuotemerkeillä. Lisäksi rikastetaan näillä markkinoilla sijaitsevia asiakasprofiileja käyttämällä Microsoft Graphin paikallisia tietoja.
  Lisätietoja on kohdassa [Asiakasprofiilien rikastaminen brändin ja kiinnostuksen kohteiden affiniteeteillä](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>Kesäkuun 2020 päivitykset

Kesäkuun 2020 päivitykset sisältävät useita toimintoja, suorituskykypäivityksiä ja virheiden korjauksia.

### <a name="new-and-updated-features-in-june-2020"></a>Uudet ja päivitetyt toiminnot kesäkuussa 2020

#### <a name="enrichment"></a>Rikastaminen

- **Yritystietojen rikastaminen Leadspacesta**
  
  Määritä yhdistetyissä asiakasprofiileissa kentät, joilla haetaan liittyviä yritystietoja Leadspacesta. Kun rikastusprosessi on suoritettu, yritystenväliset profiilit rikastetaan määritteillä, kuten yrityksen koko, sijainti ja toimiala.    
  Tämä yhteistyön avulla voi parantaa tietojen laatua kolmen osapuolen palveluista saatavilla tiedoilla. Tämän rikastamisen käyttöön tarvitaan Leadspacen käyttöoikeus, jolla voi käyttää sen yritystenvälisiä yritystietoja. Järjestelmä käyttää kyseistä käyttöoikeutta tietojen jatkuvaan rikastamiseen.    
  Lisätietoja on kohdassa [Yritysprofiilien rikastaminen Leadspacen avulla](enrichment-leadspace.md).

- **Rikastamiskeskuksen sivu**

  Kaikki käytössä oleva rikastettu tieto sekä ensimmäisen että kolmannen osapuolen rikastamispalveluista määritetään samassa paikassa. Tietojen rikastamisen määrittäminen on sujuva kokemus, jotta hallitaan samasta paikasta.    
  Lisätietoja on kohdassa [Asiakasprofiilien rikastaminen](enrichment-hub.md).

- **Erillinen tuotemerkin ja kiinnostuksen kohteiden affiniteetin rikastaminen**

  Tuotemerkkien ja kiinnostuksen kohteiden affiniteetit ovat nyt saatavana kahtena erillisenä rikastamisena. Koska rikastamiset ovat erillisiä, niitä voi määrittää ja hallita joustavasti liiketoiminnan tarpeiden mukaan.    
  Lisätietoja on kohdassa [Asiakasprofiilien rikastaminen brändin ja kiinnostuksen kohteiden affiniteeteillä](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Laajennettavuus

- **Yhdistettyjen aktiviteettien napsautettavat URL-osoitteet Dynamics 365:n asiakaskortin apuohjelmalla**

  Asiakaskortin apuohjelman yhtenäistetyissä aktiviteeteissa näkyy nyt napsautettavia URL-osoitteita, jos kyseiset URL-osoitteet on määritetty aktiviteettien määrityksen yhteydessä.    
  Lisätietoja on kohdassa [Asiakasortti-apuohjelma](customer-card-add-in.md).

- **Tuotemerkin ja kiinnostuksen kohteiden affiniteetit ovat saatavana Dynamics 365:n asiakaskortin apuohjelmassa**

  Dynamics 365:n asiakaskortin apuohjelman uudella ohjausobjektilla voi näyttää tuotemerkin ja kiinnostuksen kohteiden rikastamiset, jotka on tehty Dynamics 365:n asiakkaan osallistamissovellusten yhteyshenkilöissä.    
  Lisätietoja on kohdassa [Asiakasortti-apuohjelma](customer-card-add-in.md).

- **Lisää Power Automate -käynnistimiä**

  Power Automate -käynnistimiä on laajennettu ja seuraavat käynnistimet on lisätty:
  - Ilmoitus tai toiminnon suorittaminen, kun automaattinen täydellinen päivitys (tietolähteissä, yhdistämisessä, segmenteissä, mittareissa, viennissä) valmistuu
  - Määritä liiketoimintamittarin raja-arvo. Voit esimerkiksi luoda ilmoituksen, joka lähetetään, kun määritetty kynnysarvo ohitetaan. Lisäksi käynnistimellä saadaan tietoja, joiden avulla voi muodostaa entistä monimutkaisempia työnkulkuja Power Automatessa.    
  Lisätietoja on kohdassa [Power Automate -yhdistin](export-power-automate.md).

- **Vienti Facebookin mainosten hallintaan**
  
  Tämän ominaisuuden avulla segmentit voidaan viedä Facebookin mainosten hallintaan. Segmentit viedään mukautettuina käyttäjäryhminä, jotka käyttävät yhtenäistettyjä asiakasprofiileja Facebookin markkinointikampanjoissa ja mainoksissa. Mukautettuja käyttäjäryhmiä voi käyttää myös kampanjoiden luontiin Instagrammissa Facebookin mainosten hallinnan avulla.    
  Lisätietoja on kohdassa [Facebookin mainosten hallinnan yhdistin](export-facebook.md).

#### <a name="predictions"></a>Ennusteet

- **Tilauksen vaihtuvuusennuste**

  Luo tilausalueille, kuten pilvipalveluille, asiakasjäsenyydelle ja muille sektoreille, vaihtuvuusennuste opastetun kokemuksen ohjeiden avulla. 

  Tilauksen vaihtuvuuden ennustetoiminnolla voi ennustaa ilman tietotutkijoiden apua, kuinka todennäköisesti asiakas lopettaa tilauspohjaisten tuotteiden tai palvelujen käytön. Ennusteen pistemäärän avulla voi yhdistää muita asiakasta koskevia tietoja ja luoda suuren vaihtuvuusriskin segmenttejä. Tämän segmentin avulla on helppo kohdistaa markkinointi, asiakastuki ja muut skenaariot suoraan asiakkaille ja vähentää tällä tavoin tiettyjen asiakkaiden vaihtuvuusriskiä. Tämä puolestaan lisää tuottoa ja pienentää kustannuksia.

  Kokemuksessa voi määrittää vaihtuvuuden määritelmän liiketoimintakohtaiseksi aikaikkunaksi. Esimerkiksi kuukausitilauksia käyttävässä videoiden suoratoistopalvelussa asiakas voidaan katsoa vaihtuneeksi 15 päivää tilauksen päättymisen jälkeen.

  Kun siirryt ennusteessa, saat ohjeita tarvittavista tiedoista ja niiden yhdistämisestä liiketoiminnassa kenttiin, joita tarvitaan asiakkaiden vaihtuvuuden ennustamiseen. Koska liiketoimintatiedot muuttuvat, voit myös määrittää aikataulun, jolla järjestelmässä olevat uudet tiedot koulutetaan uudelleen muuttuvan liiketoiminnan mukaisesti.    
  Lisätietoja on kohdassa [Tilauksen vaihtuvuusennuste (esiversio)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmentit

- **Etsi samankaltaisia asiakkaita**
  
  Etsi samankaltaisia asiakkaita asiakaskunnasta tekoälyn avulla. Koneoppimismallin binaariluokitus määrittää samankaltaisuuspistemäärän asiakkaille laajennetussa segmentissä. Pistemäärä perustuu lähdesegmentin asiakkaiden samankaltaisuuteen. Asiakasprofiilit lisätään samankaltaisuuspistemäärän perusteella juuri luotuun segmenttiin.

  Sitä kutsutaan joskus digitaalisessa markkinoinnissa samankaltaisuuden mallintamiseksi ja se käyttää tekoälymallia etsiessään asiakkaita, jotka ovat samanlaisia kuin toisen segmentin asiakkaat. Tämä saadaan aikaan tekemällä lisää määritteitä. Määritteiden valinnan lisäksi voit myös määrittää asiakkaiden enimmäismäärän uuteen segmenttiin. Tekoälymalli laskee sitten samankaltaisuuspistemäärän kullekin asiakkaalle valittujen määritteiden perusteella ja etsii asiakkaat, joilla on korkea keskimääräinen samankaltaisuuspistemäärä. Tuloksena on segmentti, joka sisältää alkuperäisessä segmentissä ollutta asiakasta muistuttavia asiakkaita.    
  Lisätietoja on kohdassa [Samankaltaiset asiakkaat](find-similar-customer-segments.md).

- **Segmentin päällekkäisyys ja erottavat tekijät**

  Segmentin päällekkäisyyden avulla nähdään, kuinka paljon vähintään kahdella segmentillä on samoja asiakkaita ja keitä nämä asiakkaat ovat. Esimerkkejä ovat esimerkiksi paljon kuluttavien segmentin päällekkäisyys erittäin tyytyväisten asiakkaiden segmentin kanssa tai asiakkaiden vaihtuvuussegmentin päällekkäisyys tyytymättömien asiakkaiden segmentin kanssa. Voit myös analysoida, miten päällekkäisyys muuttuu valitsemasi lisämääritteen perusteella.

  Segmentin erottavat tekijät paljastavat, mikä erottaa segmentin muista asiakkaista tai toisesta segmentistä. Sinun ei tarvitse tehdä muuta kuin määrittää segmentti. Järjestelmä määrittää sitten profiilin määritteet ja mittaa, mikä erottaa segmentin, käyttämällä erottavien tekijöiden luettelon, joka on järjestetty merkittävimmästä erottavasta tekijästä heikoimpaan erottavaan tekijään.    
  Lisätietoja on kohdassa [Segmentin tiedot (esiversio)](segment-insights.md).

- **Segmentin elinkaari**
  
  Määritä segmentin aktivointi- ja aktivoinnin poistoaikataulu.    
  Lisätietoja on kohdassa [Aiemmin luotujen segmenttien hallinta](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Toukokuun 2020 päivityksey

Toukokuun 2020 päivitykset sisältävät useita ominaisuuksia, suorituskykypäivityksiä ja korjauksia.

### <a name="new-and-updated-features-in-may-2020"></a>Uudet ja päivitetyt ominaisuudet toukokuussa 2020

#### <a name="data-ingestion"></a>Tietojen käsittely

- **Reaaliaikaisten tietojen käsittely: historianäkymät**

  Kun käytät API-liittymää reaaliaikaisten päivitysten käsittelyyn, näihin päivityksiin voi tulla enintään 30 päivää koottua historiaa. Voit käyttää kaikkien onnistuneiden tai epäonnistuneiden API-kutsujen koosteita, kuten tuloksia, lähdejärjestelmää ja muita hyödyllisiä metatietoja.    
  Lisätietoja on kohdassa [Reaaliaikainen tietojen käyttö](real-time-data-ingestion.md).

- **Reaaliaikaisten tietojen käsittely: profiilipäivitykset**

  Tämän reaaliaikaisen tietojen käsittelyn laajennuksen ansiosta voit nähdä muutamassa sekunnissa muutoksia tiettyihin käyttäjäprofiilikenttiin.    
  Aktiviteettien reaaliaikaisten toimintojen lisäksi järjestelmä tukee profiilikenttien lyhyen viiveen päivityksiä. Profiilikenttien reaaliaikaisilla päivityksillä on vanhenemisaika, joten ne eivät korvaa aikataulutettuja päivityksiä.    
  Lisätietoja on kohdassa [Reaaliaikainen tietojen käyttö](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Laajennettavuus

- **Päivitetty aikajana ja sivutus asiakaskortin apuohjelmassa**

  Asiakaskortin apuohjelmaratkaisun aikajana vastaa aktiviteetin aikajanaa. Aikajanan sivutus parani ja jopa 50 aktiviteettia näkyy samalla kertaa. Se sallii myös useampien aktiviteettien lataamisen aikajanalle.    
  Lisätietoja on kohdassa [Asiakasortti-apuohjelma](customer-card-add-in.md).

- **Power Automate -käynnistin segmenttimuutoksille**

  Power Automaten käynnistimet määrittävät, mistä työnkulun voi rakentaa. Juuri lisätyn käynnistimen avulla voit määrittää segmentin kynnysarvon. Voit esimerkiksi luoda ilmoituksen, joka lähetetään, kun määritetty kynnysarvo ohitetaan.    
  Lisätietoja: [Power Automate -yhdistin](export-power-automate.md).

- **Mukautettujen mallien usean vuokraajan tuki**

  Mukautettujen mallien työnkulkujen määrittäminen käyttämällä eri Azure Machine Learning -vuokraajan verkkopalvelua. Voit kirjautua Azure Machine Learning -vuokraajaan mukautettujen mallien uutta työnkulkua luotaessa. Tämä ominaisuus on lisäys olemassa olevaan kykyyn integroida oma mukautettu Azure Machine Learning -verkkopalvelu.    
  Lisätietoja on aiheessa [Mukautetut koneoppimismallit](custom-models.md).

#### <a name="segments"></a>Segmentit

- **Entiteettipolun automatisointi**

  Käyttäjien on määritettävä entiteettipolku segmenttiä luotaessa. Tämä ominaisuus ottaa ensimmäisen askelen entiteettipolun määrityksen automatisoinnissa, jotta voit keskittyä haluamiisi segmentointiehtoihin.    
  Jos entiteetti, jonka mukaan haluat segmentoida asiakkaat, liittyy suoraan yhdistettyyn asiakasentiteettiin, entiteetin polkua ei enää tarvitse määrittää. Jos mahdollisia entiteetin polkuja on kuitenkin enemmän kuin yksi, se on määritettävä manuaalisesti.

- **Toiminnot useille segmenteille**
  
  Käyttäjät voivat valita useita segmenttejä ja tehdä niihin toimintoja, kuten päivittää segmentit yhdellä napsautuksella.    

- **Päivitä segmentit**

  Käyttäjät voivat päivittää yksittäisen segmentin tai valita vain ne segmentit, jotka haluavat päivittää.    

  
- **Parannuksia yhdistelmäsegmentteihin**

  Käyttäjät voivat luoda, muokata ja poistaa segmenttejä, jotka perustuvat muihin segmentteihin. Esimerkiksi toisen segmentin pohjalta muodostettu segmentti, joka on muodostettu kolmannen segmentin pohjalta.    

- **Segmenttiluettelosivu**

  Segmentit-sivun uusi rakenne käyttää luettelomuotoa, jonka avulla voit tarkastella useampia segmenttejä samalla kertaa. Hakukenttä lisätään, jotta voit etsiä segmenttejä nopeasti. Käyttäjät voivat nyt käyttää toimintoja, kuten ladata tai poistaa useita segmenttejä kerralla. Uusi trendikokemus on otettu käyttöön, jotta segmentteihin tehdyt merkittävät muutokset voidaan nopeasti havaita.    
  Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).

#### <a name="system-administration"></a>Järjestelmän hallinta

- **Customer Insights saatavilla Microsoft Dynamics 365 Online Government -ratkaisussa**

  Kun yhä useammat kanavat liittyvät vuorovaikutukseen, kansalaisten tiedot ovat hajallaan lukemattomissa järjestelmissä, mikä johtaa siiloihin ja pirstoutuneeseen tietoon kansalaisten kanssakäymisestä. Hallituksen ei ole mahdollista nykyaikaistaa toimintoja suuressa mittakaavassa, ellei kunkin kansalaisen vuorovaikutuksesta eri kanavissa ole kokonaiskuvaa. Microsoft on sitoutunut tukemaan hallituksen tarpeita, jotta se voi pysyä kansalaisten odotusten tasalla luodakseen johdonmukaisia ja mukautuvia käyttökokemuksia.    
  Vuoden 2020 1. julkaisuaallossa Dynamics 365 Customer Insights on käytettävissä Government Community Cloud (GCC) -ympäristössä, joka on suunniteltu täyttämään Yhdysvaltain hallituksen virastojen tiukemmat vaatimukset. Virastot saavat yhdistetyn näkemyksen kansalaisista ja käyttävät valmiita tekoälytoimintoja johtaakseen näkemyksiä, jotka parantavat vuorovaikutusta, auttavat työntekijöitä, ja uudistavat yhteisöjä samalla vähentäen IT:n monimutkaisuutta ja täyttää Yhdysvaltojen vaatimustenmukaisuus- ja turvallisuusstandardit. Dynamics 365 Government täyttää tiukat US Federal Risk and Authorization Management Program (FedRAMP) -ohjelman vaatimukset, jolloin Yhdysvaltain liittovaltion virastot voivat hyötyä Microsoft Cloudin kustannussäästöistä ja vankasta turvallisuudesta.

## <a name="april-2020-updates"></a>Huhtikuun 2020 päivitykset

Huhtikuun 2020 päivitykset sisältävät useita ominaisuuksia, suorituskykypäivityksiä ja korjauksia.

### <a name="new-and-updated-features-in-april-2020"></a>Uudet ja päivitetyt ominaisuudet huhtikuussa 2020

#### <a name="activities"></a>Aktiviteetit

- **Yhdistää aktiviteettientiteetit vakioaktiviteettityyppeihin**
  
  Aktiviteetin määritys ja tallennus perustuvat tällä hetkellä staattiseen rakenteeseen, jotta niitä voidaan tarkastella aikajanalla. Aktiviteettien semanttinen merkitys, jolla on potentiaalia useisiin käyttötapauksiin tekoälymalleissa, ei ole tällä hetkellä täysin käytössä. Aktiviteettiaikajanasta on tarkoitus tehdä dynaamisempi aktiviteettityypin perusteella ja parempi aktiviteettien semanttisessa ymmärtämisessä. Tämän ominaisuuden tarkoituksena on määrittää kaikkien käsiteltyjen aktiviteettien Common Data Modelissa määritetty aktiviteettityyppi.
  Lisätietoja on kohdassa [Asiakasaktiviteetit](activities.md).

#### <a name="data-ingestion"></a>Tietojen käsittely

- **Reaaliaikaisten tietojen käsittely: aktiviteetit**
  
  Reaaliaikaisesta tietojen käsittelystä saadaan heti tietoja käyttöön siihen saakka, että seuraava ajoitettu päivitys hakee nämä tiedot tietolähteestä.    
  Lisätietoja on kohdassa [Reaaliaikainen tietojen käyttö](real-time-data-ingestion.md).

- **Parannukset tietojen valmisteluun**
  
  Lisätietoja entiteetissä käsitellyistä tiedoista. Tietojen yhteenvedon avulla voit ymmärtää tietojen laatuominaisuudet, jotka voivat auttaa toteuttamaan tarvittavat toimet.    
  Lisätietoja on aiheessa [Tutustu entiteettien tietoihin](entities.md#exploring-a-specific-entitys-data).

- **Analyysitietojen käsittely Dynamics 365 -järjestelmästä Common Data Servicen avulla**
  
  Common Data Service on saatavana tietolähteiden luontitapana. Aiemmin luodut Dynamics 365 -asiakkaat voivat käsitellä analyysientiteettejä Common Data Servicesta Customer Insightsiin. Yksi tietolähde voi käyttää kerralla samaa Common Data Servicen hallittua Data Lake -tallennustilaa Customer Insights -ympäristössä.    
  Lisätietoja on aiheessa [Yhteyden muodostaminen hallitun Common Data Service Data Laken tietoihin](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Laajennettavuus

- **Vie LiveRampiin**

  Aktivoi tietosi LiveRamp® -ratkaisussa muodostaaksesi yhteyden yli 500 ympäristöön digitaalisissa, yhteisöllisissä ja television ekosysteemeissä. Käytä LiveRamp-tietoja mainoskampanjoiden kohdistamisessa, estämisessä ja mukauttamisessa.    
  Lisätietoja: [LiveRamp&reg; -yhdistin](export-liveramp.md).

- **Customer Insightsin Teams-laajennus**
  
  Botti tarjoaa yhdistettyjen asiakasprofiilien hakumahdollisuuksia. Siinä näkyy kortti, jossa on enintään 15 kenttää tuloksena olevasta asiakasprofiilista. Useat vastaavuudet palauttavat tulosluettelon, josta voit valita profiilin.    
  Lisätietoja on kohdassa [Teams-botti Customer Insightsille](export-teams-bot.md).

#### <a name="measures"></a>Mittarit

- **Mittariluettelosivu**
  
  Mittarit-sivun parannukset sisältävät yksittäisen mittarin ja useiden mittarien samanaikaisten toimintojen tuen. Lisäksi löydät hakukentän, jonka avulla voit etsiä ja seurata mittareita nopeasti.    
  Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).

- **Parannuksia yhdistelmämittareihin**
  
  Käyttäjät voivat luoda, muokata ja poistaa mittareita, jotka perustuvat muihin mittareihin. Esimerkiksi toisen mittarin pohjalta muodostettu mittari, joka on muodostettu kolmannen mittarin pohjalta.

#### <a name="segments"></a>Segmentit

- **Toinen operaattori**
  
  In-set -operaattori sallii asiakkaiden segmentoinnin useilla mahdollisilla merkkijonoarvoilla. Ennen tämän operaattorin lisäämistä sinun oli rakennettava tällaiset segmentit useilla OR-ehdoilla. In-set -operaattorin avulla voit tehdä sen yhdellä ehdolla.    
  Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).

#### <a name="system-administration"></a>Järjestelmän hallinta

- **Määritysasetusten kopioiminen uuteen ympäristöön**
  
  Kopioi määritys ympäristöstä toiseen. Kun luot uutta ympäristöä, voit valita aiemmin luodun ympäristön, josta haluat kopioida määrityksen. Tällä hetkellä kopioinnissa tuetaan tietolähteitä, tietojen yhdistämistä, suhteita, mittareita ja segmenttejä. Tietolähteen tunnistetietoja ja itse tietoja ei kopioida.    
  Lisätietoja on kohdassa [Ympäristöjen hallinta](manage-environments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]