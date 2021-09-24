---
title: Työtilojen ja ympäristöjen hallinta
description: Työtilojen ja ympäristöjen luominen, nimeäminen uudelleen ja poistaminen.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 09/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: a5b48db5ae23ea65bf608d67348d493bfdc7678f
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486031"
---
# <a name="manage-environments-and-workspaces"></a>Ympäristöjen ja työtilojen hallinta

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Yleiskuvaus

Työtila on paikka tapahtumien ja raporttien tallentamista ja hallintaa varten. Siellä voit tarkastella käyttäjäaktiviteetteja reaaliaikaisesti. Kun luot työtilan, voit valita työtilaan lähetettävien tietojen tyypin. Tällä hetkellä tuetaan verkkotietoja ja mobiilisovelluksia.

Ympäristö on paikka, jossa voit hallita työtiloja ja yhteyksiä. Ympäristön käyttö vaihtelee organisaation ja käyttötapauksen mukaan. Voit esimerkiksi luoda

-   yksittäisen ympäristön.
-   erillisiä ympäristöjä testausta ja tuotantoa varten.
-   erillisiä kullekin kohderyhmälle merkityksellisiä tapahtumia sisältäviä ympäristöjä organisaation tietyille ryhmille tai osastoille.
-   erillisiä ympäristöjä yrityksen eri puolilla maailmaa sijaitseville haaroille.
-   yhteyksiä Customer Insightsin kohderyhmän merkitykselliset tiedot -ominaisuuteen.

## <a name="choose-an-environment-and-create-a-workspace"></a>Ympäristön valinta ja työtilan luominen 

Jokaisen työtilan on oltava ympäristössä. Voit valita aiemmin luodun ympäristön tai luoda uuden, kun luot työtilan. Tämän jälkeen voit lisätä työtilaan jäseniä ja aloittaa tietojen keräämisen.

**Ensimmäisen työtilan luominen**

1. Valitse vuorovaikutuksen merkityksellisten tietojen työtilan valintakytkimestä **Uusi**. 

   :::image type="content" source="media/New-workspace.png" alt-text="Customer Insights -sivun työtilanvalitsin.":::

1. Valitse ympäristö luettelosta tai valitse **Luo uusi ympäristö**.

1. Kirjoita nimi kohtaan **Työtilan nimi**. 

1. Valitse luotavan ympäristön tyyppi sen mukaan, haluatko mitata sivuston vai mobiilisovelluksen tapahtumia. 

1. Voit lisätä jäseniä ja määrittää heidän käyttöoikeustasonsa **Rooli**-luettelossa. Valitse sitten **Viimeistele** luodaksesi työtilan tai **Seuraava** asentaaksesi koodia. 

1. Asenna koodikatkelma, jotta voit aloittaa tietojen vastaanottamisen, ja valitse sitten **Valmis**. 

## <a name="manage-a-workspace"></a>Työtilan hallinta

Ympäristössä voi olla samanaikaisesti useita työtiloja. [Roolisi](user-roles.md) määrittää, mitä voit tehdä niissä. 

 - Vain ympäristön tai työtilan järjestelmänvalvoja voi hallita työtilaa.
 - Työtilan järjestelmänvalvojana voit nimetä olemassa olevia työtiloja uudelleen tai poistaa niitä. 

### <a name="edit-a-workspace-name"></a>Työtilan nimen muokkaaminen

1. Siirry kohtaan **Järjestelmänvalvoja** > **Työtila** ja valitse **Asetukset**.

1. Anna uusi nimi **Työtilan nimi** -ruudussa.

1. Ota muutokset käyttöön valitsemalla **Tallenna**.

### <a name="delete-a-workspace"></a>Työtilan poistaminen

Työtilan poistaminen poistaa pysyvästi kaiken sen sisällön, tiedot, asetukset ja oikeudet. Tätä ei voi peruuttaa.

1. Siirry kohtaan **Järjestelmänvalvoja** > **Työtila** ja valitse **Asetukset**.

1. Valitse **Poista työtila**. 

1. Syötä **Poista työtila** -valintaikkunassa **VAHVISTA POISTO**. 

1. Poista työtila pysyvästi valitsemalla **Poista**.

### <a name="manage-workspace-members"></a>Työtilan jäsenten hallinta

1. Siirry kohtaan **Järjestelmänvalvoja** > **Työtila** ja valitse **Jäsenet**.

1. Valitse **Lisää jäseniä**, jos haluat antaa käyttöoikeuksia ja [määrittää rooleja](user-roles.md). Tällä hetkellä käytettävissä on vain **Työtilan järjestelmänvalvoja**.

1. Lisää jäseniä työtilaasi valitsemalla **Lisää jäseniä**.

## <a name="manage-an-environment"></a>Ympäristön hallinta

Ympäristön järjestelmänvalvojana voit käyttää ympäristöä vasemmassa siirtymisruudussa. Voit määrittää ympäristön asetukset, muut ympäristön järjestelmänvalvojat ja työtilat. Voit siirtyä hallintakeskuksen eri alueiden välillä valitsemalla välilehtiä.

:::image type="content" source="media/New-environment.png" alt-text="Ympäristön hallintakeskus.":::

### <a name="create-an-environment"></a>Luo ympäristö

1. Valitse työtilanvalitsimessa **+Uusi**.

1. Avaa ohjatussa käyttökokemuksessa avattava **Ympäristö**-valikko ja valitse **Luo uusi ympäristö**. 

1. Anna **Ympäristön nimi**.

   :::image type="content" source="media/create-environment.png" alt-text="Määritä ympäristön tiedot opastetun kokemuksen mukaan.":::

1. Valitse **Alue** ja valitse **Seuraava**. 

1. Anna työtilan nimi ja valitse luotavan työtilan tyyppi. 

1.  Voit halutessasi lisätä jäseniä ja kopioida koodikatkelman saattaaksesi luontiprosessin loppuun.

### <a name="rename-an-environment"></a>Ympäristön nimeäminen uudelleen

1. Siirry kohtaan **Järjestelmänvalvoja** > **Ympäristö** ja valitse **Asetukset**.

1. Päivitä **Ympäristön nimi** ja ota muutokset käyttöön valitsemalla **Tallenna**.

### <a name="manage-environment-members"></a>Ympäristön jäsenten hallinta

1. Siirry kohtaan **Ympäristö** > **Työtila** ja valitse **Jäsenet**.

1. Valitse **Lisää jäseniä**, jos haluat antaa päivittää jäseniä ja [määrittää rooleja](user-roles.md). Tällä hetkellä käytettävissä on vain **Ympäristön järjestelmänvalvoja**.

1. Lisää jäseniä ympäristöösi valitsemalla **Lisää jäseniä**.

### <a name="delete-an-environment"></a>Ympäristön poistaminen

Ympäristön järjestelmänvalvojat voivat poistaa ympäristöjä. Ennen kuin voit poistaa ympäristön, sinun on poistettava kaikki sen alla olevat työtilat.

1. Siirry kohtaan **Järjestelmänvalvoja** > **Ympäristö** ja valitse **Asetukset**.

1. Valitse **Ympäristön poisto**. 

1. Syötä **Poista työtila** -valintaikkunassa **VAHVISTA POISTO**. 

1. Valitse **Poista** poistaaksesi ympäristön pysyvästi.

## <a name="manage-connections"></a>Yhteyksien hallinta

Yhteyden luominen kohderyhmän merkityksellisiin tietoihin sallii sinun tarkastella raportteja vuorovaikutuksen merkityksellisissä tiedoissa yhdistettyjen asiakasprofiilien perusteella. 

Lue lisätietoja kohdasta [Linkin luominen kohdeyleisön ja sitoutumistietojen välille](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Henkilötietojen hallinta

Voit suojata asiakkaan henkilötiedot poistamalla tai viemällä käyttäjän yksilöiviä tietoja.

Lisätietoja: [Henkilötietoja sisältävien tapahtumatietojen poistaminen ja vieminen](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
