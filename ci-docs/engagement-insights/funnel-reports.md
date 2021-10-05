---
title: Suppiloraportit
description: Suppiloraporttien käyttö sen ymmärtämiseen, miten käyttäjäryhmä tekee päätöksiä.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/21/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: efb10f2664630a5851d9582ff09c378c01777b96
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558916"
---
# <a name="create-and-manage-funnel-reports"></a>Suppiloraporttien luominen ja hallinta

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Suppiloraporttiin kerätään sivuston tai mobiilisovelluksen asiakassiirtymän tietojen vaiheet. Se auttaa ymmärtämään, miten kohderyhmä etenee prosessin aikana ja tunnistaa luovutuskohtia. Suppiloraportin avulla voit esimerkiksi tunnistaa reittejä, joita asiakkaat käyttävät ennen ostoa. Suppiloraportti sisältää tietoja päätösten perustaksi ja optimoinnin ja prosessiparannusten alueiden tunnistamiseksi.

## <a name="create-a-funnel-report"></a>Suppiloraportin luominen

Luo suppiloraportti määrittämällä sisällytettävät vaiheet ja kunkin vaiheen aktiviteetti. Aktiviteetti on [tapahtuma](glossary.md), joka edustaa käyttäjän käyttäytymistä. Suppiloraportti näyttää kunkin määritetyn vaiheen suorittaneiden käyttäjien määrän. 

1. Aloita suppiloraportti siirtymällä kohtaan **Suppilot** ja valitsemalla **+Uusi suppilo**.

1. Valitse **Suppiloeditori**-kohdassa **Vaiheet** ja sitten **+Lisää vaihe**. 

1. Kirjoita nimi kohtaan **Vaiheen otsikko**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Uusi suppiloraportti.":::

1. Valitse **Aktiviteetti**. Aktiviteetti kirjaa ylös, milloin käyttäjä tarkastelee sivua (**Katselu**-aktiviteetti) tai on vuorovaikutuksessa sen sisällön kanssa (**Toiminto**-aktiviteetti).

1. Määritä aktiviteetin dimensio kohdassa **Vaiheen ehdot**. [Dimensiot](dimensions.md) ovat määritteitä, jotka voivat kuvailla, suodattaa tai ryhmitellä tietoja.

1. Voit myös määrittää moniehtoisia suppilovaiheita. Valitse **Lisää ehto**, jos haluat määrittää lisää dimensioita vaiheessa. Lisäehtoja on käytettävä samalla aktiviteettityypillä. Voit valita, liittyykö JA- vai TAI-operaattoriin useita ehtoja.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Suppiloeditori, jossa on vaihemääritykset moniehtoisten vaiheiden kanssa.":::

1. Valitse **Lisää vaihe**, kunnes olet suorittanut kaikki raporttiin haluamasi vaiheet.

1. Valitse **Tallenna**, anna raportille nimi ja valitse taas **Tallenna**. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Esimerkki: Yrityksen Fourth Coffee suppiloraportti

Seuraavassa skenaariossa esitellään yksi tapa käyttää suppiloraporttia. Yrityksen Fourth Coffee analyytikko haluaa tietää, miten äskettäinen kampanja vaikuttaa tilausmääriin. Analysoija luo suppiloraportin asiakasaktiviteettien tunnistamiseksi. Se alkaa, kun asiakkaat saapuvat yrityksen kotisivulle ja päättyy siihen, että he käyttävät tilauskampanjakoodia. Analyytikko luo suppiloraportin, jossa on seuraavat vaiheet:

Vaihe 1: Asiakkaat, jotka tulevat kotisivulle   
Vaihe 2: Asiakkaat, jotka tekevät oston   
Vaihe 3: Asiakkaat, jotka käyttävät kampanjakoodia saadakseen alennuksen tilauksesta   
Vaihe 4: Tilauksen rekisteröinti   

:::image type="content" source="media/funnel-report-example.png" alt-text="esimerkki suppiloraportista.":::
  
Tässä suppilossa voit nähdä niiden käyttäjien määrän, jotka käyttivät kampanjakoodia kertaostoksen jälkeen rekisteröityäkseen tilausohjelmaan.

### <a name="configure-advanced-settings"></a>Lisäasetusten määrittäminen 

Suppiloraporttien avulla voit määrittää raja-arvon siihen, miten kauan suppilon valmistuminen kestää. Voit esimerkiksi asettaa suppilon valmistumisajaksi neljä päivää. Tämä asetus laskee vain ne onnistuneet tilauskirjaukset, jotka tapahtuivat neljän päivän kuluessa kotisivulla käyvästä käyttäjästä.

1. Avaa **Suppilokirjasto** kohdassa **Suppilot**.

1. Avaa raportti valitsemalla sen nimi. 

1. Valitse **Suppiloeditori**-ruudussa **Lisäasetukset**. 

1. Aseta suppilon valmistumisajan arvoksi **Käytössä**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Suppiloeditori, jossa näkyvät lisäasetukset ja vaihtoehdot, jotka rajoittavat suppiloajan valmistumista.":::

1. Valitse avattavasta **Määritä rajaksi** -luettelosta aika, jolloin suppilon on oltava valmis.

1. Ota muutokset käyttöön valitsemalla **Tallenna**.


## <a name="cross-channel-funnel-reports"></a>Kanavien väliset suppiloraportit 

Vuorovaikutuksen merkitykselliset tiedot voivat kerätä myös toiminnallisia asiakastietoja mobiilisovelluksessa. Kun mobiilisovellus on instrumentoitu vuorovaikutuksen merkityksellisten tietojen [Android SDK:n](get-started-android.md) tai [iOS SDK:n](get-started-ios.md) avulla, voit luoda kanavien välisiä suppiloraportteja. 

### <a name="create-a-cross-channel-funnel-report"></a>Kanavien välisten suppiloraporttien luominen 

1. Näiden vaiheiden avulla voit [luoda suppiloraportin](#create-a-funnel-report).    

1. Jos haluat seurata asiakkaiden vuorovaikutusta tuotemerkin kanssa sekä sivustossa että mobiilisovelluksessa tai useissa sivustoissa, käytä työtilan valitsinta ja luo suppilovaiheet muiden työtilojen tietojen avulla. Valitse **Vaiheet**-kohdan **Suppilon editori** -kohdassa työtila, josta suppilovaiheen tiedot saadaan.

## <a name="manage-funnel-reports"></a>Suppiloraporttien hallinta

Voit tarkastella suppiloraportteja analysoidaksesi tietoja, seurataksesi tehokkuutta ja kerätäksesi tietoja.

> [!NOTE]
> - Vuorovaikutuksen merkityksellisten tietojen suppiloraportit tukevat tällä hetkellä skenaarioita, joissa kaikki suppiloon käyttäjät ovat anonyymeja tai joissa kaikki käyttäjät todennetaan. 
> - Suppiloraporttien historiatiedot ovat käytettävissä 30 päivän ajalta.

### <a name="view-funnel-reports"></a>Suppiloraporttien tarkastelu

1. Avaa **Suppilokirjasto** kohdassa **Suppilot**.
1. Avaa raportti valitsemalla sen nimi.    

### <a name="see-the-data-collected-for-a-report"></a>Raporttia varten kerättyjen tietojen tarkastelu   

Vaiheen tietojen tarkasteleminen

- Osoita raportin vaihetta.

:::image type="content" source="media/funnel-step-data.png" alt-text="suppilotiedot.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Suppiloraportin päivämäärävälin muuttaminen

1. Avaa **Suppilokirjasto** kohdassa **Suppilot**.

1. Avaa raportti valitsemalla sen nimi.

1. Määritä päivämääräväli avaamalla **aikaväli** ja valitsemalla uusi ajanjakso luettelosta tai valitsemalla **Kiinteä päivämääräväli**.

## <a name="edit-or-delete-funnel-reports"></a>Suppiloraporttien muokkaaminen tai poistaminen

Voit muuttaa suppiloraportin nimeä, poistaa sen tai muokata raportin vaiheita.

### <a name="rename-or-delete-a-funnel-report"></a>Suppiloraportin nimeäminen uudelleen tai poistaminen

1. Avaa **Suppilokirjasto** kohdassa **Suppilot**. 

1. Valitse muutettavan raportin vierestä **Lisää** ja valitse sitten **Muokkaa nimeä** tai **Poista**.

### <a name="edit-a-funnel-step"></a>Suppilon vaiheen muokkaaminen  

1. Avaa **Suppilokirjasto** kohdassa **Suppilot**. 

1. Avaa raportti valitsemalla sen nimi.

1. Valitse muokattava vaihe.

1. Valitse **muokkaa**.

1. Päivitä muutettavat tiedot kohdassa **Suppiloeditori**.  

1. Valitse **Tallenna**.

### <a name="reorder-a-funnel-step"></a>Suppilovaiheen uudelleenjärjestely

1. Avaa **Suppilokirjasto** kohdassa **Suppilot**. 

1. Avaa raportti valitsemalla sen nimi.

1. Valitse uudelleenjärjestettävä vaihe.

1. Siirrä vaihetta valitsemalla **Siirrä** ja sitten **Ylös**, **Alas**, **Ylimmäksi** tai **Alimmaksi**.

### <a name="delete-a-funnel-step"></a>Suppilovaiheen poistaminen

1. Avaa **Suppilokirjasto** kohdassa **Suppilot**. 

1. Avaa raportti valitsemalla sen nimi.

1. Valitse ensin poistettava vaihe ja sitten **Poista**.

## <a name="funnel-insights"></a>Suppilon merkitykselliset tiedot 

Osallistumisen merkitykselliset tiedot antavat nyt suppilotietoja asiakkaille. Suppilotietojen avulla saat lisätietoja asiakaskäyttäytymisestä suppiloraportin vaiheissa. Kun luot ja tallennat uuden suppiloraportin, raporttiin luodaan automaattisesti suppilotietoja. 

:::image type="content" source="media/funnel-insights.png" alt-text="Suppilon merkitykselliset tiedot.":::

> [!NOTE]
> Suppilotietoja voi luoda vain suppilovaiheille, jotka **eivät** sisällä mukautettuja dimensioita. Jos haluat luoda suppilotietoja suppilosi kaikista osavaiheista, luo suppilovaiheet käyttämällä sitouttamisnäkemyksien valmiita dimensioita. 

Voit tarkastella suppilotietoja seuraavista luokista sekä pää- että vaihetasolla: 

 - Muunnosprosentti
 -    Konversioaste Kassan ja Oston välillä on 22 %.
 - Siirtoaika 
 -    Keskimääräinen siirtymisaika Ostoskorin ja Kassan välillä on 23 minuuttia. 
 - Valmistumisaika 
 -    Keskimääräinen aika, jonka asiakkaat käyttävät suppilon suorittamiseen, on 47 minuuttia. 

Näiden näkemysten avulla voit tutkia asiakaskäyttäytymistä ja ymmärtää paremmin suppiloraportin päätepistettä ja muunnoksia. 

Jos haluat verrata eri vaiheiden tietoja, valitse **Näytä vaiheiden erittely** tai **Vertaa muihin vaiheisiin** tietokorteissa. Niissä näkyy pylväskaavio, jossa verrataan kunkin suppilon vaiheen tietoja. 

Suppilotiedot lasketaan uudelleen 24 tunnin välein tai kun **tallennat** suppiloraportin. 

> [!NOTE]
> Jotta voit tarkastella suppilosi tietoja, raportti on tallennettava aina, kun teet muutoksia. 

