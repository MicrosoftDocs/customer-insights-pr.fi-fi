---
title: Segmenttien vieminen LiveRampiin (esiversio)
description: Tietoja yhteyden määrittämisestä ja viennistä LiveRampiin.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 3e30a16dcb276fa6c951ad0b42ed0a4792f87ce3
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050759"
---
# <a name="export-segments-to-liverampreg-preview"></a>Segmenttien vieminen LiveRampiin&reg; (esiversio)

Aktivoi tiedot LiveRampissa, jotta voit muodostaa yhteyden yli 500 ympäristöön digitaalisissa kanavissa, yhteisöpalveluissa ja televisioissa. Työstä tietojasi LiveRampissa kohdistaaksesi, estääksesi ja yksilöllistääksesi mainoskampanjoita.

## <a name="prerequisites-for-a-connection"></a>Yhteyden edellytykset

- Tämän yhdistimen käyttö edellyttää LiveRamp-tilausta.
- Hanki tilaus [ottamalla suoraan yhteyttä LiveRampiin](https://liveramp.com/contact/). [Lisätietoja LiveRamp-käyttöönotosta](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Määritä yhteys LiveRampiin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **LiveRamp**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna LiveRamp Secure FTP (SFTP) -tilillesi **Käyttäjänimi** ja **Salasana**.
Nämä tunnistetiedot voivat erota LiveRamp-käyttöönoton tunnistetiedoista.

1. Testaa yhteys LiveRampiin valitsemalla **Tarkista**.

1. Kun yhteys on tarkistettu, hyväksy **Tietosuoja ja vaatimuksenmukaisuus** valitsemalla **Hyväksyn**-valintaruutu.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys LiveRamp-osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Valitse **Valitse avaintunniste** -kentässä **Sähköposti**, **Nimi ja osoite** tai **Puhelin** lähetettäväksi LiveRampille käyttäjätietojen ratkaisemiseksi.
   > [!div class="mx-imgBorder"]
   > ![LiveRamp-yhdistin ja määritteiden yhdistämismääritys.](media/export-liveramp-segments.png "LiveRamp-yhdistin ja määritteiden yhdistämismääritys")

1. Yhdistä vastaavat määritteet *Asiakas*-entiteetistä valittua avaintunnistetta varten.

1. Valitse **Lisää määrite**, jos haluat yhdistää lisää määritteitä lähetettäväksi LiveRampiin.

   > [!TIP]
   > Useiden avaintunnistemääritteiden lähettäminen LiveRampille tuottaa todennäköisesti suuremman vastaavuuden.

1. Valitse segmentit, jotka haluat viedä LiveRampiin.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Liverampiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Liveramp noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
