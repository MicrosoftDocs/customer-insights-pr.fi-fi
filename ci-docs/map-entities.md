---
title: Valitse lähdekentät tietojen yhdistämistä varten
description: Ensimmäisessä vaiheessa valitaan entiteetit, määritteet, perusavaimet ja semanttiset tyypit, jotta tiedot voidaan yhdistää unified customer profile -profiiliin.
recommendations: false
ms.date: 04/22/2022
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
ms.openlocfilehash: a962f1353b6e25b40c60b39a81ac936873f34d92
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740991"
---
# <a name="select-source-fields-for-data-unification"></a>Valitse lähdekentät tietojen yhdistämistä varten

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Yhdistämisen ensimmäisessä vaiheessa valitaan tietojoukkojen entiteetit ja kentät, jotka halutaan yhdistää. Valitse entiteetit, jotka sisältävät asiakkaan tietoja, kuten nimen, osoitteen, puhelinnumeron ja sähköpostin. Voit valita yhden tai useampia entiteettejä.

## <a name="select-entities-and-fields"></a>Valitse entiteettejä ja kenttiä

1. Siirry kohtaan **Tiedot** > **Yhdistä**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Näyttökuva yhdistämisen saapumissivun ensimmäisestä käyttökokemuksesta, jossa Aloitus on korostettu.":::

1. Valitse **Aloita**.

1. Valitse **Lähdekentät**-sivulla **Valitse entiteetit ja kentät** . Näkyviin tulee **Valitse entiteetit ja kentät** -ruutu.

1. Valitse ainakin yksi entiteetti.

1. Tunnista kunkin valitun entiteetin kentät, joiden avulla haluat yhdistää asiakastietueet ja yhdistetyn profiilin kentät. Näitä kenttiä kutsutaan *Määritteiksi*. Voit valita pakolliset määritteet yksitellen entiteetistä tai sisällyttää entiteetin kaikki määritteet valitsemalla valintaruudun entiteettitasolla. Voit hakea avainsanoilla kaikista määritteistä ja entiteeteistä ja valita tarvittavat määritteet, jotka haluat yhdistää.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Näyttökuva valituista entiteeteistä ja määritteistä.":::

   Tässä esimerkissä lisätään **Yhteyshenkilöt**- ja **CustomerLoyalty**-entiteetit. Valitsemalla nämä entiteetit voit johtaa tietoja siitä, ketkä verkkoliiketoiminnan asiakkaista kuuluvat kanta-asiakasohjelman piiriin.

1. Vahvista valintasi valitsemalla **Käytä**. Valittujen entiteettien ja määritteiden näyttö.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Valitse määritteille perusavain ja semanttinen tyyppi

   :::image type="content" source="media/m3_select_primary.png" alt-text="Näyttökuva valituista entiteeteistä, joiden perusavainta ei ole valittu." lightbox="media/m3_select_primary.png":::

Suorita kullekin entiteetille seuraavat vaiheet.

1. Valitse **Perusavain**. Perusavain on entiteetin yksilöllinen määrite. Jotta määrite olisi kelvollinen perusavain, se ei saa sisältää arvojen kaksoiskappaleita, siitä ei saa puuttua arvoja eikä siinä saa olla tyhjiä arvoja. Merkkijono-, kokonaisluku- ja GUID-tietotyypin määritteitä tuetaan perusavaimina.

1. Voit käyttää tekoälymalleja semantiteetin älykkääseen ennustamiseen sekä säästää aikaa ja parantaa tarkkuutta varmistamalla, että **älykäs yhdistäminen** on käytössä. Älykäs yhdistämismääritys korostaa tekoälyyn perustuvat semanttiset suositukset **Tyyppi**-kentässä. Voit ohittaa ehdotetun valinnan valitsemalla haluamasi semanttisen tyypin käytettävissä olevasta asetusluettelosta.

1. Valitse kullekin määritteelle semanttinen **tyyppi**, joka parhaiten kuvaa määritettä, kuten nimeä, postiosoitetta tai sähköpostiosoitetta.

   > [!NOTE]
   > Yhden kentän on oltava yhdistetty semanttiseen *Person.FullName*-tyyppiin, jotta asiakkaan nimi voidaan täyttää asiakaskortissa. Muussa tapauksessa asiakaskortit näkyvät nimettöminä.

   1. Voit vaihtaa järjestelmän tunnistamaa määritetyyppiä valitsemalla toisen tyypin. Jos tyyppiä ei ole, luo mukautettu semanttinen tyyppi valitsemalla määritteelle **Tyyppi**-kenttä ja kirjoittamalla mukautetun semanttisen tyypin nimen.

   1. Jos haluat lisätä määritteen, joka sisältää URL-osoitteen julkisesti saatavilla oleviiin profiilikuviin tai logoihin, valitse entiteetti ja kenttä, joka sisältää URL-osoitteen. Syötä seuraava **Tyyppi**-kenttään:
      - Henkilölle: Person.ProfileImage
      - Organisaatiolle: Organization.LogoImage

   1. Syötä tilin nimi -määritteelle "Organization.Name"**Tyyppi**-kenttään.

1. Tarkista määritteet, joiden semanttinen tyyppi tunnistetaan automaattisesti. Nämä määritteet näkyvät **Yhdistettyjen kenttien tarkistaminen** -kohdassa. Vain samantyyppiset määritteet voi yhdistää **Yhdistetyt asiakaskentät** -vaiheessa. Semanttisten tyyppien avulla voidaan automaattisesti ehdottaa merkityksellisiä tietoja. Varmista, että valitsemasi tyypit ovat yhdenmukaiset kaikissa valituissa entiteetissä.

1. Jos määritteitä ei määritetä automaattisesti semanttiseen tyyppiin, valitse semanttinen tyyppikenttä, syötä mukautetun määritetyypin nimi tai jätä ne yhdistämättä. Nämä määritteet on lueteltu kohdassa **Määritä yhdistämättömien kenttien tiedot**.

1. Kun olet suorittanut kunkin entiteetin vaiheet, valitse **Tallenna lähdekentät**.

1. Valitse **Seuraava**.

> [!div class="nextstepaction"]
> [Seuraava vaihe: Kaksoiskappaleiden poistaminen](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
