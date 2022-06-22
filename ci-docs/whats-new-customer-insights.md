---
title: Uudet ja päivitetyt toiminnot
description: Tietoja uusista ominaisuuksista, parannuksista ja virheiden korjauksista.
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: d06f8be114f558d7adadf2913107c5fd69686875
ms.sourcegitcommit: 9dd767051014e06d8d9f2f616e248573f24df4cb
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/03/2022
ms.locfileid: "8843343"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insightsin uudet ominaisuudet

Olemme innoissamme voidessamme ilmoittaa uusimmista päivityksistämme! Tässä artikkelissa on yhteenveto yleisen esiversion ominaisuuksista, yleisen saatavuuden parannuksista ja ominaisuuksien päivityksistä. Katso ominaisuuksien pitkäaikaiset suunnitelmat [Dynamics 365- ja Power Platform -julkaisusuunnitelmista](/dynamics365/release-plans/).

Julkaisemme päivitykset alueittain. Näin siis jotkin alueet saattavat nähdä ominaisuuksia ennen muita. Ellei toisin määritetä, sinun ei tarvitse tehdä mitään, vaan päivitämme sovelluksen automaattisesti ilman käyttökatkoja.

> [!TIP]
> Jos haluat lähettää ominaisuuspyyntöjä ja tuote-ehdotuksia tai äänestää niistä, siirry [Dynamics 365 Application Ideas -portaaliin](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="may-2022-updates"></a>Toukokuun 2022 päivityksey

Toukokuun 2022 päivitykset sisältävät uudet ominaisuudet, suorituskykypäivitykset ja ohjelmavirheiden korjaukset.

### <a name="updated-data-unification-experience"></a>Päivitetty tietojen yhdistämiskokemus

 Tietojen yhdistämisen avulla voit yhdistää aiemmin erilliset tietolähteet yhdeksi päätietojoukoksi, joka tarjoaa yhtenäisen näkymän kyseisistä tiedoista. Tiedot voidaan yhtenäistää yhdessä entiteetissä tai useassa entiteetissä. Ensin [valitaan entiteetit ja lähdekentät](map-entities.md), [poistetaan tietueiden kaksoiskappaleet](remove-duplicates.md), määritetään [vastaavuusehtojen](match-entities.md) säännöt sekä määritetään, mitkä [kentät sisällytetään yhdistettyihin asiakasprofiileihin](merge-entities.md).

Lisätietoja on kohdassa [Tietojen yhdistämisen yleiskatsaus](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Customer Insightsin päivitetty aloitussivu

**Aloitussivu** opastaa tärkeiden ominaisuuksien määritysprosessissa sekä antaa yleiskuvan segmenttien, toimenpiteiden ja täydennystietojen määrityksestä. Kokemus on päivitetty sisältämään entistä enemmän olennaisia tietoja kerralla nähtäväksi.

Lisätietoja on kohdassa [Customer Insightsiin tutustuminen](home.md).

### <a name="track-usage-of-a-segment"></a>Segmentin käytön seuranta

[Segmenttien käyttöä voi nyt seurata](segments.md#track-usage-of-a-segment) sovelluksissa, jotka perustuvat Customer Insightsiin yhdistettyyn Dataverse-organisaatioon. [Dynamics 365 Marketingin asiakassiirtymissä käytettävien Customer Insights -segmenttien osalta](/dynamics365/marketing/real-time-marketing-ci-profile) järjestelmä ilmoittaa sinulle segmentin käytöstä.

### <a name="export-to-criteo"></a>Vienti Criteoon

Criteo on verkkoympäristön, jonka avulla käyttäjät voivat hallita digitaalista markkinointia. Yhdistetyistä asiakasprofiileista voidaan nyt viedä Criteon avulla segmenttejä, joilla voidaan luoda kampanjoita, tehdä sähköpostimarkkinointia ja käyttää tiettyjä asiakasryhmiä.

Lisätietoja on kohdassa [Segmenttien vienti Criteoon (esiversio)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Ympäristön luonnin tarkennettu ohjerakenne

Ympäristöjen luontiin ja hallintaan Customer Insightsissa liittyviä ohjeasiakirjoja on korjattu. Artikkelit ryhmitellään nyt sisällysluettelossa ympäristösolmun mukaan. Rakenteeltaan uudistetuissa artikkeleissa on enemmän erilaisia ympäristöjen määrittämistä koskevia ohjeita. Lisäksi artikkelien rakennetta on selkeytetty. Voit antaa meille palautetta ohjeartikkelien loppupuolella olevien ohjausobjektien avulla.

Lisätietoja on kohdassa [Toimintaohje: Uuden ympäristön luominen](create-environment.md).

## <a name="april-2022-updates"></a>Huhtikuun 2022 päivitykset

Huhtikuun 2022 päivitykset sisältävät uudet ominaisuudet, suorituskykypäivitykset ja ohjelmavirheiden korjaukset.

### <a name="dun--bradstreet-enrichment-preview"></a>Dun & Bradstreet -rikastus (esiversio)

Dun & Bradstreet tarjoaa liikeyrityksille merkityksellisiä kaupallisia tietoja, analyyseja ja oivalluksia. Sen avulla voidaan täydentää niiden asiakkaiden tietoja, joilla on yhtenäiset asiakasprofiilit yrityksissä. Rikastamiseen sisältyy määritteitä, kuten DUNS-numerolla, yrityksen koolla, sijainnilla, toimialalla ja muilla tiedoilla.

Lisätietoja on ohjeaiheessa [Yritysprofiilien rikastaminen Dun & Bradstreet -tietojen avulla (esiversio)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Mittayksikön tyypin määritteleminen uutta mittayksikköä luotaessa

Nyt voit erotella yksittäisten profiilien ja koko yrityksen mitat toisistaan. Vaikka liiketoiminnan mitat näkyvät Customer Insights -kotisivulla, asiakkaan mitat näkyvät yksityiskohtaisissa asiakasnäkymissä.

Lisätietoja on kohdassa [Mittareiden luominen tyhjästä mittarien luontitoiminnon avulla](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Customer Insights -dokumentaation yhdistäminen

Olemme käyneet uudelleen dokumentointiartikkeleissamme ja poistaneet mainintoja vuorovaikutuksen merkityksellisistä tiedoista ja käyttäjäryhmän merkityksellisistä tiedoista. Tämän jälkeen viitataan johdonmukaisesti Customer Insights -tuotenimeen, kun kirjoitamme sovelluksen ydinominaisuuksista. Tämä muutos johtaa myös siihen, että sisällysluettelo, URL-rakenne ja taustalla olevan dokumentaatiosäilön tiedostopolut ovat muuttuneet merkittävästi. Kaikki kirjanmerkkisi tai aiemmin luodut linkit toimivat edelleen ja ohjaavat uudelleen päivitettyihin URL-osoitteisiin.

Jos haluat kertoa meille mielipiteesi muutoksesta tai havaitset jotain, mikä ei toimi odotetusti, kerro siitä meille [lähettämällä meille palautetta tästä sivusta](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

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

Lisätietoja on kohdassa [Tietojen jakamisen käyttöönotto Dataversen kanssa omasta Azure Data Lake Storage (esiversio) -ratkaisusta](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

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