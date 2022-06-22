---
title: Customer Insights -tietojen vieminen SFTP-palvelimiin (sisältää videon)
description: Tietoja yhteyden määrittämisestä ja viennistä SFTP-sijaintiin.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b56d628c8286ba6697cccc9b002f609aa929951b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947180"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>Segmenttien ja muiden tietojen vieminen SFTP-sijaintiin (esiversio)

Käytä asiakastietojasi kolmansien osapuolten sovelluksissa viemällä ne Secure File Transfer Protocol (SFTP) -sijaintiin.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>Yhteyden edellytykset

- SFTP-isännän ja vastaavien valtuustietojen käytettävyys.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Palomuurin takana olevia SFTP-kohteita ei tueta tällä hetkellä. 
- Viennin suoritusaika määräytyy järjestelmän suorituskyvyn mukaan. Suosittelemme, että palvelimen käytössä on vähintään kaksi suoritinydintä ja yksi gigatavu muistia.
- Entiteettien vieminen enintään 100 miljoonalle asiakasprofiilille voi kestää 90 minuuttia, kun käytössä on suositeltu vähimmäismääritys eli kaksi suoritinydintä ja yksi gigatavu muistia.

## <a name="set-up-connection-to-sftp"></a>Määritä SFTP-yhteydet

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **SFTP**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna SFTP-tilille **Käyttäjänimi**, **Salasana**, **Isäntänimi** ja **Vientikansio**.

1. Valitse **Tarkista** yhteyden testausta varten.

1. Valitse, haluatko viedä tiedot **gzip**-muodossa vai **pakkaamattomina** sekä vietävien tiedostojen **kenttäerotin**.

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys SFTP-osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Valitse vietävät entiteetit, esimerkiksi segmentit.

   > [!NOTE]
   > Kukin valittu kohde jaetaan enintään viiteen tulostiedostoon vietäessä.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa.
Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand).

> [!TIP]
> Suuren määrän tietoja sisältävien entiteettien vienti voi aiheuttaa sen, että samassa kansiossa on useita CSV-tiedostoja kunkin viennin osalta. Viennit jaetaan suorituskykysyistä, sillä näin kunkin viennin suorittamiseen kuluva aika voidaan pitää mahdollisimman lyhyenä.

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys SFTP:n kautta otetaan käyttöön Dynamics 365 Customer Insightsissa, tietojen siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että vientikohde noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
