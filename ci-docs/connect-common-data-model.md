---
title: Common Data Model -kansioon yhdistäminen Azure Data Lake -tilillä
description: Common Data Model -tietojen käyttäminen Azure Data Lake Storagen avulla.
ms.date: 09/29/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: c12603b9ed8a814356a0f8d0137e97afc749b87c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609938"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Yhdistä Azure Data Lake Storagein tietoihin

Tietojen käsittely Dynamics 365 Customer Insightsiin Azure Data Lake Storage Gen2 -tilin avulla. Tiedot voidaan ottaa käsiteltäviksi kerralla tai vähitellen.

## <a name="prerequisites"></a>edellytykset

- Tietojen käsittely tukee ainoastaan Azure Data Lake Storage *Gen2* -tilejä. Data Lake Gen1 -tilejä ei voi käyttää tietojen käsittelyyn.

- Azure Data Lake Storage -tileissä on oltava [hierarkkinen nimitila otettuna käyttöön](/azure/storage/blobs/data-lake-storage-namespace). Tietojen on oltava tallennettuna sellaisessa hierarkkisessa kansiomuodossa, joka määrittää pääkansion ja jossa kullakin entiteetillä on oma alikansio. Alikansiot voivat olla kaikki tiedot sisältäviä kansioita tai tietoja lisääviä kansioita.

- Azure-palveluobjektin käyttäminen todentamiseen edellyttää, että se on määritetty vuokraajassa. Lisätietoja on kohdassa [Yhteyden muodostaminen Azure Data Lake Storage Gen2 -tiliin Azure-palvelun päänimen avulla](connect-service-principal.md).

- Sen Azure Data Lake Storage -tallennustilan, joka halutaan yhdistää ja josta tietoja halutaan käsitellä, on oltava samalla Azure-alueella kuin Dynamics 365 Customer Insights -ympäristö. Yhteyksiä Common Data Model -kansioon toisen Azure-alueen Data Lake -tallennustilasta ei tueta. Jos haluat tietää ympäristön Azure-alueen, siirry kohtaan **Järjestelmänhallinta** > **Järjestelmä** > **Tietoja** Customer Insightsissa.

- Online-palveluihin tallennetut tiedot voivat olla tallennettu eri sijaintiin kuin missä tietoja käsitellään ja mihin ne tallennetaan Dynamics 365 Customer Insightsissa. Tuomalla verkkopalveluun tallennetut tiedot tai muodostamalla niihin yhteyden hyväksyt, että tiedot voidaan siirtää ja tallentaa yhdessä Dynamics 365 Customer Insightsin kanssa.  [Lisätietoja on Microsoftin luottamuskeskuksessa](https://www.microsoft.com/trust-center).

- Tallennustilin käyttö edellyttää, että Customer Insights -palvelun päänimen rooli on jokin seuraavista. Lisätietoja on kohdassa [Tallennustilin käyttöön tarvittavien oikeuksien myöntäminen palvelun päänimelle](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Tallennustilan Blob-tietojen lukija
  - Tallennustilan Blob-tietojen omistaja
  - Tallennustilan Blob-tietojen osallistuja

- Käyttäjä, joka määrittää tietolähteen yhteyden, tarvitsee vähiten Tallennustilan Blob-tietojen osallistuja -käyttöoikeudet tallennustilille.

- Data Lake Storagen tietojen on noudatettava tietojen Common Data Model -tallennusstandardia ja niillä on oltava datatiedostojen rakenteen (*.csv tai *.parquet) ilmaiseva Common Data Model -luettelotiedosto. Luettelotiedostossa on oltava entiteettien, kuten entiteetin sarakkeiden ja tietotyyppien; tiedot sekä datatiedoston sijainti ja tiedostotyyppi. Lisätietoja on kohdassa [Common Data Model -luettelotiedosto](/common-data-model/sdk/manifest). Jos luettelotiedostoa ei ole, järjestelmänvalvojat, joilla on tallennustilan blob-tietojen omistajan tai osallistujan oikeudet, voivat määrittää rakenteen tietoja käsiteltäessä.

## <a name="recommendations"></a>Suosituksia

Optimaalisen suorituskyvyn kannalta Customer Insights suosittelee osion koon olevan enintään 1 gigatavu ja kansiossa olevien osiotiedostojen enimmäismäärä on 1 000.

## <a name="connect-to-azure-data-lake-storage"></a>Yhdistä Azure Data Lake Storageen

1. Valitse **Tiedot** > **Tietolähteet**.

1. Valitse **Lisää tietolähde**.

1. Valitse **Azure Data Lake Storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Valintaikkuna Azure Data Laken yhteystietojen antamiseen" lightbox="media/data_sources_ADLS.png":::

1. Anna tietolähteelle **nimi** ja valinnainen **kuvaus** Nimi yksilöi tietolähteen ja siihen viitataan myöhemmissä prosesseissa. Tätä nimeä ei voi muuttaa.

1. Valitse jokin seuraavista **Yhdistä omaan tallennustilaan seuraavasti:** -vaihtoehtoista. Lisätietoja on kohdassa [Customer Insightsin liittäminen Azure Data Lake Storage Gen2 -tiliin Azure-palvelun päänimen avulla](connect-service-principal.md).

   - **Azure-resurssi**: Anna **Resurssin tunnus**. Jos tietoja halutaan käsitellä tallennustililtä Azuren yksityisen linkin kautta, valitse myös **Ota yksityinen linkki käyttöön**. Lisätietoja on kohdassa [Yksityiset linkit](security-overview.md#set-up-an-azure-private-link).
   - **Azure-tilaus**: Valitse ensin **Tilaus** sekä sen jälkeen **Resurssiryhmä** ja **Tallennustili**. Jos tietoja halutaan käsitellä tallennustililtä Azuren yksityisen linkin kautta, valitse myös **Ota yksityinen linkki käyttöön**. Lisätietoja on kohdassa [Yksityiset linkit](security-overview.md#set-up-an-azure-private-link).
  
   > [!NOTE]
   > Tietolähteen luontia varten säilön tai tallennustilin osalta tarvitaan jokin seuraavista rooleista:
   >
   >  - Säilön BLOB-tietojen lukija riittää lukemaan tallennustililtä ja syöttämään tiedot Customer Insightsiin.
   >  - Säilön BLOB-tietojen osallistuja tai Omistaja tarvitaan, jos haluat muokata luettelotiedostoja suoraan Customer Insightsissa.  
  
1. Valitse sen **säilön** nimi, jossa tuotavien tietojen tiedot ja rakenne (model.json- tai manifest.json-tiedosto) on ja valitse sitten **Seuraava**.
   > [!NOTE]
   > Toiseen ympäristön tietolähteeseen liitetyt model.json- tai manifest.json-tiedostot eivät näy luettelossa. Samaa model.json- tai manifest.json-tiedostoa voi kuitenkin käyttää tietolähteissä useissa ympäristöissä.

1. Lisätietoja uuden rakenteen luomisesta on kohdassa [Uuden rakennetiedoston luominen](#create-a-new-schema-file).

1. Aiemmin luotua rakennetta voi käyttää siirtymällä model.json- tai manifest.cdm.json-tiedoston sisältävään kansioon. Tiedoston voi etsiä hakemalla sitä hakemistossa.

1. Valitse ensin json-tiedosto ja sitten **Seuraava**. Käytettävissä olevien entiteettien luettelon tulee näkyviin.

   :::image type="content" source="media/review-entities.png" alt-text="Valintaikkuna valittavissa olevien entiteettien luettelossa":::

1. Valitse sisällytettävät entiteetit.

   :::image type="content" source="media/ADLS_required.png" alt-text="Valintaikkunassa näkyy Perusavain-valinta Pakollinen":::

   > [!TIP]
   > Entiteettiä voi muokata JSON-muokkausliittymässä valitsemalla entiteetin ja **Muokkaa rakennetiedostoa**. Tee muutokset ja valitse **Tallenna**.

1. Jos valituissa entiteeteissä edellytetään lisäävää käsittelyä, **Lisäävä päivitys** -kohdassa näkyy **Pakollinen**. Lisätietoja kustakin entiteetistä on kohdassa [Azure Data Lake Data -lähteiden lisäävän päivityksen määrittäminen](incremental-refresh-data-sources.md).

1. Jos valitulle entiteetille ei ole määritetty perusavainta, **Pakollinen** näkyy **Perusavain**-asetuksena. Toimi seuraavasti kyseisten entiteettien osalta:
   1. Valitse **Pakollinen**. **Muokkaa entiteettiä** -paneeli avautuu.
   1. Valitse **Perusavain**. Perusavain on entiteetin yksilöllinen määrite. Jotta määrite olisi kelvollinen perusavain, se ei saa sisältää arvojen kaksoiskappaleita, siitä ei saa puuttua arvoja eikä siinä saa olla tyhjiä arvoja. Merkkijono-, kokonaisluku- ja GUID-tietotyypin määritteitä tuetaan perusavaimina.
   1. Myös osiomallia voidaan muuttaa.
   1. Tallenna ja sulje paneeli lomake valitsemalla **Sulje**.

1. Valitse kunkin sisällytetyn entiteetin **määritteiden** määrä. **Hallitse määritteitä** -sivu avautuu.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Tietojen profilointivalinnan valintaruutu":::

   1. Luo uusi määritteitä taikka muokkaa tai poista aiemmin luotuja määritteitä. Nimen tai tiedostomuodon voi muuttaa tai sementtisen tyypin lisätä.
   1. Analytiikka ja muut ominaisuudet otetaan käyttöön valitsemalla **Tietojen profilointi** koskemaan koko entiteettiä tai vain tiettyjä määritteitä. Tietojen profilointi ei ole oletusarvoisesti otettu käyttöön missään entiteetissä.
   1. Valitse **Valmis**.

1. Valitse **Tallenna**. Avautuvalla **Tietolähteet**-sivulla on näkyy uusi tietolähde, jonka tilana on **Päivitetään**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Tietojen lataaminen voi viedä aikaa. Kun päivitys on onnistunut, käsiteltyjä tietoja voi tarkastella [**Entiteetit**](entities.md)-sivulla.

### <a name="create-a-new-schema-file"></a>Uuden rakennetiedoston luominen

1. Valitse **Uusi rakennetiedosto**.

1. Anna tiedostolle nimi ja valitse **Tallenna**.

1. Valitse **Uusi entiteetti**. **Uusi entiteetti** -paneeli avautuu.

1. Anna entiteetin nimi ja valitse **Datatiedostojen sijainti**.
   - **Useita .csv- tai .parquet-tiedostoja**: siirry pääkansioon, valitse kaavatyyppi ja kirjoita lauseke.
   - **Yksi .csv- tai .parquet-tiedosto**: siirry .csv- tai .parquet-tiedostoon ja valitse se.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Uuden entiteetin luonti-ikkuna Datatiedostojen sijainti korostettuna":::

1. Valitse **Tallenna**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Määritteiden määritys- tai automaattinen luonti-ikkuna":::

1. Lisää määritteet manuaalisesti valitsemalla **määritteiden määrittäminen** tai valitse **niiden luominen automaattisesti**. Määritteet määritetään antamalla nimi, valitsemalla tietomuoto ja valinnaisena myös semanttinen tyyppi. Määritteiden automaattinen luonti:

   1. Valitse määritteiden automaattisen luonnin jälkeen **Tarkista määritteet**. **Hallitse määritteitä** -sivu avautuu.

   1. Varmista, että kunkin määritteet tietomuoto on oikea.

   1. Analytiikka ja muut ominaisuudet otetaan käyttöön valitsemalla **Tietojen profilointi** koskemaan koko entiteettiä tai vain tiettyjä määritteitä. Tietojen profilointi ei ole oletusarvoisesti otettu käyttöön missään entiteetissä.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Tietojen profilointivalinnan valintaruutu":::

   1. Valitse **Valmis**. **Valitse entiteetit** -sivu avautuu.

1. Jatka tarvittaessa entiteettien ja määritteiden lisäämistä.

1. Kun kaikki entiteetit on lisätty, sisällytä entiteetit tietolähteen käsittelyyn valitsemalla **Sisällytä**.

   :::image type="content" source="media/ADLS_required.png" alt-text="Valintaikkunassa näkyy Perusavain-valinta Pakollinen":::

1. Jos valituissa entiteeteissä edellytetään lisäävää käsittelyä, **Lisäävä päivitys** -kohdassa näkyy **Pakollinen**. Lisätietoja kustakin entiteetistä on kohdassa [Azure Data Lake Data -lähteiden lisäävän päivityksen määrittäminen](incremental-refresh-data-sources.md).

1. Jos valitulle entiteetille ei ole määritetty perusavainta, **Pakollinen** näkyy **Perusavain**-asetuksena. Toimi seuraavasti kyseisten entiteettien osalta:
   1. Valitse **Pakollinen**. **Muokkaa entiteettiä** -paneeli avautuu.
   1. Valitse **Perusavain**. Perusavain on entiteetin yksilöllinen määrite. Jotta määrite olisi kelvollinen perusavain, se ei saa sisältää arvojen kaksoiskappaleita, siitä ei saa puuttua arvoja eikä siinä saa olla tyhjiä arvoja. Merkkijono-, kokonaisluku- ja GUID-tietotyypin määritteitä tuetaan perusavaimina.
   1. Myös osiomallia voidaan muuttaa.
   1. Tallenna ja sulje paneeli lomake valitsemalla **Sulje**.

1. Valitse **Tallenna**. Avautuvalla **Tietolähteet**-sivulla on näkyy uusi tietolähde, jonka tilana on **Päivitetään**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Tietojen lataaminen voi viedä aikaa. Kun päivitys on onnistunut, käsiteltyjä tietoja voi tarkastella [**Entiteetit**](entities.md)-sivulla.

## <a name="edit-an-azure-data-lake-storage-data-source"></a>Azure Data Lake Storage -tietolähteen muokkaaminen

*Yhdistä tallennustilatiliisi käyttämällä* -vaihtoehto voidaan päivittää. Lisätietoja on kohdassa [Customer Insightsin liittäminen Azure Data Lake Storage Gen2 -tiliin Azure-palvelun päänimen avulla](connect-service-principal.md). Jos haluat muodostaa yhteyden toiseen säilöön tallennustilatililtä tai muuttaa tilin nimeä, sinun on [luotava uusi tietolähdeyhteys](#connect-to-azure-data-lake-storage).

1. Valitse **Tiedot** > **Tietolähteet**.

1. Valitse päivitettävän tietolähteen vieressä **Muokkaa**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Azure Data Lake -tietolähteen muokkausikkuna":::

1. Muokkaa seuraavia tietoja:

   - **Description**
   - **Yhdistä tallennustilatiliisi käyttämällä** ja yhteystiedot. **Säilö**-tietoja ei voi muuttaa yhteyttä päivitettäessä.
      > [!NOTE]
      > Tallennustilatilille tai säilölle on määritettävä jokin seuraavista rooleista:
        > - Tallennustilan Blob-tietojen lukija
        > - Tallennustilan Blob-tietojen omistaja
        > - Tallennustilan Blob-tietojen osallistuja

   - **Ota yksityinen linkki käyttöön**, jos tietoja halutaan käsitellä tallennustililtä Azuren yksityisen linkin kautta. Lisätietoja on kohdassa [Yksityiset linkit](security-overview.md#set-up-an-azure-private-link).

1. Valitse **Seuraava**.
1. Seuraavia voi muokata:
   - Siirry toiseen model.json- tai manifest.json-tiedostoon, jossa on säilöstä poikkeava entiteettijoukko.
   - Lisää muita käsiteltäviä entiteettejä valitsemalla **Uusi entiteetti**.
   - Poista jo valittuja entiteettejä, joissa ei ole riippuvuuksia valitsemalla entiteetti ja **Poista**.
      > [!IMPORTANT]
      > Jos aiemmin luodussa model.json- tai manifest.json-tiedostossa ja entiteettijoukkossa on riippuvuuksia, näkyviin tulee virhesanoma, eikä toista model.json- tai manifest.json-tiedostoa voi valita. Poista nämä riippuvuudet, ennen kuin muutat model.json- tai manifest.json-tiedostoa, tai luo uusi tietolähde sillä model.json- tai manifest.json-tiedostolla, jota haluat käyttää. Tällöin riippuvuuksia ei tarvitse poistaa.
   - Muuta datatiedoston sijaintia tai perusavainta valitsemalla **Muokkaa**.
   - Lisätietoja tietojen lisäävästä käsittelystä on kohdassa [Azure Data Lake -tietolähteiden lisäävän päivityksen määrittäminen](incremental-refresh-data-sources.md)
   - Muuta entiteetin nimi vain vastaamaan .json-tiedoston entiteetin nimeä.

     > [!NOTE]
     > Pidä Customer Insightsissa aina entiteetin nimi samana kuin model.json- tai manifest.json-tiedostossa käsittelyn jälkeen. Customer Insights hyväksyy kaikki entiteettien nimet model.json- tai manifest.json-tiedoston kanssa jokaisen järjestelmäpäivityksen aikana. Jos entiteetin nimeä muutetaan joko Customer Insightsin sisällä tai ulkopuolella, tapahtuu virhe, koska Customer Insights ei löydä uutta entiteetin nimeä .json-tiedostosta. Jos olet vahingossa muuttanut entiteetin nimen, muokkaa Customer Insightsin entiteetin nimeä niin, että se vastaa .json-tiedostossa olevaa nimeä.

1. Lisää tai muuta määritteitä taikka ota tietojen profilointi käyttöön valitsemalla **Määritteet**. Valitse sitten **Valmis**.

1. Ota muutokset käyttöön ja palaa **Tietolähteet**-sivulle valitsemalla **Tallenna**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Käsittelyvirheiden tai vioittuneiden tietojen yleisiä syitä

Yleisiä syitä tietueen vaurioitumiselle tietojen käsittelyn aikana:

- Tietotyypit ja kentän arvot eivät ole samat lähdetiedostossa ja rakenteessa
- Lähdetiedoston sarakkeiden määrä ei ole sama kuin rakenteessa
- Kentissä on merkkejä, joiden vuoksi sarakkeet vinoutuvat odotettuun rakenteeseen verrattuna. Esimerkkejä: väärin muotoillut lainausmerkit, virheellisiä lainausmerkit, uuden rivin merkit tai sarkainmerkit.
- Osiotiedostot puuttuvat
- Mahdollisten päivämäärä ja aika-, päivämäärä- tai päivämääräsiirtymäsarakkeiden muoto on määritettävä rakenteessa, jos se ei noudata vakiomuotoa.

### <a name="schema-or-data-type-mismatch"></a>Rakenteen tai tietotyypin ristiriita

Jos tiedot eivät ole rakenteen mukaisia, käsittelyprosessi valmistuu mutta siinä on virheitä. Korjaa joko lähdetiedot tai rakenne ja käsittele tiedot uudelleen.

### <a name="partition-files-are-missing"></a>Osiotiedostot puuttuvat

- Jos käsittely onnistui ilman vioittuneita tietueita mutta mitään tietoja ei ole näkyvissä, varmista, että osiot on määritetty muokkaamalla model.json- tai manifest.json-tiedostoa. [Päivitä tielähde](data-sources.md#refresh-data-sources) sitten.

- jos tietoja käsitellään samanaikaisesti tietojen automaattisesti aikataulutetun päivityksen aikana, osiotiedostot voivat olla tyhjiä tai niitä ei voi käsitellä Customer Insightsissa. Kohdistus yläpuoliseen päivitysaikatauluun voidaan tehdä muuttamalla [järjestelmän päivitysaikataulua](schedule-refresh.md) tai tietolähteen päivitysaikataulua. Ajoitus kohdistetaan siten, että kaikki päivitykset eivät tapahdu samanaikaisesti ja että päivityksessä saadaan uusimmat tiedot Customer Insightsissa käsiteltäviksi.

### <a name="datetime-fields-in-the-wrong-format"></a>Päivämäärä- ja aika kenttien muoto väärä

Entiteetin päivämäärä- ja aikakentät eivät ole ISO 8601- tai en-US-muotoisia. Päivämäärän ja ajan oletusmuoto Customer Insightsissa on en-US. Kaikissa entiteetin päivämäärä- ja aikakentissä on oltava sama muoto. Customer Insights tukee muita muotoja, kunhan huomautukset tai ominaisuudet tehdään mallin tai manifest.json-tiedoston lähde- tai entiteettitasolla. Esimerkki:

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  Manifest.json-tiedostossa päivämäärä- ja aikamuoto voidaan määrittää entiteetti- tai määritetasolla. Määritä päivämäärä- ja aikamuoto käyttämällä entiteettitasolla entiteetissä exhibitsTraits-ominaisuutta *.manifest.cdm.json-tiedostossa. Käytä määritetasolla appliedTraits-ominaisuutta entityname.cdm.json-tiedoston määritteessä.

**Manifest.json entiteettitasolla**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json määritetasolla**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
