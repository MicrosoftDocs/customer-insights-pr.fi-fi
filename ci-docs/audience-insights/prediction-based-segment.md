---
title: Ennusteen tulokseen perustuvat segmentit
description: Luo segmentit ennustemallin tulosentiteetin perusteella.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741425"
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