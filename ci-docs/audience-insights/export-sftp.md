---
title: Customer Insightsin tietojen vieminen SFTP-isäntiin
description: Opettele määrittämään yhteys SFTP-palvelimeen.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267994"
---
# <a name="connector-for-sftp-preview"></a>SFTP-yhdistin (esiversio)

Asiakastietojen käyttäminen kolmansien osapuolten sovelluksissa viemällä ne SFTP (Secure File Transfer Protocol) -isäntään.

## <a name="prerequisites"></a>Edellytykset

- SFTP-isännän ja vastaavien valtuustietojen käytettävyys.

## <a name="connect-to-sftp"></a>Muodosta yhteys SFTP:hen

1. Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.

1. Valitse kohdassa **SFTP** **Määritä**.

1. Anna kohteelle tunnistettava nimi **Näyttönimi**-kentässä.

1. Anna SFTP-tilille **Käyttäjänimi**, **Salasana**, **Isäntänimi** ja **Vientikansio**.

1. Valitse **Tarkista** yhteyden testausta varten.

1. Kun tarkistus on tehty, määritä, viedäänkö tiedot **Gzip-pakattuina** vai **purettuina**. Valitse sitten vietyjen tiedostojen **kentän erotin**.

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Aloita viennin määrittäminen valitsemalla **Seuraava**.

## <a name="configure-the-export"></a>Viennin määrittäminen

1. Valitse vietävät entiteetit, esimerkiksi segmentit.

   > [!NOTE]
   > Kukin valittu entiteetti sisältää enintään viisi tulostetiedostoa vietäessä. 

1. Valitse **Tallenna**.

## <a name="export-the-data"></a>Tietojen vieminen

Voit [viedä tietoja tarvittaessa](export-destinations.md). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Viennin suoritusaika määräytyy järjestelmän suorituskyvyn mukaan. Suosittelemme, että palvelimen käytössä on vähintään kaksi suoritinydintä ja yksi gigatavu muistia. 
- Entiteettien vieminen enintään 100 miljoonalle asiakasprofiilille voi kestää 90 minuuttia, kun käytössä on suositeltu vähimmäismääritys eli kaksi suoritinydintä ja yksi gigatavu muistia. 

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys SFTP:n kautta otetaan käyttöön Dynamics 365 Customer Insightsissa, tietojen siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että vientikohde noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]