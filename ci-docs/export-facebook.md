---
title: Segmenttien vienti Facebook Ads Manageriin (esiversio) (sisältää videon)
description: Tietoja yhteyden määrittämisestä ja viennistä Facebook Ads Manageriin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724584"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Segmenttien vienti Facebook Ads Manageriin (esiversio)

Voit luoda kampanjoita Facebookissa ja Instagramissa viemällä yhdistettyjen asiakasprofiilien segmenttejä Facebook Ads Manageriin.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>edellytykset

- [Facebook Ads -tili](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), joka sisältää [Facebookin yritystilin](https://business.facebook.com/).
- [Facebook Ads-tilin](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) järjestelmänvalvojan oikeudet.
- Sen käyttäjän, joka määrittää yhteyden Customer Insightsissa on hyväksyttävä Mukautetun käyttäjäryhmän ehdot.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Vientiä kohden voi viedä enintään 10 miljoonaa asiakasprofiilia Facebook Ads Manageriin, mikä voi kestää 90 minuuttia.
- Vain segmentit.
- Facebook Ads -integrointi ei tue käyttäjiä, joilla on yli 25 mainostiliä.
- Facebook *-asiakasluettelon* tyyppi vain [mukautetuille kohderyhmille](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
  > [!NOTE]
  > Joissakin tapauksissa avattavassa luettelossa voi olla eri tyyppisiä mukautettuja käyttäjäryhmiä. Jos valitset jonkin toisen tyypin kuin *asiakasluettelo*, vienti epäonnistuu.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Määritä yhteys Facebook Ads Manageriin

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **Facebook Ads Manager**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. [Salli osallistujien käyttää yhteyttä vientiin](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Todenna Facebook Adsin avulla:

   1. Valitse **Jatka Facebookilla**, jos haluat kirjautua sisään Facebook Ads -tilillä.

   1. Salli **ads_management**-oikeus Facebook-todennuksen jälkeen.

   1. Valitse **Facebook Ad -tili**, jota haluat käyttää.

   1. Valitse **aiemmin luotu mukautettu käyttäjäryhmä** avattavasta luettelosta tai luo **uusi mukautettu käyttäjäryhmä**.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Facebook Ads Manager -osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Valitse **Yhteyden muodostaminen tietoihin** -kentässä **Sähköposti**, **Nimi ja osoite** tai **Puhelin** Facebook Ads Manageriin lähettämistä varten.

1. Yhdistä yhdistetyn asiakasentiteetin vastaavat määritteet valittua avaintunnistetta varten.
   > [!TIP]
   > Parhaat vastaavuudet saat, jos valitset avaintunnisteeksi **sähköpostin**. Lisätunnusten lisääminen voi parantaa vastaavuutta.

1. Valitse **Lisää määrite**, jos haluat yhdistää lisää määritteitä lähetettäväksi Facebook Ads Manageriin. Facebook Ads -ratkaisun hallinnan määritteiden vastaavuus määritetään seuraaviin käyttäjän määrittämiin kutsumanimiin: **FN** = **etunimi**, **LN** = **sukunimi**, **FI** = **ensimmäinen alkukirjain**, **PHONE** = **puhelin**, **GEN** = **sukupuoli**, **DOB** = **syntymäaika**, **ST** = **osavaltio**, **CT** = **kaupunki**, **ZIP** = **postinumero**, **COUNTRY** = **maa tai alue**

1. Valitse segmentit, jotka haluat viedä.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
