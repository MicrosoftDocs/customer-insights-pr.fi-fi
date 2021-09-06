---
title: Yhtenäisten asiakasprofiilien rikastaminen
description: Asiakastietojen rikastaminen ominaisuuksien avulla.
ms.date: 07/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: a64bbd754d4013d0a6243074ac9f55991547be82b269047a9937b583baf98697
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032524"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Asiakasprofiilien täydentäminen (esikatselu)

Voit täydentää asiakastietoja Microsoftin ja muiden kumppaneiden kaltaisten lähteiden tiedoilla.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Rikastamiskeskuksen sivu.":::

Käytä rikastamisasetuksia valitsemalla käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Rikastaminen**.  

Sinulla on oltava osallistujan tai järjestelmänvalvojan oikeudet, jos haluat luoda tai muokata täydennyksiä. Lisätietoja on kohdassa [Oikeudet](permissions.md).

**Tutustu**-välilehdessä ovat seuraavat täydennykset:

- [Tuotemerkit](enrichment-microsoft.md), jotka toimittaa Microsoft
- [Kiinnostuksen kohteet](enrichment-microsoft.md), jotka toimittaa Microsoft
- Microsoftin toimittamat [Parannetut osoitteet](enrichment-enhanced-addresses.md)
- Leadspacen toimittamat [yritystiedot](enrichment-leadspace.md)
- Experianin tarjoamat [demografiatiedot](enrichment-experian.md)
- HERE Technologiesin toimittamat [sijaintitiedot](enrichment-here.md)
- [Tietojen mukauttaminen ](enrichment-SFTP-custom-import.md) suojatulla tiedostonsiirtoprotokollalla (SFTP)

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

Kolmannen osapuolen rikastukset määritetään käyttämällä [yhteyksiä](connections.md), jotka järjestelmänvalvoja tunnistetiedoilla ja antaa tietojen siirron hyväksynnän. Tämän jälkeen sekä järjestelmänvalvojat että osallistujat voivat käyttää yhteyttä rikastusten määrittämiseen.  

## <a name="multiple-enrichments-of-the-same-type"></a>Useita samantyyppisiä rikastuksia

Rikastusmäärityksen yhteydessä määritettävä rikastettava entiteetti, joka sallii vain vain profiilien alijoukon rikastamisen. Esimerkiksi vain tietyn segmentin tietojen rikastaminen on mahdollista. Voit määrittää useita samantyyppisiä rikastuksia ja käyttää samaa yhteyttä uudelleen. Joillakin rikastuksilla on rajansa samantyyppisten rikastusten luonnin määrälle. Rajoitukset ja nykyinen käyttö näkyy **Rikastus**-sivulla.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
