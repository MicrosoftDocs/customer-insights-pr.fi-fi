---
title: Yhdistä Microsoft Dataversen taulukoihin
description: Tietojen tuominen Microsoft Dataversen hallitusta Data Lake -tallennustilasta.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: f92d64723e6a4d2fcebdbb3758519d4bfd4aeaf4
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692570"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Yhteyden muodostaminen hallinnoidun Microsoft Dataverse Data Lake -tallennustilan tietoihin

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Tässä artikkelissa on tietoa siitä, miten Dataverse-käyttäjät voivat nopeasti muodostaa yhteyden analyyttisiin kokonaisuuksiinsa Dataversen hallitsemassa järvessä. Vain Dataverse -organisaation järjestelmänvalvojat voivat jatkaa tarkastelemaan hallitussa Data Lake -tallennustilassa käytettävissä olevia entiteettejä.

## <a name="important-considerations"></a>Tärkeitä huomioon otettavia seikkoja

Verkkopalveluihin, kuten Azure Data Lake Storageen, tallennetut tiedot voivat tallennettuina eri sijainnissa kuin missä tietoja käsitellään tai tallennetaan Dynamics 365 Customer Insightsissa. Tuomalla verkkopalveluun tallennetut tiedot tai muodostamalla niihin yhteyden hyväksyt, että tiedot voidaan siirtää ja tallentaa yhdessä Dynamics 365 Customer Insightsin kanssa.  [Lisätietoja on Microsoftin luottamuskeskuksessa.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Yhteyden muodostaminen Dataversen hallittuun tallennustilaan

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.

2. Valitse **Lisää tietolähde**.

3. Valitse **Yhdistä Microsoft Dataversen hallitsemaan järveen** ja valitse **Seuraava** .

4. Anna tietolähteen **nimi** ja valitse **Seuraava**. Nimen ohjeet: 
   - Alussa on oltava kirjain.
   - Käytä vain kirjaimia ja numeroita. Erikoismerkit ja välilyönnit eivät ole sallittuja.
   - Käytä 3–64 merkkiä.

5. Anna Dataverse-organisaation **palvelinosoite** ja valitse **Kirjaudu sisään**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Näyttö tietojenkäsittelyvaiheessa, jossa käyttäjä voi syöttää Dataverse-ympäristön URL-osoitteen.":::

6. Valitse käytettävissä olevasta luettelosta taulukot, jotka haluat lisätä entiteetteinä kävijätilastoihin.    

   > [!NOTE]
   > Jos jotkin taulukot on jo valittu, muut Dynamics 365 -sovellukset (kuten Dynamics 365 Sales Insights tai Customer Service Insights) saattavat käyttää niitä. Tätä valintaa ei voi muuttaa. Nämä taulukot ovat käytettävissä entiteetteinä, kun tietolähde on luotu.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Valintaikkuna, jossa näkyy luettelo Dataverse-ympäristön entiteeteistä.":::

7. Tallenna valinta, jos haluat aloittaa valittujen taulukoiden synkronoinnin Dataversesta. Löydät juuri lisätyn yhteyden **Tietolähteet**-sivulta. Se laitetaan jonoon päivitystä varten ja se näyttää entiteetin määränä 0, kunnes kaikki valitut taulukot on synkronoitu.

Vain yksi ympäristön tietolähde voi käyttää samanaikaisesti samaa Dataversen hallittua Data Lake -tallennustilaa.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataversen hallitun tallennustilan tietolähteen muokkaaminen

Entiteetin valintaa voi muokata vasta tietolähteen luomisen jälkeen. Esimerkiksi silloin, jos lisäentiteettejä lisättiin Dataverseen ja haluat tuoda myös ne.    
Jos haluat muodostaa yhteyden toiseen Dataverse-tietojärveen, [luo uusi tietolähde](#connect-to-a-dataverse-managed-lake).

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.

2. Valitse päivitettävän tietolähteen vieressä kolme pistettä.

3. Valitse luettelossa **Muokkaa**-vaihtoehto.

4. Valitse lisäentiteetit käytettävissä olevien entiteettien luettelosta ja valitse **Tallenna**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]