---
title: Tietojen yhdistämisen ehtojen vastaavuuden avulla
description: Yhtenäisten asiakasprofiilien luominen entiteettien vastaavuuden avulla.
recommendations: false
ms.date: 05/05/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: e3e4e37d5b4c9caf2520a789d5f78ef33b491793
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139695"
---
# <a name="match-conditions-for-data-unification"></a>Tietojen yhdistämisen ehtojen vastaavuuden avulla

Tämä yhdistämisen vaihe määrittää täsmäytysjärjestyksen ja entiteettien välisen täsmäytyksen säännöt. Tässä vaiheessa tarvitaan vähintään kaksi entiteettiä.

> [!NOTE]
> Kun olet luonut vastaavuusehdot ja valinnut **Seuraava**, et voi poistaa valittua entiteettiä tai määritettä. Tarkista valitut entiteetit ja määritteet tarvittaessa valitsemalla **Takaisin**, ennen kuin jatkat.

## <a name="include-enriched-entities-preview"></a>Rikastettujen entiteettien sisällyttäminen (esiversio)

Jos olet rikastanut entiteetit tietolähteen tasolla parantaaksesi yhdistämisen tuloksia, valitse ne. Lisätietoja: [Rikastus tietolähteitä varten](data-sources-enrichment.md). Jos valitsit **Tietueiden kaksoiskappaleet** -sivulla rikastetut entiteetit, niitä ei tarvitse valita uudelleen.

1. Valitse **Vastaavuusehdot** - sivun yläreunassa **Käytä rikastettuja entiteettejä**.

1. Valitse vähintään yksi rikastettu entiteetti **Käytä rikastettuja entiteettejä** -ruudusta.

1. Valitse **Valmis**.

## <a name="specify-the-match-order"></a>Määritä täsmäytysjärjestys.

Kukin vastine yhdistää vähintään kaksi entiteettiä yhdeksi konsolidoiduksi entiteetiksi. Samalla se säilyttää yksilölliset asiakastietueet. Vastinejärjestys ilmaisee järjestyksen, jossa järjestelmä yrittää yhdistää tietueet.

> [!IMPORTANT]
> Luettelon ensimmäistä entiteettiä kutsutaan ensisijaiseksi entiteetiksi. Ensisijainen entiteetti toimii yhtenäisten profiilien tietojoukon perustana. Entiteettiin lisätään lisää valittuja entiteettejä.
>
> Tärkeitä huomioon otettavia seikkoja:
>
> - Valitse entiteetti, jossa on täydellisimmät ja luotettavat profiilitiedot asiakkaistasi ensisijaiseksi entiteetiksi.
> - Valitse ensisijaiseksi entiteetiksi entiteetti, jolla on useita yhteisiä määritteitä muiden entiteettien kanssa (esimerkiksi nimi, puhelinnumero tai sähköpostiosoite).

1. Siirrä **Vastaavuusehdot**-sivulla ylä- ja alanuolien avulla entiteetit haluamaasi järjestykseen ylä- ja alanuolen avulla tai vedä ja pudota ne. Valitse esimerkiksi **Contacts:eCommerce** ensisijaiseksi entiteetiksi ja **CustomerLoyalty:Loyalty** toiseksi entiteetiksi.

1. Valitse **sisällytä kaikki tietueet**, jos haluat jokaisesta entiteetin tietueesta yksilöidyn asiakkaan riippumatta siitä, löytyykö vastinetta. Kaikki tämän entiteetin tietueet, jotka eivät vastaa muiden entiteettien tietueita, sisällytetään yhdistettyyn profiiliin. Tietueita, joilla ei ole vastinetta, kutsutaan singleton-tietueiksi.
  
Ensisijainen entiteetti *Contacts:eCommerce* vastaa seuraavaa entiteettiä *CustomerLoyalty:Loyalty*. Ensimmäisestä täsmäytysvaiheesta tuloksena oleva tietojoukko täsmäytetään seuraavan entiteetin kanssa, jos entiteettejä on enemmän kuin kaksi.

:::image type="content" source="media/m3_match.png" alt-text="Näyttökuva entiteettien valitusta vastaavuusjärjestyksestä." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Vastaavuusparien sääntöjen määritteleminen

Täsmäytyssäännöt määrittävät logiikan, jonka avulla määritetty entiteettipari täsmäytetään. Sääntö koostuu yhdestä tai useasta ehdosta.

Entiteetin nimen vieressä on varoitus, jonka mukaan vastineparille ei ole määritetty vastaavuussääntöä.

1. Määritä vastaavuussäännöt valitsemalla entiteettiparille **Lisää sääntö**.

1. Määritä Säännön ehdot **Lisää sääntö** -ruudussa.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Näyttökuva Lisää sääntö -ruudusta.":::

   - **Valitse Entiteetti/kenttä (ensimmäinen rivi)**: Valitse liittyvä entiteetti ja määrite, jos haluat määrittää tietueen ominaisuuden, joka on todennäköisesti yksilöllinen asiakkaalle. Esimerkiksi puhelinnumero tai sähköpostiosoite. Vältä yhdistämistä aktiviteettityyppisten määritteiden mukaan. Esimerkiksi ostotunnus ei todennäköisesti vastaa muita tietuetyyppejä.

   - **Valitse entiteetti/kenttä (toinen rivi)**: Valitse määrite, joka liittyy ensimmäisellä rivillä määritetyn entiteetin määritteeseen.

   - **Normalisoi**: Valitse seuraavista normalisointivaihtoehdoista valituille määritteille.
     - **Numeraalit**: muuntaa muut numerojärjestelmät, kuten roomalaiset numerot arabialaisiksi numeroiksi. *VIII* muuttuu muotoon *8*.
     - **Symbolit**: poistaa kaikki symbolit ja erikoismerkit. *Head&Shoulder* muuttuu muotoon *HeadShoulder*.
     - **Teksti pieniksi kirjaimiksi**: Muuntaa kaikki merkit pieniksi. *KAIKKI ISOLLA- ja Ensimmäiset Kirjaimet Isolla* -tapaukset muuttuvat muotoon *kaikki isolla- ja ensimmäiset kirjaimet isolla*.
     - **Tyyppi (Puhelin, Nimi, Osoite, Organisaatio)**: standardoi nimet, otsikot, puhelinnumerot, osoitteet ja organisaatiot.
     - **Unicode ASCII-muotoon**: muuntaa Unicode-merkinnät ASCII-merkeiksi. */u00B2* muuttuu muotoon *2*.
     - **Tyhjä tila**: poistaa kaikki välilyönnit. *Hello Worldista* tulee *HelloWorld*.

   - **Tarkkuus**: Määritä tässä ehdossa käyttöönotettu tarkkuustaso.
     - **Perustiedot**: Valitse arvoksi *Matala (30 %)*, *Keskitaso (60 %)*, *Korkea (80 %)* tai *Tarkka (100 %)*. Valitse **Tarkka**, jos haluat yhdistää vain tietueet, jotka vastaavat 100 prosentin tarkkuudella.
     - **Mukautettu**: Määritä prosenttiluku, jota tietueiden on vastattava. Järjestelmä yhdistää vain tämän raja-arvon ohittavat tietueet.

   - **Nimi**: Säännön nimi.

1. Jos haluat yhdistää entiteetit vain, jos määritteet vastaavat useita ehtoja, valitse **Lisää** > **Lisää ehto** valitaksesi lisää ehtoja vastaavuussääntöön.  Ehdot yhdistetään loogiseen JA-operaattoriin, joten ne suoritetaan vain, jos kaikki ehdot täyttyvät.

1. Voit myös harkita lisäasetusten käyttöä, joita ovat [poikkeukset](#add-exceptions-to-a-rule) ja [mukautetut vastaavuusehdot](#specify-custom-match-conditions).

1. Valmista sääntö valitsemalla **Valmis**.

1. Voit myös [lisätä muita sääntöjä](#add-rules-to-a-match-pair).

1. Valitse **Seuraava**.

> [!div class="nextstepaction"]
> [Seuraava vaihe: Kenttien yhtenäistäminen](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Sääntöjen lisääminen vastinepariin

Vastinesäännöt edustavat ehtojen joukkoja. Lisää sääntöjä täsmäyttääksesi entiteettejä useiden määritteiden perusteella.

1. Valitse **Lisää sääntö** siinä entiteetissä, johon haluat lisätä sääntöjä.

1. Noudata ohjeita kohdassa [Vastaavuusparien sääntöjen määrittäminen](#define-rules-for-match-pairs).

> [!NOTE]
> Sääntöjen järjestys on tärkeä. Vastaavuusalgoritmi yrittää yhdistää tietyn asiakastietueen ensimmäisen säännön perusteella ja jatkaa toiseen sääntöön vain, jos ensimmäiselle säännöllä ei löydetty vastaavuuksia.

## <a name="advanced-options"></a>Lisäasetukset

### <a name="add-exceptions-to-a-rule"></a>Poikkeuksien lisääminen sääntöön

Useimmissa tapauksissa entiteettien vastaavuus johtaa yksilöllisiin asiakasprofiileihin, joissa on yhdistettyjä tietoja. Jos haluat käsitellä dynaamisesti harvinaisia virheellisiä esiintymiä, voit määrittää vastaavuussäännölle poikkeuksia. Poikkeuksia sovelletaan vastaavuussääntöjen käsittelyn jälkeen, eikä kaikkia tietueita, jotka täyttävät poikkeusehdot, täsmäytetä.

Jos esimerkiksi vastaavuussäännössä on sukunimi, kaupunki ja syntymäpäivä, järjestelmä tunnistaa kaksoset, joilla on sama sukunimi, jotka asuvat samassa kaupungissa kuin sama profiili. Voit määrittää poikkeuksen, joka ei täsmäytä profiileja, jos yhdistettävien entiteettien etunimi ole sama.

1. Valitse **Muokkaa sääntöä** -ruudussa **Lisää** > **Lisää poikkeus**.

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

1. Valitaan **Mukautettu**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Mukautettu painike":::

1. Valitse **Mukautettu tyyppi** ja valitse **Lataa malli**. Jokaiselle vastinevaihtoehdolle on oltava oma malli.

1. Avaa ladattu mallitiedosto ja täytä tiedot. Malli sisältää kenttiä, jotka määrittävät entiteetin ja entiteetin ensisijaisen avaimen arvot. Niitä käytetään mukautetussa täsmäytyksessä. Jos esimerkiksi haluat, että *Myynti*-kohteen perusavain *12345* vastaa aina *Yhteyshenkilö*-kohteen perusavainta *34567*, täytä malli:
    - Entiteetti1: Myynti
    - Entiteetti1Avain: 12345
    - Entiteetti2: Yhteyshenkilö
    - Entiteetti2avain: 34567

   Sama mallitiedosto voi määrittää mukautetut täsmäytystietueet useista entiteeteistä.

   Jos haluat määrittää mukautetun vastaavuuden entiteetin kaksoiskappaleiden poistolle, määritä sama entiteetti sekä kohtaan Entiteetti1 ja Entiteetti2 ja määritä erilaisetn ensisijaisen avaimen arvot.

1. Kun olet lisännyt kaikki ohitukset, tallenna mallitiedosto.

1. Valitse **Tiedot** > **Tietolähteet** ja käsittele mallitiedostot uusina entiteetteinä.

1. Kun olet ladannut tiedostot, valitse **Mukauta**-vaihtoehto uudelleen. Valitse pakolliset entiteetit avattavasta valikosta ja valitse sitten **Valmis**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Näyttökuva dialogista, kun haluat valita mukautetun vastineen skenaarion ohitukset.":::

1. Mukautetun vastineen käyttö määräytyy sen mukaan, mitä vastinevaihtoehtoa haluat käyttää.

   - Siirry seuraavaan vaiheeseen, valitsemalla **Vastaavat aina toisiaan** tai **Eivät koskaan vastaa toisiaan**.
   - Valitse **Ohitus**- tai **Alias-yhdistämismääritys**-määritystä varten **Muokkaa** aiemmin luodussa vastaavuussäännössä tai luo uusi sääntö. Valitse normalisoinnin avattavasta luettelosta **Mukautettu ohitus**- tai **Alias-yhdistämismääritys** -asetus ja valitse **Valmis**.

1. Valitse **Valmis** **Mukauta**-ruudussa ottaaksesi käyttöön mukautetun yhdistämismäärityksen määritykset.

> [!div class="nextstepaction"]
> [Seuraava vaihe: Kenttien yhtenäistäminen](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
