---
title: Customer Insightsin tietojen vieminen Facebookin mainosten hallintaan
description: Opettele määrittämään yhteys Facebook Ads Manageriin.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269970"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Yhdistä Facebook Ads Manageriin (esiversio)

Voit luoda kampanjoita Facebookissa ja Instagramissaa viemällä yhdistettyjen asiakasprofiilien segmenttejä Facebook Ads Manageriin.

## <a name="prerequisites"></a>Edellytykset

- Tarvitset [**Facebook Ad -tilin**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), joka sisältää [**Facebook -yritystilin**](https://business.facebook.com/).
- Sinun on oltava [**Facebook Ad -tilin**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) järjestelmänvalvoja.

## <a name="connect-to-facebook-ads-manager"></a>Yhteyden muodostaminen Facebook Ads Manageriin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.

1. Valitse **Facebook Ads Manager** -kohdassa **määritä**.

1. Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.

1. Valitse **Continue with Facebook** kirjautuaksesi Facebook Ad -tiliisi.

1. Salli **ads_management**-oikeus Facebook-todennuksen jälkeen.

1. Valitse **Facebook Ad -tili**, jota haluat käyttää.

1. Valitse yleisö avattavasta **Existing custom audience** -valikosta tai luo uusi **New custom audience** -kohdassa. Lisätietoja on kohdassa [**Kohdeyleisöt Facebook Ads Managerissa**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Määritä vienti valitsemalla **Next**.

## <a name="configure-the-connector"></a>Yhdistimen määrittäminen

1. Valitse **Choose your key identifier** -kentässä **Email**, **Name and address** tai **Phone**, jonka avulla lähetetään Facebook Ads Manageriin.

1. Yhdistä yhdistetyn asiakasentiteetin vastaavat määritteet valittua avaintunnistetta varten.
   > [VIHJE] Paras vaihtoehtosi on se, että valitaan **Email** tunnukseksi. Lisätunnusten lisääminen voi parantaa vastaavuutta.

1. Valitsemalla **Add attribute** voit yhdistää Facebook Ads Manageriin lähetettävät lisämääritteet. Facebook Ads Managerin määritteet yhdistetään seuraaviin kenttien lyhyisiin nimiin: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**

1. Valitse segmentit, jotka haluat viedä.

1. Valitse **Tallenna**.

## <a name="export-the-data"></a>Tietojen vieminen

Voit [viedä tietoja tarvittaessa](export-destinations.md). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Enintään 10 miljoonaa asiakasprofiilia Facebookin mainosten hallintaan 
- Vienti Facebookin mainosten hallintaan on rajoitettu segmentteihin
- Yhteensä 10 miljoonan profiilin segmenttien vienti voi kestää 90 minuuttia

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Facebookin mainosten hallintaan otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Facebook Ads noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]