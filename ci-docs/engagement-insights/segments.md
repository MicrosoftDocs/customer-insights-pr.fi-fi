---
title: Segmenttien tarkasteleminen ja luominen
description: Segmenttien luominen, muokkaaminen ja poistaminen sekä se, missä niitä käytetään.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036144"
---
# <a name="view-and-create-segments"></a>Segmenttien tarkasteleminen ja luominen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Segmenttien avulla voit tunnistaa vierailijoiden alijoukot ominaisuuksien tai verkkosivuston aktiiteetteihin perustuen. Segmenttien avulla voit käyttää suodattimia ja analysoida niitä. Analyysi auttaa tarkastelemaan liiketoiminnan trendejä ja vastaamaan niihin. 

:::image type="content" source="media/segments-page.png" alt-text="Näyttökuva käyttäjäryhmän merkitykselliset tiedot -sovelluksesta, jossa näkyy työtilan aiemmin luotujen segmenttien luettelo.":::

## <a name="view-segments"></a>Näytä segmentit

1. Valitse vasemmassa siirtymisruudussa **Tiedot**. 

1. Valitsemalla **Segmentit**-välilehden voit tarkastella työtilan kaikkien segmenttien luetteloa. 

## <a name="create-a-segment"></a>Luo segmentti

Segmentit koostuvat loogisiin operaattoreihin liitetyistä säännöistä ja ehdoista. Ehdot kohdistavat suodattimia valittuun dimensioon. Jokainen segmentti voi käyttää enintään viittä dimensiota.

Seuraavassa esimerkissä segmentti, jossa on kaksi ehtoa yhdessä säännössä. Se suodattaa kaikki verkkosivustotapahtumat, joissa selain on Chrome ja käyttöjärjestelmät ovat iOS- tai Android.

:::image type="content" source="media/segment-sample.png" alt-text="Esimerkkisegmentit, joilla on kaksi ehtoa verkkosivustotapahtumien suodatussäännössä.":::

Tässä osassa kuvataan, miten *tyhjä segmentti* luodaan alusta alkaen.

1. Siirry kohtaan **Tiedot** > **Segmentit**.

1. Valitse **Uusi segmentti**.

1. Valitse **resurssikirjastossa** määrite, jonka mukaan haluat suodattaa. Tällä hetkellä voit luoda vain dimensioihin perustuvia segmenttejä.

1. Valitse operaattori ja arvo valitulle määritteelle. Seuraavia tapahtumia tuetaan.
   - **on**: edellyttää täsmällistä vastaavuusarvoa. Käyttää **yhtä kuin** yhdelle arvolle tai **joku näistä** useiden arvojen sisällyttämiseksi.
   - **ei ole**: edellyttää täsmällistä vastaavuusarvoa arvojen poissulkemiseksi. Käyttää **yhtä kuin** yhdelle arvolle tai **joku näistä** useiden arvojen sisällyttämiseksi.
   - **alkaa**: merkkijono, jolla vastaavat arvot alkavat.
   - **päättyy**: merkkijono, jolla vastaavat arvot päättyvät.
   - **sisältää**: vastaavien arvojen sisältämä merkkijono.

1. Jos haluat lisätä ryhmään ehtoja, voit käyttää seuraavaa kahta loogista operaattoria. Projisoidut määritteet otetaan huomioon, kun joukko-operaattoreita käytetään.
   - **JA**-operaattori: Molempien ehtojen on täytyttävä segmentointiprosessin aikana. Tämä vaihtoehto on hyödyllinen, kun määrität ehtoja eri entiteeteille.
   - **TAI**-operaattori: Jommankumman ehdoista on täytyttävä segmentointiprosessin aikana. Tämä vaihtoehto on hyödyllinen, kun määrität useita ehtoja samalle entiteetille.

1. Valitse **Tallenna** ja nimeä segmentti. 

Segmentti näkyy Segmentit-sivulla, ja voit käyttää sitä työtilan kaikissa raporteissa ja suppiloissa.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Segmentin käyttö raportissa tai suppilossa

Voit suodattaa segmenttejä raportissa tai suppilossa segmentin ehtojen mukaan. Tosiaikaista käyttöraporttia ei kuitenkaan voi käyttää segmenteissä.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Sivunäkymien raportti, jossa on laajennettu avattava luettelo käytettävien segmenttien valitsemista varten.":::

Jos haluat ottaa segmentin käyttöön, avaa raportti tai suppilo. Valitse **Lisää ehto** ja valitse sitten **Suodata segmentin mukaan**. Valitse segmentti luettelosta, jota haluat käyttää. Segmentti kohdistetaan raporttiin. Jos kaavio ei tue segmenttiä, siinä näkyy virhe.
 
Voit käyttää raportissa tai suppilossa *enintään kolmea segmenttiä*.

## <a name="edit-a-segment"></a>Muokkaa segmenttiä

1. Siirry kohtaan **Tiedot** > **Segmentit**.
1. Avaa segmentti valitsemalla se luettelosta. 
1. Muuta tai lisää arvoja tarpeen mukaan.
1. Ota muutokset käyttöön valitsemalla **Tallenna**.

## <a name="change-the-name-of-a-segment"></a>Muuta segmentin nimi

1. Siirry kohtaan **Tiedot** > **Segmentit**.
1. Valitse segmenttiluettelosta **Lisää [...]**. 
1. Valitse avattavasta luettelosta **Muokkaa nimeä**.
1. Anna uusi nimi ja valitse **Nimeä uudelleen**.

## <a name="delete-a-segment"></a>Poista segmentti

1. Siirry kohtaan **Tiedot** > **Segmentit**.
1. Valitse segmenttiluettelosta **Lisää [...]**. 
1. Valitse avattavasta luettelosta **Poista**.
1. Valitse **Poista** vahvistaaksesi.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
