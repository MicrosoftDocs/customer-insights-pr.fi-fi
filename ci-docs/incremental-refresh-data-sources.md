---
title: Power Queryyn perustuvien tietolähteiden lisäävä päivitys
description: Power Queryyn perustuvien suurten tietolähteiden uusien ja päivitettyjen tietojen päivittäminen.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646326"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Power Queryyn perustuvien tietolähteiden lisäävä päivitys

Tässä artikkelissa käsitellään Power Queryyn perustuvien tietolähteiden lisäävän päivityksen määrittämistä.

Tietolähteiden lisäävän päivityksen edut:

- **Päivitysten nopeutuminen** – Vain muuttuneet tiedot päivitetään. Esimerkiksi historiallisessa tietojoukossa päivitetään vain viisi viimeisintä päivää.
- **Parantuntu luotettavuus** – koska päivitykset ovat pienempiä, yhteyksiä epävakaisiin lähdejärjestelmiin ei tarvitse ylläpitää yhtä pitkään, mikä vähentää yhteysongelmien riskiä.
- **Resurssin kulutus vähenee** – vain kaikkien tietojen alijoukon päivittäminen tehostaa laskentaresurssien käyttöä ja vähentää ympäristön rasitusta.

## <a name="configure-incremental-refresh"></a>Lisäävän päivityksen määrittäminen

Customer Insights sallii Power Queryn kautta tuotujen, lisäävää käsittelyä tukevien tietolähteiden lisäävän päivityksen. Esimerkiksi Azure SQL -tietokannat, joiden päivämäärä- ja aikakentät ilmaisevat, milloin tietotietueet päivitettiin viimeksi.

1. [Luo uusi Power Queryyn perustuva tietolähde](connect-power-query.md).

1. Anna tietolähteelle **Nimi**.

1. Valitse lisäävää päivitystä tukeva tietolähde, kuten [Azure SQL -tietokanta](/power-query/connectors/azuresqldatabase).

1. Valitse käsiteltävät entiteetit tai taulukot.

1. Tee muunnoksen vaiheet ja valitse **Seuraava**.

1. Avaa **Lisäävän päivityksen asetukset** valitsemalla **Määritä lisäävä päivitys** -valintaikkunassa **Määritä**. Jos valitset **Ohita**, tietolähde päivittää koko tietojoukon.
   > [!TIP]
   > Voit käyttää lisäävää päivitystä myös myöhemmin muokkaamalla aiemmin luotua tietolähdettä.

1. **Lisäävän päivityksen asetukset** -kohdassa määritetään kaikkien tietolähdettä luotaessa valittujen entiteettien lisäävä päivitys.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Tietolähteen entiteettien määrittäminen lisäävää päivitystä varten.":::

1. Valitse entiteetti ja anna seuraavat tiedot:

   - **Valitse ensisijainen avain**: valitse entiteetin tai taulukon perusavain.
   - **Määritä viimeksi päivitetty -kenttä**: Tässä kentässä näytetään vain päivämäärä- ja aikatyypin määritteitä. Valitse määrite, joka ilmaisee, milloin tietueet viimeksi päivitettiin. Sen avulla määritetään tietueet, jotka sijoittuvat lisäävän päivityksen aikavälille.
   - **Etsi päivityksiä joka**: määritä, kuinka pitkä lisäävän päivityksen aikaväli on.

1. Viimeistele tietolähteen luonti valitsemalla **Tallenna**. Ensimmäinen tietojen päivitys on täydellinen päivitys. Sen jälkeen tietojen lisäävä päivitys tapahtuu edellisessä vaiheessa määritetyllä tavalla.


[!INCLUDE [footer-include](includes/footer-banner.md)]
