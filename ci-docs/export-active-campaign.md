---
title: Asiakkaan merkityksellisten tietojen vieminen ActiveCampaign-ratkaisuun
description: Lisätietoja yhteyden ja viemisen määrittämisestä ActiveCampaign-ratkaisuun
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d15b9bf7383d06070ac92d7a729fc6e6e00c9d7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646213"
---
# <a name="export-segments-to-activecampaign-preview"></a>Segmenttien vieminen ActiveCampaign-ratkaisuun (esiversio)

Vie yhdistettyjen asiakasprofiilien segmentit ActiveCampaign-ratkaisuun ja käytä niitä markkinointiaktiviteeteissa.

## <a name="prerequisites"></a>Edellytykset

-   Sinulla on [ActiveCampaign-tili](https://www.activecampaign.com/) ja vastaavat järjestelmänvalvojan valtuustiedot.
-   Olet [määrittänyt segmenttejä](segments.md) Customer Insightsissa.
-   Viedyissä segmenteissä yhdenmukaistetut asiakasprofiilit sisältävät kentän, jolla on sähköpostiosoite.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Vientiä kohden voit viedä enintään miljoona asiakasprofiilia ActiveCampaigniin, ja se voi kestää 90 minuuttia.
- Vieminen ActiveCampaign-ratkaisuun on rajoitettu segmentteihin.
- ActiveCampaigniin vietävien asiakasprofiilien määrä riippuu sopimuksestasi ActiveCampaignin kanssa.

## <a name="set-up-connection-to-activecampaign"></a>Yhteyden määrittäminen ActiveCampaign-ratkaisuun

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Määritä yhteys valitsemalla **Lisää yhteys**. Valitse lopuksi **ActiveCampaign**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Syötä [ActiveCampaign-ohjelmointirajapinnan avain ja REST-päätepisteen isäntänimi](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). REST-päätepisteen hostname on vain isäntänimi ilman https://. 

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Valitse **Muodosta yhteys** ja muodosta yhteys ActiveCampaign-ratkaisuun.

1. Valitse **Lisää itsesi vientikäyttäjäksi** ja anna Customer Insights -tunnistetiedot.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys ActiveCampaign-osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Syötä [**ActiveCampaign-luettelon tunnus**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä, joka edustaa asiakkaan sähköpostiosoitetta. Segmenttien vieminen ActiveCampaign-ratkaisuun on pakollista. Vaihtoehtoisesti voit viedä etunimen, sukunimen tai puhelinnumeron mukaan. Näin voit luoda mukautettuja sähköpostiviestejä. Yhdistä nämä kenttä valitsemalla Lisää määrite.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun otat käyttöön Dynamics 365 Customer Insightsin tietojen siirtämiseksi ActiveCampaign-ratkaisuun, sallit tietojen siirtämisen säännöstenmukaisuuden rajan ulkopuolelle Dynamics 365 Customer Insightsissa, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilökohtaiset tiedot. Microsoft siirtää nämä tiedot pyyntösi mukaisesti, mutta olet vastuussa siitä, että ActiveCampaign täyttää kaikki liiketoimintaasi koskevat tietosuoja- tai tietoturvavelvoitteet. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.
