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
ms.custom: intro-internal
ms.openlocfilehash: bf1bbcd31333c8a557b59b001112042a1783546ab0cd2af394d8af2953a493f4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032754"
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