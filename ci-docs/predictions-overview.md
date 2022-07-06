---
title: Ennusteiden yleiskatsaus
description: Dynamics 365 Customer Insights -sovelluksen kattamia ennusteskenaarioita ja vaihtoehtoja.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: a87af80fa713a1ac70493345c0c920e416692b0f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081200"
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

> [!TIP]
> On suositeltavaa päivittää vakiomallit säännöllisesti päivitetyillä tiedoilla, jotta ne ilmoittavat yrityksen käyttötapauksen tarkasti. Tiedot päivittyvät tilapäisinä, kun järjestelmä käyttää uusia tai päivitettyjä tietolähteitä. Mallit kuitenkin vain päivittävät pisteet tässä tapauksessa ja jatkavat nykyisten koulutustietojen käyttöä.
> 
> Voit määrittää **päivitysaikataulun** määrittämällä mallin uudelleenkoulutusaikataulun määrityskokemuksessa. Malli uudelleenkouluttaa ja uudelleenpisteyttää tämän aikataulun mukaan, jota voit muuttaa milloin tahansa.


## <a name="azure-machine-learning-integration"></a>Azuren automaattianalyysipalvelujen integraatio

Jos organisaatio käyttää jo koneoppimisen skenaarioita, jotka perustuvat Azure-koneoppimisen kokeiluihin, Customer Insightsin mukautetut mallit -ominaisuus auttaa yhdistämään pisteet. Luo työnkulkuja, jotka auttavat valitsemaan tiedot, joista haluat saada tietoja, ja yhdistä tulokset yhtenäisiksi asiakasprofiileiksi. Lisätietoja on aiheessa [Mukautetut koneoppimismallit](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder -ennuste

Joskus tietojoukot ovat puutteellisia ja joitakin arvoja puuttuu. Customer Insights voi auttaa ennustamaan puuttuvat arvot Asiakas-entiteetistä ja segmentistä. Lisätietoja on ohjeaiheessa [Osittaisten tietojen täydentäminen ennusteilla](predictions.md).
