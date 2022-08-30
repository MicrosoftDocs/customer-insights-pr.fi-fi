---
title: Asiakkaan, tilin tai yhteyshenkilön yhtenäistämisasetusten päivittäminen
description: Voit päivittää sääntöjen kaksoiskappaleita, vastaavuussääntöjä tai yhtenäisiä kenttiä asiakkaan tai tilin yhdistämisasetuksissa.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: f2c14c169f5973b5f400989b9eeea593eba09182
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304331"
---
# <a name="update-unification-settings"></a>Yhdistysasetusten päivittäminen

Voit tarkastella tai muuttaa yhtenäisten profiilien yhdistämisasetuksia toimimalla seuraavasti.

1. Siirry kohtaan **Tiedot** > **Yhdistä**.

   Yksittäisten asiakkaiden (B2C) osalta **Yhtenäistä**-sivulla näkyy yhtenäisten asiakasprofiilien ja ruutujen määrä kunkin yhdistämisvaiheen osalta.

   :::image type="content" source="media/m3_unified.png" alt-text="Näyttökuva Tietojen yhtenäistäminen -sivusta, kun tiedot on yhdistetty." lightbox="media/m3_unified.png":::

   Yritysasiakkaiden (B2B) osalta **Yhtenäistä**-sivulla näkyy yhtenäisten tiliprofiilien ja ruutujen määrä kunkin tilin yhdistämisvaiheen osalta. Jos yhteyshenkilöt on yhdistetty, yhdistettyjen yhteyshenkilöprofiilien määrä ja kunkin yhteyshenkilöprofiilien yhdistämisvaiheen ruutujen määrä näkyy. Valitse **Yhtenäistä tilit**- tai **Yhtenäistä yhteyshenkilöt (esiversio)** -kohdassa haluamasi ruutu sen mukaan, mitä haluat päivittää.

   :::image type="content" source="media/b2b_unified.png" alt-text="Näyttökuva Tietojen yhtenäistäminen -sivusta, kun tili- ja yhteyshenkilötiedot on yhdistetty." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > **Vastaavat ehdot** -ruutu näkyy vain, jos valittuna on useita entiteettejä.

1. Valitse, mitä haluat päivittää:
   - [Lähdekentät](#edit-source-fields), joiden avulla voit lisätä entiteettejä tai määritteitä tai muuttaa määritetyyppejä.
   - [Tietueiden kaksoiskappaleet](#manage-deduplication-rules) kaksoiskappaleiden poistosääntöjen tai yhdistämisasetusten hallintaa varten.
   - [Ehtojen täsmäytäminen](#manage-match-rules) kahden tai usean entiteettien vastaavuussääntöjen päivittämiseksi.
   - [Yhdistettyjen asiakaskenttien](#manage-unified-fields) yhdisteleminen tai poissulkeminen. Voit myös ryhmitellä toisiinsa liittyviä profiileja klusteriksi.
   - [Semanttiset kentät](#manage-semantic-fields-for-unified-contacts) yhtenäisten yhteyshenkilökenttien semanttisten tyyppien hallintaa varten.
   - [Suhteet](#manage-contact-and-account-relationships) yhteyshenkilö-tili-suhteen hallintaan.

1. Kun olet tehnyt muutokset, valitse seuraava vaihtoehto:

   - [Vastaavuuksien haun ehtojen suorittaminen](#run-matching-conditions) antaa mahdollisuuden arvioida nopeasti vastaavuuksien haun ehtojen laatua (kaksoiskappaleiden poiston ja vastaavuussääntöjen) päivittämättä yhdistettyjä profiilia. **Suorita vain vastaavuusehdot** -vaihtoehto ei näy yksittäiselle entiteetille.
   - [Profiilien yhdistäminen](#run-updates-to-the-unified-profile) suorittamaan vastaavuuksien haun ehdot ja päivittämään yhdistetyn profiilin entiteetti vaikuttamatta riippuvuuksiin (kuten rikastuksiin, segmentteihin tai mittareihin). Riippuvaisia prosesseja ei suoriteta, mutta ne päivittyvät [päivitysaikataulun mukaisesti](schedule-refresh.md).
   - [Profiilien ja riippuvuuksien yhdistäminen](#run-updates-to-the-unified-profile) suorittamaan vastaavuuksien haun ehdot ja päivittämään yhdistetyn profiilin entiteetti ja kaikki riippuvuudet (kuten rikastukset, segmentit tai mittarit). Kaikki prosessit käynnistyvät uudelleen automaattisesti. B2B-tilanteessa yhdistäminen suoritetaan sekä tili- että yhteyshenkilöentiteeteille, jotka päivittävät yhdistettyjä profiileita.

## <a name="edit-source-fields"></a>Muokkaa lähdekenttiä

Määritettä tai entiteettiä ei voi poistaa, jos se on jo yhdistetty.

1. Valitse **Muokkaa** **Lähdekentät**-ruudussa.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Näyttökuva lähdekenttien sivusta, jossa näkyy perusavaimien, yhdistettyjen ja yhdistämättömien kenttien määrä":::

   Yhdistettyjen ja yhdistämättömien kenttien määrän näyttö.

1. Valitse **Valitse entiteetit ja kentät**, jos haluat lisätä muita määritteitä tai entiteettejä.

1. Vaihtoehtoisesti voit muuttaa entiteetin perusavainta, määritetyyppejä ja ottaa **älykkään yhdistämismäärityksen** käyttöön tai poistaa sen käytöstä. Lisätietoja on kohdassa [Lähdekenttien valinta](map-entities.md).

1. Valitse **Seuraava**, jos haluat tehdä muutoksia kaksoiskappaleiden poistosääntöihin, tai valitse **Tallenna ja sulje** ja palaa kohtaan [Päivitä yhdistämisasetukset](#update-unification-settings).

## <a name="manage-deduplication-rules"></a>Kaksoiskappaleiden poistamissääntöjen hallinta

1. Valitse **Muokkaa** **Kaksoiskappaleet**-ruudussa.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Näyttökuva tietueiden kaksoiskappaleiden sivusta, jossa näkyy tietueiden kaksoiskappaleiden määrä" lightbox="media/m3_duplicates_edit.png":::

   **Kaksoiskappaleet**-kohdassa näkyy löydettyjen tietueiden kaksoiskappaleiden määrä. **Tietueiden kaksoiskappaleiden poistot** -sarakkeessa näkyvät entiteetit, joilla oli tietueiden kaksoiskappaleita, ja tietueiden kaksoiskappaleiden prosenttiosuus.

1. Jos haluat käyttää rikastettua entiteettiä, valitse **Käytä rikastettuja entiteettejä**. Lisätietoja: [Rikastus tietolähteitä varten](data-sources-enrichment.md).

1. Jos haluat hallita kaksoiskappaleiden poistamissääntöjä, valitse jokin seuraavista vaihtoehdoista:
   - **Luo uusi sääntö**: valitse **Lisää sääntö** asianmukaisen entiteetin alta. Lisätietoja on kohdassa [Kaksoiskappaleiden poistosääntöjen määrittäminen](remove-duplicates.md#define-deduplication-rules).
   - **Muuta säännön ehtoja**: Valitse sääntö ja sitten **Muokkaa**. Muuta kenttiä, lisää tai poista ehtoja tai lisää tai poista poikkeuksia.
   - **Esikatselu**: Valitse sääntö ja **esikatsele**, jos haluat tarkastella säännön viimeisimmän suorituksen tuloksia.
   - **Säännön aktivoinnin poistaminen**: valitse sääntö ja **poista sen jälkeen aktivointi**, jos haluat säilyttää kaksoiskappaleiden poistosäännön ja sulkea sen pois vastaavasta prosessista.
   - **Säännön kaksoiskappale**: valitse sääntö ja luo sitten **kaksoiskappale**, jos haluat luoda samanlaisen säännön muutoksin.
   - **Säännön poistaminen**: Valitse sääntö ja **poista**.

1. Voit muuttaa yhdistämisasetuksia valitsemalla entiteetin. Voit muuttaa asetuksia vain, jos sääntö on luotu.
   1. Valitse **Muokkaa yhdistämisasetuksia** ja muuta **Säilytettävää tietuetta**, jos haluat säilyttää vaihtoehdon.
   1. Jos haluat muuttaa entiteetin yksittäisten määritteiden yhdistämisasetuksia, valitse **Lisäasetukset** ja tee tarvittavat muutokset.

   1. Valitse **Valmis**.

1. Valitse **Seuraava**, jos haluat tehdä muutoksia yhdistämissääntöihin, tai valitse **Tallenna ja sulje** ja palaa kohtaan [Päivitä yhdistämisasetukset](#update-unification-settings).

## <a name="manage-match-rules"></a>Täsmäytyssääntöjen hallinta

Voit määrittää ja hienosäätää useimpia vastineparametreja. Et voi lisätä tai poistaa entiteettejä. Vastinesäännöt eivät koske yksittäistä entiteettiä.

1. Valitse **Muokkaa** **Yhdistämissäännöt**-ruudussa.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Näyttökuva Täsmäytä säännöt ja ehdot -sivusta tilastotietojen kanssa." lightbox="media/m3_match_edit.png":::

   Sivulla näkyvät vastaavuusjärjestys ja määritetyt säännöt sekä seuraavat tilastot:
   - **Yksilöllisissä lähdetietueissa** näkyy viime hakusuorituksessa käsiteltyjen yksittäisten lähdetietueiden määrä.
   - **Täsmäytettyjen ja yhdistettyjen tietueiden** perusteella voidaan korostaa, kuinka monta yksilöllistä tietuetta on jäljellä vastaavuussääntöjen käsittelyn jälkeen.
   - **Vain täsmäytetyt tietueet** osoittavat vain kaikkien vastineparien vastaavuudet.

1. Jos haluat tarkastella kaikkien sääntöjen tuloksia ja niiden pistemäärää, valitse **Näytä viimeinen suoritus**. Tulokset, mukaan lukien vaihtoehtoiset yhteyshenkilötunnukset, näytetään. Voit ladata tulokset.

1. Jos haluat tarkastella tietyn säännön tuloksia ja pisteitä, valitse sääntö ja **esikatsele**. Tulokset näytetään. Voit ladata tulokset.

1. Jos haluat tarkastella tietyn ehdon tuloksia säännössä, valitse sääntö ja **Muokkaa**. Valitse Muokkaa-ruudusta ehdon alapuolelta **Esikatselu**. Voit ladata tulokset.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Graafinen esitys yhdistetyistä ja yhdistämättömistä tietueista, mukaan lukien tietoluettelo.":::

1. Jos olet lisännyt rikastetun entiteetin, valitse **Käytä rikastettuja entiteettejä**. Lisätietoja: [Rikastus tietolähteitä varten](data-sources-enrichment.md).

1. Jos haluat hallita sääntöjä, valitse jokin seuraavista vaihtoehdoista:
   - **Luo uusi sääntö**: valitse **Lisää sääntö** asianmukaisen entiteetin alta. Lisätietoja on ohjeaiheessa [Vastaavuusparien sääntöjen määrittäminen](match-entities.md#define-rules-for-match-pairs).
   - **Muuta sääntöjen järjestystä**, jos olet määrittänyt useita sääntöjä: vedä ja pudota säännöt haluamaasi järjestykseen. Lisätietoja on kohdassa [Määritä vastaavuusjärjestys](match-entities.md#specify-the-match-order).
   - **Muuta säännön ehtoja**: Valitse sääntö ja sitten **Muokkaa**. Muuta kenttiä, lisää tai poista ehtoja tai lisää tai poista poikkeuksia.
   - **Säännön aktivoinnin poistaminen**: valitse sääntö ja **Poista aktivointi**, jos haluat säilyttää yhdistämissäännön ja sulkea sen pois vastaavasta prosessista.
   - **Säännön kaksoiskappale**: valitse sääntö ja luo sitten **kaksoiskappale**, jos haluat luoda samanlaisen säännön muutoksin.
   - **Säännön poistaminen**: Valitse sääntö ja **poista**.

1. Valitse **Seuraava**, jos haluat tehdä muutoksia yhtenäistettyihin kenttiin, tai valitse **Tallenna ja sulje** ja palaa kohtaan [Päivitä yhdistämisasetukset](#update-unification-settings).

## <a name="manage-unified-fields"></a>Yhdenmukaistettujen kenttien hallinta

1. Valitse **Muokkaa** **Yhdistetyt asiakaskentät**-ruudussa.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Näyttökuva yhdistetyistä asiakaskentistä":::

1. Tarkista yhdistetyt ja poisjätetyt kentät ja tee tarvittavat muutokset. Voit lisätä CustomerID-avaimen tai muokata sitä tai ryhmitellä profiileja klustereiksi. Lisätietoja on kohdassa [Yhdistä asiakaskentät](merge-entities.md).

1. Jos käytössäsi on asiakkaat tai tilit, tarkista ja [päivitä yhtenäinen profiili ja riippuvuudet](#run-updates-to-the-unified-profile) valitsemalla **Seuraava**. Jos haluat tehdä lisää muutoksia, valitse **Tallenna ja sulje** ja palaa kohtaan [Päivitä yhdistämisasetukset](#update-unification-settings).

   Jos haluat hallita semanttisia kenttiä yhteyshenkilöille, valitse **Seuraava**. Jos haluat tehdä lisää muutoksia, valitse **Tallenna ja sulje** ja palaa kohtaan [Päivitä yhdistämisasetukset](#update-unification-settings).

## <a name="manage-semantic-fields-for-unified-contacts"></a>Yhdenmukaistettujen yhteyshenkilöiden semanttisten kenttien hallinta

1. Valitse **Muokkaa** **Semanttiset kentät** -ruudussa.

1. Jos haluat muuttaa yhdistetyn kentän semanttista tyyppiä, valitse uusi tyyppi. Lisätietoja on ohjeaiheessa [Yhtenäisten yhteyshenkilöiden semanttisten kenttien määrittäminen](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Valitse **Seuraava**, jos haluat hallita tili-yhteyshenkilö-suhteita tai tee lisää muutoksia valitsemalla **Tallenna ja sulje** ja palaa kohtaan [Päivitä yhdistämisasetukset](#update-unification-settings).

## <a name="manage-contact-and-account-relationships"></a>Yhteyshenkilö-tili-suhteiden hallinta

1. Valitse **Muokkaa** **Suhteet**-ruudussa.

1. Jos haluat muuttaa yhteyshenkilön ja tilin suhdetta, muuta seuraavia tietoja:

   - **Viiteavain yhteyshenkilöentiteetistä**: Valitse määrite, joka yhdistää yhteyshenkilöentiteetin tiliin.
   - **Tilientiteettiin**: Valitse yhteyshenkilöön liittyvä tilientiteetti.

1. Valitse **Seuraava**, jos haluat tarkistaa yhdistämisasetukset ja [päivittää yhdistetyn profiilin ja riippuvuudet](#run-updates-to-the-unified-profile), tai valitse **Tallenna ja sulje** ja palaa [Päivitä yhdistämisasetukset](#update-unification-settings) -kohtaan, jos haluat tehdä lisää muutoksia.

## <a name="run-matching-conditions"></a>Suorita vastaavuusehdot

Vastaavuuksien haun ehtojen suorittaminen suorittaa vain kaksoiskappaleiden poiston ja vastaavuussäännöt sekä päivittää *Deduplication_*- ja *ConflationMatchPair*-entiteetit.

1. Valitse **Tiedot** > **Yhdistä** -sivulta **Suorita vain vastaavuussäännöt**.

   **Tietueiden kaksoiskappaleet**- ja **Vastaavuuksien haun ehdot** -ruuduissa tilana on **Jonossa** tai **Päivitä**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Kun yhdistämisprosessi on valmis, valitse **Muokkaa** **Vastaavuusehdot**-ruudussa.

   :::image type="content" source="media/match-KPIs.png" alt-text="Rajattu näyttökuva vertailusivun mittausarvoista lukujen ja tietojen kanssa.":::

1. Lisätietoja muutosten tekemisestä on ohjeaiheessa [Kaksoiskappaleiden poistosääntöjen hallinta](#manage-deduplication-rules) tai [Vastaavuussääntöjen hallinta](#manage-match-rules).

1. Suorita yhdistämisprosessi uudelleen tai [suorita profiilin päivitykset](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Suorita yhdistetyn profiilin päivitykset

- Suorita vastaavuuksien haun ehdot ja päivitä yhdistetyn profiilin entiteetti *ilman*, että vaikutat riippuvuuksiin (kuten asiakaskortteihin, rikastuksiin, segmentteihin tai mittareihin) valitsemalla **Yhtenäistä asiakasprofiilit** Valitse tileille **Yhtenäistä tilit** > **Yhtenäistä profiilit**. Valitse yhteyshenkilöille **Yhtenäistä yhteyshenkilöt (esiversio)** > **Yhtenäistä profiilit**. Riippuvaisia prosesseja ei suoriteta, mutta ne päivittyvät [päivitysaikataulun mukaisesti](schedule-refresh.md).
- Suorita vastaavuuksien haun ehdot sekä päivitä yhtenäisen profiilin ja kaikki riippuvuudet valitsemalla **Yhdistä asiakasprofiilit ja riippuvuudet**. Kaikki prosessit käynnistyvät uudelleen automaattisesti. Jos valitset tilit ja yhteyshenkilöt, valitse **Yhtenäistä tilit** > **Yhtenäistä profiilit ja riippuvuudet**. Sekä tileille että yhteyshenkilöille suoritetaan vastaavuusehdot, jotka päivittävät molemmat yhtenäiset profiilit ja muut riippuvuudet suoritetaan.

Kaikissa muissa ruuduissa paitsi **Lähdekentät** tilana on **Jonossa** tai **Päivittää**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Onnistuneen suorituksen tulokset näkyvät **Yhtenäistä**-sivulla , jossa näkyy yhdistettyjen profiilien määrä.
