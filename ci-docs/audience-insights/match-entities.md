---
title: Tietojen yhtenäistäminen entiteettien vastaavuuden avulla
description: Yhtenäisten asiakasprofiilien luominen entiteettien vastaavuuden avulla.
ms.date: 01/28/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
  - ci-match
---

# <a name="match-entities"></a>Entiteettien vastaavuus

Täsmäytysvaihe määrittää, miten tietojoukot yhdistetään yhdistetyksi asiakasprofiilin tietojoukoksi. Kun [yhdistämisvaihe](map-entities.md) tietojen yhdistämisessä on valmis, voit yhdistää kaikki entiteetit. Täsmäytysvaihe edellyttää vähintään kahta yhdistettyä entiteettiä.

Hakusivu koostuu kolmesta osasta: 
- Tärkeimmät mittausarvot, jotka tiivistävät yhdistettyjen tietueiden määrän
- Täsmäytä järjestys ja säännöt entiteettienvälistä täsmäytystä varten
- Yhdistettyjen entiteettien kaksoiskappaleiden poistamissäännöt

## <a name="specify-the-match-order"></a>Määritä täsmäytysjärjestys.

Siirry kohtaan **Tiedot** > **Yhdistä** > **Määritä vastaavuus** ja valitse **Määritä järjestys**, kun haluat aloittaa vastaavuuden määrityksen.

Kukin vastine yhdistää vähintään kaksi entiteettiä yhdeksi konsolidoiduksi entiteetiksi. Samalla se säilyttää yksilölliset asiakastietueet. Valitsimme esimerkiksi kaksi entiteettiä: **eCommerce:eCommerceContacts** ensisijaisena entiteettinä ja **LoyaltyScheme:loyCustomers** toisena entiteettinä. Entiteettien järjestys määrittää, missä järjestyksessä järjestelmä yrittää yhdistää tietueet.

:::image type="content" source="media/match-page.png" alt-text="Näyttökuva tietojen yhdistämisprosessin yhdistämisalueen vastaavuussivusta.":::
  
Ensisijainen entiteetti *eCommerce:eCommerceContacts* yhdistetään seuraavaan *LoyaltyScheme:loyCustomers*-entiteettiin. Ensimmäisestä täsmäytysvaiheesta tuloksena oleva tietojoukko täsmäytetään seuraavan entiteetin kanssa, jos entiteettejä on enemmän kuin kaksi.

> [!IMPORTANT]
> Entiteetti, jonka valitset ensisijaiseksi entiteetiksi, toimii yhdistettyjen profiilien perustana. Täsmäytysvaiheen aikana valitut lisäentiteetit lisätään tähän entiteettiin. Tämä ei tarkoita, että yhtenäinen entiteetti sisältää *kaikki* entiteettiin sisältyvät tiedot.
>
> Seuraavat kaksi seikkaa auttavat entiteettihierarkian valinnassa:
>
> - Valitse entiteetti, jolla on täydellisimmät ja luotettavat profiilitiedot asiakkaistasi ensisijaisena entiteettinä.
> - Valitse ensisijaiseksi entiteetiksi entiteetti, jolla on useita yhteisiä määritteitä (esimerkiksi nimi, puhelinnumero tai sähköpostiosoite).

Kun olet määrittänyt vastinejärjestyksen, näet määritetyt vastaavuusparit **Täsmäytettyjen tietueiden tiedot** -osassa kohdassa **Tiedot** > **Yhtenäistä** > **Täsmäytä**. Tärkeimmät mittausarvot ovat tyhjiä, kunnes vastineprosessi on valmis.

## <a name="define-rules-for-match-pairs"></a>Vastaavuusparien sääntöjen määritteleminen

Täsmäytyssäännöt määrittävät logiikan, jonka avulla määritetty entiteettipari täsmäytetään.

Entiteetin nimen vieressä on **Tarvesäännöt**-varoitus, joka viittaa siihen, että vastineparille ei ole määritetty vastaavuussääntöä. 

:::image type="content" source="media/match-rule-add.png" alt-text="Näyttökuva Täsmäytettyjen tietueiden tiedot -osasta, jossa on ohjausobjekti, jolla lisätään korostettuja sääntöjä.":::

1. Määritä vastaavuussäännöt valitsemalla **Täsmäytettyjen tietueiden tiedot** -osassa **Lisää säännöt**.

1. Määritä **Luo sääntö** -ruudussa säännön ehdot.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Näyttökuva avatun vastaavuussäännön ehdoista.":::

   - **Entiteetti/kenttä (ensimmäinen rivi)**: Valitse liittyvä entiteetti ja määrite, jos haluat määrittää tietueen ominaisuuden, joka on todennäköisesti yksilöllinen asiakkaalle. Esimerkiksi puhelinnumero tai sähköpostiosoite. Vältä yhdistämistä aktiviteettityyppisten määritteiden mukaan. Esimerkiksi ostotunnus ei todennäköisesti vastaa muita tietuetyyppejä.

   - **Entiteetti/kenttä (toinen rivi)**: Valitse määrite, joka liittyy ensimmäisellä rivillä määritetyn entiteetin määritteeseen.

   - **Normalisoi**: Valitse seuraavista normalisointivaihtoehdoista valituille määritteille. 
     - Tyhjä tila: poistaa kaikki välilyönnit. *Hello Worldista* tulee *HelloWorld*.
     - Symbolit: poistaa kaikki symbolit ja erikoismerkit. *Head&Shoulder* muuttuu muotoon *HeadShoulder*.
     - Teksti pieniksi kirjaimiksi: Muuntaa kaikki merkit pieniksi. *KAIKKI ISOLLA- ja Ensimmäiset Kirjaimet Isolla* -tapaukset muuttuvat muotoon *kaikki isolla- ja ensimmäiset kirjaimet isolla*.
     - Unicode ASCII-muotoon: muuntaa unicode-merkinnät ASCII-merkeiksi. */u00B2* muuttuu muotoon *2*.
     - Numeraalit: muuntaa muut numerojärjestelmät, kuten roomalaiset numerot arabialaisiksi numeroiksi. *VIII* muuttuu muotoon *8*.
     - Semanttiset tyypit: standardoi nimet, otsikot, puhelinnumerot ja osoitteet, yms. 

   - **Tarkkuus**: Määritä tässä ehdossa käyttöönotettu tarkkuustaso. 
     - **Perustiedot**: Valitse arvoksi *Matala*, *Keskitaso*, *Korkea* ja *Tarkka*. Valitse **Tarkka** vain, jos haluat täsmäyttää tietueita, joiden täsmäävyys on 100 prosenttia. Valitse jokin toinen taso, jos haluat täsmäyttää tietueita, jotka eivät ole täysin identtisiä.
     - **Mukautettu**: Määritä prosenttiluku, jota tietueiden on vastattava. Järjestelmä yhdistää vain tämän raja-arvon ohittavat tietueet.

1. Anna säännön **Nimi**.

1. [Lisää ehtoja](#add-conditions-to-a-rule) tai viimeistele sääntö valitsemalla **Valmis**.

1. Voit myös [lisätä muita sääntöjä](#add-rules-to-a-match-pair).

1. Ota muutokset käyttöön valitsemalla **Tallenna**.

### <a name="add-conditions-to-a-rule"></a>Lisää säännön ehdot

Jos haluat yhdistää entiteetit vain, jos määritteet vastaavat useita ehtoja, lisää vastaavalle säännölle ehtoja. Ehdot yhdistetään loogiseen JA-operaattoriin, joten ne suoritetaan vain, jos kaikki ehdot täyttyvät.

1. Siirry kohtaan **Tiedot** > **Yhdenmukaista** > **Täsmäytä** ja valitse **Muokkaa** sääntöä, johon haluat lisätä ehtoja.

1. Valitse **Muokkaa sääntöä** -ruudussa **Lisää ehto**.

1. Tallenna sääntö valitsemalla **Valmis**.

### <a name="add-rules-to-a-match-pair"></a>Sääntöjen lisääminen vastinepariin

Vastinesäännöt edustavat ehtojen joukkoja. Lisää sääntöjä täsmäyttääksesi entiteettejä useiden määritteiden perusteella

1.  Siirry kohtaan **Tiedot** > **Yhdenmukaista** > **Täsmäytä** ja valitse **Lisää sääntö** entiteettiin, johon haluat lisätä sääntöjä.

2. Noudata ohjeita kohdassa [Vastaavuusparien sääntöjen määrittäminen](#define-rules-for-match-pairs).

> [!NOTE]
> Sääntöjen järjestys on tärkeä. Vastaava algoritmi yrittää suorittaa vastineen ensimmäisen säännön perusteella ja jatkaa toista sääntöä vain, jos ensimmäisellä säännöllä ei ole määritetty vastaavuuksia.

### <a name="change-the-entity-order-in-match-rules"></a>Entiteettijärjestyksen muuttaminen vastaavuussäännöissä

Voit järjestää entiteetit uudelleen täsmäytyssääntöjen mukaan, jos haluat muuttaa niiden käsittelyjärjestystä. Säännöt, jotka ovat ristiriidassa muuttuneen järjestyksen vuoksi, poistetaan. Poistetut säännöt täytyy luoda uudelleen päivitetyllä määrityksellä.

1. Siirry kohtaan **Tiedot** > **Yhdistäminen** > **Yhdistä** ja valitse **Muokkaa**.

1. Valitse **Muokkaa sääntöä** -ruudussa **Siirrä ylös/alas** -ohjausobjekti, tai vedä ja pudota entiteettejä järjestyksen vaihtamiseksi.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Vaihtoehdot, joilla voidaan muuttaa sitä, missä järjestyksessä entiteetit käsitellään yhdistämisvaiheessa.":::

1. Tallenna sääntö valitsemalla **Valmis**.

## <a name="define-deduplication-on-a-match-entity"></a>Vastaavan entiteetin kaksoiskappaleiden poistaminen

[Entiteettien ristiintaulukointisääntöjen](#define-rules-for-match-pairs) lisäksi voit myös määrittää kaksoiskappaleiden poistamissääntöjä. *Kaksoiskappaleiden poistaminen* on myös yksi prosessi tietueita täsmäytettäessä. Se tunnistaa tietueiden kaksoiskappaleet ja yhdistää ne yhteen tietueeseen. Lähdetietueet linkitetään yhdistettyyn tietueeseen vaihtoehtoisilla tunnuksilla.

Tietueita, joista on poistettu kaksoiskappaleet, käytetään sitten entiteettien välisessä vastaavuusprosessissa. Kaksoiskappaleiden poistaminen tapahtuu yksittäisille entiteeteille ja voidaan määrittää jokaiselle kohteelle, jota käytetään vastineparissa.

Kaksoiskappaleiden poistosääntöjen määrittäminen ei ole pakollista. Jos kyseisiä sääntöjä ei ole määritetty, järjestelmän määrittämiä sääntöjä käytetään. Ne yhdistävät kaikki tietueet yhdeksi tietueeksi, ennen kuin ne välittyvät entiteettienväliseen vastaavuuteen suorituskyvyn parantamiseksi.

### <a name="add-deduplication-rules"></a>Kaksoiskappaleiden poistosääntöjen lisääminen

1. Valitse **Tiedot** > **Yhtenäistä** > **Täsmäytä**.

1. **Kahdentamattomat tietuetiedot** -osassa valitse **Määritä entiteetit**. Jos kaksoiskappaleiden poistamisen säännöt on jo luotu, valitse **Muokkaa**.

1. Valitse **Yhdistä asetukset** -ruudussa entiteetit, joissa haluat suorittaa kaksoiskappaleiden poiston.

   1. Määritä, miten kaksoiskappaletietueet yhdistetään, ja valitse jokin kolmesta yhdistämisvaihtoehdosta:
      - **Useimmat täytetyt**: Määrittää voittavaksi tietueeksi tietueen, jossa on eniten täytettyjä määritekenttiä. Se on yhdistämisen oletusasetus.
      - **Uusin**: Määrittää voittajatietueeksi uusimman tietueen. Viimeaikaisuuden määrittämiseen tarvitaan päivämäärä- tai numerokenttä.
      - **Vähiten viimeaikaiset**: Määrittää voittajatietueeksi vähiten viimeaikaisimman tietueen. Viimeaikaisuuden määrittämiseen tarvitaan päivämäärä- tai numerokenttä.

   1. Voit myös määrittää entiteetin yksittäisten määritteiden kaksoiskappaleiden poistosäännöt valitsemalla **Lisäasetukset**. Voit esimerkiksi säilyttää uusimman sähköpostiviestin JA täydellisimmän osoitteen eri tietueista. Laajenna entiteettiä, kun haluat nähdä sen kaikki määritteet, ja määritä, mitä asetusta käytetään yksittäisissä määritteissä. Jos valitset viimeaikaisuuteen perustuvan vaihtoehdon, sinun täytyy myös määrittää päivämäärä-/aikakenttä, joka määrittää viimeaikaisuuden. 
 
      > [!div class="mx-imgBorder"]
      > ![Kaksoiskappaleiden poistosääntöjen vaihe 1.](media/match-selfconflation.png "Kaksoiskappaleiden poistosääntöjen vaihe 1")

   1. Valitse **Valmis**, jos haluat ottaa yhdistämisasetukset käyttöön kaksoiskappaleiden poistossa.
 
1. Kun entiteetit on valittu ja niiden yhdistämisasetus on määritetty, määritä kaksoiskappaleiden poistosäännöt entiteettitasolla valitsemalla **Lisää sääntö**.
   - **Valitse kenttä** sisältää kaikki entiteetin käytettävissä olevat kentät. Valitse kenttä, jonka haluat tarkistaa kaksoiskappaleiden varalta. Valitse kentät, jotka ovat todennäköisesti yksilöllisiä jokaiselle asiakkaalle. Esimerkiksi sähköpostiosoite tai nimen, postiosoitteen ja puhelinnumeron yhdistelmä.
   - Määritä normalisointi- ja tarkkuusasetukset.
   - Määritä lisäehtoja valitsemalla **Lisää ehto**.
 
   > [!div class="mx-imgBorder"]
   > ![Kaksoiskappaleiden poistosääntöjen vaihe 2.](media/match-selfconflation-rules.png "Kaksoiskappaleiden poistosääntöjen vaihe 2")

  Voit luoda entiteetille useita kaksoiskappaleiden poistosääntöjä. 

1. Vastaavuusprosessin suorittaminen ryhmittelee nyt tietueet kaksoiskappaleiden poistosäännöissä määritettyjen ehtojen perusteella. Kun tietueet on ryhmitelty, voittajatietue määritetään käyttämällä vastaavuuskäytäntöä.

1. Tämän jälkeen tämä voittanut tietue välitetään entiteettien väliseen vastaavuuden määritykseen. Muut kuin voittaneet tietueet (esimerkiksi vaihtoehtoiset tunnukset) parantavat vastaavuuden laatua.

1. Mukautetut vastaavuussäännöt korvaavat kaksoiskappaleiden poistamisen säännöt. Jos kaksoiskappaleiden poistosääntö määrittää vastaavia tietueita ja mukautetuksi vastaavuussääntönä on, etteivät tietueet saa koskaan vastata toisiin, näille kahdelle tietueelle ei etsitä vastaavuutta.

1. Kun [vastaavuusprosessi on](#run-the-match-process) suoritettu, näet kaksoiskappaleiden tilastot tärkeimpien mittausarvojen ruuduissa.

### <a name="deduplication-output-as-an-entity"></a>Kaksoiskappaleiden poiston tulos entiteettinä

Kaksoiskappaleiden poistamisprosessi luo uuden entiteetin jokaiselle entiteetille vastineparien avulla, jotta tunnistetaan pois jätetyt tietueet. Nämä entiteetit löytyvät yhdessä **ConflationMatchPairs:CustomerInsights**-entiteetin kanssa **Järjestelmä**-osasta **Entiteetit**-sivulta nimellä **Deduplication_DataSource_Entity**.

Kaksoiskappaleiden poiston tulosentiteetti sisältää seuraavat tiedot:
- Tunnukset/avaimet
  - Perusavaimen kenttä ja sen vaihtoehtoisten tunnusten kenttä. Vaihtoehtoisten tunnusten kenttä sisältää kaikki tietueen vaihtoehtoiset tunnukset.
  - Deduplication_GroupId-kentässä on ryhmä tai klusteri, joka sellainen entiteetti määrittää, joka ryhmittelee kaikki samanlaiset tietueet määritettyjen kaksoiskappaleiden poiston kenttien perusteella. Sitä käytetään järjestelmän käsittelyssä. Jos manuaalisia kaksoiskappaleiden poiston sääntöjä ei ole määritetty, ja järjestelmän määrittämät kaksoiskappaleiden poiston säännöt on otettu käyttöön, tätä kenttää ei ehkä löydy kaksoiskappaleiden poiston tulosentiteetistä.
  - Deduplication_WinnerId: Tämä kenttä sisältää määritettyjen ryhmien tai klustereiden voittaneen tunnuksen. Jos Deduplication_WinnerId on sama kuin tietueen ensisijaisen avaimen arvo, tietue on voittanut tietue.
- Kenttiä käytetään kaksoiskappaleiden poiston sääntöjen määrittämisessä.
- Sääntö- ja Pistemäärä-kentät määrittävät, mitä kaksoiskappaleiden poiston sääntöjä noudatetaan. Ne määrittävät myös vastaavan algoritmin palauttaman pistemäärän.
   
## <a name="run-the-match-process"></a>Suorita täsmäytysprosessi

Määritetyillä vastaavuussäännöillä, mukaan lukien entiteettien välinen vastaavuuksien etsiminen ja kaksoiskappaleiden poistosäännöt, on määritetty, voit suorittaa täsmäytysprosessin. 

Siirry kohtaan **Tiedot** > **Yhdistä** > **Täsmäytä** ja aloita prosessi valitsemalla **Suorita**. Vastaavan algoritmin valmistuminen kestää jonkin aikaa, eikä määritystä voi muuttaa, ennen kuin se on valmis. Tehdäksesi muutoksia sinun tulee peruuttaa suoritus. Valitse työn tila ja valitse sitten **Peruuta työ** **Edistymisen tiedot** -ruudussa.

Onnistuneen suorituksen eli yhtenäisen asiakasprofiilientiteetin tulokset ovat **Entiteetit**-sivulla. Yhdistettyä asiakasentiteettiä kutsutaan **Profiilit**-osassa nimellä **Asiakkaat**. Ensimmäinen onnistunut täsmäytetty kohde luo yhtenäisen *Asiakas*-entiteetin. Kaikki myöhemmät vastineet laajentavat tätä entiteettiä.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="review-and-validate-your-matches"></a>Täsmäytysten tarkistaminen ja vahvistaminen

Siirry kohtaan **Tiedot** > **Yhdistä** > **Täsmäytä**, jotta voit arvioida vastaavuusparien laatua ja tarkentaa niitä tarvittaessa.

Sivun yläreunassa olevassa ruudussa näkyvät tärkeimmät mittausarvot, joissa yhteenvedossa on täsmäytettyjen tietueiden ja kaksoiskappaleiden määrä.

:::image type="content" source="media/match-KPIs.png" alt-text="Rajattu näyttökuva vertailusivun mittausarvoista lukujen ja tietojen kanssa.":::

- **Yksilöllisissä lähdetietueissa** näkyy viime hakusuorituksessa käsiteltyjen yksittäisten lähdetietueiden määrä.
- **Täsmäytettyjen ja yhdistätyjen tietueiden** perusteella voidaan korostaa, kuinka monta yksilöllistä tietuetta on jäljellä vastaavuussääntöjen käsittelyn jälkeen.
- **Vain täsmäytetyt tietueet** osoittavat vain kaikkien vastineparien vastaavuudet.

Voit arvioida kunkin vastaavuusparin ja sen sääntöjen tuloksia **Täsmäytettyjen tietueiden tiedot** -taulukossa. Vertaa vastineparista tulleiden tietueiden määrää niiden tietueiden prosenttiosuuteen, jotka on hyväksytty.

Tarkista vastineparin säännöt, jotta näet, kuinka monta prosenttia onnistuneesti liitetyistä tietueista on säännön tasolla. Valitse kolme pistettä (...) ja valitse sitten **Vastineen esikatselu**, jotta voit tarkastella kaikkia tietueita sääntötasolla. Suosittelemme, että joitakin tietueita tarkistetaan, että ne on määritetty oikein.

Yritä etsiä optimaalinen arvo eri tarkkuuskynnyksillä.

  1. Valitse sen säännön kolme pistettä (...), jota haluat kokeilla, ja valitse sitten **Muokkaa**.

  2. Vaihda tarkkuusarvot niiden ehtojen osalta, joita haluat tarkistella.

  3. Valitse **Esikatselu**, jotta näet valitun ehdon täsmäyttämättömien ja vertaamattomien tietueiden määrän.

## <a name="manage-match-rules"></a>Täsmäytyssääntöjen hallinta

Voit määrittää ja hienosäätää useimpia vastineparametreja.

:::image type="content" source="media/match-rules-management.png" alt-text="Näyttökuva avattavasta valikosta ja vastaavuussääntövaihtoehdoista.":::

- **Muuta sääntöjen järjestystä**, jos määritit useita sääntöjä. Voit järjestää vastaavuussäännöt uudelleen valitsemalla **Siirrä ylöspäin**- ja **Siirrä alaspäin**  -vaihtoehdot tai vetämällä ja pudottamalla.

- **Muuta säännön ehtoja** valitsemalla **Muokkaa** ja valitse sitten eri kentät.

- **Poista säännön aktivointi**, jos haluat säilyttää vastaavuussäännön, mutta poistaa sen vastaavuusprosessista.

- **Kopioi säännöt**, jos olet määrittänyt vastaavuussäännön ja haluat luoda samanlaisen säännön muokkauksin, valitse **Kopioi**.

- **Poista sääntö** valitsemalla **Poista**-symboli.

## <a name="advanced-options"></a>Lisäasetukset

### <a name="add-exceptions-to-a-rule"></a>Poikkeuksien lisääminen sääntöön

Useimmissa tapauksissa entiteettien vastaavuus johtaa yksilöiviin käyttäjäprofiileihin, joissa on yhdistettyjä tietoja. Jos haluat käsitellä dynaamisesti harvinaisia virheellisiä esiintymiä, voit määrittää vastaavuussäännölle poikkeuksia. Poikkeuksia sovelletaan vastaavuussääntöjen käsittelyn jälkeen, eikä kaikkia tietueita, jotka täyttävät poikkeusehdot, täsmäytetä.

Jos esimerkiksi vastaavuussäännössä on sukunimi, kaupunki ja syntymäpäivä, järjestelmä tunnistaa kaksoset, joilla on sama sukunimi, jotka asuvat samassa kaupungissa kuin sama profiili. Voit määrittää poikkeuksen, joka ei täsmäytä profiileja, jos yhdistettävien entiteettien etunimi ole sama.

1. Siirry kohtaan **Tiedot** > **Yhdenmukaista** > **Täsmäytä** ja valitse **Muokkaa** sääntöä, johon haluat lisätä ehtoja.

1. Valitse **Muokkaa sääntöä** -ruudussa **Lisää poikkeus**.

1. Määritä poikkeusehdot. 

1. Tallenna sääntö valitsemalla **Valmis**.

### <a name="specify-custom-match-conditions"></a>Mukautettujen täsmäytysehtojen määritteleminen

Voit määrittää ehtoja, jotka korvaavat oletusvastaavuuslogiikan. Käytettävissä on neljä vaihtoehtoa: 

|Asetus  |Description |Esimerkki:  |
|---------|---------|---------|
|Vastaavat aina toisiaan     | Määrittää arvot, joiden vastaavuutta aina haetaan.         |  Hae aina vastaavuudet merkkijonoille *Mike* ja *MikeR*.       |
|Eivät vastaa toisiaan koskaan     | Määrittää arvot, joiden vastaavuutta ei koskaan haeta.        | Älä koskaan hae vastaavuutta merkkijonoille *John* ja *Jonathan*.        |
|Mukautettu ohitus     | Määrittää arvot, jotka järjestelmän on aina ohitettava vastaavuushaun vaiheessa. |  Ohita arvot *11111* ja *Tuntematon* vastaavuushaun aikana.        |
|Aliaksen yhdistämismääritys    | Määritetään arvot, jotka järjestelmän tulisi ottaa huomioon samana arvona.         | Ota huomioon *Joe* samana kuin *Joseph*.        |

1. Siirry kohtaan **Tiedot** > **yhdistä** > **Täsmäytä** ja valitse **Mukautettu vastine** **Täsmäytettyjen tietueiden tiedot** -osassa.

   :::image type="content" source="media/custom-match-create.png" alt-text="Näyttökuva täsmäytyssääntöosasta, jossa on mukautettu täsmäytyksen hallinta korostettuna.":::

1. Siirry **Mukautettu**-ruudussa **Tietueet**-välilehteen.

1. Valitse mukautetun vastineen vaihtoehto avattavasta **Mukautettu tyyppi** -luettelosta ja valitse **Lataa malli**. Jokaiselle vastinevaihtoehdolle on oltava oma malli.

1. Avaa ladattu mallitiedosto ja täytä tiedot. Malli sisältää kenttiä, jotka määrittävät entiteetin ja entiteetin ensisijaisen avaimen arvot. Niitä käytetään mukautetussa täsmäytyksessä. Jos esimerkiksi haluat, että *Myynti*-kohteen perusavain *12345* vastaa aina *Yhteyshenkilö*-kohteen perusavainta *34567*, täytä malli:
    - Entiteetti1: Myynti
    - Entiteetti1Avain: 12345
    - Entiteetti2: Yhteyshenkilö
    - Entiteetti2avain: 34567

   Sama mallitiedosto voi määrittää mukautetut täsmäytystietueet useista entiteeteistä.
   
   Jos haluat määrittää mukautetun vastaavuuden entiteetin kaksoiskappaleiden poistolle, määritä sama entiteetti sekä kohtaan Entiteetti1 ja Entiteetti2 ja määritä erilaisetn ensisijaisen avaimen arvot.

1. Kun olet lisännyt kaikki ohitukset, tallenna mallitiedosto.

1. Valitse **Tiedot** > **Tietolähteet** ja käsittele mallitiedostot uusina entiteetteinä.

1. Kun tiedostot on ladattu ja entiteetit ovat käytettävissä, valitse uudelleen **Mukautettu täsmäytys** -vaihtoehto. Näkyviin tulee vaihtoehtoja, joilla määritetään sisällytettävät kohteet. Valitse pakolliset entiteetit avattavasta valikosta ja valitse sitten **Valmis**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Näyttökuva dialogista, kun haluat valita mukautetun vastineen skenaarion ohitukset.":::

1. Mukautetun vastineen käyttö määräytyy sen mukaan, mitä vastinevaihtoehtoa haluat käyttää. 

   - Siirry seuraavaan vaiheeseen, valitsemalla **Vastaavat aina toisiaan** tai **Eivät koskaan vastaa toisiaan**.
   - Valitse **Mukautettu ohitus**- tai **Alias-yhdistämismääritys** -kohdassa **Muokkaa** aiemmin luodussa vastaavuussäännössä tai luo uusi sääntö. Valitse normalisoinnin avattavasta luettelosta **Mukautettu ohitus**- tai **Alias-yhdistämismääritys** -asetus ja valitse **Valmis**.

1. Ota mukautettu täsmäytysmääritys käyttöön valitsemalla **Täsmäytys**-sivulla **Tallenna**.

1. Aloita vastaava prosessi valitsemalla **Täsmäytys**-sivulla **Suorita**. Mukautettu täsmäytysmääritys ohittaa muut määritetyt vastaavuussäännöt.

#### <a name="known-issues"></a>Tunnetut ongelmat

- Itseyhdistäminen ei näytä normalisoituja tietoja entiteeteille, joiden kaksoiskappaleet poistetaan. Se kuitenkin käyttää normalisointia sisäisesti kaksoiskappaleiden poiston aikana. Se on toiminnallisuuden mukaan kaikille normalisoinnille. 
- Jos semanttinen tyyppiasetus poistetaan **Yhdistämismääritys**-vaiheessa, kun vastinesääntö käyttää Alias-yhdistämismääritystä tai mukautettua ohitusmääritystä, normalisointia ei käytetä. Se tapahtuu vain, jos poistat semanttisen tyypin, kun olet määrittänyt normalisoinnin vastinesäännössä, koska semanttinen tyyppi on tuntematon.


## <a name="next-step"></a>Seuraava vaihe

Kun olet suorittanut vähintään yhden vastaavuusparin vastaavuusprosessin, jatka [**Yhdistä**](merge-entities.md)-vaiheeseen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
