---
title: Mittareiden luominen ja hallinta
description: Määritä yrityksen suorituskyvyn analysoimiseen ja kuvaamiseen liittyvät mittarit.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654728"
---
# <a name="define-and-manage-measures"></a>Mittojen määrittäminen ja hallinta

Mittareiden avulla saat lisätietoja asiakkaan toiminnasta ja liiketoiminnan suorituskyvystä noutamalla olennaisia arvoja [yhdistetyistä profiileista](data-unification.md). Esimerkissä yritys haluaa lisätietoja yksittäisen asiakkaan ostohistoriasta *asiakaskohtaisen kokonaiskulutuksen* avulla. Vaihtoehtoisesti halutaan tietoja koko yrityksen koostetusta myyntituotosta *yrityksen kokonaismyyntiä* kuvaavan mittarin avulla.  

Mittarit luodaan käyttämällä mittareiden luontiohjelmaa. Se on tietojen kysely-ympäristö, jossa on useita operaattoreita ja yksinkertaiset yhdistämisvalinnat. Sen avulla voi suodattaa tietoja, ryhmitellä tuloksia, havaita [entiteettisuhteiden polkuja](relationships.md) ja esikatsella tulosta.

Käytä mittarin luontiohjelmaa liiketoiminta-aktiviteettien suunnittelemisessa tekemällä kyselyjä asiakastiedoista ja poimimalla tietoja. Esimerkiksi *asiakaskohtainen kokonaiskulutus*- ja *asiakaskohtainen kokonaispalautus* -mittarin luominen auttaa tunnistamaan asiakkaat, jotka ostavat paljon, mutta tekevät myös paljon palautuksia. Voit [luoda segmentin](segments.md) seuraavien parhaiden toimintojen suorittamiseksi. 

## <a name="create-a-measure"></a>Luo mittari

Tässä osassa kerrotaan uuden mittarin luomisesta alusta alkaen. Voit luoda mittarin ja tietomääritteet tietoentiteeteistä, joille on määritetty suhde yhteyden muodostamiseksi asiakasentiteettiin. 

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Mittarit**.

1. Valitse **Uusi**.

1. Valitse **Muokkaa nimeä** ja anna mittarille **nimi**. 
   > [!NOTE]
   > Jos uudella mittarin määrityksellä on vain kaksi kenttää, esimerkiksi CustomerID ja yksi laskelma, tulos lisätään uudeksi sarakkeeksi järjestelmän luomaan entiteettiin nimeltä Customer_Measure. Voit myös nähdä mittarin arvon yhdistetyssä asiakasprofiilissa. Muut mittarit luovat omat entiteetit.

1. Valitse määritysalueessa koostetoiminto avattavasta **Valitse toiminto** -valikosta. Koostetoimintoja ovat seuraavat: 
   - **Sum**
   - **Keskiarvo**
   - **Määrä**
   - **Yksilöllinen määrä**
   - **Enintään**
   - **Min**
   - **Ensimmäinen**: ottaa tietueen ensimmäisen arvon
   - **Viimeinen**: ottaa tietueeseen lisätyn viimeisen arvon

   :::image type="content" source="media/measure-operators.png" alt-text="Mittarin laskelmien operaattorit.":::

1. Valitse **Lisää määrite**, jos haluat valita tälle mittarille luotavat tiedot.
   
   1. Valitse **Määritteet**-välilehti. 
   1. Tietoentiteetti: valitse entiteetti, joka sisältää mitattavan määritteen. 
   1. Tietomäärite: valitse määrite, jota haluat käyttää koostetoiminnossa mittarin laskemiseksi. Voit valita vain yhden määritteen kerrallaan.
   1. Voit valita myös tietomääritteen olemassa olevasta mittarista valitsemalla **Mittarit**-välilehden. Vaihtoehtoisesti voit hakea mitä tahansa entiteetin tai mittarin nimeä. 
   1. Valitse **Lisää**, jos haluat lisätä valitun määritteen mittariin.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Valitse laskelmissa käytettävä määrite.":::

1. Jos haluat luoda monimutkaisia mittareita, voit lisätä määritteiden määrää tai käyttää mittarin toiminnossa matemaattisia operaattoreita.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Luo monimutkainen mittari, jossa on matemaattisia operaattoreita.":::

1. Jos haluat lisätä suodattimia, valitse määritysalueen **Suodatin**-kohta. 
  
   1. Valitse **Suodattimet**-ruudun **Lisää määrite** -osassa määrite, jota haluat käyttää suodattimien luomisessa.
   1. Aseta suodatinoperaattorit, jos haluat määrittää jokaiselle valitulle määritteelle suodattimen.
   1. Valitse **Käytä**, jos haluat lisätä suodattimet mittariin.

1. Jos haluat lisätä dimensioita, valitse määritysalueen **Dimensio**-kohta. Dimensiot näkyvät mittarin tulosentiteetin sarakkeina.
   1. Valitse **Muokkaa dimensioita**, jos haluat lisätä tietomääritteitä, joiden mukaan mittarin arvot ryhmitellään. Tämä voi olla esimerkiksi kaupunki tai sukupuoli. Oletusarvoisesti valitaan *CustomerID*-dimensio *asiakastason mittareiden* luomiseksi. Voit poistaa oletusdimension, jos haluat luoda *yritystason mittareita*.
   1. Valitse **Valmis**, jos haluat lisätä dimensiot mittariin.

1. Jos yhdistetyn tietoentiteetin ja *asiakas*-entiteetin välillä on useita polkuja, tulee valita jokin määritetyistä [entiteettisuhteen poluista](relationships.md). Mittarin tulokset voivat vaihdella valitun polun mukaan. 
   1. Valitse **Tietomääritteet** ja valitse sitten entiteettipolku, jota käytetään mittarin tunnistamisessa. Jos *Asiakas*-entiteetissä on vain yksi polku, ohjausobjektia ei näy.
   1. Ota valinta käyttöön valitsemalla **Valmis**. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Valitse mittarin entiteettipolku.":::

1. Jos haluat lisätä mittarille lisää laskelmia, valitse **Uusi laskelma**. Uusissa laskelmissa voi käyttää vain saman entiteettipolun entiteettejä. Lisälaskelmat näkyvät uusina sarakkeina mittarin tulosentiteetissä.

1. Valitse laskelman **...**-kohta, jos haluat **monistaa**, **uudelleennimetä** tai **poistaa** laskelman mittarista.

1. **Esiversio**-alueessa on näkyvissä mittarin tulosentiteetin tietorakenne, myös suodattimet ja dimensiot. Esiversio readoi dynaamisesti määrityksen muutoksiin.

1. Laske määritetyn mittarin tulokset valitsemalla **Suorita**. Valitse **Tallenna ja sulje**, jos haluat pitää nykyisen määrityksen ja suorittaa mittarin myöhemmin.

1. Siirry **Mittarit**-kohtaan, jos haluat nähdä juuri luodun mittarin luettelossa.

## <a name="manage-your-measures"></a>Hallitse mittoja

Kun [mittari on luotu](#create-a-measure), **Mittarit**-sivulla näkyy mittariluettelo.

Saat tietoja mittarityypistä, tekijästä, luontipäivästä ja tilasta. Jos valitset mittarin luettelosta, voit esikatsella tulostetta ja ladata .CSV-tiedoston.

Jos haluat päivittää kaikki mitat samalla kertaa, valitse **Päivitä kaikki** valitsematta tiettyä mittaa.

> [!div class="mx-imgBorder"]
> ![Yksittäisten mittojen hallintatoiminnot](media/measure-actions.png "Yksittäisten mittojen hallintatoiminnot")

Valitse seuraaville vaihtoehdoille mittari luettelosta:

- Voit tarkastella tietoja valitsemalla mitan nimen.
- **Muokkaa** mitan määritystä.
- **Päivitä** mittari uusimpien tietojen perusteella.
- **Nimeä uudelleen** mitta.
- **Poista** mitta.
- **Aktivoi** tai **poista aktivointi**. Passiivisia mittareita ei päivitetä [aikataulutetun päivityksen](system.md#schedule-tab) aikana.

> [!TIP]
> Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types). Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies). Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja. Kun työn jossakin tehtävissä on valittu **Näytä tiedot**, saat lisätietoja: käsittelyajan, viimeisimmän käsittelypäivämäärän sekä kaikki tehtävään liitetyt virheet ja varoitukset.

## <a name="next-step"></a>Seuraava vaihe

Voit luoda [asiakassegmentin](segments.md) olemassa olevien mittareiden avulla.


[!INCLUDE[footer-include](../includes/footer-banner.md)]