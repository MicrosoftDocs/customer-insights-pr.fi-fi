---
title: Asiakkaan merkityksellisten tietojen vieminen Sendinblue-ratkaisuun
description: Lisätietoja yhteyden ja viennin määrittämisestä Sendinblue-ratkaisuun.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e6d63e0017caa50379426cd5f9b663571b568de7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646118"
---
# <a name="export-segments-to-sendinblue-preview"></a>Segmenttien vieminen Sendinblue-ratkaisuun (esiversio)

Vie yhdistettyjen asiakasprofiilien segmenttejä luodaksesi kampanjoita, tarjotaksesi sähköpostimarkkinointia ja käyttääksesi tiettyjä asiakasryhmiä Sendinblue-ratkaisun kanssa.

## <a name="prerequisites-for-connection"></a>Yhteyden edellytykset

-   Sinulla on [Sendinblue-tili](https://www.sendinblue.com/) ja vastaavat järjestelmänvalvojan valtuustiedot.
-   Sendinblue-ratkaisussa on olemassa olevat luettelot ja vastaavat tunnukset.
-   [Segmentit on määritetty](segments.md).
-   Vietyjen segmenttien yhtenäistetyissä asiakasprofiileissa on sähköpostiosoitetta vastaava kenttä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään miljoona asiakasprofiilia Sendinblue-vientiä kohden.
- Vieminen Sendinblue-ratkaisuun on rajoitettu segmentteihin.
- Miljoona asiakasprofiilia sisältävien segmenttien vieminen voi kestää 90 minuuttia. 
- Sendinblueen vietävien asiakasprofiilien määrä riippuu Sendinblue-sopimuksestasi ja sen sisältämistä rajoituksista.

## <a name="set-up-connection-to-sendinblue"></a>Yhteyden määrittäminen Sendinblue-ratkaisuun

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Määritä yhteys valitsemalla **Lisää yhteys**. Valitse lopuksi **Sendinblue**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Syötä **[SendinBlue-ohjelmointirajapinnan avain](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Valitse **Hyväksyn**, jos haluat vahvistaa **Tietojen yksityisyys ja vaatimustenmukaisuus** -kohdan. Valitse **Muodosta yhteys**, jolloin yhteys Sendinblue-ratkaisuun muodostetaan.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Sendinblue-osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Syötä **Sendinblue-luettelon tunnus** 

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta. 

1. Vaihtoehtoisesti voit viedä **etunimen**, **sukunimen** tai **puhelinnumeron** mukaan. Näin voit luoda mukautettuja sähköpostiviestejä. Yhdistä nämä kenttä valitsemalla **Lisää määrite**.

1. Valitse segmentit, jotka haluat viedä. 

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun otat käyttöön Dynamics 365 Customer Insightsin tietojen siirtämiseksi Sendinblue-ratkaisuun, sallit tietojen siirtämisen säännöstenmukaisuuden rajan ulkopuolelle Dynamics 365 Customer Insightsissa, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilökohtaiset tiedot. Microsoft siirtää nämä tiedot pyyntösi mukaisesti, mutta olet vastuussa siitä, että Sendinblue täyttää kaikki liiketoimintaasi koskevat tietosuoja- tai tietoturvavelvoitteet. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
