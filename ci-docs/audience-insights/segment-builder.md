---
title: Luo segmenttejä segmentin muodostintyökalun avulla
description: Luo asiakassegmenttejä ja ryhmittele ne eri määritteiden perusteella.
ms.date: 09/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f7bd0e7e581305836287bd503ef273a2d556bff
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494492"
---
# <a name="create-segments"></a>Segmenttien luominen

Määritä yhdistetyn asiakasentiteetin ja siihen liittyvien entiteettien monimutkaiset suodattimet. Kukin segmentti luo käsittelyn jälkeen joukon asiakastietueita, joita voit viedä ja joihin voit tehdä toimintoja. Segmenttejä hallitaan **Segmentit**-sivulla. Voit [luoda uusia segmenttejä](#create-a-new-segment) [segmentin muodostimen](#segment-builder) avulla tai [luoda pikasegmenttejä](#quick-segments) sovelluksen muista alueista.

## <a name="segment-builder"></a>Segmentin muodostin

Seuraavassa kuvassa on kuvattu segmentin muodostimen eri osia. Se näyttää segmentin, joka johtaa asiakasryhmään. Asiakkaat tilasivat tavaroita tietyllä aikavälillä ja keräsivät useita palkintopisteitä tai käyttivät tietyn summan rahaa. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Segmentin muodostimen elementit." lightbox="media/segment-builder-overview.png":::

1 - Järjestä segmentti sääntöjen ja alisääntöjen avulla. Kukin sääntö tai alisääntö koostuu ehdoista. Ehtojen yhdistäminen loogisiin operaattoreihin

2 - Valitse sääntöä koskeva [suhdepolku](relationships.md) entiteettien välillä. Suhdepolku määrittää, mitä määritteitä ehdossa voi käyttää.

3 - Hallitse sääntöjä ja alisääntöjä. Muuta säännön sijaintia tai poista se.

4 - Ehtojen lisääminen ja oikean kerrosteisuustason muodostaminen alisääntöjen avulla.

5 - Käytä määritettyjä toimintoja yhdistettyihin sääntöihin.

6 - Lisää määriteruudussa käytettävissä olevat entiteettimääritteet tai luo määritteeseen perustuvia ehtoja. Ruudussa näkyy valitun säännön käytettävissä olevien entiteettien ja määritteiden luettelo valitun suhdepolun perusteella.

7 - Voit lisätä määritteitä koskevia ehtoja aiemmin luotuihin sääntöihin ja alisääntöihin tai lisätä ne uuteen sääntöön.

8 - Kumoa muutokset ja tee muutokset uudelleen segmenttiä rakennettaessa.

Yllä olevassa esimerkissä on kuvattu segmentointiominaisuudet. Olemme määrittäneet segmentin asiakkaille, jotka ovat ostaneet vähintään 500 dollarilla tuotteita verkosta *ja* ovat kiinnostuneita ohjelmistokehityksessä.

## <a name="create-a-new-segment"></a>Luo uusi segmentti

Uuden segmentin voi luoda useilla tavoilla. Tässä osassa kuvataan, miten oma segmentti voidaan rakentaa alusta. Voit myös luoda *pikasegmentin* olemassa olevien entiteettien perusteella tai käyttää koneoppimismalleja *segmenttiehdotusten* saamiseksi. Lisätietoja: [Yleiskatsaus segmentteihin](segments.md).

Luodessasi segmenttiä voit tallentaa luonnoksen. Se tallentuu passiiviseksi segmenttiksi, eikä sitä voi aktivoida valmiiksi kelvollisen määrityksen avulla.

1. Siirry **Segmentit**-sivulle.

1. Valitse **Uusi** > **Luo oma**.

1. Määritä ensimmäinen sääntö segmentin muodostimen sivulle. Sääntö koostuu yhdestä tai useasta ehdosta ja määrittää asiakasjoukon.

1. Valitse **Sääntö1**-osassa entiteetin määrite, jonka mukaan haluat suodattaa asiakkaita. Määritteiden valintatapoja on kaksi: 
   - Tarkista **Lisää sääntöön** -ruudun käytettävissä olevien entiteettien ja määritteiden luettelo ja valitse lisättävän määritteen vieressä oleva **+**-kuvake. Valitse, haluatko lisätä määritteen aiemmin luotuun sääntöön vai luoda sen avulla uuden säännön.
   - Kun kirjoitat määritteen nimen sääntöosaan, näet vastaavat ehdotukset.

1. Valitse operaattorit, jotka määrittävät ehdon vastaavat arvot. Määritteen arvo voi olla jokin neljästä tietotyypistä: numeerinen, merkkijono, päivämäärä tai totuusarvo. Määritteen tietotyypistä riippuen eri operaattorit ovat käytettävissä määrittämään ehdon. 

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

   1. Voit luoda useita sääntöjä eri asiakastietueiden joukkoja varten. Voit yhdistää ryhmiä niin, että niihin sisällytetään liiketoimintatapausta varten tarvittavat asiakkaat. Luo uusi sääntö valitsemalla **Lisää sääntö**. Jos et erityisesti voi lisätä sääntöön eikä entiteettiä määritetyn suhdepolun vuoksi, sinun täytyy luoda uusi sääntö, jotta voit valita määritteet sen muodostamiseksi.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Lisää uusi sääntö segmenttiin ja valitse määritetty operaattori.":::

   1. Valitse jokin joukko-operaattoreista: **Unioni**, **Leikkaus** tai **Paitsi**.

   - **Liitos** yhdistää kaksi ryhmää.

   - **Leikkaa** asettaa kaksi ryhmää päällekkäin. Vain molemmille ryhmille *yhteiset* tiedot säilytetään yhdistetyssä ryhmässä.

   - **Lukuun ottamatta** yhdistää kaksi ryhmää. Vain ryhmän A tiedot, jotka *eivät ole yhteisiä* ryhmän B tietojen kanssa, säilytetään.

1. Segmentit luovat oletusarvoisesti tulosentiteetin, joka sisältää kaikki määritettyjä suodattimia vastaavat asiakasprofiilien määritteet. Jos segmentti perustuu muihin entiteetteihin kuin *Asiakas*-entiteettiin, voit lisätä näistä entiteeteistä lisämääritteitä tulosentiteettiin. Valitse **Projekti**-määritteet, jos haluat valita tulosentiteettiin liitettävät määritteet.  

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Esimerkki sivuruudussa valituista ennustetuista määritteistä, jotka lisätään tulosentiteettiin.":::
  
   Esimerkki: Segmentti perustuu entiteettiin, joka sisältää ostotietoja, jotka liittyvät *Asiakas*-entiteettiin. Segmentti etsii Espanjasta kaikkia asiakkaita, jotka ostivat tavaroita kuluvana vuonna. Voit liittää määritteitä, kuten tuotteiden hinnan, tai ostopäivämäärän kaikkiin tulosentiteetin vastaaviin asiakastietueisiin. Nämä tiedot voivat olla hyödyllisiä analysoitaessa kokonaismenojen kausittaisia korrelaatioita.

   > [!NOTE]
   > - Projisoidut määritteet koskevat vain entiteettejä, joilla on yksi moneen -suhde asiakasentiteettiin. Esimerkiksi yhdellä asiakkaalla voi olla useita tilauksia.
   > - Voit käyttää vain entiteetin projektimääritteitä, joita käytetään jokaisessa rakennettamassasi segmenttikyselyn säännössä.
   > - Projisoidut määritteet otetaan huomioon, kun joukko-operaattoreita käytetään.

1. Ennen kuin tallennat ja suoritat segmentin, valitse segmentin nimen vierestä **Muokkaa tietoja**. Anna segmentille nimi ja päivitä segmentin ehdotetun **Tulos-entiteetin nimi**. Voit myös lisätä segmenttiin kuvauksen.

1. Valitse **Suorita**, jos haluat tallentaa ja käsitellä segmentin, jos kaikki vaatimukset on tarkistettu. Muussa tapauksessa se tallentuu passiivisena segmenttiluonnoksena.

1. Valitse **Palaa segmentteihin**, jos haluat siirtyä takaisin **Segmentit**-sivulle.

> [!TIP]
> - Segmentin muodostin ei ehdota entiteeteille kelvollisia arvoja, kun operaattorit määritetään ehdoille. Voit tarkastella käytettävissä olevia arvoja siirtymällä kohtaan **Tieto** > **Entiteetit** ja lataamalla entiteettitiedot.
> - Päivämääriin perustuvien ehtojen avulla voit siirtyä kiinteän päivämäärän ja liukuvan päivämäärävälin välillä.
> - Jos segmentille on useita sääntöjä, muokattavan säännön ympärillä on sininen palkki.
> - Voit siirtää sääntöjä ja ehtoja muihin kohtiin segmentin määrityksessä. Valitse säännön tai ehdon vierestä [...] ja valitse, miten ja mihin se siirretään.
> - Komentopalkin **Kumoa**- ja **Tee uudelleen** -ohjausobjektien avulla voit peruuttaa muutokset.

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

    > [!div class="mx-imgBorder"]
    > ![Nopean segmentin nimi ja arvioi.](media/quick-segment-name.png "Nopean segmentin nimi ja arvioi")

5. Anna segmentille **nimi**. Vaihtoehtoisesti voit antaa **näyttönimen**.

6. Luo segmentti valitsemalla **Tallenna**.

7. Kun segmentin käsittely on valmis, voit tarkistaa sen kuten minkä tahansa luodun segmentin.

## <a name="next-steps"></a>Seuraavat vaiheet

[Vie segmentti](export-destinations.md) ja tutustu [asiakaskorttien integrointiin](customer-card-add-in.md), jotta voit käyttää segmenttejä muissa sovelluksissa.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
