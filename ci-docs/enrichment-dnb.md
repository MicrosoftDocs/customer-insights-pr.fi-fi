---
title: Yritysprofiilien rikastaminen Dun & Bradstreetin avulla
description: Yleisiä tietoja Dun & Bradstreetin kolmannen osapuolen rikastamisesta.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653707"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Yritysprofiilien rikastaminen Dun & Bradstreetin avulla (esiversio)

Dun & Bradstreet tarjoaa liikeyrityksille merkityksellisiä kaupallisia tietoja, analyyseja ja oivalluksia. Sen avulla voidaan täydentää niiden asiakkaiden tietoja, joilla on yhtenäiset asiakasprofiilit yrityksissä. Rikastamiseen sisältyy määritteitä, kuten DUNS-numerolla, yrityksen koolla, sijainnilla, toimialalla ja muilla tiedoilla.

## <a name="prerequisites"></a>edellytykset

Jotta voit määrittää Dun & Bradstreet -rikastuksen, seuraavien edellytysten on täytyttävä:

- Tarvitset aktiivisen [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) -pilvikäyttöoikeuden.
- Sinulla on [yhtenäiset asiakasprofiilit](customer-profiles.md) yrityksiä varten.
- Järjestelmänvalvoja on määrittänyt Dun & Bradstreet -[yhteyden](connections.md). Voit luoda sen, jos sinulla on [Järjestelmänvalvoja](permissions.md#admin)-käyttöoikeudet ja tunnistetiedot Dun & Bradstreet Connectista. 

## <a name="setting-up-your-dun--bradstreet-project"></a>Dun & Bradstreet -projektin asetusten määrittäminen

Voit määrittää projektin Dun & Bradstreetin käyttöoikeuden omistavana käyttäjänä [Dun & Bradstreet Connectissa](https://connect.dnb.com?lead_source=microsoft_audienceinsights). 


1. Kirjaudu [Dun & Bradstreet Connectiin](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Jos haluat hakea tunnistetiedot, [palauta salasanasi](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Lataa [CSV-mallitiedosto](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv), jonka avulla käyttäjäryhmien tietokentät yhdistetään vastaaviin Dun & Bradstreet -kenttiin. 

1. Lataa tiedosto Dun & Bradstreet -projektin luontikokemuksen **Lataa tiedot** -vaiheessa. 

1. Näet käytettävissä olevat vaihtoehdot valitsemalla vaakapisteet sopivan **lähteen** alla juuri luodussa Dun & Bradstreet -projektissa.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Näyttökuva Dun & Bradstreet -projektin pisteistä.":::

1. Valitse **Hae S3-tiedot**. Tallenna nämä tiedot turvalliseen paikkaan. Tarvitset sen, jotta voit [määrittää yhteyden rikastusta varten](#configure-a-connection-for-dun--bradstreet) kohdeyleisön perusteella. 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Näyttökuva Dun & Bradstreet -projektin s3-tietojen valinnasta.":::



## <a name="configure-the-enrichment"></a>Määritä rikastus

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Rikastaminen**.

1. Valitse Dun & Bradstreet -ruudussa **Tietojen rikastaminen** ja valitse sitten **Aloitus**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Näyttökuva Dun & Bradstreet -ruudusta.":::

1. Valitse [yhteys](connections.md) avattavasta luettelosta. Ota yhteyttä järjestelmänvalvojaan, jos yhteyttä ei ole käytettävissä. Jos olet Järjestelmänvalvoja, voit luoda yhteyden. Valitse **Lisää yhteys** ja valitse sitten **Dun & Bradstreet**. 

1. Vahvista yhteys valitsemalla **Yhdistä Dun & Bradstreetiin**.

1. Valitse **Seuraava** ja valitse **Asiakkaan tietojoukko**, jota haluat rikastaa Dun & Bradstreet -liiketoimintatietojen avulla. Voit valita **asiakas**-entiteetin, joka rikastaa kaikkia asiakasprofiileja, tai segmenttientiteetin, joka rikastaa vain segmenttiin sisältyviä Unified customer profileja.

1. Valitse **Seuraava** ja määritä, minkä tyyppisiä yhdistettyjen profiilien kenttiä käytetään vastaavien Dun & Bradstreet-liiketoimintatietojen etsimiseen. Joko **DUNS-numero** tai **Yrityksen nimi**- ja **Maa**-kentät ovat pakollisia. Maakenttä tukee [kaksi- tai kolmekirjaimista maakoodia](https://www.iso.org/iso-3166-country-codes.html), maan nimeä englanniksi, maan nimeä alkuperäisellä kielellä ja puhelimen etuliitettä. Yleisiä maavariaatioita ovat muun muassa seuraavat:

   * US: Amerikan yhdysvallat, Yhdysvallat, USA, Amerikka.
   * CA: Kanada.
   * GB: Yhdistynyt kuningaskunta, UK, Iso-Britannia, GB, Ison-Britannian ja Pohjois-Irlannin yhdistynyt kuningaskunta, Ison-Britannian yhdistynyt kuningaskunta.
   * AU: Australia, Australian liittovaltio.
   * FR: Ranska, Ranskan tasavalta.
   * DE: Saksa, saksalainen, Deutschland, Allemagne, Saksan liittotasavalta, Saksan tasavalta.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet -kentänyhdistämismääritysruutu.":::

1. Viimeistele kentän vastaavuusmääritys valitsemalla **Seuraava**.

1. Anna rikastusta varten nimi ja valitse vaihtoehtojen tarkistamisen jälkeen **Tallenna rikastus**.


## <a name="configure-a-connection-for-dun--bradstreet"></a>Yhteyden määrittäminen Dun & Bradstreetia varten 

Yhteyksien määrittämiseen tarvitaan järjestelmänvalvojan oikeudet. Valitse **Lisää yhteys** määrittäessäsi rikastusta *tai* siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja valitse **Määritä** Dun & Bradstreet -ruudussa.

1. Valitse **Aloita**. 

1. Kirjoita yhteyden nimi **Näyttönimi**-ruutuun.

1. Anna kelvolliset Dun & Bradstreet -tunnukset sekä Dun & Bradstreet -projektin tiedot *Alue, pudotuskansiopolku ja pudotuskansion nimi*. [Saat nämä tiedot](#setting-up-your-dun--bradstreet-project) Dun & Bradstreet -projektista.

1. Tarkista **Tietojen yksityisyys ja vaatimustenmukaisuus** -kohta ja hyväksy se valitsemalla **Hyväksyn**.

1. Tarkista määritys valitsemalla **Tarkista**.

1. Kun tarkistus on suoritettu, valitse **Tallenna**.
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet -yhteyden määrittämissivu.":::

## <a name="enrichment-results"></a>Rikastamisen tulokset

Kun rikastaminen on päivitetty, voit tarkastella uusia rikastettuja yritystietoja [Omat rikastukset](enrichment-hub.md) -kohdassa. Voit etsiä viimeisimmän päivityksen ajankohdan ja täydennettyjen profiilien määrän.

Voit tarkastella kunkin täydennetyn profiilin yksityiskohtaista näkymää valitsemalla **Näytä täydennetyt tiedot**.

## <a name="next-steps"></a>Seuraavat vaiheet

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Tietojen yksityisyys ja vaatimustenmukaisuus

Kun tietojen lähetys Dun & Bradstreetiin otetaan käyttöön Dynamics 365 Customer Insightsissa, tietoja siirtäminen sallitaan silloin Dynamics 365 Customer Insightsin säännöstenmukaisuusrajan ulkopuolelle, mikä voi mahdollisesti koskea myös arkaluonteisia tietoja, kuten henkilötietoja. Microsoft siirtää tällaiset tiedot ohjeittesi mukaisesti, mutta olet vastuussa siitä, että Dun & Bradstreet täyttää tietosuoja- ja tietoturvavaatimukset. Lisätietoja on [Microsoftin tietosuojalausekkeessa](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insightsin järjestelmänvalvoja voi lopettaa tämän toiminnon käytön milloin tahansa poistaa tämän rikastamisen käytöstä.


[!INCLUDE[footer-include](includes/footer-banner.md)]
