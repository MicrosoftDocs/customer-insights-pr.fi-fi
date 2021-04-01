---
title: Customer Insights -tietojen vienti Dynamics 365 Marketingiin
description: Tutustu Dynamics 365 Marketing -yhteyden määrittämiseen.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597599"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Dynamics 365 Marketingin yhdistin (esikatselu)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Luo [segmenttien](segments.md) avulla kampanjoita ja ota yhteyttä tiettyihin asiakasryhmiin Dynamics 365 Marketingin avulla. Lisätietoja on kohdassa [Dynamics 365 Customer Insightsin segmenttien käyttäminen Dynamics 365 Marketingin kanssa](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Edellytykset

- Yhteyshenkilötietueiden on oltava Dynamics 365 Marketingissa, ennen kuin segmentti voidaan viedä Customer Insightsista Marketingiin. Lisätietoja yhteyshenkilöiden käyttämisestä [Dynamics 365 Marketingissa Common Data Servicesin avulla](connect-power-query.md).

  > [!NOTE]
  > Segmenttien vieminen käyttäjäryhmän tiedoista Marketingiin ei luo Marketing-esiintymiin uusia yhteyshenkilötietueita. Marketingin yhteyshenkilötietueet on käsiteltävä käyttäjäryhmän tiedoissa, ja niitä on käytettävä tietolähteenä. Ne on myös sisällytettävä yhdistettyyn asiakasentiteettiin, jotta asiakastunnukset voidaan yhdistää yhteyshenkilötunnuksiin ennen segmenttien viemistä.

## <a name="configure-the-connector-for-marketing"></a>Määritä Marketingin yhdistin

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Vientikohteet**.

1. Valitse **Dynamics 365 Marketing** -kohdassa **Määritä**.

1. Anna vientikohteelle tunnistettava nimi **Näyttönimi**-kentässä.

1. Syötä organisaatiosi Marketing-URL-osoite **Palvelinosoite**-kentässä.

1. Valitse **Palvelimen järjestelmänvalvojan tili** -osassa **Kirjaudu sisään** ja valitse sitten Dynamics 365 Marketing -tili.

1. Yhdistä asiakastunnuskenttä Dynamics 365 -yhteyshenkilön tunnukseen.

1. Valitse **Seuraava**.

1. Valitse vähintään yksi segmentti.

1. Valitse **Tallenna**.

## <a name="export-the-data"></a>Tietojen vieminen

Voit [viedä tietoja tarvittaessa](export-destinations.md). Vienti suoritetaan myös jokaisen [ajoitetun päivityskerran](system.md#schedule-tab) yhteydessä.


[!INCLUDE[footer-include](../includes/footer-banner.md)]