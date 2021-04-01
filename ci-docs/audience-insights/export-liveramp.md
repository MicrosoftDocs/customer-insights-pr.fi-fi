---
title: LiveRamp-yhdistin
description: Tietoja tietojen viennistä LiveRampiin.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597553"
---
# <a name="liverampreg-connector-preview"></a>LiveRamp&reg; yhdistin (esikatselu)

Aktivoi tietosi LiveRampissa muodostaaksesi yhteyden yli 500 ympäristöön digitaalisissa, yhteisöllisissä ja television ekosysteemeissä. Työstä tietojasi LiveRampissa kohdistaaksesi, estääksesi ja yksilöllistääksesi mainoskampanjoita.

## <a name="prerequisites"></a>Edellytykset

- Tämän yhdistimen käyttö edellyttää LiveRamp-tilausta.
- Hanki tilaus [ottamalla suoraan yhteyttä LiveRampiin](https://liveramp.com/contact/). [Lisätietoja LiveRamp-käyttöönotosta](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>LiveRampiin yhdistäminen

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.

1. Valitse **LiveRamp**-ruudussa **Määritä**.

1. Anna kohteelle tunnistettava nimi **Näyttönimi**-kentässä.

1. Anna LiveRamp Secure FTP (SFTP) -tilillesi **Käyttäjänimi** ja **Salasana**.
Nämä tunnistetiedot voivat erota LiveRamp-käyttöönoton tunnistetiedoista.

1. Testaa yhteys LiveRampiin valitsemalla **Tarkista**.

1. Kun yhteys on tarkistettu, hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu.

1. Määritä LiveRamp-yhdistin valitsemalla **Seuraava**.

## <a name="configure-the-connector"></a>Yhdistimen määrittäminen

1. Valitse **Valitse avaintunniste** -kentässä **Sähköposti**, **Nimi ja osoite** tai **Puhelin** lähetettäväksi LiveRampille käyttäjätietojen ratkaisemiseksi.

1. Yhdistä yhdistetyn asiakasentiteetin vastaavat määritteet valittua avaintunnistetta varten.

1. Valitse **Lisää määrite**, jos haluat yhdistää lisää määritteitä LiveRampille lähetettäväksi.

   > [!TIP]
   > Useiden avaintunnistemääritteiden lähettäminen LiveRampille tuottaa todennäköisesti suuremman vastaavuuden.

1. Valitse segmentit, jotka haluat viedä LiveRampiin.

1. Valitse **Tallenna**.

> [!div class="mx-imgBorder"]
> ![LiveRamp-yhdistin ja määritteiden yhdistämismääritys](media/export-liveramp-segments.png "LiveRamp-yhdistin ja määritteiden yhdistämismääritys")

## <a name="export-the-data"></a>Tietojen vieminen

Vienti käynnistyy pian, jos kaikki viennin edellytykset täyttyvät. Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.
Kun vienti on suoritettu onnistuneesti, voit kirjautua LiveRampin käyttöönottoon tietojesi aktivointia ja jakelu varten.

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Liverampiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Liveramp noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]