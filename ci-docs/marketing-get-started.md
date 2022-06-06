---
title: Yhtenäisten profiilien käyttäminen Dynamics 365 Marketingissa
description: Katso, miten voit integroida yhtenäisiä profiileja ja segmenttejä Dynamics 365 Marketingiin.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4cc3cbde97d0f9da198652e86c0843476393b646
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833304"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Yhtenäisten asiakasprofiilien käyttäminen Dynamics 365 Marketingissa

[Dynamics 365 Marketing](/dynamics365/marketing/overview) parantaa asiakaskokemuksia, jolloin voit järjestää yksilöllisiä siirtymiä kaikissa kosketuspisteissä suhteiden vahvistamiseksi ja uskollisuuden ansaitsemiseksi. Dynamics 365 Marketing -sovellus toimii saumattomasti Dynamics 365 Salesin, Dynamics 365 Customer Insightsin, Microsoft Teamsin ja muiden tuotteiden kanssa, ja sen avulla voit tehdä nopeampia ja parempia päätöksiä datan ja tekoälyn avulla.

Yhdistämällä Customer Insights -tiedot Marketingiin voit:

- Keskittyä yhdistettyihin asiakasprofiileihin ja -segmentteihin. Näin voit lähestyä kutakin asiakasta riippumatta asiakastietojen sijainnista.
- Käyttää sähköpostien, tekstiviestien ja palveluilmoitusten dynaamisen sisällön (kuten mukautettujen tunnusten) perustana kanta-asiakkuuden tilaa, tilauksen uusimispäivämäärää, pääasiakasta tai mitä tahansa muuta mittaa, jonka olet tallentanut yhdistettyyn Customer Insights -profiiliin.
- Ladata tietoja Marketingista Customer Insightsiin ja yhdistää ne muista lähteistä saatuihin asiakastietoihin.
- Käyttää Customer Insights -tietojen puhdistusta, rikastamista ja epätarkkojen vastaavuuksien työkaluja.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Monipuolisten asiakasprofiilien käyttö reaaliaikaisessa markkinoinnissa

Reaaliaikaisen markkinoinnin avulla voit luoda [mukautettuja käynnistimiä](/dynamics365/marketing/real-time-marketing-custom-triggers), jotka käynnistävät asiakassiirtymiä asiakkaiden toimintojen perusteella. Mitä henkilökohtaisempia tietosi ovat, sitä merkityksellisempiä ja henkilökohtaisempia siirtymäsi ovat. Tämä tekee Marketing- ja Customer Insights -palveluiden yhdistämisestä niin tehokasta. Voit [yhdistää tietoja](data-unification.md) mistä tahansa lähteestä ja käyttää niitä sitten täysin räätälöityjen asiakassiirtymien pohjana.

Lisätietoja: [Customer Insights -profiilien ja -segmenttien käyttö reaaliaikaisessa markkinoinnissa](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Yhdistettyjen segmenttien käyttäminen lähtevien asiakassiirtymien kanssa

Customer Insights sallii sinun jalostaa tietoja useista lähteistä ja yhdistää ne koostettuihin asiakassegmentteihin. Kun [Customer Insights yhdistetään lähtevään markkinointiin](export-dynamics365-marketing.md), nämä segmentit näytetään *ja* päivitetään automaattisesti asiakassiirtymien suunnitteluohjelmassa.

Lue lisää: [Käytä Dynamics 365 Customer Insightsin segmenttejä Dynamics 365 Marketingin kanssa](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Tietojen noutaminen omasta Azure Data Lake Storage -säiliöstäsi

Pilvitallennustila ei ole ainoa vaihtoehtosi, jos haluat käyttää Customer Insights -tietoja Marketing-palvelun kanssa. Jos olet jo määrittänyt oman Azure Data Lake Storage -säiliösi, voit yhdistää sen Customer Insightsiin ja jakaa tiedot sitten Marketing-sovelluksen kanssa samalla tavalla kuin pilvipohjaista kokoonpanoa käytettäessä.

Lue lisää: [Tietojen jakamisen ottaminen käyttöön Dataversen kanssa omasta Azure Data Lake Storagesta](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
