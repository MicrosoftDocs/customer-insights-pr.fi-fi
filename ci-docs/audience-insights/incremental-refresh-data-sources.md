---
title: Power Query -pohjaisten tietolähteiden lisäävä päivitys
description: Power Queryyn perustuvien suurten tietolähteiden uusien ja päivitettyjen tietojen päivittäminen.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: f614d701aeb06720a60b14549a7fe666f8fe0617
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900251"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Power Queryyn perustuvien tietolähteiden lisäävä päivitys

Tässä artikkelissa käsitellään Power Query perustuvien tietolähteiden lisäävän päivityksen määrittämistä.

Tietolähteiden lisäävän päivityksen edut:

- **Päivitysten nopeutuminen** – Vain muuttuneet tiedot päivitetään. Esimerkiksi historiallisessa tietojoukossa päivitetään vain viisi viimeisintä päivää.
- **Parantuntu luotettavuus** – koska päivitykset ovat pienempiä, yhteyksiä epävakaisiin lähdejärjestelmiin ei tarvitse ylläpitää yhtä pitkään, mikä vähentää yhteysongelmien riskiä.
- **Resurssin kulutus vähenee** – vain kaikkien tietojen alijoukon päivittäminen tehostaa laskentaresurssien käyttöä ja vähentää ympäristön rasitusta.

## <a name="configure-incremental-refresh"></a>Määritä lisäävä päivitys

Käyttäjäryhmän merkityksellisissä tiedoissa on mahdollista tehdä sellaisten Power Queryn kautta tuotujen tietolähteiden lisäävä päivitys, jotka tukevat lisäävää käyttöä. Esimerkiksi Azure SQL -tietokannat, joiden päivämäärä- ja aikakentät ilmaisevat, milloin tietotietueet päivitettiin viimeksi.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
