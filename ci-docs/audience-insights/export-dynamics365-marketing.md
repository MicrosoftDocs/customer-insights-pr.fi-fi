---
title: Customer Insights -tietojen vienti Dynamics 365 Marketingiin
description: Tutustu Dynamics 365 Marketing -yhteyden määrittämiseen.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643769"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Dynamics 365 Marketingin yhdistin (esikatselu)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Luo [segmenttien](segments.md) avulla kampanjoita ja ota yhteyttä tiettyihin asiakasryhmiin Dynamics 365 Marketingin avulla. Lisätietoja on kohdassa [Dynamics 365 Customer Insightsin segmenttien käyttäminen Dynamics 365 Marketingin kanssa](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Edellytykset

[Common Data Servicea käyttäneet Dynamics 365 Marketingin](connect-power-query.md) yhteyshenkilötietueet

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
