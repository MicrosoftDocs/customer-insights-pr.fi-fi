---
title: Aktiviteettiin perustuvat ehdotetut mittarit (esiversio)
description: Koneoppimisen avulla voit etsiä uusia ja mielenkiintoisia segmenttejä asiakasmääritteiden perusteella.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170953"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Aktiviteettiin perustuvat ehdotetut mittarit (esiversio)

Tutustu asiakkaiden kiinnostaviin segmentteihin tekoälymallin avulla. Tämä koneoppimisen tehostama ominaisuus ehdottaa segmenttejä mittareiden tai asiakasmääritteiden perusteella. Se voi auttaa parantamaan KPI-tunnuslukuja tai ymmärtämään määritteiden vaikutusta muiden määritteiden yhteydessä.

> [!NOTE]
> Ehdotettujen segmenttien toiminto käyttää automaattisia tietoja arvioidakseen tietoja ja tehdäkseen ennusteita näiden tietojen perusteella. Siksi sitä voidaan käyttää profilointimenetelmänä, koska tämä termi on määritetty yleisessä tietosuoja-asetuksessa (”tietosuoja-asetus”). Jos tätä ominaisuutta käytetään tietojen käsittelemiseen, siihen sovelletaan GDPR-määrityksiä tai muita lakeja ja säännöksiä. Olet vastuussa siitä, että Dynamics 365 Customer Insightsin käyttäminen, myös tämän ominaisuuden käyttäminen, on kaikkien lakien ja säädösten mukaista. Näihin kuuluvat yksityisyyteen, henkilökohtaisiin tietoihin, biometrisiin tietoihin, tietosuojaan ja viestintäsalaisuuteen liittyvät lait.

:::image type="content" source="media/suggested-segments.png" alt-text="Ehdotettujen segmenttien sivulla näkyy ehdotuksen tiedot sivuruudussa":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segmentit, joita on ehdotettu KPI-lukujen parantamista varten

Jos käytät KPI-tunnuslukujen [seuraamiseen luotuja toimenpiteitä](measures.md), voit tarkastella vaikutuksia tunnuslukuihin luomalla segmenttejä. Tietojen avulla voit suorittaa erittäin kohdennetun kampanjan.

Voit esimerkiksi seurata *TotalSpendPerCustomer*-mittaria. Yritys haluaa tämän luvun kasvavan. Jos mittari valitaan ensisijaiseksi määritteeksi, voit valita määritteet, joiden vaikutusta haluat arvioida. Valitaan määritteiksi *jäsenyystaso*, *jäsenyyden kausi* ja *toiminta*. Customer Insights voi sitten ehdottaa segmenttiä, joka kertoo mittariin eniten vaikuttavan tekijän. Esimerkiksi *TotalSpendPerCustomer*-mittariin eniten vaikuttavia tekijöitä ovat *kirjanpitäjät*, jotka ovat *kultatason* jäseniä ja jotka ovat olleet yrityksessä *vähintään viisi vuotta*. Saat jokaisesta ehdotuksesta arvion segmentin koosta. Tietojen avulla voit luoda kampanjoita kohdeyleisöille.

## <a name="understand-what-influences-a-customer-attribute"></a>Tietoja siitä, mikä vaikuttaa asiakasmääritteeseen

Voit valita ensisijaiseksi määritteeksi mittarin sijaan asiakasmääritteen. Tekoälymalli luo valittujen vaikuttavien määritteiden perusteella ehdotusten sarjan. Siinä näytetään, miten valitut määritteet vaikuttavat ensisijaiseen määritteeseen.

Voit esimerkiksi valita ensisijaiseksi määritteeksi *Palkkio-ohjelmien jäsen (kyllä/ei)* -arvon. *Asiakkuuden kesto*-, *Toiminta*- ja *Tukipalvelupyyntöjen määrä* -kohdat määritetään muiksi vaikuttaviksi määritteiksi. Tekoälymalli voi ehdottaa segmenttejä, jotka osoittavat erityisesti yli kaksi vuotta asiakkuutta omaavien IT-alan ammattilaisten olevan palkkio-ohjelman jäseniä. Toinen ehdotus voi korostaa, että yli vuoden asiakkuuden keston ja vähemmän kuin kolme tukipalvelupyyntöä omaavat kirjanpitäjät ovat palkkio-ohjelman jäseniä.

## <a name="artificial-intelligence-usage"></a>Tekoälyn käyttö

Jos käytössä on ensisijainen määrite ja vaikuttavat määritteet, päätöspuun algoritmi ehdottaa kiinnostavia segmenttejä. Ehdotukset perustuvat tekoälyn algoritmin valitsemaan sääntöihin tai malleihin. Vain segmentit, jotka eroavat merkittävästi keskimääräisestä perusjoukosta, näkyvät ehdotuksina. Vertailu keskimääräiseen perusjoukkoon perustuu valittuun mittariin tai ensisijaiseen määritteeseen.

### <a name="responsible-ai"></a>Tekoälyn vastuullinen käyttö

Ehdotettujen segmenttien avulla voit valita määritteitä uusien segmenttien luontia ja valittujen tietojen käsittelyä varten. Kun valitset määritteitä, mukaan lukien arkaluontoisia määritteitä, kuten rotu, seksuaalinen suuntautuminen tai sukupuoli, varmista, että voit käsitellä näitä tietoja. Olet vastuussa siitä, että organisaatiossa sovellettavia lakeja ja organisaation periaatteita ja tietosuojakäytäntöjä noudatetaan.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Erilaiset tulokset ensisijaisille määritteille, joilla on luokitteluarvot ja numeeriset arvot

Segmenttiehdotukset ovat erilaisia, jos ensisijaisena määritteenä käytetään numeerista tai luokittelevaan määritettä. Luokittelevan määritteen arvot sisältävät vähintään kaksi luokkaa tai tyyppiä. Numeerinen määrite sisältää kvantitatiivisia tietoja, ja siihen liittyy mittayksikkö.

Kun ensisijainen määrite on esimerkiksi *vuositulot* tai *jäsenyyskausi*, järjestelmä ehdottaa segmenttejä, joilla on korkeampi tai matalampi numeerisen määritteen keskimääräinen arvo verrattuna kaikkiin asiakkaisiin.

Jos ensisijaisena määritteenä on luokitteleva määrite, kuten *asiakastyytyväisyys*, tuloksena saadaan ehdotettuja segmenttejä, joilla on korkeampi tai matalampi prosenttiosuus tiettyyn luokkaan kuuluvia asiakkaita verrattuna samaan luokkaan kuuluviin kaikkiin asiakkaisiin. Esimerkiksi *asiakastyytyväisyys* valitaan ensisijaiseksi määritteeksi. Se sisältää kolme luokkaa (*Matala*, *Keskitaso* ja *Korkea*). Kuhunkin luokkaan ehdotetaan segmenttejä, joissa kyseiseen luokkaan kuuluvien asiakkaiden prosenttiosuus on suurempi tai pienempi verrattuna kaikkien asiakkaiden osuuteen samassa luokassa. Jos kaikista asiakkaista 22 prosentin tyytyväisyys on *Suuri*, kyseiseen luokkaan ehdotetaan silloin vain segmenttejä, joiden osuus asiakkaista, joiden tyytyväisyys on *Suuri*, on suurempi tai pienempi verrattuna 22 prosenttiin: Vastaavasti kaikille muille luokille (*Matala* ja *Keskitaso*) ehdotetaan segmenttejä, jos ne ovat tilastollisesti merkittäviä.

> [!NOTE]
> Tällä hetkellä tuetaan vain ensisijaisia luokittelevia määritteitä, joissa on enintään 10 luokkaa. Jos haluat tarkastella segmenttiehdotuksia, jotka perustuvat yli 10 luokkaa sisältävään ensisijaiseen määritteeseen, on suositeltavaa ryhmitellä joitakin luokkia niin, että luokkien määrä on 10 tai alle. Tämä rajoitus koskee vain ensisijaisia määritteitä. Vaikuttavissa luokittelevissa määritteissä tuetaan tällä hetkellä enintään 100 luokkaa.

## <a name="generate-suggested-segments"></a>Ehdotettujen segmenttien luominen

1. Siirry kohtaan **Segmentit** ja valitse **Ehdotukset (esiversio)** -välilehti.

1. Valitse **Etsi uusia ehdotuksia** ja valitse sitten **Paranna mittaria/mittausarvoa**. Valitse **Aloita**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Valitseminen parantaa ehdotettujen segmenttien mittaria.":::

1. Valitse ensisijaiseksi määritteeksi asiakasmäärite tai mittari ja valitse sitten **Seuraava**.

1. Valitse vaikuttavat määritteet ja valitse sitten **Suorita**.

   > [!TIP]
   > Useiden vaikuttavien määritteiden valitseminen parantaa mahdollisuuksia arvioida, miten ne vaikuttavat ensisijaiseen määritteeseen. Älä lisää määritteitä, jotka eivät vaikuta ensisijaiseen määritteeseen. Jos esimerkiksi kaikki asiakkaat ovat tietystä maasta, älä *maa*-määritettä, koska se ei vaikuta tulokseen.

Valittujen asiakasprofiilien ja määritteiden määrästä riippuen voi kestää muutaman minuutin, ennen kuin valitut määritteet käsitellään.

## <a name="manage-suggested-segments"></a>Hallitse ehdotettuja segmenttejä

Siirry **segmentteihin** ja valitse **Ehdotukset (esikatselu)** -välilehti. Valitse **Määritteeseen perustuvat segmenttiehdotukset** -osassa ehdotettu segmentti, jotta voit tarkastella käytettävissä olevia toimintoja.

- **Näytä** ehdotetut segmenttitiedot ja määritteiden arvot tai säännöt, jotka tekoälymalli oppi.
- **Tallenna segmenttinä** ehdotus segmenttinä. Se näkyy **Kaikki segmentit** -välilehdessä, ja sen voi [päivittää, muokata tai poistaa](segments.md).
- **Muokkaa määritteitä** ja muokkaa nykyiset ehdotukset poistavia määritettyjä ominaisuuksia.
- **Päivitä ehdotukset**, jos haluat päivittää ehdotukset ja säilyttää määritetyt määritteet.

## <a name="limitations"></a>Rajoitukset

1. Arvioitu segmentin koon ristiriita: Jos valitset tyhjiä arvoja sisältävän ensisijaisen määritteen, valinta voi vaikuttaa segmentin ehdotusten arvioituun segmentin kokoon. Kun tallennat tällaisen segmentin, todellinen segmentin koko voi olla erilainen kuin alkuperäinen arvio.

2. Totuusarvotyyppiset ensisijaiset määritteet eivät toimi. Tällä hetkellä ensisijaisina määritteinä tuetaan vain merkkijono- ja numerotyyppisiä tietoja.

3. Ehdotetut segmentit eivät ole riittävän erilaisia. Muista, että valitut määritteet ja näiden määritteiden arvojen jakautuminen vaikuttavat tuloksiin. Voit muuttaa vaikuttavia määritteitä tai jopa ensisijaista määritettä, jos haluat saada erilaisia tuloksia.

[!INCLUDE [footer-include](includes/footer-banner.md)]