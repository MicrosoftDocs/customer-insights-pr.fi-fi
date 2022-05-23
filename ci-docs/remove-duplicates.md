---
title: Kaksoiskappaleiden poistaminen ennen tietojen yhdistämistä
description: Toinen vaihe yhdistämisprosessissa on valita tietue, joka tallennetaan, kun kaksoiskappaleita löytyy.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 27dff3551ab411a12c273536d7431d651c48573e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741631"
---
# <a name="remove-duplicates-before-unifying-data"></a>Kaksoiskappaleiden poistaminen ennen tietojen yhdistämistä

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Tämän yhdistämisvaiheen avulla voit vaihtoehtoisesti määrittää säännöt entiteetin tietueiden kaksoiskappaleiden käsittelyä varten. *Kaksoiskappaleiden poisto* tunnistaa tietueiden kaksoiskappaleet ja yhdistää ne yhteen tietueeseen. Lähdetietueet linkitetään yhdistettyyn tietueeseen vaihtoehtoisilla tunnuksilla. Jos sääntöjä ei ole määritetty, sovelletaan järjestelmän määrittämiä sääntöjä.

## <a name="include-enriched-entities-preview"></a>Rikastettujen entiteettien sisällyttäminen (esiversio)

Jos olet rikastanut entiteetit tietolähteen tasolla parantaaksesi yhdistämisen tuloksia, valitse ne. Lisätietoja: [Rikastus tietolähteitä varten](data-sources-enrichment.md).

1. Valitse **Kaksoiskappaleet** - sivun yläreunassa **Käytä rikastettuja entiteettejä**.

1. Valitse vähintään yksi rikastettu entiteetti **Käytä rikastettuja entiteettejä** -ruudusta.

1. Valitse **Valmis**.

## <a name="define-deduplication-rules"></a>Määritä kaksoiskappaleiden poistamissäännöt

1. Valitse **Tietueiden kaksoiskappaleet** -sivulla entiteetti ja määritä kaksoiskappaleiden poistamissäännöt valitsemalla **Lisää sääntö**.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Näyttökuva Tietueiden kaksoiskappaleet -sivuista, jossa Näytä lisää on korostettu":::

   1. Syötä **Lisää sääntö** -ruutuun seuraavat tiedot:
      - **Valitse kenttä**: Valitse sen entiteetin käytettävissä olevien kenttien luettelosta, jonka kaksoiskappaleita haluat tarkistaa. Valitse kentät, jotka ovat todennäköisesti yksilöllisiä jokaiselle asiakkaalle. Esimerkiksi sähköpostiosoite tai nimen, postiosoitteen ja puhelinnumeron yhdistelmä.
      - **Normalisoi**: Valitse seuraavista normalisointivaihtoehdoista valituille määritteille.
        - **Numeraalit**: muuntaa muut numerojärjestelmät, kuten roomalaiset numerot arabialaisiksi numeroiksi. *VIII* muuttuu muotoon *8*.
        - **Symbolit**: poistaa kaikki symbolit ja erikoismerkit. *Head&Shoulder* muuttuu muotoon *HeadShoulder*.
        - **Teksti pieniksi kirjaimiksi: Muuntaa kaikki merkit pieniksi**. *KAIKKI ISOLLA- ja Ensimmäiset Kirjaimet Isolla* -tapaukset muuttuvat muotoon *kaikki isolla- ja ensimmäiset kirjaimet isolla*.
        - **Tyyppi (Puhelin, Nimi, Osoite, Organisaatio)**: standardoi nimet, otsikot, puhelinnumerot, osoitteet jne.
        - **Unicode ASCII-muotoon**: muuntaa Unicode-merkinnät ASCII-merkeiksi. */u00B2* muuttuu muotoon *2*.
        - **Tyhjä tila**: poistaa kaikki välilyönnit. *Hello Worldista* tulee *HelloWorld*.
      - **Tarkkuus**: Määritä tässä ehdossa käyttöönotettu tarkkuustaso.
        - **Perustiedot**: Valitse arvoksi *Matala (30 %)*, *Keskitaso (60 %)*, *Korkea (80 %)* tai *Tarkka (100 %)*. Valitse **Tarkka**, jos haluat yhdistää vain tietueet, jotka vastaavat 100 prosentin tarkkuudella.
        - **Mukautettu**: Määritä prosenttiluku, jota tietueiden on vastattava. Järjestelmä yhdistää vain tämän raja-arvon ohittavat tietueet.
      - **Nimi**: Säännön nimi.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Näyttökuva Lisää sääntö -ruudusta kaksoiskappaleiden poistamista varten.":::

   1. Voit valinnaisesti valita **Lisää** > **Lisää ehto** lisätäksesi sääntöön lisää ehtoja. Ehdot yhdistetään loogiseen JA-operaattoriin, joten ne suoritetaan vain, jos kaikki ehdot täyttyvät.

   1. Vaihtoehtoisesti voit valita **Lisää** > **Lisää poikkeus** [lisätäksesi sääntöön poikkeuksia](match-entities.md#add-exceptions-to-a-rule). Poikkeuksia käytetään harvoissa väärissä positiivisissa ja väärissä negatiivisissa tapauksissa.

   1. Luo sääntö valitsemalla **Valmis**.

1. Voit myös [lisätä muita sääntöjä](#define-deduplication-rules).

1. Valitse entiteetti ja sitten **Muokkaa yhdistämisasetuksia**.

1. Valitse **Yhdistämisasetukset** -ruudussa seuraavat tiedot:
   1. Valitse jokin kolmesta vaihtoehdosta sen määrittämiseksi, mikä tietue säilytetään, jos kaksoiskappale löytyy:
      - **Useimmat täytetyt**: Määrittää voittavaksi tietueeksi tietueen, jossa on eniten täytettyjä määritekenttiä. Se on yhdistämisen oletusasetus.
      - **Uusin**: Määrittää voittajatietueeksi uusimman tietueen. Viimeaikaisuuden määrittämiseen tarvitaan päivämäärä- tai numerokenttä.
      - **Vähiten viimeaikaiset**: Määrittää voittajatietueeksi vähiten viimeaikaisimman tietueen. Viimeaikaisuuden määrittämiseen tarvitaan päivämäärä- tai numerokenttä.
      
      Jos arvo on tasapeli, voittajatietue on se, jolla on MAX(PK) tai suurempi perusavaimen arvo.
      
   1. Jos haluat määrittää yhdistämisen asetukset entiteetin yksittäisille määritteille, valitse ruudun alaosasta **Lisäasetukset**. Voit esimerkiksi säilyttää uusimman sähköpostiviestin JA täydellisimmän osoitteen eri tietueista. Laajenna entiteettiä, kun haluat nähdä sen kaikki määritteet, ja määritä, mitä asetusta käytetään yksittäisissä määritteissä. Jos valitset viimeaikaisuuteen perustuvan vaihtoehdon, sinun täytyy myös määrittää päivämäärä-/aikakenttä, joka määrittää viimeaikaisuuden.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Yhdistämisasetusten lisäasetukset, joissa näkyvät uusin sähköposti ja täydellinen osoite":::

   1. Ota yhdistämisasetukset käyttöön valitsemalla **Valmis**.

1. Kun olet määrittänut kaksoiskappaleiden poistosäännöt ja yhdistämisasetukset, valitse **Seuraava**.
  
> [!div class="nextstepaction"]
> [Yksittäisen entiteetin seuraava vaihe: Kenttien yhdistäminen](merge-entities.md)

> [!div class="nextstepaction"]
> [Useiden entiteettien seuraava vaihe: Vastaavuusehdot](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Kaksoiskappaleiden poiston tulos entiteettinä

Kaksoiskappaleiden poistoprosessi luo uuden entiteetin, josta kaksoiskappaleet on poistettu kullekin lähde-entiteetille. Nämä entiteetit löytyvät yhdessä **ConflationMatchPairs:CustomerInsights**-entiteetin kanssa **Järjestelmä**-osasta **Entiteetit**-sivulta nimellä **Deduplication_DataSource_Entity**.

Kaksoiskappaleiden poiston tulosentiteetti sisältää seuraavat tiedot:

- Tunnukset/avaimet
  - Perusavaimen ja vaihtoehtoisen tunnuksen kentät. Vaihtoehtoinen tunnuskenttä sisältää kaikki tietueelle tunnistetut vaihtoehtoiset tunnukset.
  - Deduplication_GroupId-kentässä on ryhmä tai klusteri, joka sellainen entiteetti määrittää, joka ryhmittelee kaikki samanlaiset tietueet määritettyjen kaksoiskappaleiden poiston kenttien perusteella. Sitä käytetään järjestelmän käsittelyssä. Jos manuaalisia kaksoiskappaleiden poiston sääntöjä ei ole määritetty, ja järjestelmän määrittämät kaksoiskappaleiden poiston säännöt on otettu käyttöön, tätä kenttää ei ehkä löydy kaksoiskappaleiden poiston tulosentiteetistä.
  - Deduplication_WinnerId: Tämä kenttä sisältää määritettyjen ryhmien tai klustereiden voittaneen tunnuksen. Jos Deduplication_WinnerId on sama kuin tietueen ensisijaisen avaimen arvo, tietue on voittanut tietue.
- Kenttiä käytetään kaksoiskappaleiden poiston sääntöjen määrittämisessä.
- Sääntö- ja Pistemäärä-kentät määrittävät, mitä kaksoiskappaleiden poiston sääntöjä noudatetaan. Ne määrittävät myös vastaavan algoritmin palauttaman pistemäärän.

[!INCLUDE[footer-include](includes/footer-banner.md)]
