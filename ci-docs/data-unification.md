---
title: Yhtenäisen näkymän luominen asiakkaille
description: Käy tietojen yhdistäminen läpi tietojen kanssa ja luo asiakasprofiilien yksittäinen päätietojoukko.
ms.date: 10/18/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: eb5bbc538f93bc7097581db233d684870ade84a2
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646008"
---
# <a name="data-unification-overview"></a>Tietojen yhdistämisen yleiskatsaus

Kun [tietolähteet on määritetty](data-sources.md), tiedot voidaan yhdistää. Tietojen yhdistämisessä on kolme vaihetta: **vastaavuusmääritys**, **täsmäyttäminen** ja **yhdistäminen**.

Tietojen yhdistämisprosessin avulla voit yhdistää erilliset tietolähteet yhdeksi päätietojoukoksi, jolla saadaan yhdistetty näkymä asiakkaista. Yhdistämisvaiheet ovat pakollisia, ja ne suoritetaan seuraavassa järjestyksessä:

1. [Kartta](map-entities.md)
2. [Täsmäyttäminen](match-entities.md)
3. [Yhdistäminen](merge-entities.md)

Tietojen yhdistämisen jälkeen voit valinnaisesti

- [määrittää entiteettien väliset suhteet](relationships.md), joilla luodaan edistyneitä segmenttejä
- [rikastaa tietoja](enrichment-hub.md), joiden avulla saat merkityksellisiä tietoja asiakkaista
- [määrittää aktiviteetteja](activities.md) joistakin käytetyistä määritteistä.


[!INCLUDE [footer-include](includes/footer-banner.md)]