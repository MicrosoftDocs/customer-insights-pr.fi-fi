---
title: Luo monimutkaisia segmenttejä segmentin muodostintyökalun avulla
description: Monimutkaisia asiakassegmenttejä luodaan ryhmittelemällä niitä erilaisten määritteiden perusteella käyttämällä segmentin muodostinta.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 7f691fd0b2ea76a2960d5adf766a4b166f02ebb4
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304745"
---
# <a name="create-complex-segments-with-segment-builder"></a>Luo monimutkaisia segmenttejä segmentin muodostintyökalun avulla

Määritä yhdistetyn asiakasentiteetin tai yhdistetyn yhteyshenkilön ja siihen liittyvien entiteettien monimutkaiset suodattimet. Kukin segmentti luo käsittelyn jälkeen asiakas- tai yhteyshenkilötietuejoukon, jonka voi viedä ja jota voi käsitellä.

> [!TIP]
> Segmentit, jotka perustuvat **yksittäisiin asiakkaisiin**, sisältävät automaattisesti käytössä olevat segmentin jäsenten yhteystiedot. Jos **yritystileillä** [yhdenmukaistat](data-unification.md) sekä tilit ja yhteyshenkilöt, valitse, perustuuko segmentti tileihin vai yhteyshenkilöihin. Jos haluat viedä tietoja kohteeseen, joka odottaa yhteystietoja, käytä yhteyshenkilöiden segmenttiä. Jos haluat viedä tietoja kohteeseen, joka odottaa tilitietoja, käytä tilien segmenttiä.

## <a name="segment-builder"></a>Segmentin muodostin

Seuraavassa kuvassa on kuvattu segmentin muodostimen eri osia. Se näyttää segmentin, joka johtaa asiakasryhmään. Asiakkaat tilasivat tuotteita tietyllä aikavälillä ja keräsivät palkkiopisteitä tai käyttivät tietyn rahasumman.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Segmentin muodostimen elementit." lightbox="media/segment-builder-overview.png":::

1. Järjestä segmentti sääntöjen ja alisääntöjen avulla. Kukin sääntö tai alisääntö koostuu ehdoista. Ehtojen yhdistäminen loogisiin operaattoreihin.

1. Valitse sääntöä koskeva [suhdepolku](relationships.md) entiteettien välillä. Suhdepolku määrittää, mitä määritteitä ehdossa voi käyttää.

1. Hallitse sääntöjä ja alisääntöjä. Muuta säännön sijaintia tai poista se.

1. Ehtojen lisääminen ja oikean kerrosteisuustason muodostaminen alisääntöjen avulla.

1. Käytä määritettyjä toimintoja yhdistettyihin sääntöihin.

1. Lisää määriteruudussa käytettävissä olevat entiteettimääritteet tai luo määritteeseen perustuvia ehtoja. Ruudussa näkyy valitun säännön käytettävissä olevien entiteettien ja määritteiden luettelo valitun suhdepolun perusteella.

1. Voit lisätä määritteitä koskevia ehtoja aiemmin luotuihin sääntöihin ja alisääntöihin tai lisätä ne uuteen sääntöön.

1. Kumoa muutokset ja tee muutokset uudelleen segmenttiä rakennettaessa.

Yllä olevassa esimerkissä on kuvattu segmentointiominaisuudet. Olemme määrittäneet segmentin asiakkaille, jotka ovat ostaneet vähintään 500 dollarilla tuotteita verkosta *ja* ovat kiinnostuneita ohjelmistokehityksessä.

## <a name="create-a-new-segment-with-segment-builder"></a>Luo uusi segmentti segmentin muodostintyökalun avulla

1. Valitse **Segmentit**.

1. Valitse **Uusi** > **Luo oma**. Segmentin muodostin -sivulla voit määrittää tai luoda sääntöjä. Sääntö koostuu yhdestä tai useasta asiakasjoukon määrittävästä ehdosta.

   > [!NOTE]
   > Jos ympäristöt perustuvat yritystileihin, valitse **Uusi** > **Tilisegmentti** tai **Yhteyshenkilösegmentti (esiversio)** luotavan segmentin tyypin perusteella. Jos [tilihierarkia](relationships.md#set-up-account-hierarchies) on määritetty ja haluat luoda sääntöjä, joiden avulla suodatetaan pois tietoja ali- ja ylätason suhteen perusteella, valitse **Käytetäänkö hierarkiaa? (esiversio)**, valitse hierarkia ja valitse sitten **Käytä**.
   >
   > :::image type="content" source="media/segment_acct_hierarchy.png" alt-text="Segmentin valinnan tilihierarkian ruutu.":::

1. Valitse nimettömän segmentin vieressä oleva **Muokkaa tietoja** -kohta. Anna segmentille nimi ja päivitä segmentin ehdotetun **Tulos-entiteetin nimi**. Vaihtoehtoisesti voit lisätä segmenttiin kuvauksen ja [tunnisteet](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/segments_edit_details.png" alt-text="Muokkaa tietoja -valintaikkuna.":::

1. Valitse **Sääntö1**-osassa sen entiteetin määrite, jonka mukaan haluat suodattaa asiakkaat. Määritteiden valintatapoja on kaksi:
   - Tarkista **Lisää sääntöön** -ruudun käytettävissä olevien entiteettien ja määritteiden luettelo ja valitse lisättävän määritteen vieressä oleva **+**-kuvake. Valitse, haluatko lisätä määritteen aiemmin luotuun sääntöön vai luoda sen avulla uuden säännön.
   - Kun kirjoitat määritteen nimen sääntöosaan, näet vastaavat ehdotukset.

1. Valitse operaattorit, jotka määrittävät ehdon vastaavat arvot. Määritteen arvo voi olla jokin neljästä tietotyypistä: numeerinen, merkkijono, päivämäärä tai totuusarvo. Määritteen tietotyypistä riippuen eri operaattorit ovat käytettävissä määrittämään ehdon.

1. Valitse **Lisää ehto**, jos haluat lisätä sääntöön lisää ehtoja. Jos haluat luoda säännön nykyisen säännön alle, valitse **Lisää alisääntö**.

1. Jos sääntö käyttää muita entiteettejä kuin *Asiakas*-entiteettiä (tai B2B:n *ContactProfile*-entiteettiä), yhdistä valittu entiteetti yhdistettyyn asiakasentiteettiin valitsemalla **Määritä suhdepolku**. Jos mahdollisia suhdepolkuja on vain yksi, järjestelmä valitsee sen automaattisesti. Eri [suhdepolut](relationships.md#relationship-paths) voivat tuottaa erilaisia tuloksia. Jokaisella säännöllä voi olla oma suhdepolkunsa.

   :::image type="content" source="media/relationship-path.png" alt-text="Mahdollinen suhdepolku luotaessa sääntöä, joka perustuu yhdistettyyn asiakasentiteettiin yhdistettyyn entiteettiin.":::

1. Jos säännössä on useita ehtoja, voit valita, mikä looginen operaattori yhdistää ne.  
   - **AND**-operaattori: Kaikkien ehtojen on täytyttävä, jotta segmenttiin voi lisätä tietueen. Käytä tätä vaihtoehtoa, kun määrität ehtoja eri entiteeteille.
   - **OR**-operaattori: Jommankumman ehdon on täytyttävä, jotta segmenttiin voi lisätä tietueen. Käytä tätä vaihtoehtoa, kun määrität useita ehtoja samalle entiteetille.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Sääntö, jossa on kaksi AND-ehtoa.":::

   OR-operaattoria käytettäessä kaikkien ehtojen on perustuttava suhdepolkuun sisältyviin entiteetteihin.

1. Voit luoda useita asiakastietueiden joukkoja luomalla eri sääntöjä. Yhdistää ryhmiä, niin niihin sisällytetään liiketoimintatapausta varten tarvittavat asiakkaat. Jos entiteettiä ei voi sisällyttää sääntöön määritetyn suhdepolun vuoksi, siitä valittavia määrityksiä varten on luotava uusi sääntö.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Lisää uusi sääntö segmenttiin ja valitse määritetty operaattori.":::

   1. Valitse **Lisää sääntö**.
   1. Valitse jokin joukko-operaattoreista: **Unioni**, **Leikkaus** tai **Paitsi**.

      - **Liitos** yhdistää kaksi ryhmää.
      - **Leikkaa** asettaa kaksi ryhmää päällekkäin. Vain molemmille ryhmille *yhteiset* tiedot säilyvät yhdistetyssä ryhmässä.
      - **Lukuun ottamatta** yhdistää kaksi ryhmää. Vain ne ryhmän A tiedot, jotka *eivät ole yhteisiä* ryhmän B tietojen kanssa, säilytetään.

1. Tulosentiteetti sisältää automaattisesti kaikki määritettyjä suodattimia vastaavat asiakasprofiilien määritteet. Kun B2B-tilanteessa käytetään *ContactProfile*-entiteettiä, lisätään automaattisesti tilitunnus. Jos segmentti perustuu muihin entiteetteihin kuin *Asiakas*-entiteettiin tai jos haluat sisällyttää enemmän *ContactProfile*-määritteitä, valitse **Projektin määritteet**, jos haluat lisätä näistä entiteeteistä enemmän määritteitä tulosentiteettiin.
 
   Esimerkki: Segmentti perustuu entiteettiin, joka sisältää ostotietoja, jotka liittyvät *Asiakas*-entiteettiin. Segmentti etsii Espanjasta kaikkia asiakkaita, jotka ostivat tavaroita kuluvana vuonna. Voit liittää määritteitä, kuten tuotteiden hinnan, tai ostopäivämäärän kaikkiin tulosentiteetin vastaaviin asiakastietueisiin. Nämä tiedot voivat olla hyödyllisiä analysoitaessa kokonaismenojen kausittaisia korrelaatioita.

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Esimerkki sivuruudussa valituista ennustetuista määritteistä, jotka lisätään tulosentiteettiin.":::
 
   Yhteyshenkilöiden projisoituja määritteitä sisältäviin yritystileihin perustuvan segmentin esimerkkitulos voi olla seuraavan kaltainen:

   |Tunnus  |Asiakkaan nimi  |Tuotto  |Yhteyshenkilön nimi  | Yhteyshenkilön rooli|
   |---------|---------|---------|---------|---|
   |10021     | Contoso | 100 000 | [Abbie Moss, Ruth Soto]  | [Toimitusjohtaja, hankintapäällikkö]

   > [!NOTE]
   > - **Projektin määritteet** toimivat vain entiteeteille, joilla on yksi moneen -suhde *Asiakas*- tai *ContactProfile*-entiteettiin. Esimerkiksi yhdellä asiakkaalla voi olla useita tilauksia.
   > - Jos määrite, jonka haluat projisoida, on enemmän kuin yhden siirtymisen päässä *Asiakas*- tai *ContactProfile*-entiteetistä suhteen määrityksen perusteella, tätä määritettä tulee käyttää tekemäsi segmenttikyselyn jokaisessa säännössä.
   > - Jos määrite, jonka haluat projisoida, on vain yhden siirtymisen päässä *Asiakas*- tai *ContactProfile*-entiteetistä, tämän määritteen ei tarvitse olla mukana tekemäsi segmenttikyselyn jokaisessa säännössä.
   > - **Projisoidut määritteet** otetaan huomioon, kun joukko-operaattoreita käytetään.

1. Luo segmentti valitsemalla **Suorita**. Valitse **Tallenna**, jos haluat pitää nykyisen määrityksen ja suorittaa segmentin myöhemmin. **Segmentit**-sivu avautuu.

### <a name="segment-builder-tips"></a>Segmentin muodostinvinkit

Kun luot segmenttiä käyttämällä segmentin muodostinta, muista seuraavat vinkit:

- Segmentin muodostin ei ehdota entiteeteille kelvollisia arvoja, kun operaattorit määritetään ehdoille. Voit tarkastella käytettävissä olevia arvoja siirtymällä kohtaan **Tieto** > **Entiteetit** ja lataamalla entiteettitiedot.
- Päivämääriin perustuvien ehtojen avulla voit siirtyä kiinteän päivämäärän ja liukuvan päivämäärävälin välillä.
- Jos segmentille on useita sääntöjä, muokattavan säännön vieressä on pystysuuntainen sininen viiva.
- Voit siirtää sääntöjä ja ehtoja muihin kohtiin segmentin määrityksessä. Valitse säännön tai ehdon vierestä kolme pystysuuntaista pistettä (&vellip;) ja valitse, miten ja mihin se siirtää.
- Komentopalkin **Kumoa**- ja **Tee uudelleen** -ohjausobjektien avulla voit perua muutoksia.
- Kun olet luonut segmentin, joidenkin segmenttien avulla voit [seurata segmentin käyttöä](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Seuraavat vaiheet

[Vie segmentti](export-destinations.md) ja tutustu [asiakaskorttien integrointiin](customer-card-add-in.md), jotta voit käyttää segmenttejä muissa sovelluksissa.

[!INCLUDE [footer-include](includes/footer-banner.md)]
