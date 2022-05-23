---
title: Yhdistysasetusten päivittäminen
description: Voit päivittää sääntöjen kaksoiskappaleita, vastaavuussääntöjä tai yhtenäisiä kenttiä yhdistämisasetuksissa.
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: be399da9b98d8803d7d1a90f44a40e0d638a8d47
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755586"
---
# <a name="update-the-unification-settings"></a>Yhdistysasetusten päivittäminen

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Voit tarkastella tai muuttaa yhtenäisten profiilien yhdistämisasetuksia toimimalla seuraavasti.

1. Siirry kohtaan **Tiedot** > **Yhdistä**.

   :::image type="content" source="media/m3_unified.png" alt-text="Näyttökuva Tietojen yhtenäistäminen -sivusta, kun tiedot on yhdistetty.":::

   > [!TIP]
   > **Vastaavat ehdot** -ruutu näkyy vain, jos valittuna on useita entiteettejä.

1. Valitse, mitä haluat päivittää:
   - [Lähdekentät](#edit-source-fields), joiden avulla voit lisätä entiteettejä tai määritteitä tai muuttaa määritetyyppejä.
   - [Tietueiden kaksoiskappaleet](#manage-deduplication-rules) kaksoiskappaleiden poistosääntöjen tai yhdistämisasetusten hallintaa varten.
   - [Ehtojen täsmäytäminen](#manage-match-rules) kahden tai usean entiteettien vastaavuussääntöjen päivittämiseksi.
   - [Yhdistettyjen asiakaskenttien](#manage-unified-fields) yhdisteleminen tai poissulkeminen. Voit myös ryhmitellä toisiinsa liittyviä profiileja klusteriksi.

1. Kun olet tehnyt muutokset, valitse seuraava vaihtoehto:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Näyttökuva Tietojen yhdistäminen -sivusta, jossa Yhdistä-vaihtoehdot on korostettu.":::

   - Lisätietoja unified customer profile -profiilin päivittämisestä (riippuvuuksien kanssa tai ilman niitä) on ohjeaiheessa [Asiakasprofiilin päivitysten suoritus](#run-updates-to-the-unified-customer-profile).
   - Tietoja vastaavuusehtojen laadun arvioinnista päivittämättä yhdistettyjä profiilia on ohjeaiheessa [Vastaavien ehtojen suoritus](#run-matching-conditions). **Suorita vain vastaavuusehdot** -vaihtoehto ei näy yksittäiselle entiteetille.

## <a name="edit-source-fields"></a>Muokkaa lähdekenttiä

Määritettä tai entiteettiä ei voi poistaa, jos se on jo yhdistetty.

1. Valitse **Muokkaa** **Lähdekentät**-ruudussa.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Näyttökuva lähdekenttien sivusta, jossa näkyy perusavaimien, yhdistettyjen ja yhdistämättömien kenttien määrä":::

   Yhdistettyjen ja yhdistämättömien kenttien määrän näyttö.

1. Valitse **Valitse entiteetit ja kentät**, jos haluat lisätä muita määritteitä tai entiteettejä. Etsi ja valitse haluamasi määritteet ja entiteetit haun tai vierityksen avulla. Valitse **Käytä**.

1. Vaihtoehtoisesti voit muuttaa entiteetin perusavainta, määritetyyppejä ja ottaa **älykkään yhdistämismäärityksen** käyttöön tai poistaa sen käytöstä. Lisätietoja on ohjeaiheessa [Perusavaimen ja määritteiden semanttiseb tyypin valinta](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Valitse **Seuraava**, jos haluat tehdä muutoksia kaksoiskappaleiden poistosääntöihin, tai valitse **Tallenna ja sulje** ja palaa [Päivitä yhdistämisasetuksiin](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Kaksoiskappaleiden poistamissääntöjen hallinta

1. Valitse **Muokkaa** **Kaksoiskappaleet**-ruudussa.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Näyttökuva tietueiden kaksoiskappaleiden sivusta, jossa näkyy tietueiden kaksoiskappaleiden määrä" lightbox="media/m3_duplicates_edit.png":::

   **Kaksoiskappaleet**-kohdassa näkyy löydettyjen tietueiden kaksoiskappaleiden määrä. **Tietueiden kaksoiskappaleiden poistot** -sarakkeessa näkyvät entiteetit, joilla oli tietueiden kaksoiskappaleita, ja tietueiden kaksoiskappaleiden prosenttiosuus.

1. Jos olet lisännyt rikastetun entiteetin, valitse **Käytä rikastettuja entiteettejä**. Lisätietoja: [Rikastus tietolähteitä varten](data-sources-enrichment.md).

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

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Näyttökuva yhdistämisasetusten lisäasetuksista, joissa näkyvät uusin sähköpostiviesti ja täydellisin osoite":::

   1. Valitse **Valmis**.

1. Valitse **Seuraava**, jos haluat tehdä muutoksia yhdistämissääntöihin, tai valitse **Tallenna ja sulje** ja palaa [Päivitä yhdistämisasetuksiin](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Täsmäytyssääntöjen hallinta

Voit määrittää ja hienosäätää useimpia vastineparametreja. Et voi lisätä tai poistaa entiteettejä. Vastinesäännöt eivät koske yksittäistä entiteettiä.

1. Valitse **Muokkaa** **Yhdistämissäännöt**-ruudussa.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Näyttökuva Täsmäytä säännöt ja ehdot -sivusta tilastotietojen kanssa." lightbox="media/m3_match_edit.png":::

   Sivulla näkyvät vastaavuusjärjestys ja määritetyt säännöt sekä seuraavat tilastot:
   - **Yksilöllisissä lähdetietueissa** näkyy viime hakusuorituksessa käsiteltyjen yksittäisten lähdetietueiden määrä.
   - **Täsmäytettyjen ja yhdistätyjen tietueiden** perusteella voidaan korostaa, kuinka monta yksilöllistä tietuetta on jäljellä vastaavuussääntöjen käsittelyn jälkeen.
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

1. Valitse **Seuraava**, jos haluat tehdä muutoksia yhtenäistettyihin kenttiin, tai valitse **Tallenna ja sulje** ja palaa [Päivitä yhdistämisasetuksiin](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Yhdenmukaistettujen kenttien hallinta

1. Valitse **Muokkaa** **Yhdistetyt asiakaskentät**-ruudussa.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Näyttökuva yhdistetyistä asiakaskentistä":::

1. Tarkista yhdistetyt ja poisjätetyt kentät ja tee tarvittavat muutokset. Voit lisätä CustomerID-avaimen tai muokata sitä tai ryhmitellä profiileja klustereiksi. Lisätietoja on kohdassa [Yhdistä asiakaskentät](merge-entities.md).

1. Valitse **Seuraava**, jos haluat tarkistaa yhdistämisasetukset ja [päivittää yhdistetyn profiilin ja riippuvuudet](#run-updates-to-the-unified-customer-profile), tai valitse **Tallenna ja sulje** ja palaa [Päivitä yhdistämisasetukset](#update-the-unification-settings) -kohtaan, jos haluat tehdä lisää muutoksia.

## <a name="run-matching-conditions"></a>Suorita vastaavuusehdot

1. Valitse **Tiedot** > **Yhdistä** -sivulta **Suorita vain vastaavuussäännöt**.

   **Tietueiden kaksoiskappaleet** - ja **Vastaavat ehdot** -ruuduissa näkyy **Jonossa** tai **Päivitä**.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

1. Kun yhdistämisprosessi on valmis, valitse **Muokkaa** **Vastaavuusehdot**-ruudussa.

   :::image type="content" source="media/match-KPIs.png" alt-text="Rajattu näyttökuva vertailusivun mittausarvoista lukujen ja tietojen kanssa.":::

1. Lisätietoja muutosten tekemisestä on ohjeaiheessa [Kaksoiskappaleiden poistosääntöjen hallinta](#manage-deduplication-rules) tai [Vastaavuussääntöjen hallinta](#manage-match-rules).

1. Suorita yhdistämisprosessi uudelleen tai [suorita asiakasprofiilin päivitykset](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Suorita unified customer profile -profiilin päivitykset

1. Valitse **Tiedot** > **Yhdistä** -sivulta:

   - **Yhdistä asiakasprofiilit**: päivittää unified customer profile -profiilientiteetin vaikuttamatta riippuvuuksiin (kuten rikastuksiin, segmentteihin tai toimenpiteisiin). Riippuvaisia prosesseja ei suoriteta, mutta ne päivittyvät [päivitysaikataulun mukaisesti](system.md#schedule-tab).

   - **Yhdistä asiakasprofiileja ja riippuvuuksia**: päivittää yhtenäisen profiilin ja kaikki riippuvuudet. Kaikki prosessit käynnistyvät uudelleen automaattisesti. Kun kaikki jatkoprosessit on tehty, asiakasprofiili vastaa päivitettyjä tietoja.

   **Tietueiden kaksoiskappaleet** -, **Yhdistämisehdot**- ja **Yhdistetyt asiakaskentät** -ruuduissä näkyy **Jonossa** tai **Päivitetään**.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]
