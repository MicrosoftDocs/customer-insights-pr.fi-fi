---
title: Luo ja hallitse ympäristöjä
description: Tietoja palveluun rekisteröitymisestä ja ympäristöjen hallinnasta.
ms.date: 02/09/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 4f4e5a8415f6c2128b0480edf67f317124eeeba9
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376872"
---
# <a name="manage-environments"></a>Ympäristöjen hallinta

## <a name="switch-environments"></a>Ympäristöjen vaihtaminen

Voit vaihtaa ympäristöä valitsemalla sivun oikeassa yläkulmassa **Ympäristöt**.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Näyttökuva ohjausobjektista, jonka avulla voit vaihtaa ympäristöä.":::

Järjestelmänvalvojat voivat [Luoda](create-environment.md) ja hallita ympäristöjä.

## <a name="edit-an-existing-environment"></a>Aiemmin luodun ympäristön muokkaaminen

Voit muokata joitakin aiemmin luotujen ympäristöjen tietoja.

1.  Valitse sovelluksen otsikossa **Ympäristö**-valitsin.

2.  Valitse **Muokkaa**-kuvake.

3. Voit päivittää ympäristön asetuksia **Muokkaa ympäristöä** -ruudussa.

Lisätietoja ympäristön asetuksista on kohdassa [Uuden ympäristön luominen](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Yhdistä Microsoft Dataverseen
   
Tässä **Microsoft Dataverse** -vaiheessa voit yhdistää Customer Insightsin Dataverse-ympäristöösi.

Jos haluat käyttää [valmiita ennustemalleja](predictions-overview.md#out-of-box-models), määritä tietojen jakaminen Dataversen kanssa. Voit myös ottaa käyttöön tietojen käsittelyn paikallisista tietolähteistä antamalla organisaatiosi hallinnoiman Microsoft Dataverse -ympäristön URL-osoitteen.

> [!IMPORTANT]
> Customer Insightsin ja Dataversen on oltava samalla alueella, jotta tietojen jakaminen voidaan ottaa käyttöön.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Määritysvalinnat tietojen jakamista varten Microsoft Dataversen kanssa.":::

> [!NOTE]
> Customer Insights ei tue seuraavia tietojen jakamisen skenaarioita:
> - Jos tallennat kaikki tiedot omaan Azure Data Lake Storageen, et voi ottaa käyttöön tietojen jakamista Dataversen hallitun Data Laken kanssa.
> - Jos otat käyttöön tietojen jakamisen Dataversen kanssa, et voi [luoda ennustettuja tai puuttuvia arvoja entiteetissä](predictions.md).

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

- Tietolähteet Common Data Model -kansiosta ja Dataversen hallitusta Data Lake -tallennustilasta. Nämä tietolähteet on luotava manuaalisesti samalla nimellä kuin lähdeympäristössä.

Kun kopioit ympäristön, näkyviin tulee vahvistussanoma siitä, että uusi ympäristö on luotu. Valitse **Siirry tietolähteisiin**, kun haluat nähdä tietolähteiden luettelon.

Kaikkien tietolähteiden tilana näkyy **Vaatii tunnistetietoja**. Muokkaa tietolähteitä ja päivitä ne syöttämällä tunnistetiedot.

:::image type="content" source="media/data-sources-copied.png" alt-text="Luettelo kopioiduista tietolähteistä, jotka vaativat todennusta.":::

Kun olet päivittänyt tietolähteet, siirry kohtaan **Tiedot** > **Yhtenäistäminen**. Siellä ovat lähdeympäristön asetukset. Voit muokata niitä tarpeen mukaan tai valita **Suorita**, jolloin tietojen yhtenäistämisprosessi alkaa ja yhtenäistetty asiakasentiteetti luodaan.

Kun tietojen yhtenäistäminen on valmis, päivitä myös kohdat **Mittarit** ja **Segmentit** siirtymällä niihin.

## <a name="change-the-owner-of-an-environment"></a>Ympäristön omistajan muuttaminen

Vaikka useilla käyttäjillä voi olla järjestelmänvalvojan oikeudet Customer Insightsissa, vain yksi käyttäjä on ympäristön omistaja. Oletusarvon mukaan järjestelmänvalvoja luo ympäristön. Ympäristön järjestelmänvalvojana voit delegoida omistuksen toiselle käyttäjälle, jolla on järjestelmänvalvojan oikeudet.

1. Valitse sovelluksen otsikossa **Ympäristö**-valitsin.

1. Valitse **Muokkaa**-kuvake.

1. Siirry **Muokkaa ympäristöä** -ruudussa **Perustiedot**-vaiheeseen.

1. Valitse **Muuta ympäristön omistajaa** -kentässä ympäristön uusi omistaja.  

1. Valitse **Tarkasta ja viimeistele** ja sitten **Päivitä** ottaaksesi muutokset käyttöön. 

## <a name="claim-ownership-of-an-environment"></a>Ympäristön omistajuuden vaatiminen

Jos ympäristön omistaja lähtee organisaatiosta tai hänen tilinsä poistetaan, ympäristöllä ei ole omistajaa. Käyttäjä, jolla on järjestelmänvalvojan oikeudet, voi vaatia omistajuuden ja hänestä voi tulla uusi omistaja. Hän voi jatkaa ympäristön omistajana tai [vaihtaa omistuksen toiselle järjestelmänvalvojalle](#change-the-owner-of-an-environment). 

Vaadi omistus valitsemalla **Ota omistus** -painike, joka näkyy jokaisen Customer Insights -sivun yläosassa, kun alkuperäinen omistaja on lähtenyt organisaatiosta.

## <a name="reset-an-existing-environment"></a>Aiemmin luodun ympäristön palauttaminen

Ympäristön omistajana voit nollata ympäristön tyhjään tilaan, jos haluat poistaa kaikki määritykset ja poistaa käytetyt tiedot.

1.  Valitse sovelluksen otsikossa **Ympäristö**-valitsin. 

2.  Valitse ympäristö, jonka haluat palauttaa, ja valitse sitten kolme pistettä (**...**). 

3. Valitse **Palauta**-vaihtoehto. 

4.  Vahvista poisto antamalla ympäristön nimi ja valitsemalla **Palauta**.

## <a name="delete-an-existing-environment"></a>Olemassa olevan ympäristön poistaminen

Ympäristön omistajana voit poistaa ympäristön, jonka järjestelmänvalvoja olet.

1.  Valitse sovelluksen otsikossa **Ympäristö**-valitsin.

2.  Valitse ympäristö, jonka haluat palauttaa, ja valitse sitten kolme pistettä (**...**). 

3. Valitse **Poista**-vaihtoehto. 

4.  Vahvista poisto antamalla ympäristön nimi ja valitsemalla **Poista**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
