---
title: Uudet ja tulevat ominaisuudet
description: Tietoja uusista ominaisuuksista, parannuksista ja virheiden korjauksista.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 25c6e2897d836854408871b2c74afa16ecba7435
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646350"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insightsin uudet ominaisuudet

Olemme innoissamme voidessamme ilmoittaa uusimmista päivityksistämme! Tässä artikkelissa on yhteenveto yleisen esiversion ominaisuuksista, yleisen saatavuuden parannuksista ja ominaisuuksien päivityksistä. Katso ominaisuuksien pitkäaikaiset suunnitelmat [Dynamics 365- ja Power Platform -julkaisusuunnitelmista](/dynamics365/release-plans/).

Julkaisemme päivitykset alueittain. Näin siis jotkin alueet saattavat nähdä ominaisuuksia ennen muita. Ellei toisin määritetä, sinun ei tarvitse tehdä mitään, vaan päivitämme sovelluksen automaattisesti ilman käyttökatkoja.

> [!TIP]
> Jos haluat lähettää ominaisuuspyyntöjä ja tuote-ehdotuksia tai äänestää niistä, siirry [Dynamics 365 Application Ideas -portaaliin](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="march-2022-updates"></a>Maaliskuun 2022 päivitykset

Maaliskuun 2022 päivitykset sisältävät uudet ominaisuudet, suorituskykypäivitykset ja ohjelmavirheiden korjaukset.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec -rikastus (esiversio)

LiveRamp mahdollistaa tunnistetietojen ratkaisun ja asiakastietojen yhdistämisen. Voit liittää asiakastiedoissa olevia henkilökohtaisia tunnisteita AbiliTec-tunnistetietokaavioon ja vastaanottaa AbiliTec-tunnuksia. Sen jälkeen kyseisiä tunnuksia voi käyttää asiakastietojen aiempaa parempaa yhdistämistä varten.

Lisätietoja on ohjeaiheessa [Täydennä asiakasprofiileja LiveRamp-tunnistetietojen avulla (esiversio)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Segmenttien ja mittareiden järjestäminen tunnisteilla ja suodattimilla
Jos organisaatiossa ylläpidetään useita segmenttejä tai mittareita, oikean segmentin tai mittarin löytäminen voi joskus olla hankalaa. Tämän uuden ominaisuuden avulla luettelot voidaan järjestää tunnisteiden ja sarakkeiden avulla. Sen avulla tietojen löytäminen ja näkymien mukauttaminen on nopeaa ja helppoa.

Lisätietoja on kohdassa [Tunnisteiden ja sarakkeiden käsitteleminen](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Tietojen jakamisen käyttöönotto Dataversen kanssa oman tallennustilin käyttämisen yhteydessä

Jos ympäristösi käyttää Azure Data Lake Storagea Customer Insights -tietojen tallentamiseen, tietojen jakaminen Microsoft Dataversen kanssa edellyttää lisämäärityksiä.
Aiemmin tietojen jakaminen Dataversen kanssa voitiin ottaa käyttöön vain, kun tiedot oli tallennettu omaan hallittuun Data Lake -tallennustilaan. 

Lisätietoja on kohdassa [Tietojen jakamisen käyttöönotto Dataversen kanssa omasta Azure Data Lake Storage (esiversio) -ratkaisusta](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Uudet vientikohteet: Iterable ja Braze

Jatkamme vientikohteiden ekosysteemin laajentamista uusilla yhteyksillä. Voit nyt viedä osia Iterableen ja Brazeen ja käyttää niiden aktivointipalveluita.

Lisätietoja on kohdissa [Segmenttien vieminen Iterableen (esiversio)](export-iterable.md) ja [Segmenttien vieminen Brazeen (esiversio)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Marketo- ja Google Ads -viennin parannukset

Kun yhdistettyjen palveluiden ohjelmointirajapintoja muutetaan, yhdistimien päivitykset voidaan suorittaa luotettavasti ja sujuvasti. Olemme julkaisseet seuraavat päivitykset Marketo- ja Google Ads -palveluihin viemisestä:

- Google Ads: Google Ads -palvelun viennin yhdistin yksinkertaistaa todennuskokemusta. Se myös mahdollistaa uusien Google Ads -käyttäjäryhmien luomisen automaattisesti. 
- Marketo: Marketo-palvelun viennin yhdistin tukee Marketo-tunnusta. Sen avulla on mahdollista välttää tietojen kaksoiskappaleet, päivittää olemassa olevat tietueet ja luoda uusia tietueita Marketossa. 


## <a name="february-2022-updates"></a>Helmikuun 2022 päivitykset

Helmikuun 2022 päivitykset sisältävät uudet ominaisuudet, suorituskykypäivitykset ja ohjelmavirheiden korjaukset.

### <a name="general-availability-for-prediction-models"></a>Ennustemallien yleinen saatavuus

Valmiit ennustemallit kuten **tilausten vaihtuvuus**, **tapahtumien vaihtuvuus** ja **asiakkaan elinkaaren arvo (CLV)** tulevat yleisesti saataville osina Customer Insightsia. 

Lisätietoja on kohdassa [Ennusteiden yleiskatsaus](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Uusi tietolähde: integrointi Azure Synapse Analyticsin kanssa (esiversio)

Azure Synapse Analytics on yritysanalyysipalvelu, joka nopeuttaa tietovarastojen ja suurien tietojärjestelmien tuottamia oivalluksia.

Jos organisaatiossa on jo käytössä Azure Synapse Analytics, nämä tiedot voidaan ottaa käyttöön Customer Insightsissa. 

Lisätietoja: [Yhdistä Azure Synapse -tietolähde (esiversio)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRamp-rikastus (esiversio)

LiveRamp mahdollistaa tunnistetietojen ratkaisun ja asiakastietojen yhdistämisen. Voit liittää asiakastiedoissa olevia henkilökohtaisia tunnisteita AbiliTec-tunnistetietokaavioon ja vastaanottaa AbiliTec-tunnuksia. Sen jälkeen kyseisiä tunnuksia voi käyttää asiakastietojen aiempaa parempaa yhdistämistä varten.

Lisätietoja on ohjeaiheessa [Täydennä asiakasprofiileja LiveRamp-tunnistetietojen avulla (esiversio)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Rikastus tietolähteitä varten (esiversio)

Käytä Microsoftin ja muiden kumppanien tietoja asiakastietojen rikastukseen ennen tietojen yhdistämistä. Tietolähteiden rikastus auttaa täydellisemmän ja laadukkaamman tiedon tuottamisessa, mikä puolestaan parantaa tietojen yhdistämisen tuloksia.

Lisätietoja: [Rikastus tietolähteitä varten (esiversio)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Muuta ympäristön omistajaa

Vaikka useilla käyttäjillä voi olla järjestelmänvalvojan oikeudet Customer Insightsissa, vain yksi käyttäjä on ympäristön omistaja. Parannetun kokemuksen avulla voit vaihtaa ympäristön omistajaa tai ottaa omistuksen, jos entinen omistaja on lähtenyt organisaatiosta. 

Lisätietoja: [Ympäristön omistajan vaihtaminen](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Tietojen valmistelun prosessi luetteloi virheellisten tietueiden virheiden syyn

Tietojen valmistelu näyttää nyt kaikkien virheellisiä tietoja sisältävien kenttien virheen syyn. Tiedot on annettu yksittäisen tietueen tasolla tunnistamisen helpottamiseksi. 

Lisätietoja: [Virheelliset tietolähteet](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Vuorovaikutuksen merkityksellisten tietojen raportointiominaisuuden esiversion lopettaminen

Dynamics 365 Customer Insightsin vuorovaikutuksen merkityksellisten tietojen esiversio lopetettiin 15.2.2022.  
Tämä muutos tarkoittaa sitä, että Customer Insights -kokeilukokemus ei enää sisältää mahdollisuutta luoda suppiloja eikä muita raportointitoimintoja.

Kutsumme sinut tutustumaan ja arvioimaan [Customer Insightsin](https://dynamics.microsoft.com/ai/customer-insights/), Microsoftin asiakastietoympäristön (CDP), monia muita ominaisuuksia.    
 
Siirtymisjakson aikana olemassa olevat esiversion osallistujat voivat edelleen käyttää joitakin esiversio-ominaisuuksia ja -toimintoja:

- Koodin käyttäminen verkkosivuston tai mobiilisovelluksen luomiseen 
- Tapahtumien ja tapahtumien ominaisuuksien katsominen 
- Paranna yhtenäisiä profiileja käsiteltyjen ja jalostettujen tapahtumien avulla, jotta asiakastietojen täydestä arvosta saa hyötyä
  
Siirtymisjakson aikana siepatut tapahtumat virtautetaan yhä yhdistettyyn Data Lakeen. Kun tämä toiminto on poistettu käytöstä, tapahtumien tietojen jakaminen loppuu eikä uusia tapahtumia lähetetä yhdistettyyn tallennustilaan.
Ota yhteyttä suoraan Microsoft-asiakastiimiisi, jos sinulla on kysymyksiä ominaisuuden esiversion loppumisesta. Asiakastiimisi pitää sinut ajan tasalla tulevista julkaisuista. 

## <a name="january-2022-updates"></a>Tammikuun 2022 päivitykset

Tammikuun 2022 päivitykset sisältävät uudet ominaisuudet, suorituskykypäivitykset ja ohjelmavirheiden korjaukset.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Asiakaspalautteen asenneanalyysi

Customer Insights sisältää uuden tekoälyä hyödyntävän ominaisuuden, joka syntetisoi asiakkaiden asenteita ja tunnistaa tietyt liiketoiminnan näkökohdat mahdollisuuksiksi kohdistettuihin parannuksiin. Analysoimalla asiakkaiden kirjallisen palautteen saat tarkkoja tietoja edulliseen hintaan. Luonnollisen kielen käsittelyn (NLP) mallien avulla suoritettu asenneanalyysi, jossa luodaan kaksi merkityksellistä tietoa kullekin asiakastunnukselle. Asennepisteet (–5–5) ja soveltuvien liiketoimintanäkökohtien luettelot. 

Lisätietoja on ohjeaiheessa [Asenneanalyysi asiakaspalautteessa (Esiversio)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]