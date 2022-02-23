---
title: Asiakaspalautteen asenneanalyysi
description: Tietoja asenneanalyysimallin käyttämisestä Dynamics 365 Customer Insightsin asiakaspalautteessa.
ms.date: 12/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 8a4473c1c395bbcf8efa2bfa24cddb82e1784279
ms.sourcegitcommit: 15ec8c5f54242feda9489e7665726ec5e0983dc9
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/19/2022
ms.locfileid: "8008761"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Asiakaspalautteen asenteen analysointi (esiversio)

Asiakkaat odottavat nykyisin, että tuotteet, palvelut ja kokemukset ovat laadukkaita. Tällaisia ovat etenkin palautetta antavat asiakkaat. Organisaatioiden kannalta on erittäin haastavaa analysoida kasvavaa tietomäärää ilman, että tarkkuus heikkenee ja työvoimakustannukset nousevat. Dynamics 365 Customer Insights sisältää asiakaspalautteen asenneanalyysimallin, jonka avulla organisaatiot voivat analysoida tietoja entistä tarkemmin ja edullisemmin.

Asenneanalyysin avulla voidaan tehdä asiakkaan asennesynteesi ja määrittää liiketoiminnan osia parannusmahdollisuuksiksi. Tämä Customer Insights -ominaisuus auttaa hahmottamaan, mikä toimii ja mitä on kehitettävä. Keskittyminen keskeisiin ja vaikutukseltaan suurimpiin liiketoiminta-alueisiin parantaa asiakkaiden kokemusta. Viime kädessä se voi edistää liiketoimintoja, joihin perustuvat kokemukset voivat parantaa asiakastyytyväisyyttä ja -uskollisuutta.

## <a name="overview"></a>Yleiskuvaus

Asenneanalyysiominaisuus luo kaksi asiakastunnuskohtaista johdettua merkityksellistä tietoa. Asennepisteytys (-5...5) ja soveltuvat liiketoiminnan alueet parantavat yhdessä käytettyinä asiakaspalautteen hahmottamista. 

Nämä tiedot voivat auttaa saavuttamaan seuraavat tulokset: 
- Yleiskuvaus brändiä tai organisaatiota koskevista asiakkaiden asenteista
- Niiden asiakkaiden tunnistaminen, joilla on negatiivinen asenne, sekä kampanjoiden ja aktivoinnin keskittäminen ja tuoton optimointi niiden perusteella  
- Asiakkaiden osoittamien liiketoiminnan ongelma-alueiden määrittäminen  
- Asiakkaiden segmentointi asenteen perusteella sekä mukautettujen kampanjoiden suorittaminen näiden tietojen perusteella kohdistamalla myynti, markkinointi ja tuki
- Liiketoimintojen optimointi käsittelemällä asiakkaiden mainitsemat alueet, joihin liittyy ongelmia tai mahdollisuuksia
- Hyvin toimien liiketoiminta-alueiden tunnistaminen sekä tyytyväisten asiakkaiden palkitseminen kanta-asiakas- ja korotusongelmien avulla

Mallien tulosten luotettavuus varmistetaan antamalla läpinäkyvästi tietoja mallien päätöstentekotavoista. Saatavana on luettelo sanoista, jotka vaikuttavat mallien päätökseen määrittää tietty asennepisteytys tai liiketoiminta-alue palautteen kommentteihin.  

Käytössä on kaksi **luonnollisen kielen käsittelymallia (NLP-mallia)**: Ensimmäinen malli määrittä kullekin palautekommentille asennepisteet. Toinen malli liittää kunkin palautteen kaikkiin soveltuviin liiketoiminnan alueeseen. Mallien koulutukseen käytetään julkisia, erilaisista lähteistä saatavia tietoja. Näitä lähteitä ovat yhteisöpalvelu sekä jälleenmyynti-, ravintola- ja kuluttajatuotealat sekä autoteollisuus.    
  
Mallin palautetietoihin liitettäviä esimääritettyjä liiketoiminnan alueita ovat esimerkiksi seuraavat:
-   Asiakashallinta
-   Uloskuittaus ja maksu
-   Asiakastuki
-   Noudot myymälästä
-   Pakkauksen toimitus ja nouto
-   Ennakkotilaukset
-   Hinta
-   Tietoturva ja tietosuoja
-   Kampanjat ja palkkiot
-   Kuitti ja takuu
-   Palautusten vaihto ja peruutus
-   Täytäntöönpanojen tarkkuus
-   Sivuston/sovelluksen laatu

> [!NOTE]
> Tällä hetkellä tuetaan vain englanninkielisen palautteen asenneanalyysia. Jatkossa tuetaan myös muita kieliä. Malli palauttaa tulokset myös silloin, jos ladataan muun kielistä palautetta. Nämä tulokset eivät kuitenkaan ole tarkkoja. 

## <a name="prerequisites"></a>edellytykset

Asenneanalyysi perustuu tekstimuotoiseen palautetietoihin, joille on tehty [tietojen yhtenäistämisprosessi](data-unification.md). On erittäin suositeltavaa, että [palautetietoentiteetit määritetään semanttistyyppisinä aktiviteettientiteetteinä](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (palautetyyppi) etukäteen. 

Asenneanalyysimallin määrittämiseen tarvitaan ainakin [osallistujan oikeudet](permissions.md).

Customer Insights voi käsitellä enintään 10 miljoonaa palautetietuetta yhtä mallia suoritettaessa. Malli voi analysoida enintään 128 sanaa sisältäviä palautekommentteja. Jos palautekommentti on tätä pidempi, analyysi ottaa huomioon vain ensimmäiset 128 sanaa.

### <a name="data-requirements"></a>Tietojen vaatimukset
  
Seuraavat tietomääritteet tarvitaan:
- Yhtenäistetty asiakastunnus (UCID), jonka avulla tekstimuotoiset palautetietotietueet voidaan kohdistaa yksittäiseen asiakkaaseen. Tämä tunnus on peräisin [tietojen yhtenäistämisprosessista](data-unification.md).
- Palautteen tunnus
- Palautteen aikaleima
- Palautteen teksti   

> [!TIP]
> Asenneanalyysia varten tarvitaan asiakkaiden antamaa tekstimuotoista palautetta. Tällä hetkellä voidaan määrittää vain yksi palaute-entiteetti. Jos palaute-entiteettejä on useita, ne voidaan yhdistää Power Queryssä ennen tietojen käsittely alkamista.

## <a name="configure-a-sentiment-analysis"></a>Asenneanalyysin määrittäminen 

1. Siirry Customer Insightsissa kohtaan **Älykäs toiminto** > **Ennusteet**.

1. Valitse **Asiakkaan asenneanalyysi** -ruudussa **Käytä mallia**.

1. Valitse **Asiakkaan asenneanalyysi (esiversio)** -ruudussa **Aloita käyttö**.

1. Anna **Mallin nimi** -vaiheessa analyysin **nimi**. 

1. Anna **Liiketoimintanäkökulman tulosentiteetin nimi** ja **Asennepisteytyksen tulosentiteetin nimi** ja valitse sitten **Seuraava**.

1. Valitse **Pakolliset tiedot** -vaiheessa **Lisää tiedot**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Tietovuon lisääminen asenneanalyysimallissa":::

1. Valitse **Lisää tiedot** -ruudussa luettelossa semanttiseksi tyypiksi **Palaute**.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Määrityksen asenneanalyysin palauteaktiviteettien valintavaihe":::

1. Valitse asenneanalyysissa käytettävät aktiviteetit ja valitse sitten **Seuraava**.
 
1. Yhdistä tietojen määritteet mallin määritteisiin. Ota valinnat käyttöön valitsemalla **Tallenna**. 

1. Tietojen yhdistämismäärityksen tila on näkyvissä. Jatka valitsemalla **Seuraava**. 

1. Tarkista asenneanalyysin määritykset **Tarkista mallitiedot** -vaiheessa. Mihin tahansa ennustemäärityksen osaan on mahdollista valita. Aloita analyysi valitsemalla **Tallenna ja suorita**. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Kaikki määritetyt kohteet näyttävä asennemallin tarkistusvaihe":::

1. Poista määrityskokemuksesta valitsemalla **Valmis**. Prosessin valmistuminen voi kestää useita tunteja käytetyn tietomäärän mukaan. 

## <a name="review-analysis-status"></a>Analyysin tilan tarkasteleminen

1.  Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.
2.  Valitse ennuste, jota haluat tarkastella.
- **Ennusteen nimi**: Ennusteelle luonnin yhteydessä annettu nimi.
- **Ennustetyyppi**: Ennusteessa käytetyn mallin tyyppi.
- **Tulosentiteetti**: Sen entiteetin nimi, johon ennusteen tulos tallennetaan. Siirry kohtaan **Tiedot** > **Entiteetit**, jos haluat löytää tämännimisen entiteetin.
- **Ennustettu kenttä**: Tämä kenttä täytetään vain tietyissä ennustetyypeissä eikä sitä käytetä asiakkaan elinkaaren arvon ennusteessa.
- **Tila**: Ennusten suorituksen tila.
  - **Jonossa**: Ennuste odottaa muiden prosessien valmistumista.
  - **Päivittyy**: Ennustetta suoritetaan parhaillaan, jotta luodaan tulosentiteettiin siirrettävät tulokset.
  - **Epäonnistui**: Ennusteen suorittaminen epäonnistui. Lisätietoja saa lokeja tarkastelemalla.
  - **Onnistui**: Ennuste onnistui. Valitse kolmen pystysuuntaisen pisteen alapuolella oleva Näytä-kohta, jos haluat tarkastella ennusteen tuloksia.
- **Muokattu**: Ennusteen määrityksen muutospäivämäärä.
- **Päivitetty viimeksi**: Päivämäärä, jolloin ennusten tietoja päivitettiin tulosentiteetissä.

## <a name="manage-sentiment-analysis"></a>Asenneanalyysin hallinta

Ennusteita voidaan optimoida, päivittää ja poistaa sekä niissä voidaan tehdä vianmäärityksiä. Käytettävyysraportissa on tietoja siitä, miten tehdä ennusteista nopeampia ja luotettavampia. Lisätietoja on kohdassa [Ennusteiden hallinta](manage-predictions.md).

## <a name="review-analysis-results"></a>Analyysin tulosten tarkasteleminen
 
1. Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti. 
1. Valitse sen ennusteen nimi, jonka tuloksia halutaan tarkastella. Valitse tällöin asenneanalyysi, jonka haluat tarkastella. 

### <a name="summary-tab"></a>Yhteenveto-välilehti

Tiedot jakaantuvat tulossivulla neljään pääosaan. 

- **Keskimääräinen asennepisteytys**: Auttaa hahmottamaan kaikkien asiakkaiden yleisen asenteen. Asennepisteytys ryhmitellään kolmeen luokkaan: 
  1.    Kielteinen (-5 > 2)
  2.    Neutraali (-1 > 1)
  3.    Myönteinen (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Asiakkaiden yleisen asenteen visuaalinen esitys":::

- **Asiakasjakauma asennepisteytyksen mukaan**: Asiakkaat luokitellaan asennepisteytyksen mukaan kielteiseen, neutraaliin ja myönteiseen ryhmään. Asiakkaiden määrän ja keskimääräisen asennepisteytyksen saa näkyviin kussakin ryhmässä siirtämällä kohdistimen pylväiden päälle histogrammissa. Näiden tietojen avulla voidaan [luoda asiakassegmenttejä](segments.md) asennepisteytyksen perusteella.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Pylväskaavio ilmaisee asiakkaan asenteen kolmessa asenneryhmässä":::

- **Keskimääräinen asennepisteytys ajan kuluessa**: Asiakkaan asenne voi muuttua ajan kuluessa. Näkyvissä on asiakkaiden trendit tietojen aikaväliltä. Tämä näkymä auttaa mittaamaan kausikampanjoiden, tuotejulkistusten tai muiden aikasidonnaisten tapahtumien vaikutusta asiakkaan asenteeseen. Kaaviota voi katsoa valitsemalla vuoden avattavasta valikosta. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Historiakaavio sekä viivana ilmaistu asennepisteytys ajan mittaan":::
 
- **Asenne liiketoiminnan alueilla**: Tässä taulukossa on luettelo keskimääräisistä asenteista liiketoiminnan eri alueilla. Sen avulla voi mitata, mihin liiketoiminnan alueisiin asiakkaat ovat tyytyväisitä ja mitä on kehitettävä. Jos palautetietue ei sovi mihinkään tuettuun liiketoiminnan alueeseen, se sijoitetaan luokkaan **Muut**. Taulukko on oletusarvoisesti aakkosjärjestyksessä. Lajittelua voi muokata valitsemalla taulukon otsikon.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Luettelo liiketoiminnan alueista ja niihin liittyvästä asennearvosta sekä alueen mainitsevien asiakkaiden määrä":::
 
  Kun liiketoiminnan alueen nimi valitaan, näkyviin tulee lisätietoja siitä, miten malli määrittää liiketoiminnan alueen. Tässä ruudussa on kaksi osaa: 

  - **Vaikuttavat sanat**: näyttää tärkeimmät sanat, jotka vaikuttivat siihen, miten tekoälymalli tunnistaa liiketoiminnan alueen asiakkaan palautteessa. 
    **Näytä kirosanat**: Kirosanat voidaan sisällyttää luetteloon, joka saadaan alkuperäisistä asiakaspalautetiedoista. Se on oletusarvoisesti poistettu käytöstä.  Tekoälymalli toteuttaa kirosanojen peiton, eikä se ehkä havaitse kaikki kirosanoja. Luokittelua iteroidaan ja koulutetaan jatkuvasti, jotta tulos olisi mahdollisimman hyvä. Odotusten vastaisesti havaittu kirosana kannattaa ilmoittaa Microsoftille. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Luettelo vaikuttavista sanoista sekä vaihtopainike, jolla kirosanat näytetään tai piilotetaan":::
 
  - **Palautenäytteet**: Näyttää tietojen varsinaiset palautetietueet. Sanat on värikoodattu sen mukaan, kuinka vaikuttavia ne ovat liiketoiminnan alueen tunnistamisessa. 


### <a name="influential-words-analysis-tab"></a>Vaikuttavien sanojen analyysi -välilehti

Asennemallin toimintaa selittäviä lisätietoja on kolmessa osassa.
  
1. **Myönteiseen asenteeseen eniten vaikuttavat sanat**: näyttää sanat, jotka vaikuttivat eniten siihen, että tekoälymalli tunnistaa myönteisen asenteen asiakaspalautteessa.  
2. **Kielteiseen asenteeseen eniten vaikuttavat sanat**: näyttää sanat, jotka vaikuttivat eniten siihen, että tekoälymalli tunnistaa kielteisen asenteen asiakaspalautteessa.  
3. **Palautenäytteet**: Näyttää varsinaiset palautetietueet, joissa yhdessä on kielteinen asenne ja toisessa myönteinen asenne. Sanat on korostettu palautetietueissa sen perusteella, miten ne vaikuttavat määritettyyn asennepisteytykseen. Myönteiseen pisteytykseen vaikuttavat sanat on korostettu vihreällä. Kielteiseen pisteytykseen vaikuttavat sanat on korostettu punaisella.
   Valitsemalla **Näytä lisää** voidaan ladata lisää palautenäytteitä. Näin saadaan lisätietoja ja -kontekstia asennemallin toimintaan.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Esimerkkejä asiakaspalautteen asenneanalyysista":::
 
**Näytä kirosanat**: Kirosanat voidaan sisällyttää luetteloon, joka saadaan alkuperäisistä asiakaspalautetiedoista. Se on oletusarvoisesti poistettu käytöstä.  Tekoälymalli toteuttaa kirosanojen peiton, eikä se ehkä havaitse kaikki kirosanoja. Luokittelua iteroidaan ja koulutetaan jatkuvasti, jotta tulos olisi mahdollisimman hyvä. Odotusten vastaisesti havaittu kirosana kannattaa ilmoittaa Microsoftille. 

## <a name="act-on-analysis-results"></a>Analyysitulosten perusteella toimiminen

Asenneanalyysin tulossivulta on helppo aloittaa uusien asiakassegmenttien luominen valitsemalla **Luo segmenttejä** mallin tulossivun yläosassa.

:::image type="content" source="media/create-segment-model.png" alt-text="Komentopalkki ja ennustemallien vaihtoehtoja":::
 
## <a name="potential-bias"></a>Mahdolliset ennakkokäsitykset

Samoin kuin muissa ennakoivaa tekoälyä käyttävissä ominaisuuksissa on hyvä olla tietoinen mahdollisista ennakkokäsityksistä niissä tiedoissa, joita käytetään asiakkaan asenteen ennustamiseen. Jos palautetta esimerkiksi kerätään vain digitaalisesti, on mahdollista, että käytössä ei ole palautetta asiakkailta, jotka käyttävät henkilökohtaisia palveluja, ja tämä voi vaikuttaa ominaisuuden tulokseen.

Koska tämä ominaisuus sekä arvioi tietoja että tekee ennusteita näiden tietojen perusteella automaattisesti, sitä on mahdollista käyttää profilointiin siinä mielessä kuin profilointi on määritetty yleisessä tietosuoja-asetuksessa (GDPR-asetuksessa). Jos tätä ominaisuutta käytetään tietojen käsittelemiseen, siihen sovelletaan GDPR-määrityksiä tai muita lakeja ja säännöksiä. Käyttäjä on vastuussa siitä, että Dynamics 365 Customer Insightsia asenneanalyysi mukaan lukien käytetään kaikkien sovellettavien lakien ja määräysten mukaisesti. Tämä koskee myös tietosuojaan, henkilökohtaisiin tietoihin, biometrisiin tietoihin, tietoturvaan ja viestinnän luottamuksellisuuteen liittyviä lakeja.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

