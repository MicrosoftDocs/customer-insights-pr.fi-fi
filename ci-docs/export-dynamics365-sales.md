---
title: Segmenttien vienti Dynamics 365 Salesiin (esiversio)
description: Tietoja yhteyden määrittämisestä ja viennistä Dynamics 365 Salesiin.
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
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195977"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Segmenttien vienti Dynamics 365 Salesiin (esiversio)

Asiakastietojen avulla voit luoda markkinointiluetteloita, seurata työnkulkuja ja lähettää kampanjoita Dynamics 365 Salesin avulla.

## <a name="prerequisites"></a>edellytykset

Dynamics 365 Salesissa on oltava yhteyshenkiötietueita, ennen kuin voit viedä segmentin Customer Insightsista Salesiin. Lisätietoja siitä, miten yhteyshenkilöitä voi käsitellä [Dynamics 365 Salesista käyttämällä Microsoft Dataverse](connect-dataverse-managed-lake.md)a.

   > [!NOTE]
   > Segmenttien vieminen Customer Insightsista Salesiin ei luo uusia yhteyshenkilötietueita Sales esiintymiin. Salesin yhteyshenkilötietueet on otettava käyttöön Customer Insightsissa ja niitä on käytettävä tietolähteenä. Ne on myös sisällytettävä yhdistettyyn asiakasentiteettiin, jotta asiakastunnukset voidaan yhdistää yhteyshenkilötunnuksiin ennen segmenttien viemistä.

## <a name="known-limitations"></a>Tunnetut rajoitukset

Dynamics 365 Salesiin voi viedä segmenttiä kohti enintään 100 000, mikä kestää enintään kolme tuntia.

## <a name="set-up-connection-to-sales"></a>Määritä yhteys Salesiin

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse sitten **Dynamics 365 Sales**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Syötä organisaatiosi Sales-URL-osoite **Palvelinosoite**-kentässä.

1. Valitse **Palvelimen järjestelmänvalvojan tili** -osassa **Kirjaudu sisään** ja valitse sitten Dynamics 365 Sales -tili.

1. Yhdistä asiakastunnuskenttä Dynamics 365 -yhteyshenkilön tunnukseen.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Dynamics 365 Sales -osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Valitse asiakasentiteetin Yhteyshenkilön tunnus -kenttä, joka vastaa Dynamics 365:n yhteyshenkilön tunnusta.

1. Valitse segmentit, jotka haluat viedä.

1. Valitse **Tallenna**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
