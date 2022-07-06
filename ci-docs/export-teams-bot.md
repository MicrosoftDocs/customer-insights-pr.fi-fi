---
title: Dynamics 365 Customer Insightsin Teams-botti (esiversio)
description: Yhtenäistettyjen asiakasprofiilien hakeminen Microsoft Teamsissa botin avulla.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 62a0216de848b5a3a81fdd6ac078feb551fcfec6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081092"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Dynamics 365 Customer Insightsin Teams-botti (esiversio)

Botti käyttää Microsoft Teams -yhteyttä yhtenäistettyjen asiakasprofiilien etsimiseen Teams-kanavissa.

> [!div class="mx-imgBorder"]
> ![Teams-botti, jossa näkyy asiakastietue.](media/teams-bot.png "Teams-botti, jossa näkyy asiakastietue")

## <a name="prerequisites"></a>Edellytykset

Botin asennus ja määritys edellyttää seuraavaa:

- Vähintään yksi [tietolähde on lisättynä](data-sources.md).
- [Yhdistämisprosessi](data-unification.md) on valmis.
- Kenttiä on lisätty [haku- ja suodatusindeksiin ](search-filter-index.md).
- Customer Insights ja Teams ovat samassa organisaatiossa.
- Ympäristössäsi on yksittäisille asiakkaille ensisijainen kohdekäyttäjäryhmä määritettynä. Yritystilejä ei tueta.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Botin määritys

1. Siirry kohtaan **Järjestelmänvalvoja** > **Vientikohteet**.
1. Valitse Microsoft Teams -ruudussa **Asenna**.
1. Sinut ohjataan Teamsin **Sovellukset**-alueelle. Voit myös avata Teamsin ja valita **Sovellukset** vasemmasta alakulmasta tai [hankkia sen AppSourcesta](https://go.microsoft.com/fwlink/?linkid=2124104) suoraan.
1. Hae **Customer Insights** ja valitse sovellus.
1. Valitse **Lisää**.
1. Kun olet kirjautunut Customer Insightsiin Teamsissä, näet tervetuloviestin ja voit aloittaa.

## <a name="things-you-can-do-with-the-bot"></a>Asioita, joihin voit käyttää bottia

Botti tarjoaa yhdistettyjen asiakasprofiilien hakumahdollisuuksia.

- Syötä **haku** ja sen jälkeen nimi, sähköpostiosoite tai mikä muu yhdistetyn asiakasprofiilin kenttä, joka lisätään haku- ja suodatusindeksiin.

  Saat kortin, joka sisältää jopa 15 kenttää tuloksena olevasta asiakasprofiilista. Useat vastaavuudet palauttavat tulosluettelon, josta voit valita profiilin. Lisäämällä hakutermiin lainausmerkit voit hakea tarkkaa vastaavuutta.

- Jos organisaatiolla on samassa organisaatiossa useita Customer Insights -ympäristöjä, antamalla **switchinstance** voit valita, mihin ympäristöön botti yhdistetään.

- Kirjoita **ohje**, kun haluat nähdä luettelon käytettävissä olevista bottikomennoista.  


[!INCLUDE [footer-include](includes/footer-banner.md)]