---
title: Yleiskatsaus tuetuista ennusteskenaarioista
description: Dynamics 365 Customer Insights -sovelluksen kattamia ennusteskenaarioita ja vaihtoehtoja.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b73046844f6009a2b163b5eaadf5f63f75cda1d8
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539157"
---
# <a name="predictions-overview"></a>Ennusteiden yleiskatsaus

Dynamics 365 Customer Insightsissa on erilaisia vaihtoehtoja, joilla voit hyödyntää tekoälyä ja koneoppimista tietojen ennustamiseen. 

## <a name="out-of-box-models"></a>Valmiit mallit

Helpoin tapa aloittaa tietojen ennustaminen on esimääritetyt mallit, joita kutsutaan usein valmiiksi malleiksi. Ne edellyttävät vain tiettyjä tietoja ja rakennetta, jotta saat nopeasti tietoja. Tällä hetkellä käytettävissä ovat seuraavat mallit: 
- [Asiakkaan elinkaariarvo](predict-customer-lifetime-value.md): Ennustaa asiakkaan potentiaalisen tuoton koko ajan, jonka se on vuorovaikutuksessa yrityksen kanssa. 
- [Tuotesuositus](predict-product-recommendation.md): ehdottaa ostokäyttäytymiseen perustuvia ennakoivia tuotesuosituksia ja asiakkaita, joilla on samanlaiset ostomallit.
- [Tilausvaihtuvuus](predict-subscription-churn.md): Ennustaa, onko asiakkaalla riski lakata käyttämästä yrityksesi tilaustuotteita tai palveluja.
- [Liiketapahtumien vaihtuminen](predict-transactional-churn.md): Ennustaa, jos asiakas ei enää osta tuotteitasi tai palveluitasi tietyllä aikavälillä.

## <a name="azure-machine-learning-integration"></a>Azuren automaattianalyysipalvelujen integraatio

Jos organisaatio käyttää jo koneoppimisen skenaarioita, jotka perustuvat Azure-koneoppimisen kokeiluihin, Customer Insightsin mukautetut mallit -ominaisuus auttaa yhdistämään pisteet. Luo työnkulkuja, jotka auttavat valitsemaan tiedot, joista haluat saada tietoja, ja yhdistä tulokset yhtenäisiksi asiakasprofiileiksi. Lisätietoja on aiheessa [Mukautetut koneoppimismallit](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builderin ennuste

Joskus tietojoukot ovat puutteellisia ja joitakin arvoja puuttuu. Customer Insights voi auttaa ennustamaan puuttuvat arvot Asiakas-entiteetistä ja segmentistä. Lisätietoja on ohjeaiheessa [Osittaisten tietojen täydentäminen ennusteilla](predictions.md).
