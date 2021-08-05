---
title: Luo ja hallitse ympäristöjä
description: Tietoja palveluun rekisteröitymisestä ja ympäristöjen hallinnasta.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2f115269b9d07dd118ec18cc48b55de8aea9b5bb
ms.sourcegitcommit: 98267da3f3eddbdfbc89600a7f54e5e664a8f069
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/28/2021
ms.locfileid: "6683469"
---
# <a name="manage-environments"></a>Ympäristöjen hallinta

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Ympäristöjen vaihtaminen

Voit vaihtaa ympäristöä valitsemalla sivun oikeassa yläkulmassa **Ympäristöt**.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Näyttökuva ohjausobjektista, jonka avulla voit vaihtaa ympäristöä.":::

Järjestelmänvalvojat voivat [Luoda](get-started-paid.md) ja hallita ympäristöjä.

## <a name="edit-an-existing-environment"></a>Aiemmin luodun ympäristön muokkaaminen

Voit muokata joitakin aiemmin luotujen ympäristöjen tietoja.

1.  Valitse sovelluksen otsikossa **Ympäristö**-valitsin.

2.  Valitse **Muokkaa**-kuvake.

3. **Muokkaa ympäristöä** -ruudussa voit päivittää ympäristön **näyttönimen**, mutta et voi muuttaa **aluetta** tai **tyyppiä**.

4. Jos ympäristö on määritetty niin, että tiedot tallennetaan Azure Data Lake Storageen, voit päivittää **asiakkaan avaimen**. Et voi kuitenkaan muuttaa **tilin nimeä** tai **säilön** nimeä.

5. Voit myös tehdä päivityksen käyttöoikeusavaimeen perustuvassa yhteydessä resurssi- tai tilausperusteiseen yhteyteen. Päivitykseen jälkeen ei ole mahdollista palata käyttöoikeusavaimeen. Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md). **Säilö**-tietoja ei voi muuttaa yhteyttä päivitettäessä.

6. Vaihtoehtoisesti voit määrittää Microsoft Dataverse -ympäristön URL-osoitteen kohdassa **Tietojen jakamisen määrittäminen Microsoft Dataversen kanssa ja lisäominaisuuksien ottaminen käyttöön**. Nämä ominaisuudet sisältävät tietojen jakamisen sovelluksiin ja ratkaisuihin Microsoft Dataverseen perusteella,tietojen käsittelyn paikallisistas tietolähteistä, tai käytä [ennusteita](predictions.md). Valitse **Ota käyttöön tietojen jakaminen**, jos haluat jakaa Customer Insightsin tulostiedot Microsoft Dataversen hallitun Data Laken kanssa.

   > [!NOTE]
   > - Tietojen jakamista Microsoft Dataversen hallitun Data Laken kanssa ei tueta tällä hetkellä, jos kaikki tiedot tallennetaan omaan Azure Data Lake Storage -ratkaisuun.
   > - [Entiteetin puuttuvien arvojen ennustetta](predictions.md) ja PowerBI Embedded -raporttien käyttäjäryhmän tietoja (jos käytössä ympäristössäsi) ei tällä hetkellä tueta, kun otat tietojen jakamisen käyttöön Microsoft Dataversen hallitun tietojärven kanssa.

   Kun tietojen jakaminen Microsoft Dataversen kanssa on otettu käyttöön, aloitetaan tietolähteiden ja muiden prosessien täydellinen päivitys. Jos prosesseja tällä hetkellä suoritetaan, et näe mahdollisuutta ottaa tietojen jakamista käyttöön Microsoft Dataversen kanssa. Odota, että prosessit valmistuvat tai peruutat ne, jotta tietojen jakaminen voidaan ottaa käyttöön. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Määritysvalinnat tietojen jakamista varten Microsoft Dataversen kanssa.":::
   
   Kun suoritat prosesseja, kuten tietojen käsittelyä tai segmenttien luontia, vastaavat kansiot luodaan edellä määritettyyn tallennustiliin. Datatiedostot ja model.json-tiedostot luodaan ja lisätään vastaaviin alikansioihin suoritettavan prosessin mukaan.

## <a name="copy-the-environment-configuration"></a>Kopioi ympäristön määritys

Kun luot uuden ympäristön, voit kopioida määrityksen aiemmin luodusta ympäristöstä. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Näyttökuva ympäristöasetusten asetusvaihtoehdoista.":::

Näkyviin tulee luettelo kaikista organisaation käytettävissä olevista ympäristöistä, joista voit kopioida tietoja.

Seuraavat määritysasetukset kopioidaan:

- Käsitellyt/tuodut tietolähteet
- Tietojen yhtenäistämisen (yhdistäminen, vastaavuus) määritys
- Segmentit
- Mittarit
- Suhteet
- Aktiviteetit
- Haku- ja suodatusindeksi
- Vientikohteet
- Ajoitettu päivitys
- Rikastukset
- Mallien hallinta
- Roolimääritykset

Seuraavia tietoja *ei* kopioida:

- Asiakasprofiilit.
- Tietolähteen tunnistetiedot. Sinun on annettava kunkin tietolähteen tunnistetiedot ja päivitettävä tietolähteet manuaalisesti.
- Common Data Model -kansion ja Dataversen hallitun Data Laken tietolähteet. Nämä tietolähteet on luotava manuaalisesti samalla nimellä kuin lähdeympäristössä.

Kun kopioit ympäristön, näkyviin tulee vahvistussanoma siitä, että uusi ympäristö on luotu. Valitse **Siirry tietolähteisiin**, kun haluat nähdä tietolähteiden luettelon.

Kaikkien tietolähteiden tilana näkyy **Vaatii tunnistetietoja**. Muokkaa tietolähteitä ja päivitä ne syöttämällä tunnistetiedot.

:::image type="content" source="media/data-sources-copied.png" alt-text="Luettelo kopioiduista tietolähteistä, jotka vaativat todennusta.":::

Kun olet päivittänyt tietolähteet, siirry kohtaan **Tiedot** > **Yhtenäistäminen**. Siellä ovat lähdeympäristön asetukset. Voit muokata niitä tarpeen mukaan tai valita **Suorita**, jolloin tietojen yhtenäistämisprosessi alkaa ja yhtenäistetty asiakasentiteetti luodaan.

Kun tietojen yhtenäistäminen on valmis, päivitä myös kohdat **Mittarit** ja **Segmentit** siirtymällä niihin.

## <a name="reset-an-existing-environment"></a>Aiemmin luodun ympäristön palauttaminen

Järjestelmänvalvoja voi palauttaa ympäristön tyhjään tilaan, jos haluat poistaa kaikki määritykset ja käsitellyt tiedot.

1.  Valitse sovelluksen otsikossa **Ympäristö**-valitsin. 

2.  Valitse ympäristö, jonka haluat palauttaa, ja valitse sitten kolme pistettä (**...**). 

3. Valitse **Palauta**-vaihtoehto. 

4.  Vahvista poisto antamalla ympäristön nimi ja valitsemalla **Palauta**.

## <a name="delete-an-existing-environment"></a>Olemassa olevan ympäristön poistaminen

Järjestelmänvalvoja voi poistaa myös hallitsemasi ympäristön.

1.  Valitse sovelluksen otsikossa **Ympäristö**-valitsin.

2.  Valitse ympäristö, jonka haluat palauttaa, ja valitse sitten kolme pistettä (**...**). 

3. Valitse **Poista**-vaihtoehto. 

4.  Vahvista poisto antamalla ympäristön nimi ja valitsemalla **Poista**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
