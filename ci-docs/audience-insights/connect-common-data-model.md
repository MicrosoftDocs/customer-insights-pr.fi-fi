---
title: Common Data Model -tietojen yhdistäminen Azure Data Lake -tiliin
description: Common Data Model -tietojen käyttäminen Azure Data Lake Storagen avulla.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643454"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Common Data Model -kansioon yhdistäminen Azure Data Lake -tilillä

Tässä artikkelissa on tietoja Common Data Model -kansion tietojen käsittelemisestä Azure Data Lake Storage Gen2 -tilin avulla.

## <a name="important-considerations"></a>Tärkeitä huomioon otettavia seikkoja

- Azure Data Lake -tallennustilassa olevien tietojen muodon on oltava Common Data Model -standardin mukaisia. Muita muotoja ei tueta tällä hetkellä.

- Tietojen käsittely tukee ainoastaan Azure Data Lake *Gen2* -tallennustilejä. Azure Data Lake Gen1 -tallennustilejä ei voi käyttää tietojen käsittelyyn.

- Azure-palveluobjektin käyttäminen todentaminen edellyttää, että se on määritetty vuokraajassa. Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md).

- Azure Data Lake -tallennustilan, joka halutaan yhdistää ja jonka tietoja halutaan käsitellä, on oltava samalla Azure-alueella kuin Dynamics 365 Customer Insights -ympäristö. Yhteyksiä Common Data Model -kansioon toisen Azure-alueen Data Lake -tallennustilasta ei tueta. Ympäristön Azure-alueen voi tarkistaa valitsemalla käyttäjäryhmän merkityksellisissä tiedoissa **Hallinta** > **Järjestelmä** > **Tietoja**.

- Online-palveluihin tallennetut tiedot voivat olla tallennettu eri sijaintiin kuin missä tietoja käsitellään ja mihin ne tallennetaan Dynamics 365 Customer Insightsissa. Tuomalla verkkopalveluun tallennetut tiedot tai muodostamalla niihin yhteyden hyväksyt, että tiedot voidaan siirtää ja tallentaa yhdessä Dynamics 365 Customer Insightsin kanssa.  [Lisätietoja on Microsoftin luottamuskeskuksessa.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Muodosta yhteys Common Data Model -kansioon

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.

1. Valitse **Lisää tietolähde**.

1. Valitse **Muodosta yhteys Common Data Model -kansioon**, anna tietolähteelle **Nimi** ja valitse **Seuraava**.

1. Voit valita, käytetäänkö todennukseen resurssi- vai tilausperusteista vaihtoehtoa. Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md). Anna **säilön** tiedot ja valitse **Seuraava**.
   > [!div class="mx-imgBorder"]
   > ![Valintaikkuna Azure Data Laken yhteystietojen antamiseen](media/enter-new-storage-details.png)

1. Valitse **Common Data Model -kansion valitseminen** -valintaikkunassa model.json-tiedosto, josta tietoja tuodaan, ja valitse sitten **Seuraava**.
   > [!NOTE]
   > Toiseen ympäristön tietolähteeseen liitetyt model.json-tiedostot eivät näy luettelossa.

1. Näkyviin tulee luettelo valitussa model.json-tiedoston käytettävissä olevista entiteeteistä. Voit tarkistaa sen ja valita käytettävissä olevien entiteettien luettelosta. Valitse sitten **Tallenna**. Kaikki valitut entiteetit käsitellään uudesta tietolähteestä.
   > [!div class="mx-imgBorder"]
   > ![Valintaikkuna, jossa on model.json-tiedostosta saatu entiteettiluettelo](media/review-entities.png)

8. Määritä, missä tietoyksikköihin tietojen profilointi halutaan ottaa käyttöön ja valitse **Tallenna**. Tietojen profilointi mahdollistaa analytiikan ja muut ominaisuudet. Voit valita koko entiteetin, jolloin kaikki entiteetin määritteet valitaan, tai valita tietyt valitut määritteet. Tietojen profilointi ei ole oletusarvoisesti otettu käyttöön missään entiteetissä.
   > [!div class="mx-imgBorder"]
   > ![Valintaikkuna, jossa näkyy tietojen profilointi](media/dataprofiling-entities.png)

9. Kun olet tallentanut valinnat, näkyviin tulee **Tietolähteet**-sivu. Sinun pitäisi nyt nähdä Common Data Model -kansion yhteys tietolähteenä.

> [!NOTE]
> Model.json-tiedosto voidaan liittää vain yhteen tietolähteeseen samassa ympäristössä. Samaa model.json-tiedostoa voi kuitenkin käyttää tietolähteissä useissa ympäristöissä.

## <a name="edit-a-common-data-model-folder-data-source"></a>Common Data Model -kansion tietolähteen muokkaaminen

Voit päivittää Common Data Model -kansion sisältävän tallennustilin käyttöoikeusavaimen. Voit myös vaihtaa model.json-tiedoston. Jos haluat muodostaa yhteyden toiseen säilöön tallennustilatililtä tai muuttaa tilin nimeä, sinun on [luotava uusi tietolähdeyhteys](#connect-to-a-common-data-model-folder).

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.

2. Valitse päivitettävän tietolähteen vieressä kolme pistettä.

3. Valitse luettelossa **Muokkaa**-vaihtoehto.

4. Valinnaisesti voit päivittää **käyttöoikeusavaimen** ja valita **Seuraava**.

   ![Valintaikkuna aiemmin luodun tietolähteen käyttöoikeusavaimen muokkaamiseen ja päivittämiseen](media/edit-access-key.png)

5. Voit myös tehdä päivityksen käyttöoikeusavaimen yhteydessä resurssi- tai tilausperusteiseen yhteyteen. Lisätietoja on kohdassa [Käyttäjäryhmän merkityksellisten tietojen yhdistäminen Azure Data Lake Storage Gen2 -tiliin Azure-palveluobjektilla](connect-service-principal.md). **Säilö**-tietoja ei voi muuttaa yhteyttä päivitettäessä.
   > [!div class="mx-imgBorder"]
   > ![Valintaikkuna Azure Data Laken yhteystietojen antamiseen](media/enter-existing-storage-details.png)

6. Valinnaisesti voit valita säilössä toisen model.json-tiedoston, jossa on erilainen entiteettijoukko.

7. Voit myös valita lisää käsiteltäviä entiteettejä. Voit myös poistaa kaikki jo valitut entiteetit, jos riippuvuuksia ei ole.

   > [!IMPORTANT]
   > Jos nykyisessä model.json-tiedostossa ja entiteettijoukossa on riippuvuuksia, näkyviin tulee virhesanoma eikä toista model.json-tiedostoa voi valita. Poista kyseiset riippuvuudet ennen model.json-tiedoston vaihtamista tai luo uusi tietolähde, joka sisältää haluamasi model.json-tiedoston, jolloin riippuvuuksia ei tarvitse poistaa.

8. Voit myös valita lisää määritteitä tai entiteettejä, jossa tietojen profilointi otetaan käyttöön tai poistaa jo valitut käytöstä.   
