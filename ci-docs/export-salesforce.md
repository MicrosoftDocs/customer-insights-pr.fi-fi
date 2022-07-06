---
title: Tietojen vienti Salesforce Marketing Cloudiin (esiversio)
description: Lisätietoja yhteyden ja viemisen määrittämisestä Salesforce Marketing Cloud -sovellukseen
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c3a6a40d9b9f08c8ebca8cb4a9196a1a79f03afa
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081097"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Tietojen vienti Salesforce Marketing Cloudiin (esiversio)

Käytä Salesforce Marketing Cloud -sovelluksen asiakastietoja viemällä ne suojatun tiedostonsiirtoprotokollan (SFTP) sijainnin kautta.

## <a name="prerequisites-for-connection"></a>Yhteyden edellytykset

- SFTP-isännän ja vastaavien järjestelmänvalvojan valtuustietojen käytettävyys. [Salesforce Marketing Cloud -sovelluksen SFTP-sijaintien määrittäminen](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Yhteyden määrittäminen Salesforce Marketing Cloud -sovellukseen

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Määritä yhteys valitsemalla **Lisää yhteys**. Valitse lopuksi **Salesforce Marketing Cloud**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Anna SFTP-tilille **Käyttäjänimi**, **Salasana**, **Isäntänimi** ja **Vientikansio**.

1. Valitse **Tarkista** yhteyden testausta varten.

1. Valitse **I agree**, jolloin vahvistat **Data privacy and compliance** (tietosuojaehdot).

1. Viimeistele yhteys valitsemalla **Tallenna**.

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys SFTP-osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Valitse, haluatko viedä tiedot **gzip**-muodossa vai **pakkaamattomina** sekä vietävien tiedostojen **kenttäerotin**.

1. Valitse vietävät entiteetit, esimerkiksi segmentit.

   > [!NOTE]
   > Kukin valittu kohde jaetaan enintään viiteen tulostiedostoon vietäessä. 

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Customer Insights -tietojen tuominen SFTP-sijainnista Salesforce Marketing Cloud -sovellukseen

1. Luo [tietolaajennukset Salesforce Marketing Cloud -sovellukseen](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5), jotta voit tuoda Customer Insightsin datatiedoston SFTP-sijainnista.

2. [Tuo tiedot SFTP-sijainnista](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) Salesforce Marketing Cloud -sovelluksen tietolaajennukseen. 

3. Määritä tietojen automaattinen tuominen tietolaajennuksiin. Lisätietoja [tiedoston pudottamisen automatisoinneista ja ajoitetuista automatisoinneista](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Määritä [tiedoston pudottamisen automatisointi](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) tai [ajoitettu automatisointi](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Tässä on esimerkki [automatisoinnista SFTP:n avulla](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys SFTP:n kautta otetaan käyttöön Dynamics 365 Customer Insightsissa, tietojen siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että vientikohde noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön koska tahansa poistamalla tämän vientikohteen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
