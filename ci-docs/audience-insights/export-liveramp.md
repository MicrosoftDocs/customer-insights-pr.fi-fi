---
title: LiveRamp-yhdistin
description: Tietoja tietojen viennistä LiveRampiin.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667180"
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