---
title: Valitse lähdekentät tietojen yhdistämistä varten
description: Ensimmäisessä vaiheessa valitaan entiteetit, määritteet, perusavaimet ja semanttiset tyypit, jotta tiedot voidaan yhdistää unified customer profile -profiiliin.
recommendations: false
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304561"
---
# <a name="select-source-fields-for-data-unification"></a>Valitse lähdekentät tietojen yhdistämistä varten

Yhdistämisen ensimmäisessä vaiheessa valitaan tietojoukkojen entiteetit ja kentät, jotka halutaan yhdistää. Valitse entiteetit, jotka sisältävät asiakkaan tietoja, kuten nimen, osoitteen, puhelinnumeron ja sähköpostin. Voit valita yhden tai useampia entiteettejä.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Valitse entiteettejä ja kenttiä

1. Siirry kohtaan **Tiedot** > **Yhdistä**.

   Yksittäisten asiakkaiden (B2C) **Yhtenäistä**-saapumissivulla näkyy **Aloitus**-kohdan ensimmäisessä vaiheessa **Lähdekentät**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Näyttökuva yhdistämisen saapumissivun ensimmäisestä käyttökokemuksesta yksittäisille asiakkaille.":::

   Yritystilien (B2B) **Yhtenäistä**-saapumissivulla näkyy **Yhtenäistä tilit** -kohdassa **Aloitus**-kohdan ensimmäisessä vaiheessa **Lähdekentät**. **Yhteyshenkilöiden yhdistäminen (esiversio)** -vaiheet ovat valinnaisia ja odottavat tilien yhdistämisen valmistumista.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Näyttökuva yhdistämisen saapumissivun ensimmäisestä käyttökokemuksesta yritystileille.":::

1. Valitse **Aloita**.

1. Valitse **Lähdekentät**-sivulla **Valitse entiteetit ja kentät** . Näkyviin tulee **Valitse entiteetit ja kentät** -ruutu.

1. Valitse ainakin yksi entiteetti.

1. Tunnista kunkin valitun entiteetin kentät, joiden avulla haluat yhdistää asiakastietueet ja yhdistetyn profiilin kentät. Näitä kenttiä kutsutaan *Määritteiksi*. Voit valita pakolliset määritteet yksitellen entiteetistä tai sisällyttää entiteetin kaikki määritteet valitsemalla valintaruudun entiteettitasolla. Voit hakea avainsanoilla kaikista määritteistä ja entiteeteistä ja valita tarvittavat määritteet, jotka haluat yhdistää.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Näyttökuva valituista entiteeteistä ja määritteistä.":::

   Tässä esimerkissä lisätään entiteetit **eCommerceContacts** ja **loyCustomer**. Valitsemalla nämä entiteetit voit johtaa tietoja siitä, ketkä verkkoliiketoiminnan asiakkaista kuuluvat kanta-asiakasohjelman piiriin.

1. Vahvista valintasi valitsemalla **Käytä**. Valittujen entiteettien ja määritteiden näyttö.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Valitse määritteille perusavain ja semanttinen tyyppi

   :::image type="content" source="media/m3_select_primary.png" alt-text="Näyttökuva valituista entiteeteistä, joiden perusavainta ei ole vielä valittu." lightbox="media/m3_select_primary.png":::

Suorita kullekin entiteetille seuraavat vaiheet.

1. Valitse **Perusavain**. Perusavain on entiteetin yksilöllinen määrite. Jotta määrite olisi kelvollinen perusavain, se ei saa sisältää arvojen kaksoiskappaleita, siitä ei saa puuttua arvoja eikä siinä saa olla tyhjiä arvoja. Merkkijono-, kokonaisluku- ja GUID-tietotyypin määritteitä tuetaan perusavaimina.

1. Voit käyttää tekoälymalleja semantiikan älykkääseen ennustamiseen sekä säästää aikaa ja parantaa tarkkuutta varmistamalla, että **älykäs yhdistäminen** on käytössä. Älykäs yhdistämismääritys tarjoaa tekoälyyn perustuvat semanttiset suositukset **Tyyppi**-kentässä.

1. Valitse kullekin määritteelle semanttinen **tyyppi**, joka parhaiten kuvaa määritettä, kuten nimeä, postiosoitetta tai sähköpostiosoitetta.

   > [!NOTE]
   > B2C-tilanteessa yhden kentän on oltava yhdistetty semanttiseen *Person.FullName*-tyyppiin, jotta asiakkaan nimi voidaan täyttää asiakaskortissa. B2B-tilanteessa tilin nimi tulisi yhdistää *Organization.Name*-kenttään. Muussa tapauksessa asiakaskortit näkyvät nimettöminä.

   1. Voit korvata järjestelmän tunnistaman määritetyypin valitsemalla toisen vaihtoehdon. Jos tyyppiä ei ole, luo mukautettu semanttinen tyyppi valitsemalla määritteelle **Tyyppi**-kenttä ja kirjoittamalla mukautetun semanttisen tyypin nimen.

   1. Jos haluat lisätä määritteen, joka sisältää URL-osoitteen julkisesti saatavilla oleviiin profiilikuviin tai logoihin, valitse entiteetti ja kenttä, joka sisältää URL-osoitteen. Syötä seuraava **Tyyppi**-kenttään:
      - Henkilölle: Person.ProfileImage
      - Organisaatiolle: Organization.LogoImage

1. Tarkista määritteet, joiden semanttinen tyyppi tunnistetaan automaattisesti. Nämä määritteet näkyvät **Yhdistettyjen kenttien tarkistaminen** -kohdassa. Vain samantyyppiset määritteet voi yhdistää **Yhdistetä asiakaskentät** -vaiheessa. Semanttisten tyyppien avulla voidaan automaattisesti ehdottaa merkityksellisiä tietoja. Varmista, että valitsemasi tyypit ovat yhdenmukaiset kaikissa valituissa entiteetissä.

1. Jos määritteitä ei määritetä automaattisesti semanttiseen tyyppiin, valitse semanttinen tyyppikenttä, syötä mukautetun määritetyypin nimi tai jätä ne yhdistämättä. Nämä määritteet on lueteltu kohdassa **Määritä yhdistämättömien kenttien tiedot**.

1. Kun olet suorittanut kunkin entiteetin vaiheet, valitse **Tallenna lähdekentät**.

1. Valitse **Seuraava**.

> [!div class="nextstepaction"]
> [Seuraava vaihe: Kaksoiskappaleiden poistaminen](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
