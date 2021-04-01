---
title: Customer Insights -tietojen vienti Dynamics 365 Salesiin
description: Tutustu Dynamics 365 Sales -yhteyden määrittämiseen.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598105"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Dynamics 365 Salesin yhdistin (esikatselu)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Asiakastietojen avulla voit luoda markkinointiluetteloita, seurata työnkulkuja ja lähettää kampanjoita Dynamics 365 Salesin avulla.

## <a name="prerequisite"></a>Edellytykset

1. Dynamics 365 Salesissa on oltava yhteyshenkiötietueita, ennen kuin voit viedä segmentin Customer Insightsista Salesiin. Lisätietoja yhteyshenkilöiden käyttämisestä [Dynamics 365 Salesissa Common Data Servicesin avulla](connect-power-query.md).

   > [!NOTE]
   > Segmenttien vieminen käyttäjäryhmän tiedoista Salesiin ei luo Sales-esiintymiin uusia yhteyshenkilötietueita. Salesin yhteyshenkilötietueet on käsiteltävä käyttäjäryhmän tiedoissa, ja niitä on käytettävä tietolähteenä. Ne on myös sisällytettävä yhdistettyyn asiakasentiteettiin, jotta asiakastunnukset voidaan yhdistää yhteyshenkilötunnuksiin ennen segmenttien viemistä.

## <a name="configure-the-connector-for-sales"></a>Määritä Salesin yhdistin

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.

1. Valitse **Dynamics 365 Sales** -kohdassa **Määritä**.

1. Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.

1. Syötä organisaatiosi Sales-URL-osoite **Palvelinosoite**-kentässä.

1. Valitse **Palvelimen järjestelmänvalvojan tili** -osassa **Kirjaudu sisään** ja valitse sitten Dynamics 365 Sales -tili.

1. Yhdistä asiakastunnuskenttä Dynamics 365 -yhteyshenkilön tunnukseen.

1. Valitse **Seuraava**.

1. Valitse vähintään yksi segmentti.

1. Valitse **Tallenna**.

## <a name="export-the-data"></a>Tietojen vieminen

Voit [viedä tietoja tarvittaessa](export-destinations.md). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.


[!INCLUDE[footer-include](../includes/footer-banner.md)]