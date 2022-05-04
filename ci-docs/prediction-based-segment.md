---
title: Ennusteen tulokseen perustuvat segmentit
description: Luo segmentit ennustemallin tulosentiteetin perusteella.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b0b3357cdf3c049bd92f6c3f690f27433df9117b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646365"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Luo segmentti ennustemallin perusteella (esiversio)

Ennusteiden tulokset koskevat joskus vain asiakkaiden alijoukkoa. Lisää suositusten mukauttamista luomalla segmenttejä ennustemallin tuloksista. Voit esimerkiksi antaa tiettyjä suosituksia asiakkaille, jotka haluavat tietyntyyppistä palvelua. 

## <a name="prerequisites"></a>Edellytykset

- Vähintään [osallistujan oikeudet](permissions.md) Customer Insightsissa.

- Customer Insightsissa määritetty tuotesuositus, tapahtumaperusteisen asiakaspoistuman, tilausten asiakaspoistuman tai asiakkaan elinkaaren arvon malli. Tarkista eri mallien määrityksen edellytykset:

  - [Tuotesuositusmalli](predict-product-recommendation.md)
  - [Tilausten vaihtuvuus -malli](predict-subscription-churn.md)
  - [Tapahtumaperusteinen vaihtuvuus -malli](predict-transactional-churn.md)
  - [Asiakkaan elinkaaren arvo -malli](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Ennusteisiin perustuvan asiakassegmentin luominen

1. Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.

1. Valitse tarkasteltavan mallin vieressä pystysuuntaiset kolme pistettä ja valitse sitten **Näytä**.

1. Valitse tulossivulla **Luo segmentti**. Lisätietoja tulossivusta on malliin liittyvässä artikkelissa.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Näyttökuva ennusteen tulossivusta korostaen Luo segmentti -toimintoa.":::

1. Luo uusi segmentti valitun mallin tulosentiteetin perusteella. Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).