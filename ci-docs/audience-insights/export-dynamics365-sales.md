---
title: Customer Insights -tietojen vienti Dynamics 365 Salesiin
description: Tutustu Dynamics 365 Sales -yhteyden määrittämiseen.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643814"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Dynamics 365 Salesin yhdistin (esikatselu)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Asiakastietojen avulla voit luoda markkinointiluetteloita, seurata työnkulkuja ja lähettää kampanjoita Dynamics 365 Salesin avulla.

## <a name="prerequisite"></a>Edellytykset

[Common Data Servicella käytetyt Dynamics 365 Salesin](connect-power-query.md) yhteyshenkilötietueet.

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
