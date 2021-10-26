---
title: Työtilojen ja ympäristöjen hallinta
description: Työtilojen ja ympäristöjen luominen, nimeäminen uudelleen ja poistaminen.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 279af24358a1d6ea2b4cc75d5496042af73a7cae
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645442"
---
# <a name="manage-environments-and-workspaces"></a>Ympäristöjen ja työtilojen hallinta

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Yleiskuvaus

Tässä aiheessa käsitellään työtilojen ja ympäristöjen hallintaa, kun ne on jo luotu. 

- *Työtila* on paikka tapahtumien ja raporttien tallentamista ja hallintaa varten. Siellä voit tarkastella käyttäjäaktiviteetteja reaaliaikaisesti. Kun luot työtilan, voit valita työtilaan lähetettävien tietojen tyypin. Tällä hetkellä tuetaan verkkotietoja ja mobiilisovelluksia. Lisätietoja löytyy kohdasta [Työtilan luominen ja jäsenten lisääminen](create-workspace.md).

- *Ympäristö* on paikka, jossa voit hallita työtiloja ja yhteyksiä. Lisätietoja on kohdassa [Uuden ympäristön luominen](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Aiemmin luodun työtilan hallinta

Ympäristössä voi olla samanaikaisesti useita työtiloja. [Roolisi](user-roles.md) määrittää, mitä voit tehdä niissä. 

 - Vain ympäristön tai työtilan järjestelmänvalvoja voi hallita työtilaa.
 - Työtilan järjestelmänvalvojana voit nimetä olemassa olevia työtiloja uudelleen tai poistaa niitä. 

:::image type="content" source="media/workspace-edit.png" alt-text="Työtilan hallintakeskus.":::

### <a name="edit-a-workspace-name"></a>Työtilan nimen muokkaaminen

1. Siirry kohtaan **Järjestelmänvalvoja** > **Työtila** ja valitse **Asetukset**.

1. Anna uusi nimi **Työtilan nimi** -ruudussa.

1. Ota muutokset käyttöön valitsemalla **Tallenna**.

### <a name="delete-a-workspace"></a>Työtilan poistaminen

Työtilan poistaminen poistaa pysyvästi kaiken sen sisällön, tiedot, asetukset ja oikeudet. Tätä ei voi peruuttaa.

1. Siirry kohtaan **Järjestelmänvalvoja** > **Työtila** ja valitse **Asetukset**.

1. Valitse **Poista työtila**. 

1. Syötä **Poista työtila** -dialogiin **VAHVISTA POISTO** isoilla kirjaimilla. 

1. Poista työtila pysyvästi valitsemalla **Poista**.

### <a name="manage-workspace-members"></a>Työtilan jäsenten hallinta

1. Siirry kohtaan **Järjestelmänvalvoja** > **Työtila** ja valitse **Jäsenet**.

1. Valitse **Lisää jäseniä**, jos haluat antaa käyttöoikeuksia ja [määrittää rooleja](user-roles.md). Tällä hetkellä käytettävissä on vain **Työtilan järjestelmänvalvoja**.

1. Lisää jäseniä työtilaasi valitsemalla **Lisää jäseniä**.

## <a name="manage-an-existing-environment"></a>Aiemmin luodun ympäristön hallinta

Ympäristön järjestelmänvalvojana voit käyttää ympäristöä vasemmassa siirtymisruudussa. Voit määrittää ympäristön asetukset, muut ympäristön järjestelmänvalvojat ja työtilat. Voit siirtyä hallintakeskuksen eri alueiden välillä valitsemalla välilehtiä.

:::image type="content" source="media/environment-edit.png" alt-text="Ympäristön hallintakeskus.":::

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

1. Syötä **Poista työtila** -dialogiin **VAHVISTA POISTO** isoilla kirjaimilla. 

1. Valitse **Poista** poistaaksesi ympäristön pysyvästi.

## <a name="manage-connections"></a>Yhteyksien hallinta

Yhteyden luominen kohderyhmän merkityksellisiin tietoihin sallii sinun tarkastella raportteja vuorovaikutuksen merkityksellisissä tiedoissa yhdistettyjen asiakasprofiilien perusteella. 

Lue lisätietoja kohdasta [Linkin luominen kohdeyleisön ja sitoutumistietojen välille](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Henkilötietojen hallinta

Voit suojata asiakkaan henkilötiedot poistamalla tai viemällä käyttäjän yksilöiviä tietoja.

Lisätietoja: [Henkilötietoja sisältävien tapahtumatietojen poistaminen ja vieminen](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
