---
title: 'Ohje: Luo uusi ympäristö'
description: Ohjeet ympäristöjen luontiin Dynamics 365 Customer Insightsissa.
ms.date: 05/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 875cbbd095dfd239ab83c1c80db28ea7c0a04ed0
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245553"
---
# <a name="how-to-create-a-new-environment"></a>Ohje: Luo uusi ympäristö

Kun olet [ostanut Dynamics 365 Customer Insights -tilauksen käyttöoikeuden](paid-license.md), Microsoft 365 -vuokraajan Järjestelmänvalvoja saa sähköpostiviestin, joka kutsuu hänet luomaan ympäristön. Mene osoitteeseen [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) aloittaaksesi. Tässä skenaariossa voit siirtyä suoraan kohtaan [Vaihe 1: Anna perustiedot](#step-1-provide-basic-information).

Kun ensimmäinen ympäristö on luotu, Microsoft 365 -vuokraajan yleinen järjestelmänvalvoja voi [lisätä organisaatioonsa käyttäjiä järjestelmänvalvojiksi](permissions.md). Nämä järjestelmänvalvojat voivat edelleen hallita käyttäjiä ja ympäristöjä. Jos organisaatiosi ostaa enemmän kuin yhden Customer Insights -lisenssin, [ota yhteyttä tukihenkilöstöömme](https://go.microsoft.com/fwlink/?linkid=2079641), jotta käytössä olevien ympäristöjen määrää voidaan lisätä. Lisätietoja kapasiteetista ja lisäkapasiteetista on [Dynamics 365:n käyttöoikeusoppaassa](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Jos haluat kokeilla palvelua, katso kohta [Kokeiluympäristön määrittäminen](trial-signup.md).

## <a name="prerequisites"></a>edellytykset

Tarvitset [järjestelmänvalvojan oikeudet](permissions.md) Customer Insightsissa, jotta voit luoda ja hallita ympäristöjä.

## <a name="start-the-environment-creation-process"></a>Ympäristön luontiprosessin käynnistäminen

1. Avaa ympäristönvalitsin ja valitse **+ Uusi**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Valitse ympäristön valitsin.":::

1. Seuraavien osien ohjatun käyttökokemuksen avulla voit antaa kaikki uuteen ympäristöön tarvittavat tiedot. Jos olet määrittänyt aiemmin ympäristön, voit myös [kopioida määritykset](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Vaihe 1: Anna perustiedot

Valitse **Perustiedot**-vaiheessa, haluatko luoda ympäristön alusta asti vai [kopioida tiedot toisesta ympäristöstä](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Valintaikkuna uuden ympäristön luomisesta Customer Insightsiin.":::

Anna seuraavat tiedot:

- **Nimi**: Ympäristön nimi. Tämä kenttä on jo täytetty, jos kopioit tietoja aiemmin luodusta ympäristöstä, mutta voit muuttaa sitä. Jos työympäristöjä on useita, kullekin on annettava helposti tunnistettava nimi.
- **Valitse yritys**: Valitse uuden ympäristön ensisijainen käyttäjäryhmä. Kyse voi yksittäistä kuluttajista (kuluttajakauppa) tai [yritystilistä](work-with-business-accounts.md) (yritystenvälinen kauppa). Jos organisaatiosi tekee kauppaa pääasiassa yksityishenkilöiden, kuten vähittäismyyjän tai kahvilan, kanssa, valitse yksittäiset kuluttajat. Jos yrityksesi pääkäyttäjäryhmä ovat muut yritykset, kuten autotehdas tai paperiyhtiö, valitse yritystilit.
- **Tyyppi**: Määritä, haluatko luoda tuotanto- vai eristysympäristön. Eristysympäristöt eivät salli ajoitettua tietojen päivittämistä, ja ne on tarkoitettu esikäyttöä ja testausta varten. Eristysympäristöt käyttävät samaa ensisijaista käyttäjäryhmää kuin valittu tuotantoympäristö.
- **Alue**: Alue, jossa palvelu otetaan käyttöön ja jossa sitä isännöidään. Jotta [voit käyttää omaa Azure Data Lake Storage -tiliäsi](own-data-lake-storage.md) tai [muodostaa yhteyden olemassa olevaan Microsoft Dataverse -organisaatioon](customer-insights-dataverse.md), Customer Insights -ympäristön on oltava samalla alueella.

## <a name="step-2-configure-data-storage"></a>Vaihe 2: Määritä tietojen tallennustila

Valitse **Tietojen tallennustila** -vaiheessa, mihin tiedot Customer Insightsin tiedot tallennetaan.

Valittavana on kaksi vaihtoehtoa:

- **Customer Insights -tallennustila**: Tietojen tallennustilaa hallinnoi Customer Insights -ryhmä. Se on oletusvaihtoehto, ja jos tietojen tallentamisessa omaan tallennustilatiliisi ei ole erityisiä vaatimuksia, suosittelemme tämän vaihtoehdon valitsemista.
- **Azure Data Lake Storage**: Määritä oma Azure Data Lake Storage -tili, johon tiedot tallennetaan, jotta voit hallita tietojen tallennusta. Lisätietoja on ohjeaiheessa [Oman Azure Data Lake Storage -tilin käyttö](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Valitse haluttu vaihtoehto tietojen tallentamiseksi.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Vaihe 3: Muodosta yhteys Microsoft Dataverseen

Tässä **Microsoft Dataverse** -vaiheessa voit yhdistää Customer Insightsin Dataverse-ympäristöösi. Jaa tietoa Dataverseen käyttääksesi sitä Dataverseen perustuvissa liiketoimintasovelluksissa, kuten Dynamics 365 Marketingissa tai mallipohjaisissa sovelluksissa Power Appsissa.

Jätä tämä kenttä tyhjäksi, jos sinulla ei ole omaa Dataverse -ympäristöä, jolloin luomme sellaisen sinulle.

Lisätietoja on kohdassa [Customer Insights -tietojen käsittely Microsoft Dataversessä](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="tietojen jakaminen Microsoft Dataversen kanssa automaattisesti käytössä uusissa verkkoympäristöissä.":::

### <a name="step-4-finalize-the-settings"></a>Vaihe 4: Viimeistele asetukset

Käy **Tarkista**-vaiheessa läpi kaikki määritetyt asetukset. Kun kaikki näyttää valmiilta, valitse **Luo** asentaaksesi ympäristön.

Voit muuttaa joitakin asetuksia myöhemmin. Lisätietoja on kohdassa [Ympäristöjen hallinta](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Käytä uutta ympäristöäsi

Seuraaviin artikkeleihin tutustuminen auttaa aloittamaan Customer Insightsin määrittämisen:

- [Lisää käyttäjiä ja määritä käyttöoikeuksia](permissions.md).
- [Käytä tietolähteitäsi](data-sources.md) ja suorita ne [tietojen yhdistämisprosessin](data-unification.md) avulla [yhtenäisten asiakasprofiilien](customer-profiles.md) aikaansaamiseksi.
- [Rikastuta yhtenäisiä asiakasprofiileja](enrichment-hub.md) tai [suorita ennustavia malleja](predictions-overview.md).
- [Segmenttien](segments.md) luominen asiakkaiden ryhmittelyä varten ja [mittojen](measures.md) luominen tunnuslukujen arviointia varten.
- Määritä [yhteydet](connections.md) ja [vienti](export-destinations.md), jotta voit käsitellä tietojen alijoukkoja muissa sovelluksissa.

## <a name="copy-the-environment-configuration"></a>Kopioi ympäristön määritys

Järjestelmänvalvojana voit kopioida määrityksen aiemmin luodusta ympäristöstä, kun luot uuden.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Näyttökuva ympäristöasetusten asetusvaihtoehdoista.":::

Näkyviin tulee luettelo kaikista organisaation käytettävissä olevista ympäristöistä, joista voit kopioida tietoja.

Seuraavat määritysasetukset kopioidaan:

- Power Queryn kautta tuodut tietolähteet
- Tietojen yhdistämisen määritys
- Segments
- Mittarit
- Suhteet
- Toiminnat
- Hae ja suodata indeksi
- Viennit
- Päivitä aikataulu
- Rikastukset
- Ennustemallit
- Roolimääritykset

## <a name="set-up-a-copied-environment"></a>Kopioidun ympäristön määrittäminen

Kun kopioit ympäristön määrityksen, sinun on vahvistettava tunnistetiedot käydessäsi läpi joitakin ylimääräisiä vaiheita:

- Asiakasprofiilit. Todenna ja lisää ensin tietolähteet ja suorita tietojen yhdistäminen, jotta asiakasprofiilit voidaan luoda uudelleen.
- Tietolähteen tunnistetiedot. Jokaisen käyttäjän tunnistetiedot on annettava, jotta tietolähteet voi todentaa ja päivittää manuaalisesti.
- Tietolähteet Common Data Model -kansiosta ja Dataversestä. Nämä tietolähteet on luotava manuaalisesti samalla nimellä kuin lähdeympäristössä.
- Yhteyksiin liittyvät salaisuudet, joita käytetään viennissä ja rikastamisissa. Yhteyksien todennus on suoritettava uudelleen ja sitten rikastamisen ja viennit on aktivoitava uudelleen.

Näyttöön tulee vahvistussanoma, kun kopioitu ympäristö on luotu. Valitse **Siirry tietolähteisiin**, kun haluat nähdä tietolähteiden luettelon.

Kaikkien tietolähteiden tilana näkyy **Vaatii tunnistetietoja**. Muokkaa tietolähteitä ja päivitä ne syöttämällä tunnistetiedot.

:::image type="content" source="media/data-sources-copied.png" alt-text="Luettelo kopioiduista tietolähteistä, jotka vaativat todennusta.":::

Kun olet päivittänyt tietolähteet, siirry kohtaan **Tiedot** > **Yhtenäistäminen**. Siellä ovat lähdeympäristön asetukset. Voit muokata niitä tarpeen mukaan tai valita **Suorita**, jolloin tietojen yhtenäistämisprosessi alkaa ja yhtenäistetty asiakasentiteetti luodaan.

Kun tietojen yhtenäistäminen on valmis, päivitä myös kohdat **Mittarit** ja **Segmentit** siirtymällä niihin.

Ennen kuin aktivoit viennit ja rikastamisen uudelleen, siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja aloita yhteyksien uudelleentodennus uudessa ympäristössä.

[!INCLUDE [footer-include](includes/footer-banner.md)]
