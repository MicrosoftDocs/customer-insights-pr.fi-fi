---
title: Tietojen vieminen Customer Insightsista
description: Jaa tietoja hallitsemalla vientejä.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016610"
---
# <a name="exports-preview-overview"></a>Viennit (esiversio) – yleiskatsaus

**Viennit**-sivulla näkyvät kaikki määritetyt viennit. Viennit jakavat tiettyjä tietoja eri sovellusten kanssa. Ne voivat sisältää asiakasprofiileja tai entiteettejä, rakenteita ja yhdistämistietoja. Kukin vienti edellyttää [yhteyttä, jonka määrittää järjestelmänvalvoja todennuksen ja käytön hallitsemiseksi](connections.md).

Siirry kohtaan **Tiedot** > **Viennit**, kun haluat tarkastella vientisivua. Kaikilla käyttäjärooleilla on määritettyjen vientien tarkastelemisen oikeus. Käyttämällä komentopalkin hakukenttää voit etsiä viennit nimen, yhteyden nimen tai yhteystyypin mukaan.

## <a name="set-up-a-new-export"></a>Määritä uusi vienti

Jotta voit määrittää tai muokata vientiä, sinulla on oltava käytettävissä yhteydet. Yhteydet määräytyvät [käyttäjäroolisi](permissions.md) mukaan:
- Järjestelmänvalvojat voivat käyttää kaikkia yhteyksiä. He voivat myös luoda uusia yhteyksiä viennin määrittämisen jälkeen.
- Osallistujat voivat käyttää tiettyjä yhteyksiä. Järjestelmänvalvojat voivat määrittää ja jakaa osallistujille yhteyksiä. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Katsojat voivat tarkastella vain aiemmin luotuja vientejä, mutta eivät luoda niitä.

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vientikohde valitsemalla **Lisää vienti**.

1. Valitse **Määritä vienti** -ruudussa käytettävä yhteys. [Yhteydet](connections.md) ovat järjestelmänvalvojien hallitsemia. 

1. Anna tarvittavat tiedot ja luo vienti valitsemalla **Tallenna**.

### <a name="edit-an-export"></a>Muokkaa vientiä

1. Valitse muokattavan vientikohteen kohdalla kolme allekkaista pistettä.

1. Valitse avattavasta valikosta **Muokkaa**.

1. Muuta päivitettävät arvot ja valitse **Tallenna**.

## <a name="view-exports-and-export-details"></a>Viennin ja viennin tietojen tarkasteleminen

Kun olet luonut vientikohteet, ne näkyvät kohdassa **Tiedot** > **Viennit**. Kaikki käyttäjät näkevät jaetut tiedot ja niiden uusimman tilan.

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Käyttäjät, joilla ei ole muokkausoikeutta, valitsevat **Näytä** (ei **Muokkaa**) nähdäkseen viennin tiedot.

1. Tämä sivuruutu näyttää tämän viennin määrityksen. Arvoja ei voi muuttaa ilman muokkausoikeutta. Palaa vientisivulle valitsemalla **Sulje**.

## <a name="run-exports-on-demand"></a>Suorita vientejä tarvittaessa

Kun olet määrittänyt viennin, se suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) yhteydessä niin kauan kuin sillä on toimiva yhteys.

Jos haluat viedä tietoja odottamatta ajoitettua päivitystä, siirry kohtaan **Tiedot** > **Viennit**. Sinulla on kaksi vaihtoehtoa:

- Jos haluat suorittaa kaikki viennit, valitse komentopalkissa **Suorita kaikki**. 
- Jos haluat suorittaa yksittäisen viennin, valitse luettelokohteesta kolme pistettä (...) ja valitse sitten **Suorita**.

## <a name="remove-an-export"></a>Viennin poistaminen

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Valitse poistettavan viennin kohdalla kolme allekkaista pistettä.

1. Valitse avattavassa valikossa **Poista**.

1. Vahvista poisto valitsemalla **Poista** vahvistusnäytössä.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
