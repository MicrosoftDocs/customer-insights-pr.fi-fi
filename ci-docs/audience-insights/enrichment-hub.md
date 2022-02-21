---
title: Yhtenäisten asiakasprofiilien rikastaminen
description: Asiakastietojen rikastaminen ominaisuuksien avulla.
ms.date: 02/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5c3dda3b9bae828857258025ff79958ee22bdb6f
ms.sourcegitcommit: a399bd17523c8d06afd7d78af4fc711f93c0e8be
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/07/2022
ms.locfileid: "8098785"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Asiakasprofiilien täydentäminen (esikatselu)

Voit täydentää asiakastietoja Microsoftin ja muiden kumppaneiden kaltaisten lähteiden tiedoilla.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Rikastamiskeskuksen sivu.":::

Käytä rikastamisasetuksia valitsemalla käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Rikastaminen**.  

Sinulla on oltava osallistujan tai järjestelmänvalvojan oikeudet, jos haluat luoda tai muokata täydennyksiä. Lisätietoja on kohdassa [Oikeudet](permissions.md).

Löydät **Löydä**-välilehdestä kaikki tuetut rikastamisvaihtoehdot.

# <a name="individual-consumers-b-to-c"></a>[Yksittäiset kuluttajat (kuluttajakauppa)](#tab/b2c)

- [Tuotemerkit](enrichment-microsoft.md), jotka toimittaa Microsoft
- [Kiinnostuksen kohteet](enrichment-microsoft.md), jotka toimittaa Microsoft
- Microsoftin toimittamat [Parannetut osoitteet](enrichment-enhanced-addresses.md) 
- Experianin tarjoamat [demografiatiedot](enrichment-experian.md)
- [Tietojen mukauttaminen ](enrichment-SFTP-custom-import.md) suojatulla tiedostonsiirtoprotokollalla (SFTP) 
- Microsoftin toimittama [Azure Maps](enrichment-azure-maps.md)
- HERE Technologiesin toimittamat [sijaintitiedot](enrichment-here.md) 

# <a name="business-accounts-b-to-b"></a>[Yritystilit (yritysten väliset)](#tab/b2b)

- Leadspacen toimittamat [yritystiedot](enrichment-leadspace.md)
- Microsoftin toimittamat [Parannetut osoitteet](enrichment-enhanced-addresses.md) 
- Microsoftin tuottamat [laajennetut yritystiedot](enrichment-enhanced-company-data.md)
- HERE Technologiesin toimittamat [sijaintitiedot](enrichment-here.md) 
- [Tietojen mukauttaminen ](enrichment-SFTP-custom-import.md) suojatulla tiedostonsiirtoprotokollalla (SFTP) 
- Microsoftin toimittama [Azure Maps](enrichment-azure-maps.md)
- Microsoftin toimittamat [tilien seurantatiedot](enrichment-office.md)

---

**Omat täydennykset** -välilehdessä voit tarkastella määrittämiäsi täydennyksiä ja muokata niiden ominaisuuksia.

## <a name="manage-existing-enrichments"></a>Aiemmin luotujen rikastusten hallinta

Siirry **Omat rikastamiset** -välilehteen, jos haluat nähdä kaikki määritetyt rikastamiset. Kullakin rikastuksella on rivi, joka sisältää lisätietoja rikastamisesta.

Valitse rikastus, jos haluat nähdä käytettävissä olevat vaihtoehdot. Voit myös valita luettelokohteesta kolme pistettä (...), kun haluat nähdä vaihtoehdot. Jos olet määrittänyt useita rikasteita, voit etsiä sen nopeasti hakuruudun avulla.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Rikastusten hallinta-asetukset rikastamisluettelossa.":::

- **Näytä** rikastuksen tiedot sekä rikastettujen asiakasprofiilien määrä.
- **Muokkaa** rikastusmääritystä.
- **Suorita** asiakasprofiilien rikastaminen uusimmilla tiedoilla.
- **Poista aktivointi** aiemmin luodusta rikastuksesta, jolloin se ei enää päivity automaattisesti jokaisen ajoitetun päivityksen yhteydessä. Viimeisimmän onnistuneen päivityksen tiedot ovat edelleen käytettävissä. **Aktivoi** passiivinen rikastus, jolloin automaattinen päivitys kunkin ajoitetun päivityksen yhteydessä aloitetaan uudelleen.
- **Poista** rikastus.

Suorita useita rikasteita tai poista niiden aktivointi kerralla valitsemalla ne luettelosta. Näkymä- ja muokkausasetukset eivät ole käytettävissä joukkotoimintoina. Ne toimivat vain yhdessä rikastustyössä kerrallaan.

## <a name="enrichments-and-connections"></a>Rikastukset ja yhteydet

Kolmannen osapuolen rikastukset määritetään käyttämällä [yhteyksiä](connections.md), jotka järjestelmänvalvoja tunnistetiedoilla ja antaa tietojen siirron hyväksynnän. Järjestelmänvalvojat ja osallistujat voivat käyttää yhteyksiä rikastuksien määrittämiseen.  

## <a name="multiple-enrichments-of-the-same-type"></a>Useita samantyyppisiä rikastuksia

Rikastusmäärityksen yhteydessä määritettävä rikastettava entiteetti, joka sallii vain vain profiilien alijoukon rikastamisen. Esimerkiksi vain tietyn segmentin tietojen rikastaminen on mahdollista. Voit määrittää useita samantyyppisiä rikastuksia ja käyttää samaa yhteyttä uudelleen. Joillakin rikastuksilla on rajansa samantyyppisten rikastusten luonnin määrälle. Rajoitukset ja nykyinen käyttö näkyy **Rikastus**-sivulla.

## <a name="see-the-progress-of-the-enrichment-process"></a>Rikastusprosessin edistymisen katsominen

Voit etsiä tietoja rikastuksen käsittelystä, mukaan lukien sen tilan ja mahdolliset ongelmat päivityksen aikana tai päivityksen jälkeen. Tietoja siitä, mitkä prosessit liittyvät rikastusten päivittämiseen ja miten kauan prosessien suoritus kestää. Experian, Leadspace, HERE Technologies, SFTP-tuonti ja Azure Maps tukevat rikastamistilaa.

Rikastamistilan tarkistaminen

1. Siirry kohtaan **Tiedot** > **Täydentäminen**. 
1. Avaa sivuruutu valitsemalla **Omat rikastukset** -välilehdessä rikastuksen tila. 
1. Laajenna **Edistymisen tiedot** -ruudussa **Rikastukset**-osa. 
1. Valitse **Näytä tiedot** haluamasi rikastuksen alta tarkastellaksesi edistymistä. 
1. Valitse **Tehtävän tiedot** -ruudussa **Näytä tiedot**, kun haluat nähdä prosessit, jotka liittyvät rikastusten päivittämiseen ja niiden tilaan. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
