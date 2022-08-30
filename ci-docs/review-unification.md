---
title: Tietojen yhdistämisen tarkistaminen
description: Tarkista tietojen yhdistämisvaiheet, luo unified customer profiles -profiilit ja tarkista tulokset
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303963"
---
# <a name="review-data-unification"></a>Tietojen yhdistämisen tarkistaminen

Tarkista muutosten yhteenveto, luo yhtenäinen profiili ja tarkista tulokset.

## <a name="review-and-create-customer-profiles"></a>Tarkista ja luo asiakasprofiileja

Tässä yhdistämisprosessin viimeisessä vaiheessa näkyy yhteenveto prosessin osavaiheista ja mahdollisuus tehdä muutoksia, ennen kuin luot yhtenäisen profiilin.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Kuvakaappaus kohdasta Tarkista ja luo asiakasprofiileja.":::

1. Tarkista ja tee tarvittavat muutokset valitsemalla tietojen yhdistämisvaiheissa **Muokkaa**.

1. Jos valintasi ovat haluamasi, valitse **Luo asiakasprofiilit** (tai **Luo tiliprofiilit** B2B-tilanteessa). **Yhtenäistä**-sivu tulee näkyviin, kun unified customer profile luodaan.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Näyttökuva yhtenäistämissivulla, jossa ruutujen tilana on Jonossa tai päivittää":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Yhdistäminen-algoritmin valmistuminen kestää jonkin aikaa, eikä määritystä voi muuttaa, ennen kuin se on valmis.

## <a name="view-the-results-of-data-unification"></a>Tietojen yhdistämisen tulosten tarkasteleminen

Yhdistämisen jälkeen **Tiedot** > **Yhdistä** -sivu näyttää yhtenäistettyjen asiakasprofiilien (tai B2B-tilanteessa tiliprofiilien) määrän. Jokaisen yhdistäminenprosessin vaiheen tulokset näkyvät kussakin ruudussa. Esimerkiksi **Lähdekentät** näyttää yhdistettyjen määritteiden (kenttien) määrän ja **Tietueiden kaksoiskappaleet** näyttää löydettyjen tietueiden kaksoiskappaleiden määrän.

:::image type="content" source="media/m3_unified.png" alt-text="Näyttökuva Tietojen yhtenäistäminen -sivusta, kun tiedot on yhdistetty.":::

> [!TIP]
> **Vastaavat ehdot** -ruutu näkyy vain, jos valittuna on useita entiteettejä.

Suosittelemme, että tarkistat tulokset, erityisesti vastaavuussääntöjen [laadun ja muokkaat](data-unification-update.md#manage-match-rules) niitä tarvittaessa.

Tee tarvittaessa [muutoksia yhdistämisasetuksiin](data-unification-update.md) ja suorita yhtenäinen profiili uudelleen.

### <a name="verify-output-entities-from-data-unification"></a>Tietojen yhdistämisen tulosentiteettien tarkistaminen

Tarkista tulosentiteetit siirtymällä kohtaan **Tiedot** > **Entiteetit**.

Yhdistettyä asiakasprofiilientiteettiä kutsutaan **Profiilit**-osassa nimellä *Asiakas*. Ensimmäinen onnistunut yhdistäminen luo yhtenäisen *Asiakas*-entiteetin. Kaikki seuraavat suoritukset laajentavat kyseistä entiteettiä.

Kaksoiskappaleiden poistamisen ja yhdistämisen entiteetit luodaan ja näytetään **Järjestelmä**-osassa. Entiteetti, josta kaksoiskappaleet on poistettu luodaan kullekin lähde-entiteetille nimellä **Deduplication_DataSource_Entity**. **ConflationMatchPairs**-entiteetti sisältää tietoja entiteettien välisistä vastaavuuksista.

Kaksoiskappaleiden poiston tulosentiteetti sisältää seuraavat tiedot:
- Tunnukset/avaimet
  - Perusavaimen ja vaihtoehtoisen tunnuksen kentät. Vaihtoehtoinen tunnuskenttä sisältää kaikki tietueelle tunnistetut vaihtoehtoiset tunnukset.
  - Deduplication_GroupId-kentässä on ryhmä tai klusteri, joka sellainen entiteetti määrittää, joka ryhmittelee kaikki samanlaiset tietueet määritettyjen kaksoiskappaleiden poiston kenttien perusteella. Sitä käytetään järjestelmän käsittelyssä. Jos manuaalisia kaksoiskappaleiden poiston sääntöjä ei ole määritetty, ja järjestelmän määrittämät kaksoiskappaleiden poiston säännöt on otettu käyttöön, tätä kenttää ei ehkä löydy kaksoiskappaleiden poiston tulosentiteetistä.
  - Deduplication_WinnerId: Tämä kenttä sisältää määritettyjen ryhmien tai klustereiden voittaneen tunnuksen. Jos Deduplication_WinnerId on sama kuin tietueen ensisijaisen avaimen arvo, tietue on voittanut tietue.
- Kenttiä käytetään kaksoiskappaleiden poiston sääntöjen määrittämisessä.
- Sääntö- ja Pistemäärä-kentät määrittävät, mitä kaksoiskappaleiden poiston sääntöjä noudatetaan. Ne määrittävät myös vastaavan algoritmin palauttaman pistemäärän.

## <a name="next-step"></a>Seuraava vaihe

- B2B-tilanteissa voit suorittaa valinnaisesti [yhteyshenkilöiden yhdistämisen](data-unification-contacts.md).

- Määritä B2C-tilanteessa [aktiviteetteja](activities.md), [rikastuksia](enrichment-hub.md), [suhteita](relationships.md) tai [mittareita](measures.md) saat enemmän tietoja asiakkaistasi.

[!INCLUDE[footer-include](includes/footer-banner.md)]
