---
title: Luo segmenttejä segmentin muodostintyökalun avulla
description: Luo asiakassegmenttejä ja ryhmittele ne eri määritteiden perusteella.
ms.date: 03/25/2022
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
ms.openlocfilehash: c8e9e4976ade36c1c3c4f688a667b329bfde6e3e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646283"
---
# <a name="create-segments"></a>Segmenttien luominen

Määritä yhdistetyn asiakasentiteetin ja siihen liittyvien entiteettien monimutkaiset suodattimet. Kukin segmentti luo käsittelyn jälkeen joukon asiakastietueita, joita voit viedä ja joihin voit tehdä toimintoja. Segmenttejä hallitaan **Segmentit**-sivulla. Voit [luoda uusia segmenttejä](#create-a-new-segment) segmentin muodostimen avulla tai [luoda pikasegmenttejä](#quick-segments) sovelluksen muista alueista.

> [!TIP]
> - Pikasegmenttejä tuetaan vain **yksittäisten asiakkaiden** ympäristöissä.
> - Segmentit, jotka perustuvat **yksittäisiin asiakkaisiin**, sisältävät automaattisesti käytössä olevat segmentin jäsenten yhteystiedot. Ympäristöissä, jotka perustuvat **yritystileihin**, segmentit perustuvat asiakkaisiin (yrityksiin tai tytäryrityksiin). Jos haluat sisällyttää yhteyshenkilötiedot segmenttiin, käytä **Projektin määritteet** -toimintoa segmentin muodostimessa. Varmista, että yhteyshenkilön tietolähteet on [yhdistetty semanttisesti ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping)-entiteettiin.

## <a name="segment-builder"></a>Segmentin muodostin

Seuraavassa kuvassa on kuvattu segmentin muodostimen eri osia. Se näyttää segmentin, joka johtaa asiakasryhmään. Asiakkaat tilasivat tuotteita tietyllä aikavälillä ja keräsivät palkkiopisteitä tai käyttivät tietyn rahasumman.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Segmentin muodostimen elementit." lightbox="media/segment-builder-overview.png":::

1. Järjestä segmentti sääntöjen ja alisääntöjen avulla. Kukin sääntö tai alisääntö koostuu ehdoista. Ehtojen yhdistäminen loogisiin operaattoreihin

1. Valitse sääntöä koskeva [suhdepolku](relationships.md) entiteettien välillä. Suhdepolku määrittää, mitä määritteitä ehdossa voi käyttää.

1. Hallitse sääntöjä ja alisääntöjä. Muuta säännön sijaintia tai poista se.

1. Ehtojen lisääminen ja oikean kerrosteisuustason muodostaminen alisääntöjen avulla.

1. Käytä määritettyjä toimintoja yhdistettyihin sääntöihin.

1. Lisää määriteruudussa käytettävissä olevat entiteettimääritteet tai luo määritteeseen perustuvia ehtoja. Ruudussa näkyy valitun säännön käytettävissä olevien entiteettien ja määritteiden luettelo valitun suhdepolun perusteella.

1. Voit lisätä määritteitä koskevia ehtoja aiemmin luotuihin sääntöihin ja alisääntöihin tai lisätä ne uuteen sääntöön.

1. Kumoa muutokset ja tee muutokset uudelleen segmenttiä rakennettaessa.

Yllä olevassa esimerkissä on kuvattu segmentointiominaisuudet. Olemme määrittäneet segmentin asiakkaille, jotka ovat ostaneet vähintään 500 dollarilla tuotteita verkosta *ja* ovat kiinnostuneita ohjelmistokehityksessä.

## <a name="create-a-new-segment"></a>Luo uusi segmentti

Uuden segmentin voi luoda useilla tavoilla. Tässä osassa kuvataan, miten oma segmentti voidaan rakentaa alusta. Voit myös luoda *pikasegmentin* olemassa olevien entiteettien perusteella tai käyttää koneoppimismalleja *segmenttiehdotusten* saamiseksi. Lisätietoja löytyy kohdasta [Segmenttien yleiskatsaus](segments.md).

Luodessasi segmenttiä voit tallentaa luonnoksen. Luonnosvaiheessa segmentti tallennetaan passiiviseksi segmentiksi. Kun olet suorittanut segmentin määrityksen loppuun, aktivoi segmentti suorittamalla se. Vaihtoehtoisesti segmentti voidaan **aktivoida** **Kaikki segmentit** -sivulla.

1. Siirry **Segmentit**-sivulle.

1. Valitse **Uusi** > **Luo oma**.

1. Segmentin muodostin -sivulla voit määrittää tai luoda sääntöjä. Sääntö koostuu yhdestä tai useasta asiakasjoukon määrittävästä ehdosta.

1. Valitse **Sääntö1**-osassa sen entiteetin määrite, jonka mukaan haluat suodattaa asiakkaat. Määritteiden valintatapoja on kaksi:
   - Tarkista **Lisää sääntöön** -ruudun käytettävissä olevien entiteettien ja määritteiden luettelo ja valitse lisättävän määritteen vieressä oleva **+**-kuvake. Valitse, haluatko lisätä määritteen aiemmin luotuun sääntöön vai luoda sen avulla uuden säännön.
   - Kun kirjoitat määritteen nimen sääntöosaan, näet vastaavat ehdotukset.

1. Valitse operaattorit, jotka määrittävät ehdon vastaavat arvot. Määritteen arvo voi olla jokin neljästä tietotyypistä: numeerinen, merkkijono, päivämäärä tai totuusarvo. Määritteen tietotyypistä riippuen eri operaattorit ovat käytettävissä määrittämään ehdon. Jos segmentillä on yritystilejä, käytettävissä on kaksi erityistä operaattoria, jotka voivat sisällyttää mahdollisia hierarkkisia tietoja käytettyjen tilien välillä. Käytä *seuraavan lapsi*- ja *seuraavan vanhempi* -operaattoreita liittyvien tilien sisällyttämiseen.

1. Valitse **Lisää ehto**, jos haluat lisätä sääntöön lisää ehtoja. Jos haluat luoda säännön nykyisen säännön alle, valitse **Lisää alisääntö**.

1. Jos sääntö käyttää muita entiteettejä kuin *Asiakas*-entiteettiä, suhdepolku on määritettävä. Suhdepolkua tarvitaan ilmoittamaan järjestelmälle, millä suhteilla yhdistetty asiakasentiteetti on käytettävissä. Valitse **Määritä suhdepolku**, jos haluat yhdistää valitun entiteetin yhdistettyyn asiakasentiteettiin. Jos mahdollisia suhdepolkuja on vain yksi, järjestelmä valitsee sen automaattisesti. Eri suhdepolut voivat tuottaa erilaisia tuloksia. Jokaisella säännöllä voi olla oma suhdepolkunsa.

   :::image type="content" source="media/relationship-path.png" alt-text="Mahdollinen suhdepolku luotaessa sääntöä, joka perustuu yhdistettyyn asiakasentiteettiin yhdistettyyn entiteettiin.":::

   Esimerkiksi näyttökuvan *eCommerce_eCommercePurchases*-entiteetillä on neljä mahdollisuutta yhdistyä *Asiakas*-entiteettiin:
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Asiakas
   - eCommerce_eCommercePurchases > Asiakas
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Asiakas
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Asiakas Kun valitset viimeisen vaihtoehdon, voimme sisällyttää säännön ehtoihin määritteitä kaikista luettelossa mainituista entiteeteistä. Tuloksia on todennäköisesti vähemmän, koska vastaavien asiakastietueiden on oltava osa kaikkia entiteettejä. Tässä esimerkissä heidän on ostettava tavaroita sähköisen kaupankäynnin (*eCommerce_eCommercePurchases*) kautta myyntipisteestä (*POS_posPurchases*) ja osallistuttava kanta-asiakasohjelmaamme (*loyaltyScheme_loyCustomers*). Kun valitset toisen vaihtoehdon, voimme valita vain määritteitä *eCommerce_eCommercePurchases*- ja *Asiakas*-entiteeteistä. Tuloksena on todennäköisesti enemmän asiakasprofiileja.

1. Jos säännössä on useita ehtoja, voit valita, mikä looginen operaattori yhdistää ne.  
   - **AND**-operaattori: Kaikkien ehtojen on täytyttävä, jotta segmenttiin voi lisätä tietueen. Tämä vaihtoehto on hyödyllinen, kun määrität ehtoja eri entiteeteille.
   - **OR**-operaattori: Jommankumman ehdon on täytyttävä, jotta segmenttiin voi lisätä tietueen. Tämä vaihtoehto on hyödyllinen, kun määrität useita ehtoja samalle entiteetille.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Sääntö, jossa on kaksi AND-ehtoa.":::

   OR-operaattoria käytettäessä kaikkien ehtojen on perustuttava suhdepolkuun sisältyviin entiteetteihin.

   - Voit luoda useita sääntöjä eri asiakastietueiden joukkoja varten. Voit yhdistää ryhmiä niin, että niihin sisällytetään liiketoimintatapausta varten tarvittavat asiakkaat. Luo uusi sääntö valitsemalla **Lisää sääntö**. Jos entiteettiä ei voi sisällyttää sääntöön määritetyn suhdepolun vuoksi, siitä valittavia määrityksiä varten on luotava uusi sääntö.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Lisää uusi sääntö segmenttiin ja valitse määritetty operaattori.":::

   - Valitse jokin joukko-operaattoreista: **Unioni**, **Leikkaus** tai **Paitsi**.

      - **Liitos** yhdistää kaksi ryhmää.
      - **Leikkaa** asettaa kaksi ryhmää päällekkäin. Vain molemmille ryhmille *yhteiset* tiedot säilyvät yhdistetyssä ryhmässä.
      - **Lukuun ottamatta** yhdistää kaksi ryhmää. Vain ne ryhmän A tiedot, jotka *eivät ole yhteisiä* ryhmän B tietojen kanssa, säilytetään.

1. Segmentit luovat oletusarvoisesti tulosentiteetin, joka sisältää kaikki määritettyjä suodattimia vastaavat asiakasprofiilien määritteet. Jos segmentti perustuu muihin entiteetteihin kuin *Asiakas*-entiteettiin, voit lisätä näistä entiteeteistä lisämääritteitä tulosentiteettiin. Valitse **Projekti**-määritteet, jos haluat valita tulosentiteettiin liitettävät määritteet.

   > [!IMPORTANT]
   > Jos segmentti perustuu yritystileihin, segmenttiin on sisällytettävä jokaisesta *ContactProfile*-entiteetin tilistä vähintään yhden yhteyshenkilön tiedot, jotta segmentti voidaan aktivoida tai viedä kohteisiin, jotka vaativat yhteyshenkilöiden tietoja. Lisätietoja *ContactProfile*-entiteetistä on kohdassa [Semanttiset yhdistämismääritykset](semantic-mappings.md).
   > Yhteyshenkilöiden projisoituja määritteitä sisältäviin yritystileihin perustuvan segmentin esimerkkitulos voi olla seuraavankaltainen:
   >
   > |Tunnus  |Asiakkaan nimi  |Tuotto  |Yhteyshenkilön nimi  | Yhteyshenkilön rooli|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100 000 | [Abbie Moss, Ruth Soto]  | [Toimitusjohtaja, hankintapäällikkö]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Esimerkki sivuruudussa valituista ennustetuista määritteistä, jotka lisätään tulosentiteettiin.":::
  
   Esimerkki: Segmentti perustuu entiteettiin, joka sisältää ostotietoja, jotka liittyvät *Asiakas*-entiteettiin. Segmentti etsii Espanjasta kaikkia asiakkaita, jotka ostivat tavaroita kuluvana vuonna. Voit liittää määritteitä, kuten tuotteiden hinnan, tai ostopäivämäärän kaikkiin tulosentiteetin vastaaviin asiakastietueisiin. Nämä tiedot voivat olla hyödyllisiä analysoitaessa kokonaismenojen kausittaisia korrelaatioita.

   > [!NOTE]
   > - **Projektin määritteet** toimivat vain entiteeteille, joilla on yksi moneen -suhde asiakasentiteettiin. Esimerkiksi yhdellä asiakkaalla voi olla useita tilauksia.
   > - Jos määrite, jonka haluat projisoida, on enemmän kuin yhden siirtymisen päässä *Asiakas*-entiteetistä suhteen määrityksen perusteella, tätä määritettä tulee käyttää tekemäsi segmenttikyselyn jokaisessa säännössä.
   > - Jos määrite, jonka haluat projisoida, on vain yhden siirtymisen päässä *Asiakas*-entiteetistä, tämän määritteen ei tarvitse olla mukana tekemäsi segmenttikyselyn jokaisessa säännössä.
   > - **Projisoidut määritteet** otetaan huomioon, kun joukko-operaattoreita käytetään.

1. Valitse nimettömän segmentin vieressä oleva **Muokkaa tietoja** -kohta. Anna segmentille nimi ja päivitä segmentin ehdotetun **Tulos-entiteetin nimi**. Vaihtoehtoisesti voit lisätä segmenttiin kuvauksen ja [tunnisteet](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/segments_edit_details.png" alt-text="Muokkaa tietoja -valintaikkuna.":::

1. Valitse **Suorita**, jotta voit tallentaa segmentin, aktivoida sen ja aloittaa segmentin käsittelyn perustuen kaikkiin sääntöihin ja ehtoihin. Muussa tapauksessa se tallentuu passiiviseksi segmentiksi.

1. Valitse **Palaa segmentteihin**, jos haluat siirtyä takaisin **Segmentit**-sivulle.

1. Segmentti luodaan oletusarvoisesti dynaamisena segmenttinä. Niinpä kyseinen segmentti päivitetään järjestelmän päivityksen yhteydessä. [Automaattinen päivitys voidaan pysäyttää](segments.md#manage-existing-segments) valitsemalla valitussa segmentissä **Tee staattinen** -vaihtoehto. Staattiset segmentit voidaan [päivittää manuaalisesti](segments.md#refresh-segments) koska tahansa.

> [!TIP]
> - Segmentin muodostin ei ehdota entiteeteille kelvollisia arvoja, kun operaattorit määritetään ehdoille. Voit tarkastella käytettävissä olevia arvoja siirtymällä kohtaan **Tieto** > **Entiteetit** ja lataamalla entiteettitiedot.
> - Päivämääriin perustuvien ehtojen avulla voit siirtyä kiinteän päivämäärän ja liukuvan päivämäärävälin välillä.
> - Jos segmentille on useita sääntöjä, muokattavan säännön vieressä on pystysuuntainen sininen viiva.
> - Voit siirtää sääntöjä ja ehtoja muihin kohtiin segmentin määrityksessä. Valitse säännön tai ehdon vierestä [...] ja valitse, miten ja mihin se siirretään.
> - Komentopalkin **Kumoa**- ja **Tee uudelleen** -ohjausobjektien avulla voit perua muutoksia.

## <a name="quick-segments"></a>Pikasegmentit

Pikasegmenttien avulla voidaan nopeasti luoda yksinkertaisia segmenttejä yhdellä operaattorilla, jotta merkitykselliset tiedot saadaan nopeammin.

1. Valitse **Segmentit**-sivulla **Uusi** > **Luo kohteesta**.
   - Valitse **Profiilit**-vaihtoehto, jos haluat muodostaa segmentin, joka perustuu *yhdistettyyn asiakas* entiteettiin.
   - Valitse **Mittarit**-vaihtoehto rakentaaksesi segmentin aiemmin luotujen mittareiden perusteella.
   - Valitse **Analytiikka**-asetus, jos haluat luoda segmentin, joka on luotu käyttämällä joko **Ennusteet**-tai **Mukautetut mallit** -ominaisuuden avulla luotuja tuloskohteita.

2. Valitse **Uusi pikasegmentti** -valintaikkunasta määrite avattavasta **Kenttä**-valikosta.

3. Järjestelmä antaa enemmän tietoja, jotka auttavat luomaan parempia asiakassegmenttejä.
   - Luokkakentille näytetään 10 parasta asiakasmäärää. Valitse **Arvo** ja valitse sitten **Tarkista**.
   - Jos määrite on numeerinen, järjestelmä näyttää, mikä määrite kuuluu mihinkin asiakasprosenttipisteeseen. Valitse **Operaattori** ja **Arvo** ja valitse sitten **Tarkista**.

4. Järjestelmä näyttää **arvioidun segmentin koon**. Voit määrittää, luodaanko määritetty segmentti vai avataanko sen ensin, jolloin voit määrittää toisen segmentin koon.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nopean segmentin nimi ja arvioi.":::

5. Anna segmentille **nimi** ja **tulosentiteetin nimi**. Vaihtoehtoisesti voit lisätä [tunnisteita](work-with-tags-columns.md#manage-tags).

6. Luo segmentti valitsemalla **Tallenna**.

7. Kun segmentin käsittely on valmis, voit tarkistaa sen kuten minkä tahansa luodun segmentin.

## <a name="next-steps"></a>Seuraavat vaiheet

[Vie segmentti](export-destinations.md) ja tutustu [asiakaskorttien integrointiin](customer-card-add-in.md), jotta voit käyttää segmenttejä muissa sovelluksissa.

[!INCLUDE [footer-include](includes/footer-banner.md)]
