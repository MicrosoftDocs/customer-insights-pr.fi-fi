---
title: Common Data Model -tietojen yhdistäminen Azure Data Lake -tiliin
description: Common Data Model -tietojen käyttäminen Azure Data Lake Storagen avulla.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5f9010f78ea4c24094e0df4f8e153fb832e05cc8
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900193"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Common Data Model -kansioon yhdistäminen Azure Data Lake -tilillä

Tässä artikkelissa on tietoja Common Data Model -kansion tietojen käsittelemisestä Azure Data Lake Storage Gen2 -tilin avulla.

## <a name="important-considerations"></a>Tärkeitä huomioon otettavia seikkoja

- Azure Data Lake -tallennustilassa olevien tietojen muodon on oltava Common Data Model -standardin mukaisia. Muita muotoja ei tueta tällä hetkellä.

- Tietojen käsittely tukee ainoastaan Azure Data Lake *Gen2* -tallennustilejä. Azure Data Lake Gen1 -tallennustilejä ei voi käyttää tietojen käsittelyyn.

- Azure-palveluobjektin käyttäminen todentaminen edellyttää, että se on määritetty vuokraajassa. Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md).

- Azure Data Lake -tallennustilan, joka halutaan yhdistää ja jonka tietoja halutaan käsitellä, on oltava samalla Azure-alueella kuin Dynamics 365 Customer Insights -ympäristö. Yhteyksiä Common Data Model -kansioon toisen Azure-alueen Data Lake -tallennustilasta ei tueta. Ympäristön Azure-alueen voi tarkistaa valitsemalla käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Järjestelmä** > **Tietoja**.

- Online-palveluihin tallennetut tiedot voivat olla tallennettu eri sijaintiin kuin missä tietoja käsitellään ja mihin ne tallennetaan Dynamics 365 Customer Insightsissa. Tuomalla verkkopalveluun tallennetut tiedot tai muodostamalla niihin yhteyden hyväksyt, että tiedot voidaan siirtää ja tallentaa yhdessä Dynamics 365 Customer Insightsin kanssa.  [Lisätietoja on Microsoftin luottamuskeskuksessa](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Muodosta yhteys Common Data Model -kansioon

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.

1. Valitse **Lisää tietolähde**.

1. Valitse **Azure Data Lake Storage**, kirjoita tietolähteen **Nimi** ja valitse sitten **Seuraava**.

   - Valitse pyydettäessä jokin toimialaasi liittyvä näytetietojoukko ja valitse sitten **Seuraava**. 

1. Voit valita, käytetäänkö todennukseen resurssi- vai tilausperusteista vaihtoehtoa. Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md). Kirjoita **Palvelimen osoite**, valitse **Kirjaudu sisään** ja valitse sitten **Seuraava**.
   > [!div class="mx-imgBorder"]
   > ![Valintaikkuna, jossa voit lisätä Azure Data Laken uuden yhteyden tiedot.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Yhteyden muodostaminen ja tietolähteen luominen edellyttää säilön tai tallennustilin jotakin seuraavaa roolia:
   >  - Tallennustilan Blob-tietojen lukija
   >  - Tallennustilan Blob-tietojen omistaja
   >  - Tallennustilan Blob-tietojen osallistuja

1. Valitse **Common Data Model -kansion valitseminen** -valintaikkunassa model.json- tai manifest.json-tiedosto, josta tietoja tuodaan, ja valitse sitten **Seuraava**.
   > [!NOTE]
   > Toiseen ympäristön tietolähteeseen liitetyt model.json- tai manifest.json-tiedostot eivät näy luettelossa.

1. Valitussa model.json- tai manifest.json-tiedostossa näkyy luettelo käytettävissä olevista entiteeteistä. Katso ja valitse saatavilla olevien entiteettien luettelosta ja valitse sitten **Tallenna**. Kaikki valitut entiteetit käsitellään uudesta tietolähteestä.
   > [!div class="mx-imgBorder"]
   > ![Valintaikkuna, jossa on model.json-tiedostosta saatu entiteettiluettelo.](media/review-entities.png)

8. Määritä, mihin tietoyksikköihin tietojen profilointi otetaan käyttöön, ja valitse **Tallenna**. Tietojen profilointi mahdollistaa analytiikan ja muut ominaisuudet. Voit valita koko entiteetin, jolloin kaikki entiteetin määritteet valitaan, tai valita tietyt valitut määritteet. Tietojen profilointi ei ole oletusarvoisesti otettu käyttöön missään entiteetissä.
   > [!div class="mx-imgBorder"]
   > ![Valintaikkuna, jossa näkyy tietojen profilointi.](media/dataprofiling-entities.png)

9. Kun olet tallentanut valinnat, näkyviin tulee **Tietolähteet**-sivu. Sinun pitäisi nyt nähdä Common Data Model -kansion yhteys tietolähteenä.

> [!NOTE]
> Model.json- tai manifest.json-tiedosto voidaan liittää vain yhteen tietolähteeseen samassa ympäristössä. Samaa model.json- tai manifest.json-tiedostoa voi kuitenkin käyttää tietolähteissä useissa ympäristöissä.

## <a name="edit-a-common-data-model-folder-data-source"></a>Common Data Model -kansion tietolähteen muokkaaminen

Voit päivittää Common Data Model -kansion sisältävän tallennustilin käyttöoikeusavaimen. Voit myös muuttaa model.json- tai manifest.json-tiedostoa. Jos haluat muodostaa yhteyden toiseen säilöön tallennustilatililtä tai muuttaa tilin nimeä, sinun on [luotava uusi tietolähdeyhteys](#connect-to-a-common-data-model-folder).

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.

2. Valitse päivitettävän tietolähteen vieressä kolme pistettä.

3. Valitse luettelossa **Muokkaa**-vaihtoehto.

4. Valinnaisesti voit päivittää **käyttöoikeusavaimen** ja valita **Seuraava**.

   ![Valintaikkuna aiemmin luodun tietolähteen käyttöoikeusavaimen muokkaamiseen ja päivittämiseen.](media/edit-access-key.png)

5. Voit myös tehdä päivityksen käyttöoikeusavaimen yhteydessä resurssi- tai tilausperusteiseen yhteyteen. Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md). **Säilö**-tietoja ei voi muuttaa yhteyttä päivitettäessä.
   > [!div class="mx-imgBorder"]

   > ![Valintaikkuna, jossa annetaan Azure Data Laken yhteystiedot olemassa olevaan tallennustiliin.](media/enter-existing-storage-details.png)

   > [!NOTE]
   > Yhteyden muodostaminen ja tietolähteen luominen edellyttää säilön tai tallennustilin jotakin seuraavaa roolia:
   >  - Tallennustilan Blob-tietojen lukija
   >  - Tallennustilan Blob-tietojen omistaja
   >  - Tallennustilan Blob-tietojen osallistuja


6. Voit vaihtoehtoisesti valita toisen model.json- tai manifest.json-tiedoston, jolla on eri entiteettijoukko säilössä.

7. Voit myös valita lisää käsiteltäviä entiteettejä. Voit myös poistaa kaikki jo valitut entiteetit, jos riippuvuuksia ei ole.

   > [!IMPORTANT]
   > Jos aiemmin luodussa model.json- tai manifest.json-tiedostossa ja entiteettijoukkossa on riippuvuuksia, näkyviin tulee virhesanoma, eikä toista model.json- tai manifest.json-tiedostoa voi valita. Poista nämä riippuvuudet, ennen kuin muutat model.json- tai manifest.json-tiedostoa, tai luo uusi tietolähde sillä model.json- tai manifest.json-tiedostolla, jota haluat käyttää. Tällöin riippuvuuksia ei tarvitse poistaa.

8. Voit myös valita lisää määritteitä tai entiteettejä, jossa tietojen profilointi otetaan käyttöön tai poistaa jo valitut käytöstä.   


[!INCLUDE[footer-include](../includes/footer-banner.md)]
