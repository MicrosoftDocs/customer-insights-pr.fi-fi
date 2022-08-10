---
title: Segmenttien vienti Dynamics 365 Marketingiin (esiversio)
description: Tietoja yhteyden määrittämisestä ja viennistä Dynamics 365 Marketingiin.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196620"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Segmenttien vienti Dynamics 365 Marketingiin (esiversio)

Luo [segmenttien](segments.md) avulla kampanjoita ja ota yhteyttä tiettyihin asiakasryhmiin [Dynamics 365 Marketingin avulla](/dynamics365/marketing/customer-insights-segments).

Jos käytät Dynamics 365 Marketingin uusia ominaisuuksia reaaliaikaiseen asiakassiirtymään Dataverse-organisaatiossa, vakioviennin luominen Dynamics 365 Marketingiin ei ole tarpeen. Customer Insightsin yhteyshenkilöt ja segmentit ovat käytettävissä suoraan Dynamics 365 Marketingissa, kun olet yhdistänyt Marketingin ja Customer Insightsin. Ennen kuin poistat aiemmin luodun viennin, tutustu [Customer Insightsin ja Dynamics 365 Marketingin asiakassiirtymän orkestrointiin](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Edellytys

Yhteyshenkilötietueiden on oltava Dynamics 365 Marketingissa, ennen kuin segmentti voidaan viedä Customer Insightsista Marketingiin. Lisätietoja yhteyshenkilöiden käyttämisestä [Dynamics 365 Marketingissa Microsoft Dataversein avulla](connect-dataverse-managed-lake.md).

> [!NOTE]
> Segmenttien vieminen Customer Insightsista Marketingiin ei luo uusia yhteyshenkilötietueita Marketing-esiintymiin. Marketingin yhteyshenkilötietueet on otettava käyttöön Customer Insightsissa ja niitä on käytettävä tietolähteenä. Ne on myös sisällytettävä yhdistettyyn asiakasentiteettiin, jotta asiakastunnukset voidaan yhdistää yhteyshenkilötunnuksiin ennen segmenttien viemistä.

## <a name="set-up-connection-to-marketing"></a>Määritä yhteys Marketingiin

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **Dynamics 365 Marketing**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Syötä organisaatiosi Marketing-URL-osoite **Palvelinosoite**-kentässä.

1. Valitse **Palvelimen järjestelmänvalvojan tili** -osassa **Kirjaudu sisään** ja valitse sitten Dynamics 365 Marketing -tili.

1. Yhdistä asiakasentiteetin Yhteyshenkilön tunnus -kenttä Dynamics 365:n yhteyshenkilön tunnukseen.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Dynamics 365 Marketing -osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Valitse asiakasentiteetin Yhteyshenkilön tunnus -kenttä, joka vastaa Dynamics 365:n yhteyshenkilön tunnusta.

1. Valitse segmentit, jotka haluat viedä.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
