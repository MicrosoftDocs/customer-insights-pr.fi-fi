---
title: Luo uusi ympäristö
description: Ohjeet ympäristöjen luontiin Dynamics 365 Customer Insightsissa.
ms.date: 08/15/2022
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
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304239"
---
# <a name="create-a-new-environment"></a>Luo uusi ympäristö

Kun olet [ostanut Dynamics 365 Customer Insights -tilauksen käyttöoikeuden](paid-license.md), Microsoft 365 -vuokraajan Järjestelmänvalvoja saa sähköpostiviestin, joka kutsuu hänet luomaan ympäristön. Mene osoitteeseen [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) aloittaaksesi. Tässä skenaariossa aloitetaan kohdasta [Vaihe 1: Anna perustiedot](#step-1-provide-basic-information).

Kun ensimmäinen ympäristö on luotu, Microsoft 365 -vuokraajan yleinen järjestelmänvalvoja voi [lisätä organisaation käyttäjiä järjestelmänvalvojiksi](permissions.md). Nämä järjestelmänvalvojat voivat sitten hallita käyttäjiä ja ympäristöjä. Jos organisaatiosi ostaa enemmän kuin yhden Customer Insights -lisenssin, [ota yhteyttä tukihenkilöstöömme](https://go.microsoft.com/fwlink/?linkid=2079641), jotta käytössä olevien ympäristöjen määrää voidaan lisätä. Lisätietoja kapasiteetista ja lisäkapasiteetista on [Dynamics 365:n käyttöoikeusoppaassa](https://go.microsoft.com/fwlink/?LinkId=866544). Kun pystyt luomaan lisää ympäristöjä, siirry kohtaan [Aloita ympäristön luontiprosessi](#start-the-environment-creation-process).

> [!TIP]
> Jos haluat kokeilla palvelua, katso kohta [Kokeiluympäristön määrittäminen](trial-signup.md).

## <a name="prerequisites"></a>edellytykset

[Järjestelmänvalvojan oikeudet](permissions.md) Customer Insightsissa

## <a name="start-the-environment-creation-process"></a>Ympäristön luontiprosessin käynnistäminen

1. Avaa ympäristönvalitsin ja valitse **+ Uusi**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Valitse ympäristön valitsin.":::

1. Seuraavien osien ohjatun käyttökokemuksen avulla voit antaa kaikki uuteen ympäristöön tarvittavat tiedot.

## <a name="step-1-provide-basic-information"></a>Vaihe 1: Anna perustiedot

1. Valitse, haluatko luoda ympäristön alusta asti vai kopioida tiedot toisesta ympäristöstä. [Tietojen kopioiminen toisesta ympäristöstä](#copy-the-environment-configuration) edellyttää lisävaiheita.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Valintaikkuna uuden ympäristön luomisesta Customer Insightsiin.":::

1. Anna seuraavat tiedot:

   - **Nimi**: Ympäristön nimi. Tämä kenttä on jo täytetty, jos kopioit tietoja aiemmin luodusta ympäristöstä, mutta voit muuttaa sitä.
   - **Valitse liiketoiminta**: Uuden ympäristön ensisijainen kohdeyleisö: yksittäiset kuluttajat (kuluttajakauppa) vai [yritystilit](work-with-business-accounts.md) (yritystenvälinen). Jos organisaatiosi tekee kauppaa pääasiassa yksityishenkilöiden, kuten vähittäismyyjän tai kahvilan, kanssa, valitse yksittäiset kuluttajat. Jos yrityksesi pääkäyttäjäryhmä ovat muut yritykset, kuten autotehdas tai paperiyhtiö, valitse yritystilit.
   - **Tyyppi**: Ympäristön tyyppi: tuotanto- vai eristysympäristö. Eristysympäristöt eivät salli ajoitettua tietojen päivittämistä, ja ne on tarkoitettu esikäyttöä ja testausta varten. Eristysympäristöt käyttävät samaa ensisijaista käyttäjäryhmää kuin valittu tuotantoympäristö.
   - **Alue**: Alue, jossa palvelu otetaan käyttöön ja jossa sitä isännöidään. Jotta [voit käyttää omaa Azure Data Lake Storage -tiliäsi](own-data-lake-storage.md) tai [muodostaa yhteyden olemassa olevaan Microsoft Dataverse -organisaatioon](customer-insights-dataverse.md), Customer Insights -ympäristön on oltava samalla alueella.

1. Valitse **Seuraava**.

## <a name="step-2-configure-data-storage"></a>Vaihe 2: Määritä tietojen tallennustila

1. Valitse, mihin Customer Insights -tiedot tallennetaan:

   - **Customer Insights -tallennustila**: Tietojen tallennustilaa hallitaan automaattisesti. Se on oletusvaihtoehto, ja jos tietojen tallentamisessa omaan tallennustilatiliisi ei ole erityisiä vaatimuksia, suosittelemme tämän vaihtoehdon valitsemista.
   - **Azure Data Lake Storage**: Oma Azure Data Lake Storage -tili, johon tiedot tallennetaan, jotta voit hallita tietojen tallennusta. Noudata ohjeita kohdassa [Käytä omaa Azure Data Lake Storage -tiliäsi](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Valitse haluttu vaihtoehto tietojen tallentamiseksi.":::

1. Valitse **Seuraava**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Vaihe 3: Muodosta yhteys Microsoft Dataverseen

Jos sinulla on Dataverse-ympäristö, yhdistä Customer Insights. Jaa tietoa Dataverseen käyttääksesi sitä Dataverseen perustuvissa liiketoimintasovelluksissa, kuten Dynamics 365 Marketingissa tai mallipohjaisissa sovelluksissa Power Appsissa.

1. Noudata ohjeita: [Käytä Customer Insights -tietoja Microsoft Dataversessa](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="tietojen jakaminen Microsoft Dataversen kanssa automaattisesti käytössä uusissa verkkoympäristöissä.":::

1. Valitse **Seuraava**.

## <a name="step-4-finalize-the-settings"></a>Vaihe 4: Viimeistele asetukset

Tarkista määritetyt asetukset. Kun kaikki näyttää valmiilta, valitse **Luo** asentaaksesi ympäristön.

Jos haluat muuttaa joitakin asetuksia myöhemmin, katso kohta [Ympäristöjen hallinta](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Käytä uutta ympäristöäsi

Seuraaviin artikkeleihin tutustuminen auttaa aloittamaan Customer Insightsin määrittämisen:

- [Lisää käyttäjiä ja määritä käyttöoikeuksia](permissions.md).
- [Käytä tietolähteitäsi](data-sources.md) ja suorita ne [tietojen yhdistämisprosessin](data-unification.md) avulla [yhtenäisten asiakasprofiilien](customer-profiles.md) aikaansaamiseksi.
- [Rikastuta yhtenäisiä asiakasprofiileja](enrichment-hub.md) tai [suorita ennustavia malleja](predictions-overview.md).
- [Segmenttien](segments.md) luominen asiakkaiden ryhmittelyä varten ja [mittojen](measures.md) luominen tunnuslukujen arviointia varten.
- Määritä [yhteydet](connections.md) ja [vienti](export-destinations.md), jotta voit käsitellä tietojen alijoukkoja muissa sovelluksissa.

## <a name="copy-the-environment-configuration"></a>Kopioi ympäristön määritys

Jos päätät järjestelmänvalvojana kopioida määrityksen aiemmin luodusta ympäristöstä, valitse se organisaation kaikkien käytettävissä olevien ympäristöjen luettelosta.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Näyttökuva ympäristöasetusten asetusvaihtoehdoista.":::

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

### <a name="set-up-a-copied-environment"></a>Kopioidun ympäristön määrittäminen

Kun kopioit ympäristön määrityksen, näkyviin tulee vahvistussanoma siitä, että kopioitu ympäristö on luotu. Vahvista tunnistetiedot seuraavasti.

1. Valitse **Siirry tietolähteisiin**, kun haluat nähdä tietolähteiden luettelon. Kaikkien tietolähteiden tilana näkyy **Vaatii tunnistetietoja**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Luettelo kopioiduista tietolähteistä, jotka vaativat todennusta.":::

1. Muokkaa tietolähteitä ja päivitä ne syöttämällä tunnistetiedot. Common Data Model -kansiosta ja Dataversesta peräisin olevat tietolähteet on luotava manuaalisesti samalla nimellä kuin lähdeympäristössä.

1. Kun olet päivittänyt tietolähteet, siirry kohtaan **Tiedot** > **Yhtenäistäminen**. Siellä ovat lähdeympäristön asetukset. Voit muokata niitä tarpeen mukaan tai valita **Yhtenäistä** > **Yhdistä asiakasprofiilit ja riippuvuudet**, jolloin tietojen yhtenäistämisprosessi alkaa ja yhtenäistetty asiakasentiteetti luodaan.

   > [!TIP]
   > Jos valitset tilit ja yhteyshenkilöt, valitse **Yhtenäistä tilit** > **Yhtenäistä profiilit ja riippuvuudet**.

1. Kun tietojen yhtenäistäminen on valmis, päivitä kohdat **Mittarit** ja **Segmentit** siirtymällä niihin.

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja aloita yhteyksien uudelleentodennus uudessa ympäristössä.

1. Voit aktivoida ne uudelleen siirtymällä kohtaan **Tiedot** > **Rikastus** ja **Tiedot** > **Viennit**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
