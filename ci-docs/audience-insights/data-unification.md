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
ms.openlocfilehash: 2012d32494ccd4639cbffbb81d4f6eac1258e23b
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353815"
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