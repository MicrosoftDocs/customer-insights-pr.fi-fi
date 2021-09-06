---
title: Reaaliaikainen tietojen käsittely ja rajoitukset
description: Yleisiä tietoja käyttäjäryhmän merkityksellisten tietojen reaaliaikaisista ominaisuuksista
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 897c876306a39cd9d5842487b96cb2f0a8df7e656de0fb7f10fe8c7f53e2db6b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035273"
---
# <a name="real-time-data-ingestion-preview"></a>Reaaliaikainen tietojen käsittely (esiversio)

Lähes reaaliaikaisen toiminnon ansiosta voit nähdä muutamassa sekunnissa asiakkaiden vuorovaikutukset tuotteiden tai palveluiden kanssa.

[Ajoitetut päivitykset](system.md#schedule-tab) sisältävät suuren määrän tietueita ja useita monimutkaisia toimintoja. Tiedot noudetaan ensin tietolähteestä. Seuraavaksi tiedot on yhdistetään ja täydennetään lisätiedoilla. Prosessin jokainen suoritus voi kestää minuuteista tunteihin.

Reaaliaikaisista toiminnoista saadaan heti tietoja käyttöön siihen saakka, että seuraava ajoitettu päivitys hakee nämä tiedot tietolähteestä.

Reaaliaikaisissa päivityksissä on vanhentumisaika, jonka jälkeen ne eivät enää korvaa tietolähteen arvoa:

- Profiilipäivitykset säilytetään 4 tunnin ajan
- Aktiviteetit säilytetään 30 päivän ajan.

Nämä arvot ovat API-kutsuparametreja, joita voi muuttaa. Niiden tarkoituksena on varmistaa, että lähdetiedot säilyvät paikkansa pitävinä. Jos haluat reaaliaikaisten päivitysten sisältyvän kauemmin, ne on lisättävä tietolähteeseen siten, että ne noudetaan seuraavassa ajoitetussa päivityksessä.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Yhtenäistetyn asiakasprofiilin kenttien reaaliaikainen päivitys

Päivitetyt profiilit näkyvät asiakaskorttinäkymässä tai muissa visualisoinneissa muutamassa sekunnissa.

Koska reaaliaikaiset toiminnot tapahtuvat tietojen yhdistämisen jälkeen, ne koskevat vain yhdistettyjä asiakasprofiileja. Näin ollen reaaliaikaiset profiili muutokset eivät päivitä mittoja, segmentin jäseniä tai rikastuksia.

### <a name="limitations"></a>Rajoitukset

- Asiakasprofiilit voidaan päivittää, mutta niitä ei voi luoda tai poistaa.
- Reaaliaikaisten päivitysten vieminen ulkoisiin järjestelmiin, kuten Power BI:hin, ei ole tällä hetkellä mahdollista.

## <a name="real-time-creation-of-activities"></a>Aktiviteettien reaaliaikainen luominen

Reaaliaikaisen ohjelmointirajapinnan avulla voi julkaista uuden aktiviteetin lähdejärjestelmästä (yksittäisestä lähdetietueesta) yhtenäiseen asiakasprofiiliin. Uusi aktiviteetti on käytettävissä yhtenäisenä aktiviteettina, joka on yhdistetty asiakasprofiilin aikajanalla muutamassa sekunnissa. Aikajana näkyy asiakaskorttinäkymässä tai muussa määritetyssä aikajanaintegraatiossa.

> [!NOTE]
>
> - Aktiviteetit ovat muuttumattomia. Ne eivät muutu luonnin jälkeen.
> - Tällä hetkellä segmenttejä ja mittoja ei voi päivittää uuden aktiviteetin perusteella.
> - Vain reaaliaikaisen ohjelmointirajapinnan kautta lisätyt aktiviteetit eivät ole osa vientiä, eivätkä ne näy PowerBI:ssä.

Reaaliaikainen ohjelmointirajapinta voidaan yhdistää kahdella tavalla:

- [epäsuorasti](#connect-via-the-dynamics-365-customer-insights-connector) käyttämällä [Dynamics 365 Customer Insights -liitintä](/connectors/customerinsights/)
- [suoraan](#connect-directly-to-the-real-time-api) koodin kautta

Seuraavat edellytykset koskevat molempia tapoja:

- Customer Insights -ympäristö
- Yhdistetyt asiakasprofiilit
- Määritetyt ja suoritetut aktiviteetit
- Osallistujan tai järjestelmänvalvojan oikeudet tilin todentamiseen

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Yhdistä Dynamics 365 Customer Insights -liittimen kautta

Reaaliaikainen ohjelmointirajapinta voi käsitellä tietoja erityisestä Power Platform -liittimestä, [Dynamics 365 Customer Insights -liittimestä](/connectors/customerinsights/), ilman että sinun tarvitsee kirjoittaa ja ottaa käyttöön mitään koodia.    
Yhdistin voi tehdä samat reaaliaikaiset toiminnot kuin ohjelmointirajapinta. Tarvitset kelvollisen käyttöoikeuden premium-liittimiin. Lisätietoja:[Power Appsin ja Power Automaten käyttöoikeuksien usein kysytyt kysymykset](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps ja/tai Power Automate](/connectors/)
- Azure [Logic-sovellukset](/azure/connectors/apis-list)

Lisätietoja virtojen luomisesta on [Power Automate -ohjeessa](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Yhteyden muodostaminen suoraan reaaliaikaiseen ohjelmointirajapintaan

Voit käyttää reaaliaikaisia ominaisuuksia muodostamalla oman jakson ja yhdistämällä suoraan reaaliaikaiseen ohjelmointirajapintaan.    
Voit lähettää aktiviteetin lähdejärjestelmän muodossa tai UnifiedActivity-muodossa. Hae muoto tekemällä API-kutsu kohteeseen /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Tietoja tästä ohjelmointirajapinnasta, kuten parametrit ja vastaukset, on **EntityData**-osassa [Customer Insights -ohjelmointirajapintojen viitteessä](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Lisätietoja on kohdassa [Customer Insights -ohjelmointirajapintojen käyttäminen](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Tietoja reaaliaikaisesta käytöstä telemetriatietojen avulla

Yleiskatsaus reaaliaikaiseen ohjelmointirajapintaan tehtyjen pyyntöjen määrästä ja tietoja järjestelmässä mahdollisesti esiintyvistä ongelmista. Voit [käyttää reaaliaikaista telemetriaa](system.md#api-usage-tab). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]