---
title: Yhtenäisten asiakasprofiilien rikastaminen
description: Asiakastietojen rikastaminen ominaisuuksien avulla.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896001"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Asiakasprofiilien täydentäminen (esikatselu)

Voit täydentää asiakastietoja Microsoftin ja muiden kumppaneiden kaltaisten lähteiden tiedoilla.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Rikastamiskeskuksen sivu":::

Käytä rikastamisasetuksia valitsemalla käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Rikastaminen**.    
Sinulla on oltava osallistujan tai järjestelmänvalvojan oikeudet, jos haluat luoda tai muokata täydennyksiä. Lisätietoja on kohdassa [Oikeudet](permissions.md).

**Tutustu**-välilehdessä ovat seuraavat täydennykset:

- [Tuotemerkit](enrichment-microsoft.md), jotka toimittaa Microsoft
- [Kiinnostuksen kohteet](enrichment-microsoft.md), jotka toimittaa Microsoft
- Leadspacen toimittamat [yritystiedot](enrichment-leadspace.md)
- Experianin toimittamat [demografiatiedot](enrichment-experian.md)
- HERE Technologiesin toimittamat [sijaintitiedot](enrichment-here.md)
- [Tietojen mukauttaminen ](enrichment-SFTP-custom-import.md) suojatulla tiedostonsiirtoprotokollalla (SFTP)

**Omat täydennykset** -välilehdessä voit tarkastella määrittämiäsi täydennyksiä ja muokata niiden ominaisuuksia.

## <a name="manage-existing-enrichments"></a>Aiemmin luotujen rikastusten hallinta

Saat kaikki määritetyt rikastukset käyttöön valitsemalla **Omat rikastukset**. Kullakin rikastuksella on rivi, joka sisältää lisätietoja rikastamisesta.

Saat käytettävissä olevat vaihtoehdot näkyviin valitsemalla rikastuksen. Voit myös valita luettelokohteesta kolme pistettä (...), kun haluat nähdä vaihtoehdot.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Rikastusten hallinta-asetukset rikastamisluettelossa":::

- **Näytä** rikastuksen tiedot sekä rikastettujen asiakasprofiilien määrä.
- **Muokkaa** rikastusmääritystä.
- **Suorita** asiakasprofiilien rikastaminen uusimmilla tiedoilla.
- **Poista aktivointi** aiemmin luodusta rikastuksesta, jolloin se ei enää päivity automaattisesti jokaisen ajoitetun päivityksen yhteydessä. Viimeisimmän onnistuneen päivityksen tiedot ovat edelleen käytettävissä. **Aktivoi** passiivinen rikastus, jolloin automaattinen päivitys kunkin ajoitetun päivityksen yhteydessä aloitetaan uudelleen.
- **Poista** rikastus.

Useita rikastamisia voi suorittaa tai poistaa käytöstä samanaikaisesti valitsemalla ne luettelossa. Näyttämis- ja muokkausvaihtoehtoja ei voi käyttää joukkotoimintoja, vaan niitä voi käyttää kerralla vain yhdessä rikastamisessa.

## <a name="enrichments-and-connections"></a>Rikastukset ja yhteydet

Kolmannen osapuolen rikastukset määritetään käyttämällä [yhteyksiä](connections.md), jotka järjestelmänvalvoja tunnistetiedoilla ja antaa tietojen siirron hyväksynnän. Tämän jälkeen sekä järjestelmänvalvojat että osallistujat voivat käyttää yhteyttä rikastusten määrittämiseen.  

## <a name="multiple-enrichments-of-the-same-type"></a>Useita samantyyppisiä rikastuksia

Rikastusmäärityksen yhteydessä määritettävä rikastettava entiteetti, joka sallii vain vain profiilien alijoukon rikastamisen. Voit rikastaa tiedot esim. vain tiettyä segmenttiä varten. Voit määrittää useita samantyyppisiä rikastuksia ja käyttää samaa yhteyttä uudelleen. Joillakin rikastuksilla on rajansa samantyyppisten rikastusten luonnin määrälle. Rajoitukset ja nykyinen käyttö näkyy **Rikastus**-sivulla.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
