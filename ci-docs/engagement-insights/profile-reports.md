---
title: Valmiiden profiiliraporttien käyttöönotto
description: Valmiiden profiiliraporttien luominen sukupuolen, iän ja alkuperämaan tai -alueen mukaan ryhmiteltynä.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486116"
---
# <a name="out-of-box-profile-reports"></a>Valmiit profiiliraportit

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Raportti on yhdistelmä tietojen visualisointeja, joiden avulla voit ymmärtää käyttäjien käyttäytymistä paremmin. Kun muodostat yhteyden Customer Insightsin kohderyhmän merkityksellisiin tietoihin, vuorovaikutuksen merkitykselliset tiedot voivat näyttää raportin, joka sisältää tietoja yhdistetyistä asiakasprofiileista. Tämä raportti sisältää profiiliesi määrän ryhmiteltynä sukupuolen, iän ja maantieteellisin sijainnin perusteella.

## <a name="prerequisites"></a>Edellytykset

Kohderyhmän merkityksellisten tietojen ympäristön on tallennettava tietoja asiakkaan hallitsemalle Azure Data Lake Storage -tilille.

Jos käytät kohderyhmän merkitykselliset tiedot -ominaisuuden kokeiluversiota tai ympäristöä Customer Insightsin hallitsemassa Data Lake -tallennustilassa, [pyydä meiltä apua](https://go.microsoft.com/fwlink/?linkid=2145734).  


## <a name="enable-the-customer-profile-report"></a>Asiakasprofiiliraportin käyttöönotto

Ympäristön järjestelmänvalvojan on [linkitettävä tietoja ja käyttäjäryhmän merkityksellisiä tietoja](integrate-audience-insights-engagement-insights.md).

Kun olet määrittänyt yhteyden tiedot, järjestelmänvalvoja voi asettaa raportin muiden organisaation jäsenten nähtäville. Yhteyden määrittänyt ympäristön järjestelmänvalvoja voi automaattisesti käyttää raporttia. 

Kun yhteys on muodostettu vasemmassa siirtymisruudussa tulee käyttöön **Profiilit**-toiminto. 

- Voit tarkastella raporttia kohdassa **Löydä** > **Profiilit**.

**Profiilit**-raportti sisältää visualisointeja yhdistettyjen asiakasprofiilien sukupuolesta, iästä ja maantieteellisestä sijainnista.

:::image type="content" source="media/customer-profiles.png" alt-text="Asiakasprofiiliraportti.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]