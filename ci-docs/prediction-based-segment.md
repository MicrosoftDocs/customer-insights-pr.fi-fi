---
title: Uuden segmentin luominen ennustemallin perusteella
description: Luo segmentit ennustemallin tulosentiteetin perusteella.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610416"
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

1. Valitse ensin arvioitava malli ja sitten **Näytä**.

1. Valitse tulossivulla **Luo segmentti**. Lisätietoja tulossivusta on malliin liittyvässä artikkelissa.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Näyttökuva ennusteen tulossivusta korostaen Luo segmentti -toimintoa.":::

1. Luo uusi segmentti käyttämällä valitun mallin tulosentiteetin määritteitä. Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).

> [!TIP]
> Ennustemallin segmentti voidaan luoda myös **Segmentit**-sivulla valitsemalla ensin **Uusi** ja sitten **Luominen kohteesta** > **Älykäs toiminto**. Lisätietoja on kohdassa [Uuden segmenttien luominen pikasegmenttien avulla](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
