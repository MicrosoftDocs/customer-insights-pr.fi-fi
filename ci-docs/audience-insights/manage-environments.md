---
title: Luo ja hallitse ympäristöjä
description: Tietoja palveluun rekisteröitymisestä ja ympäristöjen hallinnasta.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304876"
---
# <a name="manage-environments"></a>Ympäristöjen hallinta

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Tässä artikkelissa käsitellään uuden organisaation luontia ja ympäristön valmistelua.

## <a name="sign-up-and-create-an-organization"></a>Rekisteröityminen ja organisaation luominen

1. Siirry [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) -sivustoon.

2. Valitse **Aloita**.

3. Valitse ensin sopiva kirjautumisskenaario ja sitten vastaava linkki.

4. Aloita organisaation luonti hyväksymällä ehdot ja valitsemalla **Jatka**.

5. Kun ympäristö on luotu, sinut ohjataan [Customer Insightsiin](https://home.ci.ai.dynamics.com).

6. Tutustu sovellukseen esittely-ympäristön avulla tai luo uusi ympäristö seuraavan osan vaiheiden avulla.

7. Kun ympäristön asetukset on määritetty, valitse **Luo**.

8. Kirjautuminen tapahtuu, kun ympäristö on luotu.

## <a name="create-an-environment-in-an-existing-organization"></a>Ympäristön luominen aiemmin luodussa organisaatiossa

Uusi ympäristö voidaan luoda kahdella tavalla. Voit joko määrittää kokonaan uuden määrityksen tai voit kopioida joitakin määritysasetuksia aiemmin luodusta ympäristöstä.

> [!NOTE]
> Organisaatiot voivat luoda *kaksi* ympäristöä jokaista Customer Insights -käyttöoikeutta varten. Jos organisaatiosi ostaa useamman kuin yhden käyttöoikeuden, [ota yhteyttä tukiryhmäämme](https://go.microsoft.com/fwlink/?linkid=2079641), jotta käytettävissä olevien ympäristöjen määrää voidaan lisätä. Lisätietoja kapasiteetista ja lisäkapasiteetista on [Dynamics 365:n käyttöoikeusoppaassa](https://go.microsoft.com/fwlink/?LinkId=866544).

Ympäristön luominen:

1. Valitse sovelluksen otsikossa **Ympäristö**-valitsin.

1. Valitse **Uusi**.

   > [!div class="mx-imgBorder"]
   > ![Ympäristöasetukset.](media/environment-settings-dialog.png)

1. Valitse **Luo ympäristö** -valintaikkunassa **Uusi ympäristö**.

   Jos haluat [kopioida tietoja nykyisestä ympäristöstä](#considerations-for-copy-configuration-preview), valitse **Kopioi aiemmasta ympäristöstä**. Näkyviin tulee luettelo kaikista organisaation käytettävissä olevista ympäristöistä, joista voit kopioida tietoja.

1. Anna seuraavat tiedot:
   - **Nimi**: Ympäristön nimi. Tämä kenttä on jo täytetty, jos kopioit tietoja aiemmin luodusta ympäristöstä, mutta voit muuttaa sitä.
   - **Tyyppi**: Määritä, haluatko luoda tuotanto- vai eristysympäristön.
   - **Alue**: Alue, jossa palvelu otetaan käyttöön ja jossa sitä isännöidään.
   
1. Valinnaisesti voit valita **Lisäasetukset**:

   - **Tallenna kaikki tiedot kohteeseen**: Määrittää, minne haluat tallentaa Customer Insightsin tulostiedot. Käytettävissä on kaksi vaihtoehtoa: **Customer Insights -tallennustila** (Customer Insights -ryhmä hallinnoi Azure Data Lake -ratkaisussa) ja **Azure Data Lake Storage** (oma Azure Data Lake Storage). Oletusarvoisesi Customer Insights -tallennustila -vaihtoehto on valittu.

     > [!NOTE]
     > Tallentamalla tiedot Azure Data Lake Storageen hyväksyt, että tiedot siirretään ja tallennetaan kyseisen Azure-tallennustilin asianmukaiseen maantieteelliseen sijaintiin. Tämä sijainti voi olla eri kuin sijainti, johon tiedot on tallennettu Dynamics 365 Customer Insightsissa. [Lisätietoja on Microsoftin luottamuskeskuksessa.](https://www.microsoft.com/trust-center)
     >
     > Tällä hetkellä käsitellyt entiteetit tallennetaan aina Customer Insightsin hallittuun Data Lake -tallennustilaan. 
     > 
     > Vain ympäristön luomisen aikana käytetyn Azure-alueen Azure Data Lake Storage -tilejä tuetaan. 
     > 
     > Vain niitä Azure Data Lake Storage -tilejä tuetaan, joille on valittu hierarkkinen nimitila.


   - Voit valita Azure Data Lake Storage -asetukselle resurssi- tai tilausperustaisen asetuksen todentamista varten. Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md). **Säilön** nimeä ei voi muuttaa, ja se tulee olemaan `customerinsights`.
   
   - Jos haluat käyttää [ennusteita](predictions.md), määritä tietojen jakaminen Microsoft Dataversen kanssa tai ota käyttöön tietojen käsittely paikallisista tietolähteistä, anna Microsoft Dataverse -ympäristön URL-osoite kohdassa **Tietojen jakamisen määrittäminen Microsoft Dataversen kanssa ja lisäominaisuuksien ottaminen käyttöön**. Valitse **Ota käyttöön tietojen jakaminen**, jos haluat jakaa Customer Insightsin tulostiedot Microsoft Dataversen hallitun Data Laken kanssa.

     > [!NOTE]
     > - Tietojen jakamista Microsoft Dataversen hallitun Data Laken kanssa ei tueta tällä hetkellä, jos kaikki tiedot tallennetaan omaan Azure Data Lake Storage -ratkaisuun.
     > - [Entiteetin puuttuvien arvojen ennustetta](predictions.md) ei tueta tällä hetkellä, jos tietojen jakaminen Microsoft Dataversen hallitun Data Laken kanssa otetaan käyttöön.

     > [!div class="mx-imgBorder"]
     > ![Määritysvalinnat tietojen jakamista varten Microsoft Dataversen kanssa.](media/datasharing-with-DataverseMDL.png)

   Kun suoritat prosesseja, kuten tietojen käsittelyä tai segmenttien luontia, vastaavat kansiot luodaan edellä määritettyyn tallennustiliin. Datatiedostot ja model.json-tiedostot luodaan ja lisätään kansioihin, jotka perustuvat prosessin nimeen.

   Jos luot useita Customer Insights -ympäristöjä ja valitset kyseisten ympäristöjen tuloste-entiteettien tallentamisen tallennustilille, kullekin ympäristölle luodaan erilliset kansiot siten, että säilössä on ci_<environmentid>.

### <a name="considerations-for-copy-configuration-preview"></a>Määrityksien kopiointiin liittyviä näkökohtia (esiversio)

Seuraavat määritysasetukset kopioidaan:

- Toiminnon määritykset
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

Seuraavia asetuksia *ei* kopioida:

- Asiakasprofiilit.
- Tietolähteen tunnistetiedot. Sinun on annettava kunkin tietolähteen tunnistetiedot ja päivitettävä tietolähteet manuaalisesti.
- Common Data Model -kansion ja Dataversen hallitun Data Laken tietolähteet. Nämä tietolähteet on luotava manuaalisesti samalla nimellä kuin lähdeympäristössä.

Kun kopioit ympäristön, näkyviin tulee vahvistussanoma siitä, että uusi ympäristö on luotu. Valitse **Siirry tietolähteisiin**, kun haluat nähdä tietolähteiden luettelon.

Kaikkien tietolähteiden tilana näkyy **Vaatii tunnistetietoja**. Muokkaa tietolähteitä ja päivitä ne syöttämällä tunnistetiedot.

> [!div class="mx-imgBorder"]
> ![Kopioidut tietolähteet.](media/data-sources-copied.png)

Kun olet päivittänyt tietolähteet, siirry kohtaan **Tiedot** > **Yhtenäistäminen**. Siellä ovat lähdeympäristön asetukset. Voit muokata niitä tarpeen mukaan tai valita **Suorita**, jolloin tietojen yhtenäistämisprosessi alkaa ja yhtenäistetty asiakasentiteetti luodaan.

Kun tietojen yhtenäistäminen on valmis, päivitä myös kohdat **Mittarit** ja **Segmentit** siirtymällä niihin.

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
   > - [Entiteettien puuttuvien arvojen ennustetta](predictions.md) ei tueta tällä hetkellä, kun otat tietojen jakamisen käyttöön Microsoft Dataversen hallitun Data Laken kanssa.

   Kun tietojen jakaminen Microsoft Dataversen kanssa on otettu käyttöön, aloitetaan tietolähteiden ja muiden prosessien täydellinen päivitys. Jos prosesseja tällä hetkellä suoritetaan, et näe mahdollisuutta ottaa tietojen jakamista käyttöön Microsoft Dataversen kanssa. Odota, että prosessit valmistuvat tai peruutat ne, jotta tietojen jakaminen voidaan ottaa käyttöön. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Määritysvalinnat tietojen jakamista varten Microsoft Dataversen kanssa.":::
   
   Kun suoritat prosesseja, kuten tietojen käsittelyä tai segmenttien luontia, vastaavat kansiot luodaan edellä määritettyyn tallennustiliin. Datatiedostot ja model.json-tiedostot luodaan ja lisätään vastaaviin alikansioihin suoritettavan prosessin mukaan.

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
