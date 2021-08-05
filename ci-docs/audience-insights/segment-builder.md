---
title: Segmenttien luonti ja hallinta
description: Luo asiakassegmenttejä ja ryhmittele ne eri määritteiden perusteella.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a19661abea42618ef1848110c05d635a925c68f
ms.sourcegitcommit: c45b094072cbe3fbf61d1e9e7d220e1f29ffebd0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/29/2021
ms.locfileid: "6685458"
---
# <a name="create-and-manage-segments"></a>Segmenttien luonti ja hallinta

> [!IMPORTANT]
> Segmentin luontikokemukseen on tehty useita muutoksia syyskuussa 2021: 
> - Segmentin muodostaja näyttää hieman erilaiselta uudelleen tyyliteltyjen elementtien ja parannetun käyttäjätyönkulun kanssa.
> - Uudet datetime-operaattorit ja parannettu päivämäärävalitsin ovat käytössä segmentin muodostimessa.
> - Voit lisätä tai poistaa ehtoja ja sääntöjä segmenteistä. 
> - Sisäkkäisiä sääntöjä, jotka alkavat OR-ehdolla, tulee saataville. Et enää tarvitse AND-ehtoa uloimmassa kerroksessa.
> - Sivuruutu määritteiden valitsemista varten on jatkuvasti käytettävissä.
> - Entiteettisuhteiden polkujen valitseminen.
> Jos haluat kokeilla uutta segmentinmuodostinta, lähetä sähköpostiviesti, jonka aihe on "Pyyntö uuden segmentinmuodostimen ottamiseksi käyttöön" osoitteeseen cihelp [at] microsoft.com. Sisällytä organisaatiosi nimi ja hiekkalaatikkoympäristön tunnus.

Määritä yhdistetyn asiakasentiteetin ja siihen liittyvien entiteettien monimutkaiset suodattimet. Kukin segmentti luo käsittelyn jälkeen joukon asiakastietueita, joita voit viedä ja joihin voit tehdä toimintoja. Segmenttejä hallitaan **Segmentit**-sivulla. 

Seuraava esimerkki kuvaa segmentointiominaisuutta. Olemme määritelleet segmentin asiakkaille, jotka tilasivat vähintään 500 dollarilla tavaraa viimeisen 90 päivän aikana *ja* jotka olivat mukana eskaloidussa asiakaspalvelupuhelussa.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Näyttökuva segmentin muodostimen käyttöliittymästä, jossa on kaksi ryhmää, jotka määrittävät asiakassegmentin.":::

## <a name="create-a-new-segment"></a>Luo uusi segmentti

Uuden segmentin voi luoda useilla tavoilla. Tässä osassa kuvataan, miten *tyhjä segmentti* luodaan alusta alkaen. Voit myös luoda *pikasegmentin* olemassa olevien entiteettien perusteella tai käyttää koneoppimismalleja *segmenttiehdotusten* saamiseksi. Lisätietoja: [Yleiskatsaus segmentteihin](segments.md).

Luodessasi segmenttiä voit tallentaa luonnoksen. Se tallentuu passiiviseksi segmenttiksi, eikä sitä voi aktivoida valmiiksi kelvollisen määrityksen avulla.

1. Siirry **Segmentit**-sivulle.

1. Valitse **Uusi** > **Tyhjä segmentti**.

1. Valitse **Uusi segmentti** -ruudussa segmentin tyyppi:

   - **Dynaamiset segmentit** [päivittyvät](segments.md#refresh-segments) toistuvan aikataulun mukaisesti.
   - **Staattiset segmentit** suoritetaan kerran, kun ne luodaan.

1. Anna segmentille **Tulosentiteetin nimi**. Vaihtoehtoisesti voit antaa näyttönimen ja kuvauksen, joiden avulla segmentin voi tunnistaa.

1. Kun valitset **Seuraava**, näyttöön avautuu **Segmentin muodostin** -sivu, jolla voit määrittää ryhmän. Ryhmä on joukko asiakkaita.

1. Valitse sen määritteen sisältävä entiteetti, jonka mukaan segmentointi tehdään.

1. Valitse segmentointiperusteen määrite. Tällä määritteellä voi olla jokin neljästä arvotyypistä: numeerinen, merkkijono, päivämäärä tai totuusarvo.

1. Valitse operaattori ja arvo valitulle määritteelle.

   > [!div class="mx-imgBorder"]
   > ![Mukautettu ryhmäsuodatin.](media/customer-group-numbers.png "Asiakkaan ryhmäsuodatin")

   |Määrä |Määritelmä  |
   |---------|---------|
   |1     |Entity          |
   |2     |Määrite          |
   |3    |Operaattori         |
   |4    |Arvo         |

   1. Jos haluat lisätä ryhmään ehtoja, voit käyttää seuraavaa kahta loogista operaattoria:

      - **JA**-operaattori: Molempien ehtojen on täytyttävä segmentointiprosessin aikana. Tämä vaihtoehto on hyödyllinen, kun määrität ehtoja eri entiteeteille.

      - **TAI**-operaattori: Jommankumman ehdoista on täytyttävä segmentointiprosessin aikana. Tämä vaihtoehto on hyödyllinen, kun määrität useita ehtoja samalle entiteetille.

      > [!div class="mx-imgBorder"]
      > ![TAI-operaattori, jossa jommankumman ehdoista on täytyttävä.](media/segmentation-either-condition.png "TAI-operaattori, jossa jommankumman ehdoista on täytyttävä")

      Tällä hetkellä on mahdollista upottaa **TAI**-operaattoria **JA**-operaattorin sisään, mutta ei toisin päin.

   1. Kukin ryhmä vastaa asiakasjoukkoa. Voit yhdistää ryhmiä niin, että niihin sisällytetään liiketoimintatapausta varten tarvittavat asiakkaat.    
   Valitse **Lisää ryhmä**.

      > [!div class="mx-imgBorder"]
      > ![Asiakasryhmä - lisää ryhmä.](media/customer-group-add-group.png "Asiakasryhmä - lisää ryhmä")

   1. Valitse jokin joukko-operaattoreista: **Unioni**, **Leikkaus** tai **Paitsi**.

   > [!div class="mx-imgBorder"]
   > ![Asiakasryhmä - lisää liitos.](media/customer-group-union.png "Asiakasryhmä - lisää liitos")

   - **Liitos** yhdistää kaksi ryhmää.

   - **Leikkaa** asettaa kaksi ryhmää päällekkäin. Vain molemmille ryhmille *yhteiset* tiedot säilytetään yhdistetyssä ryhmässä.

   - **Lukuun ottamatta** yhdistää kaksi ryhmää. Vain ryhmän A tiedot, jotka *eivät ole yhteisiä* ryhmän B tietojen kanssa, säilytetään.

1. Jos entiteetti on yhdistetty yhdistettyyn asiakaskohteeseen [suhteen](relationships.md) kautta , sinun täytyy määrittää suhdepolku, jotta voit luoda kelvollisen segmentin. Lisää entiteetit suhdepolusta, kunnes voit valita **Asiakas : CustomerInsights** -entiteetin avattavasta luettelosta. Valitse sitten jokaiselle vaiheelle **Kaikki tietueet**.

   > [!div class="mx-imgBorder"]
   > ![Suhdepolku segmentin luonnin aikana.](media/segments-multiple-relationships.png "Suhdepolku segmentin luonnin aikana")

1. Segmentit luovat oletusarvoisesti tulosentiteetin, joka sisältää kaikki määritettyjä suodattimia vastaavat asiakasprofiilien määritteet. Jos segmentti perustuu muihin entiteetteihin kuin *Asiakas*-entiteettiin, voit lisätä näistä entiteeteistä lisämääritteitä tulosentiteettiin. Valitse **Projekti**-määritteet, jos haluat valita tulosentiteettiin liitettävät määritteet.  
  
   Esimerkki: Segmentti perustuu entiteettiin, joka sisältää *Asiakas*-entiteettiin liittyviä asiakasaktiviteettitietoja. Segmentti etsii kaikkia asiakkaita, jotka ovat soittaneet tukipalveluun viimeisen 60 päivän aikana. Voit liittää puhelun keston ja puheluiden määrän kaikkiin tulosentiteetin vastaaviin asiakastietueisiin. Nämä tiedot voivat olla hyödyllisiä, jos haluat lähettää sähköpostia, jossa on hyödyllisiä linkkejä online-ohjeartikkeleihin ja usein kysyttyihin kysymyksiin asiakkaille, jotka ovat soittaneet usein.

   > [!NOTE]
   > - Projisoidut määritteet koskevat vain entiteettejä, joilla on yksi moneen -suhde asiakasentiteettiin. Esimerkiksi yhdellä asiakkaalla voi olla useita tilauksia.
   > - Määritteitä voidaan projisoida vain entiteetistä, jota käytetään sen segmenttikyselyn jokaisessa ryhmässä, jota rakennetaan.
   > - Projisoidut määritteet otetaan huomioon, kun joukko-operaattoreita käytetään.

1. Tallenna segmentti valitsemalla **Tallenna**. Segmentti tallennetaan ja käsitellään, jos kaikki vaatimukset on vahvistettu. Muussa tapauksessa se tallennetaan luonnoksena.

1. Valitse **Palaa segmentteihin**, jos haluat siirtyä takaisin **Segmentit**-sivulle.



## <a name="quick-segments"></a>Pikasegmentit

Pikasegmenttien avulla voidaan nopeasti luoda yksinkertaisia segmenttejä yhdellä operaattorilla, jotta merkitykselliset tiedot saadaan nopeammin.

1. Valitse **Segmentit**-sivulla **Uusi** > **Luo kohteesta**.

   - Valitse **Profiilit**-vaihtoehto, jos haluat muodostaa segmentin, joka perustuu *yhdistettyyn asiakas* entiteettiin.
   - Valitse **Mittarit**-vaihtoehto rakentaaksesi segmentin aiemmin luotujen mittareiden perusteella.
   - Valitse **Analytiikka**-asetus, jos haluat luoda segmentin, joka on luotu käyttämällä joko **Ennusteet**-tai **Mukautetut mallit** -ominaisuuden avulla luotuja tuloskohteita.

2. Valitse **Uusi pikasegmentti** -valintaikkunasta määrite avattavasta **Kenttä**-valikosta.

3. Järjestelmä tarjoaa lisätietoja, joiden avulla voit aiempaa helpommin luoda asiakkaille segmenttejä.
   - Luokkakentille näytetään 10 parasta asiakasmäärää. Valitse **Arvo** ja valitse sitten **Tarkista**.

   - Jos määrite on numeerinen, järjestelmä näyttää, mikä määrite kuuluu mihinkin asiakasprosenttipisteeseen. Valitse **Operaattori** ja **Arvo** ja valitse sitten **Tarkista**.

4. Järjestelmä näyttää **arvioidun segmentin koon**. Voit määrittää, luodaanko määritetty segmentti vai avataanko sen ensin, jolloin voit määrittää toisen segmentin koon.

    > [!div class="mx-imgBorder"]
    > ![Nopean segmentin nimi ja arvioi.](media/quick-segment-name.png "Nopean segmentin nimi ja arvioi")

5. Anna segmentille **nimi**. Vaihtoehtoisesti voit antaa **näyttönimen**.

6. Luo segmentti valitsemalla **Tallenna**.

7. Kun segmentin käsittely on valmis, voit tarkistaa sen kuten minkä tahansa luodun segmentin.

## <a name="next-steps"></a>Seuraavat vaiheet

[Vie segmentti](export-destinations.md) ja tutustu [asiakaskorttiin](customer-card-add-in.md) ja [yhdistimiin](export-power-bi.md), jotta saat asiakastason tietoja.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
