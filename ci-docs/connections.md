---
title: Yhteydet (esiversio) – yleiskuvaus
description: Yhteydet muihin palveluihin Customer Insightsista.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245507"
---
# <a name="connections-preview-overview"></a>Yhteydet (esiversio) – yleiskuvaus

Yhteydet ovat avain, joka mahdollistaa tietojen jakamisen Customer Insightsiin ja ulos sieltä. Kukin yhteys muodostaa tietojen jakamisen tietyn palvelun kanssa. Käytä yhteyksiä [kolmansien osapuolten rikastusten määrittämiselle](enrichment-hub.md) ja [viennin määrittämiselle](export-destinations.md). Samaa yhteyttä voidaan käyttää useita kertoja. Esimerkiksi yksi yhteys Dynamics 365 Marketingiin toimii useaa vientiä varten ja yhtä Leadspace-yhteyttä voi käyttää useisiin rikastuksiin.

## <a name="export-connections"></a>Vie yhteydet

Vain järjestelmänvalvojat voivat määrittää uusia yhteyksiä, mutta he voivat [myöntää osallistujille käyttöoikeudet](#allow-contributors-to-use-a-connection-for-exports) aiemmin luotujen yhteyksien käyttöön. Järjestelmänvalvojat määrittävät tietojen lähtemisen, osallistujat määrittävät tiedot ja tiheyden, joka vastaa heidän tarpeitaan.

## <a name="enrichment-connections"></a>Rikastusliitännät

Vain järjestelmänvalvojat voivat määrittää uusia yhteyksiä, mutta luodut yhteydet ovat aina sekä järjestelmänvalvojien että osallistujien käytettävissä. Järjestelmänvalvojat hallinnoivat tunnistetietoja ja antavat hyväksyntänsä tietojen siirroille. Tämän jälkeen sekä järjestelmänvalvojat että osallistujat voivat käyttää yhteyksiä rikastuksiin.

## <a name="add-a-new-connection"></a>Lisää uusi yhteys

### <a name="prerequisites"></a>edellytykset

- [Järjestelmänvalvojan oikeudet](permissions.md)
- Muut mahdolliset Microsoftin palvelut ovat samassa organisaatiossa

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja valitse yhteystyyppi, jonka haluat luoda. Tai, mene **Tutustu**-välilehdelle ja valitse **Määritä** yhteysruudussa.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Kirjoita tarvittavat tiedot. Täsmälliset kentät määräytyvät sen mukaan, mihin palveluun muodostat yhteyden. Lisätietoja tietystä yhteystyypistä saat kohdepalvelua koskevasta artikkelista.

1. Jos [käytät omaa Key Vaultiasi](use-azure-key-vault.md) salaisien koodien tallentamiseen, aktivoi **Käytä Key Vaultia** ja valitse sitten salainen koodi luettelosta.

1. Tarkista tietojen Tietosuoja ja vaatimustenmukaisuus ja valitse **Hyväksyn**.

1. Valitse **Tallenna** luodaksesi yhteyden.

### <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun otat tietojen siirron käyttöön Dynamics 365 Customer Insightsista kolmansille osapuolille tai muille Microsoft-tuotteille, sallit tietojen siirtämisen Dynamics 365 Customer Insightsin vaatimustenmukaisuuden rajojen ulkopuolelle, mukaan lukien mahdollisesti luottamukselliset tiedot, kuten henkilötiedot. Microsoft siirtää kyseiset tiedot annettujen ohjeiden mukaan, mutta vastaat siitä, että kolmas osapuoli noudattaa kaikkia käyttämiäsi tietosuoja- ja tietoturvavelvoitteita. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insightsin järjestelmänvalvoja voi poistaa yhteyden milloin tahansa poistaa tämän rikastamisen käytöstä.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Salli osallistujien käyttää yhteyttä vientiin

Kun määrität tai muokkaat vientiyhteyttä, valitse käyttäjät, joilla on oikeus käyttää tätä yhteyttä [vientien](export-destinations.md) määrittämiseen. Yhteys on oletusarvoisesti niiden käyttäjien käytettävissä, joilla on järjestelmänvalvojan rooli. Muuta **Valitse, kuka voi käyttää tätä yhteyttä** -asetusta salliaksesi osallistujaroolin käyttäjien käyttää tätä yhteyttä.

- Osallistujat eivät voi tarkastella tai muokata yhteyttä. He näkevät vain näyttönimen ja sen tyypin luodessaan vientiä.
- Kun jaat yhteyden, osallistujat voivat käyttää yhteyttä. Osallistujat näkevät jaetut yhteydet vientiä määrittäessään. He voivat hallita jokaista tätä yhteyttä käyttävää vientiä.
- Voit muuttaa tätä asetusta niin, että säilytetään osallistujien jo määrittämät viennit.

## <a name="manage-existing-connections"></a>Aiemmin luotujen yhteyksien hallinta

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitsemalla **Rikastaminen**- tai **Viennit**-välilehden voit tarkastella luetteloa, jossa ovat rikastamisen tai viennin yhteydet, yhteystyyppi, luontipäivämäärä ja käyttöoikeudet. Yhteydet voi lajitella minkä tahansa sarakkeen mukaan.

1. Voit tarkastella käytettävissä olevia toimintoja valitsemalla yhteyden.

   - **Muokkaa** yhteyttä.
   - [**Poista**](#remove-a-connection) yhteys.

### <a name="remove-a-connection"></a>Yhteyden poistaminen

Jos poistettavaa yhteyttä käytetään rikastuksissa tai vienneissä, ne on ensin irrotettava tai poistettava. Poistoikkuna opastaa sinut liittyviin rikastuksiin tai vienteihin.

> [!TIP]
> Deaktivoidut rikastukset ja poistetut viennit muuttuvat passiivisiksi. Voit aktivoida ne uudelleen lisäämällä niihin toisen yhteyden [Rikastus](enrichment-hub.md)- tai [Viennit](export-destinations.md)-sivulla.

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Rikastus**- tai **Viennit**-välilehti.

1. Valitse poistettava yhteys.

1. Valitse avattavassa valikossa **Poista**. Vahvistusvalintaikkuna avautuu.

   1. Jos tätä yhteyttä käyttää jokin rikastus tai vienti, valitse painike, kun haluat nähdä, mikä käyttää yhteyttä.
      - **Viennit:** Valitse joko **Poista** vienti tai **Poista yhteys**. Poistamalla yhteyden säilytät vientimäärityksen, mutta se suoritetaan vasta, kun siihen on lisätty toinen yhteys.
      - **Rikasteet:** voit joko **poistaa** rikastuksen tai **poistaa sen aktivoinnin**.
   1. Kun yhteydellä ei ole enää riippuvuuksia, palaa kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja yritä poistaa yhteys uudelleen.

1. Vahvista poisto valitsemalla **Poista**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Määritä yhteydet omassa Key Vaultissa hallitsemiesi salaisten koodien avulla

Jotkin yhteydet tarvitsevat salaisia koodeja kuten ohjelmointirajapinnan avaimia tai salasanoja. Jotkin yhteydet tukevat salaisia koodeja, jotka on tallennettu omaan Key Vaultiisi. Lisätietoja tuetuista yhteyksistä ja määrityksistä on kohdassa [oma Key Vaultisi Customer Insightsin tietoja varten](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
