---
title: Segmenttien oletussuostumussääntöjen hallinta
description: Suostumuksen hallintaominaisuuden avulla voit poistaa käytöstä oletussuostumussääntöjä tai muuttaa niitä, jos korvaukset on otettu käyttöön.
ms.date: 12/01/2021
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 43f03ea97765e112a8ea2a7da97cc548c8c84dfc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646098"
---
# <a name="disable-or-change-default-consent-rules"></a>Oletussuostumussääntöjen poistaminen käytöstä tai muuttaminen

Jos organisaatiosi käyttää [suostumuksen hallintaominaisuutta](consent-management/overview.md) Dynamics 365 Customer Insightsin kanssa, [järjestelmänvalvojat voivat pakottaa suostumussäännön käyttämisen](activate-consent.md) segmenteille. 

Segmenttialueen pakotetuilla hyväksyntäsäännöillä jokainen segmentti ilmoittaa hyväksynnän tarkistamisen tilasta ja säännöistä. Jos ohitukset ovat sallittuja, oletushyväksyntäsäännöt on poistettu käytöstä tietyissä segmenteissä. Jokainen segmentin tekijä voi lisätä segmenttiin lisää suostumussääntöjä oletussääntöjen lisäksi. 

## <a name="for-administrators"></a>Järjestelmänvalvojille

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Segmentin muodostin, jossa on hyväksyntäsäännön asetukset.":::

**Voit poistaa oletussuostumussääntöjen aktivoinnin seuraavasti:**

1. Valitse **Hyväksyntäsäännöt**-ilmoituksessa **Näytä tiedot**. 

1. Vaihda **Oletussuostumussäännöt**-valitsimen arvoksi **Ei käytössä**.

**Voit lisätä suostumussääntöjä seuraavasti:**

1. Valitse **Hyväksyntäsäännöt**-ilmoituksessa **Näytä tiedot**. 

1. Valitse **Lisää hyväksyntäsäännöt** ja valitse hyväksyntäsääntö avattavasta **Valitse suostumuksen tietotyyppi** -luettelosta.

1. Valitse **Tallenna**, jos haluat käyttää uutta sääntöä segmentissä.

## <a name="for-contributors"></a>Tekijöille

Jos haluat luoda segmentin ilman pakotettuja suostumussääntöjä, sinun on pyydettävä järjestelmänvalvojaa poistamaan ne käytöstä segmentissäsi. Voit kuitenkin lisätä omia hyväksyntäsääntöjä omistamiasi ja hallitsemiasi segmenttejä varten.

Se on kolme vaihetta: 
1. [Luo segmentti](segments.md) Customer Insightsissa ja tallenna se. 

1. Jaa segmentin nimi järjestelmänvalvojan kanssa ja pyydä heitä [sallimaan segmentin ohitukset](activate-consent.md). 

1. Avaa segmentit uudelleen. Valitse **Hyväksyntäsäännöt**-ilmoituksessa **Näytä tiedot** ja lisää haluamasi hyväksyntäsäännöt. **Tallenna** ja **Suorita** segmentti.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
