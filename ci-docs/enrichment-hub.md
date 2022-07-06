---
title: Tietojen rikastamisen (esiversio) yleiskatsaus
description: Asiakastietoja voi rikastaa Microsoftin ja muiden kolmannen osapuolen palvelujen ominaisuuksia käyttämällä.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 6b6daab480db5e37830ff58b71dcdd3bbdbe46da
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053860"
---
# <a name="data-enrichment-preview-overview"></a>Tietojen rikastamisen (esiversio) yleiskatsaus

Voit täydentää asiakastietoja Microsoftin ja muiden kumppaneiden kaltaisten lähteiden tiedoilla. Kolmannen osapuolen rikastukset määritetään käyttämällä [yhteyksiä](connections.md), jotka järjestelmänvalvoja tunnistetiedoilla ja antaa tietojen siirron hyväksynnän. Järjestelmänvalvojat ja osallistujat voivat käyttää yhteyksiä rikastuksien määrittämiseen.  

## <a name="multiple-enrichments-of-the-same-type"></a>Useita samantyyppisiä rikastuksia

Rikastusmäärityksen yhteydessä määritettävä rikastettava entiteetti, joka sallii vain vain profiilien alijoukon rikastamisen. Esimerkiksi vain tietyn segmentin tietojen rikastaminen on mahdollista. Voit määrittää useita samantyyppisiä rikastuksia ja käyttää samaa yhteyttä uudelleen. Joillakin rikastuksilla on rajansa samantyyppisten rikastusten luonnin määrälle. Rajat ja nykyinen käyttö on nähtävillä jokaisessa **Rikastaminen**-sivun **Tutustu**-välilehden ruudussa.

## <a name="enrich-data-sources-before-unification"></a>Tietolähteiden rikastus ennen yhdistämistä

Voit rikastaa asiakastietoja ennen tietojen yhdistämistä, mikä parantaa tietojen vastaavuuden laatua. Lisätietoja: [tietolähteiden rikastus](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Luo rikastus

Rikastamisten luomiseen tai muokkaamiseen tarvitaan osallistujan tai järjestelmänvalvojan [oikeudet](permissions.md).

Siirry kohtaan **Tiedot** > **Täydentäminen**. Kaikki tuetut rikastamisvaihtoehdot näkyvät **Tutustu**-välilehdessä.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Rikastamiskeskuksen sivu.":::

# <a name="individual-consumers-b-to-c"></a>[Yksittäiset kuluttajat (kuluttajakauppa)](#tab/b2c)

- [AbiliTec-käyttäjätiedot](enrichment-liveramp.md) toimittaa LiveRamp AbiliTec
- [Tuotemerkit](enrichment-microsoft.md), jotka toimittaa Microsoft
- Experianin tarjoamat [demografiatiedot](enrichment-experian.md)
- Microsoftin toimittamat [Parannetut osoitteet](enrichment-enhanced-addresses.md)
- [Kiinnostuksen kohteet](enrichment-microsoft.md), jotka toimittaa Microsoft
- [Sijaintitiedot](enrichment-azure-maps.md) toimittaa Microsoft Azure -kartat
- HERE Technologiesin toimittamat [sijaintitiedot](enrichment-here.md)
- [Mukautetut SFTP-tiedot](enrichment-SFTP-custom-import.md) suojatun tiedostonsiirtoprotokollan (SFTP) avulla

# <a name="business-accounts-b-to-b"></a>[Yritystilit (yritysten väliset)](#tab/b2b)

- Microsoftin toimittamat [tilien seurantatiedot](enrichment-office.md)
- [Yritystiedot](enrichment-dnb.md) toimittajalta Dun & Bradstreet
- Leadspacen toimittamat [yritystiedot](enrichment-leadspace.md)
- Microsoftin toimittamat [Parannetut osoitteet](enrichment-enhanced-addresses.md)
- Microsoftin tuottamat [laajennetut yritystiedot](enrichment-enhanced-company-data.md)
- [Sijaintitiedot](enrichment-azure-maps.md) toimittaa Microsoft Azure -kartat
- HERE Technologiesin toimittamat [sijaintitiedot](enrichment-here.md)
- [Mukautetut SFTP-tiedot](enrichment-SFTP-custom-import.md) suojatun tiedostonsiirtoprotokollan (SFTP) avulla

---

## <a name="manage-existing-enrichments"></a>Aiemmin luotujen rikastusten hallinta

Siirry kohtaan **Tiedot** > **Täydentäminen**. **Omat rikastukset** -välilehdessä voi tarkastella määritettyjä rikastuksia, niiden tiloja, rikastettujen asiakkaiden määrää ja tietojen viimeisintä rikastamispäivää. Rikastamisluetteloa voi lajitella minkä tahansa sarakkeen perustella. Hallittavan rikastamisen voi etsiä myös hakuruutua käyttämällä.

Voit tarkastella käytettävissä olevia toimintoja valitsemalla rikastuksen.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Rikastusten hallinta-asetukset rikastamisluettelossa.":::

- **Näytä** rikastuksen tiedot sekä rikastettujen asiakasprofiilien määrä.
- **Muokkaa** rikastusmääritystä.
- Päivitä uusimmat tiedot asiakasprofiileihin [**suorittamalla**](#run-or-refresh-enrichments) rikastus. Suorita useita rikastuksia samanaikaisesti valitsemalla ne luettelossa.
- **Aktivoi** rikastus tai **poista sen aktivointi**. Passiivisia rikastuksia ei päivitetä [ajoitetun päivityksen](system.md#schedule-tab) aikana.
- **Poista** rikastus.

Rikastuksista voi luoda myös [segmenttejä](segments.md) tai [mittareita](measures.md).

## <a name="run-or-refresh-enrichments"></a>Rikastusten suorittaminen tai päivittäminen

Suoritetut rikastukset voidaan päivittää automaattisesti aikataulun mukaisesti ja manuaalisesti tarvittaessa.

1. Rikastukset päivitetään manuaalisesti valitsemalla ensin ne ja sitten **Suorita**. [Automaattinen päivitys ajoitetaan](system.md#schedule-tab) valitsemalla **Hallinta** > **Järjestelmä** > **Aikatauluta**. Käsittelyaika riippuu asiakastietojen koosta.

1. Vaihtoehtoisesti voit [tarkastella rikastamisprosessin etenemistä](#see-the-progress-of-the-enrichment-process).

1. Valitse rikastamisprosessin päättymisen jälkeen **Omat rikastukset**. Voit tarkastella juuri rikastettujen asiakasprofiilien tietoja, viimeisimmän päivityksen ajankohtaa ja rikastettujen profiilien määrää.

1. Tarkastele [rikastustuloksia](#view-enrichment-results) valitsemalla rikastus.

### <a name="see-the-progress-of-the-enrichment-process"></a>Rikastusprosessin edistymisen katsominen

Voit etsiä tietoja rikastuksen käsittelystä, mukaan lukien sen tilan ja mahdolliset ongelmat päivityksen aikana tai päivityksen jälkeen. Tietoja siitä, mitkä prosessit liittyvät rikastusten päivittämiseen ja miten kauan prosessien suoritus kestää. Experian, Leadspace, HERE Technologies, SFTP-tuonti ja Azure Maps tukevat rikastamistilaa.

1. Siirry kohtaan **Tiedot** > **Täydentäminen**.
1. Avaa sivuruutu valitsemalla **Omat rikastukset** -välilehdessä rikastuksen tila.
1. Laajenna **Edistymisen tiedot** -ruudussa **Rikastukset**-osa.
1. Valitse **Näytä tiedot** haluamasi rikastuksen alta tarkastellaksesi edistymistä.
1. Valitse **Tehtävän tiedot** -ruudussa **Näytä tiedot**, kun haluat nähdä prosessit, jotka liittyvät rikastusten päivittämiseen ja niiden tilaan.

## <a name="view-enrichment-results"></a>Rikastamisen tulosten tarkasteleminen

Tutustu rikastamisen tuloksiin, kun rikastaminen on suoritettu loppuun.

1. Siirry kohtaan **Tiedot** > **Täydentäminen**.
1. Valitse **Omat rikastukset** -välilehdessä tarkasteltava rikastus.

Kaikissa rikastamisissa on näkyvissä perustiedot, kuten lisättyjen profiilien määrä ja rikastettujen profiilien määrän ajan mittaan. **Rikastettujen asiakkaiden esikatselu** -ruudussa näkyy esimerkki luodusta rikastusentiteetistä. Yksityiskohtaista näkymää voi tarkastella valitsemalla ensin **Näytä lisää** ja sitten **Tiedot**-välilehti.

:::image type="content" source="media/enrichments-results.png" alt-text="Rikastusten tulossivu.":::

Jos mahdollista, **Rikastettujen asiakkaiden määrä kentän mukaan** tarjoaa porautumisen kunkin rikastetun kentän kattavuuteen.

Jotkin rikastukset näyttävät myös tiedot, jotka liittyvät rikastuksen tyyppiin. Lisätietoja on liittyvissä ohjeissa.

[!INCLUDE [footer-include](includes/footer-banner.md)]
