---
title: Mittareiden luominen ja mukauttaminen
description: Määritä asiakkaaseen liittyvät mittarit tiettyjen liiketoiminta-alueiden suorituskyvyn analysointia ja kuvailua varten.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405622"
---
# <a name="define-and-manage-measures"></a>Mittojen määrittäminen ja hallinta

**Mittarit** edustavat tunnuslukuja, jotka kuvaavat tiettyjen liiketoiminta-alueiden suorituskykyä ja tilaa. Mittareiden luonti käyttäjäryhmän merkityksellisissä tiedoissa tapahtuu intuitiivisesti kyselyn muodostimessa, jossa ei tarvitse käyttää koodia eikä vahvistaa mittareita manuaalisesti. Voit seurata liiketoiminnan mittareita **aloitussivulla**, katsoa tiettyjen asiakkaiden mittareita **asiakaskortin** avulla ja käyttää mittareita asiakassegmenttien määrittämisessä **Segmentit**-sivulla.

## <a name="create-a-measure"></a>Luo mittari

Tässä osassa luodaan mittari alusta alkaen. Voit luoda mittareita useiden asiakasentiteetin kautta yhdistettyjen tietolähteiden tiedoista. Käytössä on jotakin [palvelurajoituksia](service-limits.md).

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Mittarit**.

2. Valitse **Uusi mittari**.

3. Valitse mittarin **tyyppi** seuraavasti:

   - **Asiakasmäärite**: Asiakkaan yksittäinen kenttä, joka näyttää asiakkaan pisteet, arvon tai tilan. Asiakkaan määritteet luodaan määritteinä uudessa järjestelmän luomassa entiteetissä, jonka nimi on **Customer_Measure**.

   - **Asiakasmittari**: Tietoja asiakkaan toiminnasta eriteltynä valittujen dimensioiden mukaan. Jokaiselle mittarille luodaan uusi entiteetti. Se sisältää mahdollisesti useita tietueita asiakasta kohti.

   - **Liiketoiminnan mittari**: Seuraa liiketoiminnan suorituskykyä ja tilaa. Liiketoiminnan mittareilla voi olla kaksi eri tulostetta: numeerinen tuloste, joka osoittaa **aloitussivun** tai uuden entiteetin, joka löytyy **Entiteetit**-sivulta.

4. Anna **nimi** ja valinnainen **näyttönimi** ja valitse **Seuraava**.

5. Valitse **Entiteetit**-osassa ensin entiteetti avattavasta luettelosta. Tässä vaiheessa sinun on päätettävä, tarvitaanko mittarin määrityksessä useampia entiteettejä.

   > [!div class="mx-imgBorder"]
   > ![Mittarin määritys](media/measure-definition.png "Mittarin määritys")

   Jos lisäät entiteettejä, valitse **Lisää entiteetti** ja valitse mittarissa käytettävät entiteetit.

   > [!NOTE]
   > Voit valita vain entiteettejä, joilla on suhde aloittavaan entiteettiin. Lisätietoja suhteiden määrittämisestä on kohdassa [Suhteet](relationships.md).

6. Vaihtoehtoisesti voit määrittää muuttujia. Valitse **Muuttujat**-osassa **Uusi muuttuja**.

   Muuttujat ovat laskelmia, jotka tehdään jokaiselle valitulle tietueelle. Voit esimerkiksi laskea yhteen myyntipisteen verkkomyynnin jokaiselle asiakastietueelle.

7. Anna muuttujalle **nimi**.

8. Valitse **Lauseke**-alueessa kenttä, jonka aloittaa laskelman.

9. Kirjoita lauseke **Lauseke**-alueeseen ja valitse lisää laskelmaan lisättäviä kenttiä.

   > [!NOTE]
   > Tällä hetkellä tuetaan vain aritmeettisia lausekkeita. Lisäksi muuttujan laskelma ei tue muiden [entiteettipolkujen](relationships.md) entiteettejä.

10. Valitse **Valmis**.

11. **Mittarin määritys** -osassa määritetään, miten valitut entiteetit ja lasketut muuttujat yhdistetään uudessa mittarientiteetissä tai määritteessä.

12. Valitse **Uusi dimensio**. Dimension voi ajatella olevan *ryhmittelytoiminto*. Mittarientiteetin tai -määritteen tietotuloste ryhmitellään kaikkien määritettyjen dimensioiden mukaan.

    > [!div class="mx-imgBorder"]
    > ![Valitse yhdistämisjakso](media/measures-businessreport-measure-definition2.png "Valitse yhdistämisjakso")

    Valitse tai syötä seuraavat tiedot dimension määrityksen osaksi:

    - **Entiteetti**: Jos määrität mittarientiteetin, sisällytä vähintään yksi määrite. Jos määrität mittarimääritteen, se sisältää oletusarvoisesti vain yhden määritteen. Tämä valinta koskee sellaisen entiteetin valitsemista, joka sisältää kyseisen määritteen.
    - **Kenttä**: Valitse tietty määrite, joka sisällytetään joko mittarientiteettiin tai -määritteeseen.
    - **Säilö**: Määritä, haluatko yhdistää tiedot päivittäin, kuukausittain vai vuosittain. Se on pakollinen valinta vain, jos olet valinnut päivämäärätyyppimääritteen.
    - **Kohteena**: Määrittää uuden kentän nimen.
    - **Näyttönimi**: Määrittää kentän näyttönimen.

    > [!NOTE]
    > Liiketoiminnan mittari tallennetaan yksinumeroisena entiteettinä. Se näkyy **aloitussivulla**, jos et lisää muita dimensioita mittariin. Kun olet lisännyt dimensioita, mittari *ei* näy **aloitussivulla**.

13. Vaihtoehtoisesti voit lisätä yhdistämistoimintoja. Kaikki luodut yhdistämiset luovat uuden arvon mittarientiteettiin tai -määritteeseen. Tuettuja yhdistämistoimintoja ovat seuraavat: **Vähintään**, **Enintään**, **Keskiarvo**, **Mediaani**, **Summa**, **Yksilöllinen määrä**, **Ensimmäinen** (poimii dimension arvon ensimmäisen tietueen) ja **Viimeinen** (poimii viimeisen dimension arvoon lisätyn tietueen).

14. Valitse **Tallenna**, kun haluat ottaa muutokset käyttöön mittarissa.

## <a name="manage-your-measures"></a>Hallitse mittoja

Sen jälkeen kun vähintään yksi mittari on luotu, **Mittarit**-sivulla on mittariluettelo.

Löydät tietoja mittarin tyypistä, tekijästä, luontipäivämäärästä ja -ajasta, edellisestä muokkauspäivämäärästä ja -ajasta, tilasta (mittarin tila voi olla Aktiivinen, Passiivinen tai Epäonnistunut) ja edellisestä päivityspäivämäärästä ja -ajasta. Kun valitset mitan luettelosta, näet esikatselun sen tulosteesta.

Jos haluat päivittää kaikki mitat samalla kertaa, valitse **Päivitä kaikki** valitsematta tiettyä mittaa.

> [!div class="mx-imgBorder"]
> ![Yksittäisten mittojen hallintatoiminnot](media/measure-actions.png "Yksittäisten mittojen hallintatoiminnot")

Voit vaihtoehtoisesti valita mitan luettelosta ja suorittaa jonkin seuraavista toiminnoista:

- Voit tarkastella tietoja valitsemalla mitan nimen.
- **Muokkaa** mitan määritystä.
- **Nimeä uudelleen** mitta.
- **Poista** mitta.
- Valitse kolme pistettä (...) ja sitten **Päivitä**, kun haluat aloittaa mitan päivitysprosessin.
- Valitse kolme pistettä (...) ja sitten **Lataa** saadaksesi mitan .CSV-tiedoston.

> [!TIP]
> Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types). Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies). Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja. Kun työn jossakin tehtävissä on valittu **Näytä tiedot**, saat lisätietoja: käsittelyajan, viimeisimmän käsittelypäivämäärän sekä kaikki tehtävään liitetyt virheet ja varoitukset.

## <a name="next-step"></a>Seuraava vaihe

Voit luoda ensimmäisen asiakassegmentin **Segmentit**-sivulla olemassa olevien mittareiden avulla. Lisätietoja on kohdassa [Segmentit](segments.md).
