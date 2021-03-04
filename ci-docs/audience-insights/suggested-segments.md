---
title: Koneoppimisen tehostamat ehdotetut segmentit
description: Koneoppimisen avulla voit etsiä uusia ja mielenkiintoisia segmenttejä asiakasmääritteiden perusteella.
ms.date: 02/01/2021
ms.reviewer: jimsonc
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 54655d57f4f0f723b497fe47891fd397ccb9dbf4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268222"
---
# <a name="suggested-segments-preview"></a>Ehdotetut segmentit (esiversio)

Tutustu asiakkaiden kiinnostaviin segmentteihin tekoälymallin avulla. Tämä koneoppimisen tehostama ominaisuus ehdottaa segmenttejä mittareiden tai asiakasmääritteiden perusteella. Se voi auttaa parantamaan KPI-lukuja tai ymmärtämään määritteiden vaikutusta muiden määritteiden yhteydessä. 

> [!NOTE]
> Ehdotetut segmentit -ominaisuus käyttää automaattisia menetelmiä tietojen arvioimiseen ja ennusteiden luomiseen näiden tietojen perusteella. Tämän vuoksi sitä voidaan käyttää valmiudet käyttää profilointimenetelmänä, koska kyseinen ehto on määritetty yleisessä tietosuoja-asetuksessa (GDPR). Jos tätä ominaisuutta käytetään tietojen käsittelemiseen, siihen sovelletaan GDPR-määrityksiä tai muita lakeja ja säännöksiä. Olet vastuussa siitä, että Dynamics 365 Customer Insightsin käyttäminen, myös tämän ominaisuuden käyttäminen, on kaikkien lakien ja säädösten mukaista. Näihin kuuluvat yksityisyyteen, henkilökohtaisiin tietoihin, biometrisiin tietoihin, tietosuojaan ja viestintäsalaisuuteen liittyvät lait.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Customer Insightsin ehdotettujen segmenttien sivu, jossa näkyvät ehdotuksen tiedot sivupaneelissa.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segmentit, joita on ehdotettu KPI-lukujen parantamista varten

Käyttäjäryhmän merkityksellisten tietojen käyttäjällä on todennäköisesti useita [luotuja mittareita](measures.md), jotka auttavat tunnuslukujen (KPI) seuraamisessa. On tärkeää ymmärtää, miten tietyt määritteet vaikuttavat tähän KPI-lukuun, jotta voidaan luoda segmenttejä ja suorittaa erittäin kohdistettuja kampanjoita.   
Voit esimerkiksi seurata *TotalSpendPerCustomer*-mittaria. Yritys haluaa tämän luvun kasvavan. Jos mittari valitaan ensisijaiseksi määritteeksi, voit valita määritteet, joiden vaikutusta haluat arvioida. Valitaan määritteiksi *jäsenyystaso*, *jäsenyyden kausi* ja *toiminta*. Customer Insights voi sitten ehdottaa segmenttiä, joka kertoo mittariin eniten vaikuttavan tekijän. Esimerkiksi *TotalSpendPerCustomer*-mittariin eniten vaikuttavia tekijöitä ovat *kirjanpitäjät*, jotka ovat *kultatason* jäseniä ja jotka ovat olleet yrityksessä *vähintään viisi vuotta*. Saat jokaisesta ehdotuksesta arvion segmentin koosta. Tietojen avulla voit luoda kampanjoita kohdeyleisöille.

## <a name="understand-what-influences-a-customer-attribute"></a>Tietoja siitä, mikä vaikuttaa asiakasmääritteeseen

Voit valita ensisijaiseksi määritteeksi mittarin sijaan asiakasmääritteen. Tekoälymalli luo valittujen vaikuttavien määritteiden perusteella ehdotusten sarjan. Siinä näytetään, miten valitut määritteet vaikuttavat ensisijaiseen määritteeseen.   
Voit esimerkiksi valita ensisijaiseksi määritteeksi *Palkkio-ohjelmien jäsen (kyllä/ei)* -arvon. *Asiakkuuden kesto*-, *Toiminta*- ja *Tukipalvelupyyntöjen määrä* -kohdat määritetään muiksi vaikuttaviksi määritteiksi. Tekoälymalli voi ehdottaa segmenttejä, jotka osoittavat erityisesti yli kaksi vuotta asiakkuutta omaavien IT-alan ammattilaisten olevan palkkio-ohjelman jäseniä. Toinen ehdotus voi korostaa, että yli vuoden asiakkuuden keston ja vähemmän kuin kolme tukipalvelupyyntöä omaavat kirjanpitäjät ovat palkkio-ohjelman jäseniä. 

## <a name="artificial-intelligence-usage"></a>Tekoälyn käyttö

Jos käytössä on ensisijainen määrite ja vaikuttavat määritteet, päätöspuun algoritmi ehdottaa kiinnostavia segmenttejä. Ehdotukset perustuvat tekoälyn algoritmin valitsemaan sääntöihin tai malleihin. Vain segmentit, jotka eroavat merkittävästi keskimääräisestä perusjoukosta, näkyvät ehdotuksina. Vertailu keskimääräiseen perusjoukkoon perustuu valittuun mittariin tai ensisijaiseen määritteeseen.

### <a name="responsible-ai"></a>Tekoälyn vastuullinen käyttö

Ehdotettujen segmenttien avulla voit valita määritteitä uusien segmenttien luontia ja valittujen tietojen käsittelyä varten. Kun valitset määritteitä, mukaan lukien arkaluontoisia määritteitä, kuten rotu, seksuaalinen suuntautuminen tai sukupuoli, varmista, että voit käsittellä näitä tietoja. Olet vastuussa siitä, että organisaatiossa sovellettavia lakeja ja organisaation periaatteita ja tietosuojakäytäntöjä noudatetaan.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Erilaisetn tulokset ensisijaisille määritteille, joilla on luokitteluarvot ja numeeriset arvot

Segmenttiehdotukset ovat erilaisia, jos ensisijaisena määritteenä käytetään numeerista tai luokittelevaan määritettä. Luokittelevan määritteen arvot sisältävät vähintään kaksi luokkaa tai tyyppiä. Numeerinen määrite sisältää kvantitatiivisia tietoja, ja siihen liittyy mittayksikkö.

Kun ensisijainen määrite on esimerkiksi *vuositulot* tai *jäsenyyskausi*, järjestelmä ehdottaa segmenttejä, joilla on korkeampi tai matalampi numeerisen määritteen keskimääräinen arvo verrattuna kaikkiin asiakkaisiin.

Jos ensisijaisena määritteenä on luokitteleva määrite, kuten *asiakastyytyväisyys*, tuloksena saadaan ehdotettuja segmenttejä, joilla on korkeampi tai matalampi prosenttiosuus tiettyyn luokkaan kuuluvia asiakkaita verrattuna samaan luokkaan kuuluviin kaikkiin asiakkaisiin. Esimerkiksi *asiakastyytyväisyys* valitaan ensisijaiseksi määritteeksi. Se sisältää kolme luokkaa (*Matala*, *Keskitaso* ja *Korkea*). Kullekin luokalle ehdotetaan segmenttejä, joissa tähän luokkaan kuuluvien asiakkaiden prosenttiosuus on merkittävästi korkeampi tai matalampi kuin kaikkien samaan luokkaan kuuluvien asiakkaiden osuus. Jos tyytyväisyys on *korkea* 22 prosentilla kaikista asiakkaista, kyseiseen luokkaan ehdotetaan vain asiakkaita, joiden *korkean* tyytyväisyyden tason asiakasosuus on huomattavasti korkeampi tai matalampi kuin 22 prosenttia. Vastaavasti kaikille muille luokille (*Matala* ja *Keskitaso*) ehdotetaan segmenttejä, jos ne ovat tilastollisesti merkittäviä.

> [!NOTE]
> Tällä hetkellä tuetaan vain ensisijaisia luokittelevia määritteitä, joissa on enintään 10 luokkaa. Jos haluat tarkastella segmenttiehdotuksia, jotka perustuvat yli 10 luokkaa sisältävään ensisijaiseen määritteeseen, on suositeltavaa ryhmitellä joitakin luokkia niin, että luokkien määrä on 10 tai alle. Tämä rajoitus koskee vain ensisijaisia määritteitä. Vaikuttavissa luokittelevissa määritteissä tuetaan tällä hetkellä enintään 100 luokkaa.

## <a name="generate-suggested-segments"></a>Ehdotettujen segmenttien luominen

1. Valitse **Segmentit**.

1. Valitse **Ehdotukset (esiversio)** -välilehti.

1. Valitse **Hanki uusia ehdotuksia** ohjatun käyttökokemuksen käynnistämiseksi.

1. Valitse ensisijaiseksi määritteeksi asiakasmäärite ja valitse sitten **Seuraava**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Ensisijaisen määritteen valitseminen ehdotettujen segmenttien ehdotuksia varten.":::

1. Valitse vaikuttavat määritteet ja valitse sitten **Tallenna**.
   
   > [!TIP]
   > Useiden vaikuttavien määritteiden valitseminen parantaa mahdollisuuksia arvioida, miten ne vaikuttavat ensisijaiseen määritteeseen. Älä lisää määritteitä, jotka eivät vaikuta ensisijaiseen määritteeseen. Jos esimerkiksi kaikki asiakkaat ovat tietystä maasta, älä *maa*-määritettä, koska se ei vaikuta tulokseen.

1. Valittujen asiakasprofiilien ja määritteiden määrästä riippuen voi kestää muutaman minuutin, ennen kuin valitut määritteet käsitellään. 

## <a name="view-details-of-a-suggested-segment"></a>Ehdotetun segmentin tietojen tarkasteleminen

Kun tekoälymalli on luonut ehdotukset, ne löytyvät kohdasta **Segmentit** > **Ehdotukset (esikatselu)**.
 
Tarkastele ehdotuksen tietoja valitsemalla ehdotettu segmentti. Tiedot voivat olla kuten keskiarvon ja segmentin jäsenten määrän vertailu. Voit myös tarkastella määritteiden arvoja tai sääntöjä, joiden mukaan tekoälymalli oppi ehdottamaan valittua segmenttiä.

## <a name="save-a-suggestion-as-a-segment"></a>Ehdotuksen tallentaminen segmenttinä

1. Siirry kohtaan **Segmentit** > **Ehdotukset (esiversio)**.

1. Valitse segmentti, jonka haluat tallentaa. 

1. Valitse sivuruudussa **Tallenna segmenttinä**. 

1. Kun segmentti on tallennettu, se näkyy **Kaikki segmentit** -välilehden segmenttiluettelossa. Se voidaan nyt [päivittää tai poistaa tai sitä voidaan muokata, kuten mitä tahansa segmenttiä](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Ehdotusjoukon päivittäminen tai muokkaaminen

1. Siirry kohtaan **Segmentit** > **Ehdotukset (esiversio)**.

1. Valitse **Päivitä ehdotukset**, jos haluat päivittää ehdotukset ja säilyttää määritetyt määritteet. Tai valitse **Muokkaa määritteitä**, jos haluat muokata määritettyjä määritteitä. Järjestelmä käyttää tekoälymallia uudelleen, luo segmenttiehdotuksia uusimpien tietojen perusteella ja korvaa nykyiset ehdotukset.

## <a name="limitations"></a>Rajoitukset

1. Arvioitu segmentin koon ristiriita: Jos valitset tyhjiä arvoja sisältävän ensisijaisen määritteen, valinta voi vaikuttaa segmentin ehdotusten arvioituun segmentin kokoon. Kun tallennat tällaisen segmentin, todellinen segmentin koko voi olla erilainen kuin alkuperäinen arvio.
 
2. Totuusarvotyyppiset ensisijaiset määritteet eivät toimi. Tällä hetkellä ensisijaisina määritteinä tuetaan vain merkkijono- ja numerotyyppisiä tietoja.

3. Ehdotetut segmentit eivät ole riittävän erilaisia. Muista, että valitut määritteet ja näiden määritteiden arvojen jakautuminen vaikuttavat tuloksiin. Voit muuttaa vaikuttavia määritteitä tai jopa ensisijaista määritettä, jos haluat saada erilaisia tuloksia.



[!INCLUDE[footer-include](../includes/footer-banner.md)]