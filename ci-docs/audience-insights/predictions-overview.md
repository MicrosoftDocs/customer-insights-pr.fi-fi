---
title: Yleiskatsaus tuetuista ennusteskenaarioista
description: Dynamics 365 Customer Insights -sovelluksen kattamia ennusteskenaarioita ja vaihtoehtoja.
ms.date: 12/21/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: c692785c7d81ab660ba2e07411e986c67c1a5d0a
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228240"
---
# <a name="predictions-overview"></a>Ennusteiden yleiskatsaus

Dynamics 365 Customer Insightsissa on erilaisia vaihtoehtoja, joilla voit hyödyntää tekoälyä ja koneoppimista tietojen ennustamiseen. 

## <a name="out-of-box-models"></a>Valmiit mallit

Helpoin tapa aloittaa tietojen ennustaminen on esimääritetyt mallit, joita kutsutaan usein valmiiksi malleiksi. Ne edellyttävät vain tiettyjä tietoja ja rakennetta, jotta saat nopeasti tietoja. Tällä hetkellä käytettävissä ovat seuraavat mallit: 

# <a name="individual-consumers-b-to-c"></a>[Yksittäiset kuluttajat (kuluttajakauppa)](#tab/b2c)

- [Asiakkaan elinkaariarvo](predict-customer-lifetime-value.md): Ennustaa asiakkaan potentiaalisen tuoton koko ajan, jonka se on vuorovaikutuksessa yrityksen kanssa.
- [Tuotesuositus](predict-product-recommendation.md): ehdottaa ostokäyttäytymiseen perustuvia ennakoivia tuotesuosituksia ja asiakkaita, joilla on samanlaiset ostomallit.
- [Tilausvaihtuvuus](predict-subscription-churn.md): Ennustaa, onko asiakkaalla riski lakata käyttämästä yrityksesi tilaustuotteita tai palveluja.
- [Liiketapahtumien vaihtuminen](predict-transactional-churn.md): Ennustaa, jos asiakas ei enää osta tuotteitasi tai palveluitasi tietyllä aikavälillä.
- [Asenneanalyysi](sentiment-analysis.md): asiakaspalautteen asenteen analysointi ja usein mainittujen liiketoiminnan alueiden tunnistaminen.

# <a name="business-accounts-b-to-b"></a>[Yritystilit (yritysten väliset)](#tab/b2b)

- [Liiketapahtumien vaihtuminen](predict-transactional-churn.md): Ennustaa, jos asiakas ei enää osta tuotteitasi tai palveluitasi tietyllä aikavälillä.

---


## <a name="azure-machine-learning-integration"></a>Azuren automaattianalyysipalvelujen integraatio

Jos organisaatio käyttää jo koneoppimisen skenaarioita, jotka perustuvat Azure-koneoppimisen kokeiluihin, Customer Insightsin mukautetut mallit -ominaisuus auttaa yhdistämään pisteet. Luo työnkulkuja, jotka auttavat valitsemaan tiedot, joista haluat saada tietoja, ja yhdistä tulokset yhtenäisiksi asiakasprofiileiksi. Lisätietoja on aiheessa [Mukautetut koneoppimismallit](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder -ennuste

Joskus tietojoukot ovat puutteellisia ja joitakin arvoja puuttuu. Customer Insights voi auttaa ennustamaan puuttuvat arvot Asiakas-entiteetistä ja segmentistä. Lisätietoja on ohjeaiheessa [Osittaisten tietojen täydentäminen ennusteilla](predictions.md).
