---
title: Customer Insightsin tietojen vieminen Facebookin mainosten hallintaan
description: Opettele määrittämään yhteys Facebook Ads Manageriin.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643679"
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

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Facebookin mainosten hallintaan otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että Facebook Ads noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.
