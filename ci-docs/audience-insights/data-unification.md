---
title: Tietojen yhdistäminen
description: Tietoja käytettyjen tietojen yhdistämisestä.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 73d8006c670268420f8cd6a2b37cb214ba1bbd6c
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597875"
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


[!INCLUDE[footer-include](../includes/footer-banner.md)]