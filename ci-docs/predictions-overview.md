---
title: Ennusteiden yleiskatsaus
description: Dynamics 365 Customer Insights -sovelluksen kattamia ennusteskenaarioita ja vaihtoehtoja.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610186"
---
# <a name="predictions-overview"></a>Ennusteiden yleiskatsaus

Dynamics 365 Customer Insightsissa on erilaisia vaihtoehtoja, joilla voit hyödyntää tekoälyä ja koneoppimista tietojen ennustamiseen.

## <a name="out-of-box-models"></a>Valmiit mallit

Helpoin tapa aloittaa tietojen ennustaminen on esimääritetyt mallit, joita kutsutaan usein valmiiksi malleiksi. Ne edellyttävät vain tiettyjä tietoja ja rakennetta, jotta saat nopeasti tietoja. Käytettävissä olevat mallit:

# <a name="individual-consumers-b-to-c"></a>[Yksittäiset kuluttajat (kuluttajakauppa)](#tab/b2c)

- [Asiakkaan elinkaariarvo](predict-customer-lifetime-value.md): Ennustaa asiakkaan potentiaalisen tuoton koko ajan, jonka se on vuorovaikutuksessa yrityksen kanssa.
- [Tuotesuositus](predict-product-recommendation.md): ehdottaa ostokäyttäytymiseen perustuvia ennakoivia tuotesuosituksia ja asiakkaita, joilla on samanlaiset ostomallit.
- [Tilausvaihtuvuus](predict-subscription-churn.md): Ennustaa, onko asiakkaalla riski lakata käyttämästä yrityksesi tilaustuotteita tai palveluja.
- [Liiketapahtumien vaihtuminen](predict-transactional-churn.md): Ennustaa, ostaako yksittäinen asiakas enää tuotteita tai palveluja tietyllä aikavälillä.
- [Asenneanalyysi](sentiment-analysis.md): asiakaspalautteen asenteen analysointi ja usein mainittujen liiketoiminnan alueiden tunnistaminen.

# <a name="business-accounts-b-to-b"></a>[Yritystilit (yritysten väliset)](#tab/b2b)

- [Liiketapahtumien vaihtuminen](predict-transactional-churn.md): Ennustaa, ostaako asiakas enää tuotteita tai palveluja tietyllä aikavälillä.

---

> [!TIP]
> On suositeltavaa päivittää vakiomallit säännöllisesti päivitetyillä tiedoilla, jotta ne ilmoittavat yrityksen käyttötapauksen tarkasti. Tiedot päivittyvät tilapäisinä, kun järjestelmä käyttää uusia tai päivitettyjä tietolähteitä. Mallit kuitenkin vain päivittävät pisteet tässä tapauksessa ja jatkavat nykyisten koulutustietojen käyttöä.
>
> **Päivitysaikataulu** määritetään määrittämällä mallin uudelleenkoulutusaikataulu määrityksen aikana. Malli uudelleenkouluttaa ja uudelleenpisteyttää tämän aikataulun mukaan, jota voit muuttaa milloin tahansa.

## <a name="azure-machine-learning-integration"></a>Azuren automaattianalyysipalvelujen integraatio

Jos organisaatio käyttää jo koneoppimisen skenaarioita, jotka perustuvat Azure-koneoppimisen kokeiluihin, Customer Insightsin mukautetut mallit -ominaisuus auttaa yhdistämään pisteet. Luo työnkulkuja, jotka auttavat valitsemaan tiedot, joista haluat saada tietoja, ja yhdistä tulokset yhtenäisiksi asiakasprofiileiksi. Lisätietoja on aiheessa [Mukautetut koneoppimismallit](custom-models.md).

## <a name="manage-existing-predictions"></a>Aiemmin luotujen ennusteiden hallinta

Valitse **Älykäs toiminto** > **Ennusteet**-sivu. Tarkastele **Omat ennusteet** -välilehdessä luotuja ennusteita, niiden ennustetyyppiä, tuloste-entiteetin nimeä, tilaa, ennusteen edellistä muokkausaikaa ja tietojen edellistä päivitysaikaa. Ennusteet voidaan lajitella minkä tahansa sarakkeen mukaan.

Käytettävissä olevia toimintoja voi tarkastella valitsemalla ennusteen.

:::image type="content" source="media/predictions.png" alt-text="Omat ennusteet -sivu":::

- **Muokkaa** ennustetta, jos sen ominaisuuksia halutaan muuttaa.
- [**Päivitä**](#refresh-a-prediction) ennuste sisältämään uusimmat tiedot.
- **Näytä** ennusteen tiedot.
- [**Syötetietojen käytettävyysraportti**](#view-the-input-data-usability-report) sisältää virheet, varoitukset ja suositukset.
- **Poista** ennuste.

### <a name="refresh-a-prediction"></a>Ennusteen päivittäminen

Ennusteita voidaan päivittää automaattisen aikataulun mukaan tai manuaalisesti tarvittaessa. Kaikki ennusteet voidaan päivittää manuaalisesti valitsemalla **Päivitä kaikki**. Ennuste päivitetään manuaalisesti valitsemalla ensin se ja sitten **Päivitä**. [Automaattinen päivitys ajoitetaan](schedule-refresh.md) valitsemalla **Hallinta** > **Järjestelmä** > **Aikatauluta**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Näytä syötetietojen käytettävyysraportti

Syöttötietojen käytettävyysraportti tarjoaa konsolidoidun kuvan virheistä ja varoituksista, joita valmiit ennusteet saattavat tuottaa. Se antaa myös suosituksia mallin suorituskyvyn parantamista varten.

Raportti on käytettävissä sen jälkeen, kun malli on suorittanut sen koulutusprosessin. Se luodaan kullekin mallille erikseen riippumatta siitä, onnistuiko mallin koulutus.

Valitse **Omat ennusteet** -välilehdessä ensin ennuste ja sitten **Syötetietojen käytettävyysraportti**. Vaihtoehtoisesti voit valita ennusteen tietonäkymässä **Syötetietojen käytettävyysraportti**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Esimerkki syöttötietojen käytettävyysraportista, jossa näkyy taulukko, jossa on virheitä, varoituksia ja suosituksia.":::

Raportin sisältö:

- **Nimi:** virheen, varoituksen tai suosituksen kuvaileva nimi.
- **Vaihe:** mallivaihe, kouluttaa tai pisteyttää, tietoihin viitataan.
- **Tila:** tietojen vakavuus (virhe, varoitus, suositus).
- **Sarakkeen nimi:** Entiteetin sarake, jota on muutettava mallin suorituskyvyn parantamiseksi.
- **Entiteetin nimi:** Entiteetin nimi, jota on muutettava mallin suorituskyvyn parantamiseksi.
- **Tiedot:** Tietoja virheestä, varoituksesta tai suosituksista.

[!INCLUDE [footer-include](includes/footer-banner.md)]
