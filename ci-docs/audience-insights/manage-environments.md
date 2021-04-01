---
title: Luo ja hallitse ympäristöjä
description: Tietoja palveluun rekisteröitymisestä ja ympäristöjen hallinnasta.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 1c2dfdd2889b5cb6c5285b4d7cc7f52a3d6de4d1
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598289"
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

Ympäristön luominen:

1. Valitse sovelluksen otsikossa **Ympäristö**-valitsin.

1. Valitse **Uusi**.

   > [!div class="mx-imgBorder"]
   > ![Ympäristön asetukset](media/environment-settings-dialog.png)

1. Valitse **Luo uusi ympäristö** -valintaikkunassa **Uusi ympäristö**.

   Jos haluat [kopioida tietoja nykyisestä ympäristöstä](#additional-considerations-for-copy-configuration-preview), valitse **Kopioi aiemmasta ympäristöstä**. Näkyviin tulee luettelo kaikista organisaation käytettävissä olevista ympäristöistä, joista voit kopioida tietoja.

1. Anna seuraavat tiedot:
   - **Nimi**: Ympäristön nimi. Tämä kenttä on jo täytetty, jos kopioit tietoja aiemmin luodusta ympäristöstä, mutta voit muuttaa sitä.
   - **Alue**: Alue, jossa palvelu otetaan käyttöön ja jossa sitä isännöidään.
   - **Tyyppi**: Määritä, haluatko luoda tuotanto- vai eristysympäristön.

2. Valinnaisesti voit valita **Lisäasetukset**:

   - **Tallenna kaikki tiedot kohteeseen**: Määrittää, minne haluat tallentaa Customer Insightsin tulostiedot. Vaihtoehtoja on kaksi: **Customer Insights -tallennustila** (Customer Insights -ryhmän hallitsema Azure Data Lake) ja **Azure Data Lake Storage Gen2** (oma Azure Data Lake Storage). Oletusarvoisesi Customer Insights -tallennustila -vaihtoehto on valittu.

   > [!NOTE]
   > Tallentamalla tiedot Azure Data Lake Storageen hyväksyt, että tiedot siirretään ja tallennetaan kyseisen Azure-tallennustilin asianmukaiseen maantieteelliseen sijaintiin. Tämä sijainti voi olla eri kuin sijainti, johon tiedot on tallennettu Dynamics 365 Customer Insightsissa. [Lisätietoja on Microsoftin luottamuskeskuksessa.](https://www.microsoft.com/trust-center)
   >
   > Tällä hetkellä käsitellyt entiteetit tallennetaan aina Customer Insightsin hallittuun Data Lake -tallennustilaan.
   > Vain sellaisia Azure Data Lake Gen2 -tallennustilejä tuetaan, jotka ovat ympäristöä luotaessa valitulla Azure-alueella.
   > Vain sellaisia tallennustilatilejä tuetaan, joissa on otettu käyttöön Azure Data Lake Gen2:n hierarkkinen nimitila.

   - Voit valita Azure Data Lake Storage Gen2 -vaihtoehdossa, käytetäänkö todennukseen resurssi- vai tilausperusteista vaihtoehtoa. Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md). **Säilön** nimeä ei voi muuttaa, ja se on customerinsights.
   
   - Jos haluat käyttää [ennusteita](predictions.md) tai määrittää tietojen jakamisen sovelluksissa ja ratkaisuissa Microsoft Dataversen perusteella, anna Microsoft Dataverse -ympäristön URL-osoite kohdassa **Tietojen jakamisen määrittäminen Microsoft Dataversen kanssa ja lisäominaisuuksien käyttöönotto**. Valitse **Ota käyttöön tietojen jakaminen**, jos haluat jakaa Customer Insightsin tulostiedot Microsoft Dataversen hallitun Data Laken kanssa.

     > [!NOTE]
     > - Tietojen jakamista Microsoft Dataversen hallitun Data Laken kanssa ei tueta tällä hetkellä, jos kaikki tiedot tallennetaan omaan Azure Data Lake Storage -ratkaisuun.
     > - [Entiteetin puuttuvien arvojen ennustetta](predictions.md) ei tueta tällä hetkellä, jos tietojen jakaminen Microsoft Dataversen hallitun Data Laken kanssa otetaan käyttöön.

     > [!div class="mx-imgBorder"]
     > ![Määritysvalinnat tietojen jakamista varten Microsoft Dataversen kanssa](media/Datasharing-with-DataverseMDL.png)

   Kun suoritat prosesseja, kuten tietojen käsittelyä tai segmenttien luontia, vastaavat kansiot luodaan edellä määritettyyn tallennustiliin. Datatiedostoja ja model.json-tiedostoja luodaan ja lisätään asianmukaisiin alikansioihin suorittamasi prosessin perusteella.

   Jos luot useita Customer Insights -ympäristöjä ja valitset kyseisten ympäristöjen tuloste-entiteettien tallentamisen tallennustilille, kullekin ympäristölle luodaan erilliset kansiot siten, että säilössä on ci_<environmentid>.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Muita määrityksen kopioinnissa huomioon otettavia seikkoja (esikatselu)

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
- Tietolähteet Common Data Model -kansiosta ja Common Data Service -hallitusta tallennustilasta. Nämä tietolähteet on luotava manuaalisesti samalla nimellä kuin lähdeympäristössä.

Kun kopioit ympäristön, näkyviin tulee vahvistussanoma siitä, että uusi ympäristö on luotu. Valitse **Siirry tietolähteisiin**, kun haluat nähdä tietolähteiden luettelon.

Kaikkien tietolähteiden tilana näkyy **Vaatii tunnistetietoja**. Muokkaa tietolähteitä ja päivitä ne syöttämällä tunnistetiedot.

> [!div class="mx-imgBorder"]
> ![Kopioidut tietolähteet](media/data-sources-copied.png)

Kun olet päivittänyt tietolähteet, siirry kohtaan **Tiedot** > **Yhtenäistäminen**. Siellä ovat lähdeympäristön asetukset. Voit muokata niitä tarpeen mukaan tai valita **Suorita**, jolloin tietojen yhtenäistämisprosessi alkaa ja yhtenäistetty asiakasentiteetti luodaan.

Kun tietojen yhtenäistäminen on valmis, päivitä myös kohdat **Mittarit** ja **Segmentit** siirtymällä niihin.

## <a name="edit-an-existing-environment"></a>Aiemmin luodun ympäristön muokkaaminen

Voit muokata joitakin aiemmin luotujen ympäristöjen tietoja.

1.  Valitse sovelluksen otsikossa **Ympäristö**-valitsin.

2.  Valitse **Muokkaa**-kuvake.

3. **Muokkaa ympäristöä** -ruudussa voit päivittää ympäristön **näyttönimen**, mutta et voi muuttaa **aluetta** tai **tyyppiä**.

4. Jos ympäristö on määritetty tallentamaan tiedot Azure Data Lake Storage Gen2:ään, voit päivittää **tiliavaimen**. Et voi kuitenkaan muuttaa **tilin nimeä** tai **säilön** nimeä.

5. Voit myös tehdä päivityksen käyttöoikeusavaimeen perustuvassa yhteydessä resurssi- tai tilausperusteiseen yhteyteen. Päivitykseen jälkeen ei ole mahdollista palata käyttöoikeusavaimeen. Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md). **Säilö**-tietoja ei voi muuttaa yhteyttä päivitettäessä.

## <a name="reset-an-existing-environment"></a>Aiemmin luodun ympäristön palauttaminen

Järjestelmänvalvoja voi palauttaa ympäristön tyhjään tilaan, jos haluat poistaa kaikki määritykset ja käsitellyt tiedot.

1.  Valitse sovelluksen otsikossa **Ympäristö**-valitsin. 

2.  Valitse ympäristö, jonka haluat palauttaa, ja valitse sitten kolme pistettä eli **...**. 

3. Valitse **Palauta**-vaihtoehto. 

4.  Vahvista poisto antamalla ympäristön nimi ja valitsemalla **Palauta**.

## <a name="delete-an-existing-environment-available-only-for-admins"></a>Aiemmin luodun ympäristön poistaminen (käytettävissä vain järjestelmänvalvojille)

Järjestelmänvalvoja voi poistaa myös hallitsemasi ympäristön.

1.  Valitse sovelluksen otsikossa **Ympäristö**-valitsin.

2.  Valitse ympäristö, jonka haluat palauttaa, ja valitse sitten kolme pistettä eli **...**. 

3. Valitse **Poista**-vaihtoehto. 

4.  Vahvista poisto antamalla ympäristön nimi ja valitsemalla **Poista**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]