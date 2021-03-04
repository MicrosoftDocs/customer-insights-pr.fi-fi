---
title: Yhtenäisten asiakasprofiilien rikastaminen
description: Asiakastietojen rikastaminen ominaisuuksien avulla.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269464"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Asiakasprofiilien täydentäminen (esikatselu)

Voit täydentää asiakastietoja Microsoftin ja muiden kumppaneiden kaltaisten lähteiden tiedoilla.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Rikastamiskeskuksen sivu":::

Käytä rikastamisasetuksia valitsemalla käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Rikastaminen**.    
Sinulla on oltava osallistujan tai järjestelmänvalvojan oikeudet, jos haluat luoda tai muokata täydennyksiä. Lisätietoja on kohdassa [Oikeudet](permissions.md).

**Tutustu**-välilehdessä ovat seuraavat täydennykset:

- Microsoft Graphin toimittamat [tuotemerkit](enrichment-microsoft-graph.md)
- Microsoft Graphin toimittamat [kiinnostuksen kohteet](enrichment-microsoft-graph.md)
- Leadspacen toimittamat [yritystiedot](enrichment-leadspace.md)
- Experianin toimittamat [demografiatiedot](enrichment-experian.md)
- HERE Technologiesin toimittamat [sijaintitiedot](enrichment-here.md)
- [Tietojen mukauttaminen ](enrichment-SFTP-custom-import.md) suojatulla tiedostonsiirtoprotokollalla (SFTP)

**Omat täydennykset** -välilehdessä voit tarkastella määrittämiäsi täydennyksiä ja muokata niiden ominaisuuksia.

## <a name="manage-existing-enrichments"></a>Aiemmin luotujen rikastusten hallinta

Saat kaikki määritetyt rikastukset käyttöön valitsemalla **Omat rikastukset**. Kullakin rikastuksella on rivi, joka sisältää lisätietoja rikastamisesta.

Saat käytettävissä olevat vaihtoehdot näkyviin valitsemalla rikastuksen. Vaihtoehtoisesti saat vaihtoehdot näkyviin valitsemalla luettelossa kolme pistettä (...).

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Rikastusten hallinta-asetukset rikastamisluettelossa":::

- **Näytä** rikastuksen tiedot sekä rikastettujen asiakasprofiilien määrä.
- **Muokkaa** rikastusmääritystä.
- **Suorita** asiakasprofiilien rikastaminen uusimmilla tiedoilla.
- **Poista aktivointi** aiemmin luodusta rikastuksesta, jolloin se ei enää päivity automaattisesti jokaisen ajoitetun päivityksen yhteydessä. Viimeisimmän onnistuneen päivityksen tiedot ovat edelleen käytettävissä. **Aktivoi** passiivinen rikastus, jolloin automaattinen päivitys kunkin ajoitetun päivityksen yhteydessä aloitetaan uudelleen.
- **Poista** rikastus.

Useita rikastamisia voi suorittaa tai poistaa käytöstä samanaikaisesti valitsemalla ne luettelossa. Näyttämis- ja muokkausvaihtoehtoja ei voi käyttää joukkotoimintoja, vaan niitä voi käyttää kerralla vain yhdessä rikastamisessa.


[!INCLUDE[footer-include](../includes/footer-banner.md)]