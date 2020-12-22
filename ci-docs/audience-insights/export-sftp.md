---
title: Customer Insightsin tietojen vieminen SFTP-isäntiin
description: Opettele määrittämään yhteys SFTP-palvelimeen.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643499"
---
# <a name="connector-for-sftp-preview"></a>SFTP-yhdistin (esiversio)

Asiakastietojen käyttäminen kolmansien osapuolten sovelluksissa viemällä ne SFTP (Secure File Transfer Protocol) -isäntään.

## <a name="prerequisites"></a>Edellytykset

- SFTP-isännän ja vastaavien tunnistetietojen käytettävyys.

## <a name="connect-to-sftp"></a>Yhdistäminen SFTP-palvelimeen

1. Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.

1. Valitse kohdassa **SFTP** **Määritä**.

1. Anna kohteelle tunnistettava nimi **Näyttönimi**-kentässä.

1. Anna SFTP-tilin **Käyttäjänimi**, **Salasana** ja **Isäntänimi**. Esimerkki: jos SFTP-palvelimen pääkansio on /root/folder ja haluat, että tiedot viedään kansioon /root/folder/ci_export_destination_folder, isännän on silloin oltava sftp://<server_address>/ci_export_destination_folder".

1. Valitse **Tarkista** yhteyden testausta varten.

1. Kun tarkistus on onnistunut, valitse, haluatko viedä tiedot **pakattuina** vai **purettuina**, ja valitse sitten vietyjen tiedostojen **kenttäerotin**.

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Aloita viennin määrittäminen valitsemalla **Seuraava**.

## <a name="configure-the-connection"></a>Yhteyden määrittäminen

1. Valitse vietävät **asiakkaan määritteet**. Voit viedä yhden tai useita määritteitä.

1. Valitse **Seuraava**.

1. Valitse segmentit, jotka haluat viedä.

1. Valitse **Tallenna**.

## <a name="export-the-data"></a>Tietojen vieminen

Voit [viedä tietoja tarvittaessa](export-destinations.md). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys SFTP:n kautta otetaan käyttöön Dynamics 365 Customer Insightsissa, tietojen siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että vientikohde noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.
