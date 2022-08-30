---
title: Kaksoiskappaleiden poistaminen ennen tietojen yhdistämistä
description: Toinen vaihe yhdistämisprosessissa on valita tietue, joka tallennetaan, kun kaksoiskappaleita löytyy.
recommendations: false
ms.date: 08/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 3f84c1c149f0befcbe489ccdd8a666ce6d5d798a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304469"
---
# <a name="remove-duplicates-before-unifying-data"></a>Kaksoiskappaleiden poistaminen ennen tietojen yhdistämistä

Tämän valinnaisen yhdistämisvaiheen avulla voit määrittää sääntöjä päällekkäisten tietueiden poistamiseksi **entiteetistä**. Kaksoiskappaleiden poisto tunnistaa useita tietueita asiakkaalle ja valitsee parhaan tietueen säilytettäväksi (yhdistämisasetusten perusteella) tai yhdistää tietueet yhdeksi (yhdistämisasetusten lisäasetusten perusteella). Lähdetietueet linkitetään yhdistettyyn tietueeseen vaihtoehtoisilla tunnuksilla. Jos sääntöjä ei ole määritetty, sovelletaan järjestelmän määrittämiä sääntöjä.

## <a name="default-deduplication"></a>Oletuskaksoiskappaleiden poisto

Järjestelmän määrittämiä sääntöjä sovelletaan, jos kaksoiskappaleiden poistamissääntöjä ei ole lisätty.

- Perusavaimen kaksoiskappale poistettu.
  Jos tietueella on sama perusavain, voittaja on **Eniten täytetty** tietue (joka sisältää vain muutaman tyhjäarvon).
- Entiteettiä vastaavat ristientiteettiä vastaavat säännöt koskevat entiteettiä.
  Esimerkki: Jos täsmäytysvaiheessa entiteetti A vastaa entiteettiä B *FullName* ja *DateofBirth* -kohdassa, entiteetistä A poistetaan myös kaksoiskappaleet *FullName* ja *DateofBirth*. Koska *FullName* ja *DateofBirth* ovat kelvollisia avaimia asiakkaan tunnistamiseen entiteetissä A, nämä avaimet kelpaavat myös asiakkaiden kaksoiskappaleiden tunnistamiseen entiteetissä A.

## <a name="include-enriched-entities-preview"></a>Rikastettujen entiteettien sisällyttäminen (esiversio)

Jos olet rikastanut entiteetit tietolähteen tasolla parantaaksesi yhdistämisen tuloksia, valitse ne. Lisätietoja: [Rikastus tietolähteitä varten](data-sources-enrichment.md).

1. Valitse **Kaksoiskappaleet** - sivun yläreunassa **Käytä rikastettuja entiteettejä**.

1. Valitse vähintään yksi rikastettu entiteetti **Käytä rikastettuja entiteettejä** -ruudusta.

1. Valitse **Valmis**.

## <a name="define-deduplication-rules"></a>Määritä kaksoiskappaleiden poistamissäännöt

1. Valitse **Tietueiden kaksoiskappaleet** -sivulla entiteetti ja määritä kaksoiskappaleiden poistamissäännöt valitsemalla **Lisää sääntö**.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Näyttökuva Tietueiden kaksoiskappaleet -sivusta, jossa entiteetti on korostettu ja Lisää sääntö -kohta on näkyvissä"  lightbox="media/m3_duplicates_showmore.png":::

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

[!INCLUDE[footer-include](includes/footer-banner.md)]
