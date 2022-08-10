---
title: Dynamics 365 Customer Insightsin Teams-botti (esiversio)
description: Yhtenäistettyjen asiakasprofiilien hakeminen Microsoft Teamsissa botin avulla.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195838"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Dynamics 365 Customer Insightsin Teams-botti (esiversio)

Botti käyttää Microsoft Teams -yhteyttä yhtenäistettyjen asiakasprofiilien etsimiseen Teams-kanavissa.

:::image type="content" source="media/teams-bot.png" alt-text="Teams-botti, jossa näkyy asiakastietue":::

## <a name="prerequisites"></a>edellytykset

- Vähintään yksi [tietolähde on lisättynä](data-sources.md).
- [Yhdistämisprosessi](data-unification.md) on valmis.
- Kenttiä on lisätty [haku- ja suodatusindeksiin ](search-filter-index.md).
- Customer Insights ja Teams ovat samassa organisaatiossa.
- Ympäristössäsi on yksittäisille asiakkaille ensisijainen kohdekäyttäjäryhmä määritettynä. Yritystilejä ei tueta.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Botin määritys

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.
1. Valitse Microsoft Teams -ruudussa **Asenna**.
1. Sinut ohjataan Teamsin **Sovellukset**-alueelle. Voit myös avata Teamsin ja valita **Sovellukset** vasemmasta alakulmasta tai [hankkia sen AppSourcesta](https://go.microsoft.com/fwlink/?linkid=2124104) suoraan.
1. Hae **Customer Insights** ja valitse sovellus.
1. Valitse **Lisää**.
1. Kirjaudu Customer Insightsiin Teamsin avulla. Tervetuloviestin näkyy.

## <a name="things-you-can-do-with-the-bot"></a>Asioita, joihin voit käyttää bottia

Botti tarjoaa yhdistettyjen asiakasprofiilien hakumahdollisuuksia.

- Syötä **haku** ja sen jälkeen nimi, sähköpostiosoite tai mikä muu yhdistetyn asiakasprofiilin kenttä, joka lisätään haku- ja suodatusindeksiin.

  Saat kortin, joka sisältää jopa 15 kenttää tuloksena olevasta asiakasprofiilista. Useat vastaavuudet palauttavat tulosluettelon, josta voit valita profiilin. Lisäämällä hakutermiin lainausmerkit voit hakea tarkkaa vastaavuutta.

- Jos organisaatiolla on samassa organisaatiossa useita Customer Insights -ympäristöjä, antamalla **switchinstance** voit valita, mihin ympäristöön botti yhdistetään.

- Kirjoita **ohje**, kun haluat nähdä luettelon käytettävissä olevista bottikomennoista.  

[!INCLUDE [footer-include](includes/footer-banner.md)]