---
title: Tietojen vieminen SFTP-palvelimiin (esiversio) (sisältää videon)
description: Tietoja yhteyden määrittämisestä ja viennistä SFTP-sijaintiin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207225"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Tietojen vienti SFTP-isännille (esiversio)

Käytä asiakastietojasi kolmansien osapuolten sovelluksissa viemällä ne Secure File Transfer Protocol (SFTP) -sijaintiin.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>edellytykset

- SFTP-isännän ja vastaavien valtuustietojen käytettävyys.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Palomuurin takana olevia SFTP-kohteita ei tueta tällä hetkellä.
- Viennin suoritusaika määräytyy järjestelmän suorituskyvyn mukaan. Suosittelemme, että palvelimen käytössä on vähintään kaksi suoritinydintä ja yksi gigatavu muistia.
- Enintään 100 miljoonaa asiakasprofiilia, mikä voi kestää 90 minuuttia, kun käytössä on suositeltu vähimmäismääritys eli kaksi suoritinydintä ja yksi gigatavu muistia.
- Jos käytät todentamiseen SSH-avainta, varmista, [että luot yksityisen avaimen](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) PEM- tai SSH.COM muodossa. Jos käytät Putty-sovellusta, muunna yksityinen avain viemällä se avoimena SSH:na Seuraavia yksityisen avaimen muotoja tuetaan:
  - RSA OpenSSL PEM ssh.com -muodossa
  - DSA OpenSSL PEM ssh.com -muodossa
  - ECDSA 256/384/521 OpenSSL PEM -muodossa
  - ED25519 ja RSA OpenSSH-avainmuodossa

## <a name="set-up-connection-to-sftp"></a>Määritä SFTP-yhteydet

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **SFTP**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valitse, haluatko todentaa yhteyden SSH-tunnuksen tai käyttäjänimen/salasanan kautta ja antaa tarvittavat tiedot. Jos käytät todentamiseen SSH-avainta, varmista, [että luot yksityisen avaimen](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) PEM- tai SSH.COM muodossa. Jos käytät Putty-sovellusta, muunna yksityinen avain viemällä se avoimena SSH:na Seuraavia yksityisen avaimen muotoja tuetaan:
   - RSA OpenSSL PEM ssh.com -muodossa
   - DSA OpenSSL PEM ssh.com -muodossa
   - ECDSA 256/384/521 OpenSSL PEM -muodossa
   - ED25519 ja RSA OpenSSH-avainmuodossa

1. Valitse **Tarkista** yhteyden testausta varten.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys SFTP-osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Valitse, haluatko viedä tiedot **gzip**-muodossa vai **pakkaamattomina** sekä vietävien tiedostojen **kenttäerotin**.

1. Valitse vietävät entiteetit, esimerkiksi segmentit.

   > [!NOTE]
   > Kukin valittu kohde jaetaan enintään viiteen tulostiedostoon vietäessä.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> Suuren määrän tietoja sisältävien entiteettien vienti voi aiheuttaa sen, että samassa kansiossa on useita CSV-tiedostoja kunkin viennin osalta. Viennit jaetaan suorituskykysyistä, sillä näin kunkin viennin suorittamiseen kuluva aika voidaan pitää mahdollisimman lyhyenä.

[!INCLUDE [footer-include](includes/footer-banner.md)]
