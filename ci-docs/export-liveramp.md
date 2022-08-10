---
title: Segmenttien vieminen LiveRampiin (esiversio)
description: Tietoja yhteyden määrittämisestä ja viennistä LiveRampiin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196712"
---
# <a name="export-segments-to-liverampreg-preview"></a>Segmenttien vieminen LiveRampiin&reg; (esiversio)

Aktivoi tiedot LiveRampissa, jotta voit muodostaa yhteyden yli 500 ympäristöön digitaalisissa kanavissa, yhteisöpalveluissa ja televisioissa. Työstä tietojasi LiveRampissa kohdistaaksesi, estääksesi ja yksilöllistääksesi mainoskampanjoita.

## <a name="prerequisites"></a>edellytykset

- Tämän yhdistimen käyttö edellyttää LiveRamp-tilausta. Hanki tilaus [ottamalla suoraan yhteyttä LiveRampiin](https://liveramp.com/contact/). [Lisätietoja LiveRamp-käyttöönotosta](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Tunnetut rajoitukset

- LiveRamp-vienti käyttää SFTP-vientiä. Palomuurin takana olevia SFTP-kohteita ei tueta tällä hetkellä.
- Jos käytät todentamiseen SSH-avainta, varmista, [että luot yksityisen avaimen](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) PEM- tai SSH.COM muodossa. Jos käytät Putty-sovellusta, muunna yksityinen avain viemällä se avoimena SSH:na Seuraavia yksityisen avaimen muotoja tuetaan:
  - RSA OpenSSL PEM ssh.com -muodossa
  - DSA OpenSSL PEM ssh.com -muodossa
  - ECDSA 256/384/521 OpenSSL PEM -muodossa
  - ED25519 ja RSA OpenSSH-avainmuodossa
- Viennin suoritusaika määräytyy järjestelmän suorituskyvyn mukaan. Suosittelemme, että palvelimen käytössä on vähintään kaksi suoritinydintä ja yksi gigatavu muistia.
- Entiteettien vieminen enintään 100 miljoonalle asiakasprofiilille voi kestää 90 minuuttia, kun käytössä on suositeltu vähimmäismääritys eli kaksi suoritinydintä ja yksi gigatavu muistia.
- LiveRampiin vietävien profiilien (tai tiedon) määrä riippuu LiveRamp-tilauksestasi.

## <a name="set-up-connection-to-liveramp"></a>Määritä yhteys LiveRampiin

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **LiveRamp**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valitse, haluatko todentaa yhteyden SSH-tunnuksen tai käyttäjänimen/salasanan kautta ja antaa tarvittavat tiedot.

1. Testaa yhteys LiveRampiin valitsemalla **Tarkista**.

1. Onnistuneen vahvistuksen jälkeen lue [tietosuoja ja vaatimustenmukaisuustiedot](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys LiveRamp-osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Valitse **Yhdistämistiedot** -kentässä **Sähköposti**, **Nimi ja osoite** tai **Puhelin** lähetettäväksi LiveRampille käyttäjätietojen ratkaisemiseksi.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="LiveRamp-yhdistin ja määritteiden yhdistämismääritys.":::

1. Yhdistä vastaavat määritteet *Asiakas*-entiteetistä valittua avaintunnistetta varten.

1. Valitse **Lisää määrite**, jos haluat yhdistää lisää määritteitä lähetettäväksi LiveRampiin.

   > [!TIP]
   > Useiden avaintunnistemääritteiden lähettäminen LiveRampille tuottaa todennäköisesti suuremman vastaavuuden.

1. Valitse segmentit, jotka haluat viedä.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
