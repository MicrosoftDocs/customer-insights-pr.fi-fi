---
title: Asiakkaan merkityksellisten tietojen vieminen ActiveCampaign-ratkaisuun
description: Lisätietoja yhteyden ja viemisen määrittämisestä ActiveCampaign-ratkaisuun
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 14d420205a5c60d471ef21a04ab6d02295a65ca8fd5205ba782a300703b06102
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032205"
---
# <a name="export-segments-to-activecampaign-preview"></a>Segmenttien vieminen ActiveCampaign-ratkaisuun (esiversio)

Vie yhdistettyjen asiakasprofiilien segmentit ActiveCampaign-ratkaisuun ja käytä niitä markkinointiaktiviteeteissa.

## <a name="prerequisites"></a>Edellytykset

-   Sinulla on [ActiveCampaign-tili](https://www.activecampaign.com/) ja vastaavat järjestelmänvalvojan valtuustiedot.
-   Käyttäjäryhmän merkityksellisissä tiedoissa on [määritettyjä segmenttejä](segments.md).
-   Viedyissä segmenteissä yhdenmukaistetut asiakasprofiilit sisältävät kentän, jolla on sähköpostiosoite.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Yhdessä viennissä ActiveCampaign-ratkaisuun voi olla enintään miljoona profiilia. Vienti voi kestää 90 minuuttia.
- Vieminen ActiveCampaign-ratkaisuun on rajoitettu segmentteihin.
- ActiveCampaign-ratkaisuun vietävien profiilien enimmäismäärä riippuu ActiveCampaign-sopimuksesta.

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

3. Valitse **Tietojen vastaavuus** -osan **Sähköposti**-kentässä kenttä asiakkaan sähköpostiosoitetta vastaavassa yhtenäistetyssä asiakasprofiilissa. Segmenttien vieminen ActiveCampaign-ratkaisuun on pakollista. Vaihtoehtoisesti voit viedä etunimen, sukunimen tai puhelinnumeron mukaan. Näin voit luoda mukautettuja sähköpostiviestejä. Yhdistä nämä kenttä valitsemalla Lisää määrite.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun otat käyttöön Dynamics 365 Customer Insightsin tietojen siirtämiseksi ActiveCampaign-ratkaisuun, sallit tietojen siirtämisen säännöstenmukaisuuden rajan ulkopuolelle Dynamics 365 Customer Insightsissa, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilökohtaiset tiedot. Microsoft siirtää nämä tiedot pyyntösi mukaisesti, mutta olet vastuussa siitä, että ActiveCampaign täyttää kaikki liiketoimintaasi koskevat tietosuoja- tai tietoturvavelvoitteet. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.
