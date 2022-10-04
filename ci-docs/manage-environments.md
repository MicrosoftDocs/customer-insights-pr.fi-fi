---
title: Ympäristöjen hallinta
description: Opettele hallitsemaan aiemmin luotuja Customer Insights -ympäristöjä järjestelmänvalvojana.
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 6d48f7088d722b27ca69cd591178651bdb6e2c23
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588808"
---
# <a name="manage-environments"></a>Ympäristöjen hallinta

Järjestelmänvalvojat [luovat](create-environment.md) ja hallitsevat ympäristöjä. He voivat muuttaa joitakin asetuksia nykyisissä ympäristöissä. Liiketoiminta-, tyyppi-, alue-, tallennusvaihtoehto- ja Dataverse-asetukset korjataan ympäristön luomisen jälkeen. Jos haluat muuttaa näitä asetuksia, [palauta ympäristö alkutilaan](#reset-an-existing-environment-preview) tai [luo uusi ympäristö](create-environment.md).

## <a name="edit-an-existing-environment"></a>Aiemmin luodun ympäristön muokkaaminen

Muokkaa aiemmin luodun ympäristön tietoja, kuten nimeä tai oletusympäristön asetusta.

1. Valitse sovelluksen otsikossa **Ympäristö**-valitsin.

1. Valitse **Muokkaa**-kuvake.

   :::image type="content" source="media/edit-environment.png" alt-text="Ympäristön asetusten muokkauskuvake.":::

1. Voit päivittää ympäristön asetuksia **Muokkaa ympäristöä** -ruudussa.

1. Valitse **Tarkasta ja viimeistele** ja sitten **Päivitä** ottaaksesi muutokset käyttöön.

## <a name="change-the-owner-of-an-environment"></a>Ympäristön omistajan muuttaminen

Useilla käyttäjillä voi olla järjestelmänvalvojan oikeudet, mutta vain yksi käyttäjä on ympäristön omistaja. Oletusarvon mukaan järjestelmänvalvoja luo ympäristön. Ympäristön järjestelmänvalvojana voit delegoida omistuksen toiselle käyttäjälle, jolla on järjestelmänvalvojan oikeudet.

1. Valitse sovelluksen otsikossa **Ympäristö**-valitsin.

1. Valitse **Muokkaa**-kuvake.

1. Siirry **Muokkaa ympäristöä** -ruudussa **Perustiedot**-vaiheeseen.

1. Valitse **Muuta ympäristön omistajaa** -kentässä ympäristön uusi omistaja.  

1. Valitse **Tarkasta ja viimeistele** ja sitten **Päivitä** ottaaksesi muutokset käyttöön.

## <a name="claim-ownership-of-an-environment"></a>Ympäristön omistajuuden vaatiminen

Jos ympäristön omistaja poistetaan tai peruutetaan, ympäristöllä ei ole omistajaa. Kuka tahansa, jolla on järjestelmänvalvojan oikeudet, voi vaatia omistajuuden ja hänestä voi tulla uusi omistaja. Omistava järjestelmänvalvoja voi jatkaa ympäristön omistajana tai [vaihtaa omistuksen toiselle järjestelmänvalvojalle](#change-the-owner-of-an-environment).

Vaadi omistus valitsemalla **Ota omistus** -painike, joka näkyy jokaisen Customer Insights -sivun yläosassa, kun alkuperäinen omistaja on lähtenyt organisaatiosta.

## <a name="reset-an-existing-environment-preview"></a>Nollaa aiempi ympäristö (esiversio)

Ympäristön omistajana voit nollata ympäristön tyhjään tilaan, jos haluat poistaa kaikki määritykset ja poistaa sisäänotetut tiedot.

1. Valitse sovelluksen otsikossa **Ympäristö**-valitsin.

1. Valitse ympäristö, jonka haluat palauttaa, ja valitse kolme pystysuuntaista pistettä (&vellip;).

1. Valitse **Nollaa (esiversio)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Ympäristön palauttaminen ohjausta varten.":::

1. Valitse, haluatko nollata koko ympäristön, kaiken paitsi tietolähteet vai mitä tahansa, mikä on määritetty unified customer profilen päälle.

1. Vahvista antamalla tämän ympäristön nimi ja valitsemalla **Nollaa**.

## <a name="delete-an-existing-environment"></a>Olemassa olevan ympäristön poistaminen

Ympäristön omistajana voit poistaa sen.

> [!IMPORTANT]
> Ympäristön poistaminen ei poista yhteyttä Dataverse-ympäristöön. Jos aiot yhdistää saman Dataverse-ympäristön uuteen Customer Insights -ympäristöön tulevaisuudessa, sinun täytyy [poistaa tämä yhteys Dataverse-ympäristöön](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Valitse sovelluksen otsikossa **Ympäristö**-valitsin.

1. Valitse ympäristö, jonka haluat poistaa, ja valitse kolme pystysuuntaista pistettä (&vellip;). 

1. Valitse **Poista**.

   :::image type="content" source="media/delete-environment.png" alt-text="Poistettavan ympäristön ohjausobjekti.":::

1. Vahvista poisto antamalla ympäristön nimi ja valitsemalla **Poista**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
