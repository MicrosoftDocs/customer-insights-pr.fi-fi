---
title: Tietojen vienti Salesforce Marketing Cloudiin (esiversio)
description: Lisätietoja yhteyden ja viemisen määrittämisestä Salesforce Marketing Cloud -sovellukseen
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197034"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Tietojen vienti Salesforce Marketing Cloudiin (esiversio)

Käytä Salesforce Marketing Cloud -sovelluksen asiakastietoja viemällä ne suojatun tiedostonsiirtoprotokollan (SFTP) sijainnin kautta.

## <a name="prerequisites"></a>edellytykset

- [Salesforce Marketing Cloudin SNT-isäntä](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) ja vastaavat järjestelmänvalvojan tunnistetiedot.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Yhteyden määrittäminen Salesforce Marketing Cloud -sovellukseen

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja lopuksi **Salesforce Marketing Cloud**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Oletusarvoisesti vain järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna SFTP-tilille **Käyttäjänimi**, **Salasana**, **Isäntänimi** ja **Vientikansio**.

1. Valitse **Tarkista** yhteyden testausta varten.

1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse **Lisää vienti**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys SFTP-osasta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä.

1. Anna viennin nimi.

1. Valitse, haluatko viedä tiedot **gzip**-muodossa vai **pakkaamattomina** sekä vietävien tiedostojen **kenttäerotin**.

1. Valitse vietävät entiteetit, esimerkiksi segmentit.

   > [!NOTE]
   > Kukin valittu kohde jaetaan enintään viiteen tulostiedostoon vietäessä.

1. Valitse **Tallenna**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Customer Insights -tietojen tuominen SFTP-sijainnista Salesforce Marketing Cloud -sovellukseen

1. Luo [tietolaajennukset Salesforce Marketing Cloud -sovellukseen](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5), jotta voit tuoda Customer Insightsin datatiedoston SFTP-sijainnista.

2. [Tuo tiedot SFTP-sijainnista](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) Salesforce Marketing Cloud -sovelluksen tietolaajennukseen.

3. Määritä tietojen automaattinen tuominen tietolaajennuksiin. Lisätietoja [tiedoston pudottamisen automatisoinneista ja ajoitetuista automatisoinneista](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Määritä [tiedoston pudottamisen automatisointi](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) tai [ajoitettu automatisointi](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Tässä on esimerkki [automatisoinnista SFTP:n avulla](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
