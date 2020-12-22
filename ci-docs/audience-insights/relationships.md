---
title: Entiteettien entiteettipolkujen väliset suhteet
description: Useita lähteistä peräisin olevien entiteettien keskinäisten suhteiden luominen ja hallinta.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405625"
---
# <a name="relationships-between-entities"></a>Entiteettien väliset suhteet

Suhteiden avulla voit yhdistää entiteettejä ja luoda kaavion tiedoista, kun entiteetit jakavat yhteisen tunnuksen (viiteavaimen), johon entiteetit voivat viitata. Yhdistettyjen entiteettien avulla voit määrittää segmentit ja mittarit useiden tietolähteiden avulla.

Suhdetyyppejä on kaksi. Ei-muokattavat järjestelmän suhteet, jotka luodaan automaattisesti, ja käyttäjien luomat ja määrittämät mukautetut suhteet.

Tärsmäytys- ja yhdistämisprosessien aikana taustalla luodaan järjestelmän suhteet älykkään täsmäytystoiminnon perusteella. Nämä suhteet auttavat liittämään asiakasprofiilitietueet muihin vastaaviin entiteettitietueisiin. Seuraavassa kaaviossa on kuva, jossa esitetään kolmen järjestelmän suhteen luominen, kun asiakasentiteetti täsmäytetään lisäentiteetteihin lopullisen asiakasprofiilientiteetin muodostamista varten.

> [!div class="mx-imgBorder"]
> ![Suhteen luominen](media/relationships-entities-merge.png "Suhteen luominen")

- ***CustomerToContact*-suhde** luotiin asiakasentiteetin ja yhteyshenkilöentiteetin välille. Asiakasentiteetti saa avainkentän **Contact_contactId**, joka liitetään yhteyshenkilöentiteetin avainkenttään **contactId**.
- **_CustomerToAccount_-suhde** luotiin asiakasentiteetin ja tilientiteetin välille. Asiakasentiteetti saa avainkentän **Account_accountId**, joka liitetään tilientiteetin avainkenttään **accountId**.
- **_CustomerToWebAccount_-suhde** luotiin asiakasentiteetin ja verkkotilientiteetin välille. Asiakasentiteetti saa avainkentän **WebAccount_webaccountId**, joka liitetään verkkotilientiteetin avainkenttään **webaccountId**.

## <a name="create-a-relationship"></a>Suhteen luominen

Määritä mukautetut suhteet **Suhteet**-sivulla. Jokainen suhde sisältää lähde-entiteetin (entiteetti, jossa on viiteavain) ja kohde-entiteetin (entiteetti, johon lähde-entiteetin viiteavain osoittaa).

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Suhteet**.

2. Valitse **Uusi suhde**.

3. Anna **Lisää suhde** -ruutuun seuraavat tiedot:

   > [!div class="mx-imgBorder"]
   > ![Anna suhteen tiedot](media/relationships-add.png "Anna suhteen tiedot")

   - **Suhteen nimi**: Nimi, joka vastaa suhteen tarkoitusta (esimerkiksi **Tilin verkkolokit**).
   - **Kuvaus**: Suhteen kuvaus.
   - **Lähde-entiteetti**: Valitse entiteetti, jota käytetään suhteen lähteenä (esimerkiksi verkkoloki).
   - **Kardinaliteetti**: Valitse lähde-entiteettitietueiden kardinaliteetti. Esimerkiksi "useita" tarkoittaa, että yhteen verkkotiliin liittyy useita verkkolokitietueita.
   - **Lähteen avainkenttä**: Tämä kuvaa lähde-entiteetin viiteavainkenttää. Esimerkiksi verkkolokilla on **accountId**-viiteavainkenttä.
   - **Kohde-entiteetti**: Valitse entiteetti, jota käytetään suhteen kohteena (esimerkiksi verkkotili).
   - **Kohdekardinaliteetti**: Valitse kohde-entiteettitietueiden kardinaliteetti. Esimerkiksi "yksi" tarkoittaa, että yhteen verkkotiliin liittyy useita verkkolokitietueita.
   - **Kohdeavainkenttä**: Tämä kenttä edustaa kohde-entiteetin avainkenttää. Esimerkiksi verkkotilillä on **accountId**-avainkenttä.

> [!NOTE]
> Vain monta yhteen- ja yksi yhteen -suhteita tuetaan. Monta moneen -suhteita voi luoda käyttämällä kahta monta yhteen -suhdetta ja linkittämällä entiteetin (joka on sama, jota käytettiin lähde- ja kohde-entiteetin yhdistämisessä).

## <a name="delete-a-relationship"></a>Poista suhde

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Suhteet**.

2. Valitse sen suhteen valintaruudut, jonka haluat poistaa.

3. Valitse **Poista** **Suhteet**-taulukon yläosassa.

4. Vahvista poisto.

## <a name="next-step"></a>Seuraava vaihe

Järjestelmän suhteita ja mukautettuja suhteita käytetään luotaessa segmenttejä sellaisten useiden tietolähteiden perusteella, jotka eivät ole enää siilossa. Lisätietoja on kohdassa [Segmentit](segments.md).
