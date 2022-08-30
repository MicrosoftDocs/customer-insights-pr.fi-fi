---
title: Yhtenäisen yhteyshenkilöprofiilin luominen (esiversio)
description: Käy tietojen yhdistäminen läpi ja luo yhteyshenkilöiden yksittäinen päätietojoukko.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305032"
---
# <a name="create-a-unified-contact-profile-preview"></a>Yhtenäisen yhteyshenkilöprofiilin luominen (esiversio)

Kun [olet yhdistänyt liiketoimintatilit](map-entities.md), voit halutessasi yhdistää kyseisten tilien yhteyshenkilöt ja linkittää yhdistetyt yhteyshenkilöt yhtenäistettyihin tileihin. Yhteyshenkilöiden yhdistämisprosessi yhdistää yhteyshenkilötiedot useista tietolähteistä, poistaa kaksoiskappaleet, täsmää entiteettien välisiä tietoja, määrittää semanttisen yhdistämismäärityksen, luo suhteet yhteyshenkilöiden ja tilien välille ja luo sitten yhtenäisen yhteyshenkilöprofiilin.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Ensimmäiset vaiheet ovat samat kuin tilien yhtenäistämisvaiheet.

## <a name="prerequisites"></a>edellytykset

Tili- ja yhteyshenkilötietueissa on oltava yksilöllinen avain (viiteavain), joka yhdistää ne. Esimerkiksi asiakastietueessa ja yhteyshenkilötietueessa oleva asiakastunnus, joka yhdistää asiakas- ja yhteyshenkilötiedot toisiinsa.

## <a name="preview-limitations"></a>Esiversion rajoitukset

- Yhteyshenkilöt, joilla ei ole linkkiä tiliin, poistetaan.
- Jos tilin kaksoiskappale poistetaan, yhdistämisasetusten perusteella tunnistetaan voittajatietue. Häviäjätietueita ei valita, joten ne poistetaan. Häviäjätietueisiin liittyvät yhteyshenkilöt poistetaan.
- Tilillä voi olla useita yhteyshenkilöitä, mutta yhteyshenkilö on linkitetty yhteen tiliin.
- Semanttisen yhdistämisvaiheen yhteyshenkilömääritteet ovat ainoat määritteet, jotka voidaan näyttää asiakaskortissa. Käytettävissä on kuitenkin 17 määritettä.

## <a name="select-source-fields"></a>Valitse lähdekentät

1. Valitse **Yhdistä yhteyshenkilöt (esiversio)** -kohdassa **Aloitus**.

1. [Valitse yhteyshenkilön tietolähteiden entiteetit ja kentät](map-entities.md), mukaan lukien perusavaimet ja määritetyypit.

1. Valitse **Seuraava**.

## <a name="remove-duplicate-records"></a>Tietueiden kaksoiskappaleiden poistaminen

1. Voit myös määrittää valittujen entiteettien [kaksoiskappaleiden poistamisen säännöt](remove-duplicates.md).

1. Valitse **Seuraava**.

## <a name="match-conditions"></a>Yhdistämisehdot

1. [Määritä täsmäytysjärjestys ja säännöt](match-entities.md) entiteettienvälistä täsmäytystä varten.

1. Valitse **Seuraava**.

## <a name="unify-contact-fields"></a>Yhdistä yhteyshenkilökentät

1. [Yhdistä ja sulje pois yhteyshenkilökentät](merge-entities.md).

1. Valitse **Seuraava**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Määritä yhdenmukaistettujen yhteyshenkilöiden semanttiset kentät

Tämä yhdistämisprosessin vaihe yhdistää yhdistetyt yhteyshenkilökentät semanttisiin tyyppeihin. B-B-tilanteessa asiakaskortissa näkyvät tilit. Kun kortti valitaan, kaikki tiliin liittyvät yhteyshenkilöt näkyvät. Tässä vaiheessa yhdistetyt kentät näkyvät korteissa.

1. Valitse semanttinen tyyppi, joka yhdistyy kuhunkin yhdenmukaistettuun kenttään. Valitse **Ei mitään**, jos semanttinen tyyppi ei ole käytettävissä.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Näyttökuva semanttisten kenttien sivusta semanttisten tyyppien määrittämiseksi." lightbox="media/semantic_mapping.png":::

1. Kun kaikki yhdistetyt kentät on yhdistetty, valitse **Seuraava**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Määritä yhteyshenkilöiden ja tilien välinen suhde

Tässä yhdistämisprosessin vaihe yhdistää yhteyshenkilön tiedot yhdistetään vastaaviin asiakastietoihin.

1. Anna kullekin entiteetille seuraavat tiedot:

   - **Viiteavain yhteyshenkilöentiteetistä**: Valitse määrite, joka yhdistää yhteyshenkilöentiteetin tiliin.
   - **Tilientiteettiin**: Valitse yhteyshenkilöön liittyvä tilientiteetti.

   :::image type="content" source="media/contact_relationship.png" alt-text="Näyttökuva suhdesivusta, joka yhdistää yhteyshenkilö- ja asiakasentiteetit.":::

1. Valitse **Seuraava**.

## <a name="review-contact-unification"></a>Yhteyshenkilöiden yhdistämisen tarkistaminen

Tarkista muutosten yhteenveto, luo yhtenäinen profiili ja tarkista tulokset.

### <a name="review-and-create-contact-profiles"></a>Tarkista ja luo yhteyshenkilöprofiileja

Tässä yhdistämisprosessin viimeisessä vaiheessa näkyy yhteenveto prosessin osavaiheista ja mahdollisuus tehdä muutoksia, ennen kuin luot yhtenäisen yhteyshenkilöprofiilin.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Kuvakaappaus kohdasta Tarkista ja luo yhteyshenkilöprofiileja.":::

1. Tarkista ja tee tarvittavat muutokset valitsemalla yhteyshenkilöiden yhdistämisvaiheissa **Muokkaa**.

1. Jos valintasi ovat haluamasi, valitse **Luo yhteyshenkilöprofiilit**. **Yhtenäistä**-sivu tulee näkyviin, kun yhtenäinen yhteyshenkilöprofiili luodaan.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Näyttökuva Yhtenäistä yhteyshenkilöt -sivusta, jossa ruutujen tilana on Jonossa tai Päivittää.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Yhdistäminen-algoritmin valmistuminen kestää jonkin aikaa, eikä määritystä voi muuttaa, ennen kuin se on valmis.

### <a name="view-the-results-of-contact-unification"></a>Yhteyshenkilöiden yhdistämisen tulosten tarkasteleminen

Yhdistämisen jälkeen **Tiedot** > **Yhdistä** -sivu näyttää yhtenäisten yhteyshenkilöprofiilien määrän. Jokaisen yhdistämisprosessin vaiheen tulokset näkyvät kussakin ruudussa. Esimerkiksi **Lähdekentät** näyttää yhdistettyjen määritteiden (kenttien) määrän ja **Tietueiden kaksoiskappaleet** näyttää löydettyjen tietueiden kaksoiskappaleiden määrän.

:::image type="content" source="media/unified_contacts.png" alt-text="Näyttökuva Tietojen yhtenäistäminen -sivusta, kun yhteyshenkilöt on yhdistetty.":::

> [!TIP]
> **Vastaavat ehdot** -ruutu näkyy vain, jos valittuna on useita entiteettejä.

Suosittelemme, että tarkistat tulokset, erityisesti vastaavuussääntöjen [laadun ja muokkaat](data-unification-update.md#manage-match-rules) niitä tarvittaessa.

Tee tarvittaessa [muutoksia yhteyshenkilöiden yhdistämisasetuksiin](data-unification-update.md) ja suorita yhtenäinen profiili uudelleen.

### <a name="verify-output-entities-from-data-unification"></a>Tietojen yhdistämisen tulosentiteettien tarkistaminen

Tarkista tulosentiteetit siirtymällä kohtaan **Tiedot** > **Entiteetit**.

Yhtenäinen yhteyshenkilöprofiilientiteetti eli *ContactProfile* näkyy **Semanttiset entiteetit** -osassa. Ensimmäinen onnistunut yhdistäminen luo yhtenäisen *ContactProfile*-entiteetin. Kaikki seuraavat suoritukset laajentavat kyseistä entiteettiä.

*ContactsCustomer*-entiteetti (esiversio) luodaan ja näkyy **Profiilit**-osassa. Tämä entiteetti sisältää yhteyshenkilötiedot ilman linkkejä tileihin. Tätä entiteettiä käytetään syötteenä yhteyshenkilön yhtenäistämisen semanttiseen yhdistämismääritykseen ja suhdevaiheisiin.

Kaksoiskappaleiden poistamisen ja yhdistämisen entiteetit luodaan ja näytetään **Järjestelmä**-osassa. Entiteetti, josta kaksoiskappaleet on poistettu luodaan kullekin lähde-entiteetille nimellä **Deduplication_DataSource_Entity**. **ContactsConflationMatchPairs**-entiteetti sisältää tietoja entiteettien välisistä vastaavuuksista.

Kaksoiskappaleiden poiston tulosentiteetti sisältää seuraavat tiedot:
- Tunnukset/avaimet
  - Perusavaimen ja vaihtoehtoisen tunnuksen kentät. Vaihtoehtoinen tunnuskenttä sisältää kaikki tietueelle tunnistetut vaihtoehtoiset tunnukset.
  - Deduplication_GroupId-kentässä on ryhmä tai klusteri, joka sellainen entiteetti määrittää, joka ryhmittelee kaikki samanlaiset tietueet määritettyjen kaksoiskappaleiden poiston kenttien perusteella. Sitä käytetään järjestelmän käsittelyssä. Jos manuaalisia kaksoiskappaleiden poiston sääntöjä ei ole määritetty, ja järjestelmän määrittämät kaksoiskappaleiden poiston säännöt on otettu käyttöön, tätä kenttää ei ehkä löydy kaksoiskappaleiden poiston tulosentiteetistä.
  - Deduplication_WinnerId: Tämä kenttä sisältää määritettyjen ryhmien tai klustereiden voittaneen tunnuksen. Jos Deduplication_WinnerId on sama kuin tietueen ensisijaisen avaimen arvo, tietue on voittanut tietue.
- Kenttiä käytetään kaksoiskappaleiden poiston sääntöjen määrittämisessä.
- Sääntö- ja Pistemäärä-kentät määrittävät, mitä kaksoiskappaleiden poiston sääntöjä noudatetaan. Ne määrittävät myös vastaavan algoritmin palauttaman pistemäärän.

## <a name="next-step"></a>Seuraava vaihe

Määritä [aktiviteetit](activities.md), [rikastaminen](enrichment-hub.md) tai [suhteet](relationships.md), jos haluat lisää merkityksellisiä tietoja yhteyshenkilöistä.
