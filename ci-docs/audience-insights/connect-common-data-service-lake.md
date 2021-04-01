---
title: Common Data Servicen hallittujen Data Lake -tallennustilan entiteetteihin yhdistäminen
description: Tietojen tuominen Common Data Servicen hallitusta Data Lake -tallennustilasta.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596955"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Yhteyden muodostaminen hallinnoidun Common Data Service Data Lake -tallennustilan tietoihin

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Tässä artikkelissa on tietoja siitä, miten nykyiset Dynamics 365 -asiakkaat voivat yhdistää nopeasti analytiikkaentiteetit Common Data Servicen hallitussa Data Lake -tallennustilassa. Vain Common Data Service -organisaation järjestelmänvalvojat voivat jatkaa tarkastelemaan hallitussa Data Lake -tallennustilassa käytettävissä olevia entiteettejä.

## <a name="important-considerations"></a>Tärkeitä huomioon otettavia seikkoja

Verkkopalveluihin, kuten Azure Data Lake Storageen, tallennetut tiedot voivat tallennettuina eri sijainnissa kuin missä tietoja käsitellään tai tallennetaan Dynamics 365 Customer Insightsissa. Tuomalla verkkopalveluun tallennetut tiedot tai muodostamalla niihin yhteyden hyväksyt, että tiedot voidaan siirtää ja tallentaa yhdessä Dynamics 365 Customer Insightsin kanssa.  [Lisätietoja on Microsoftin luottamuskeskuksessa.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Yhteyden muodostaminen Common Data Servicen hallittuun tallennustilaan

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.

2. Valitse **Lisää tietolähde**.

3. Valitse **Yhdistä Common Data Serviceeen** ja sitten **Seuraava**.

4. Anna tietolähteen **nimi** ja valitse **Seuraava**. Nimen ohjeet: 
   - Alussa on oltava kirjain.
   - Käytä vain kirjaimia ja numeroita. Erikoismerkit ja välilyönnit eivät ole sallittuja.
   - Käytä 3–64 merkkiä.

5. Anna Common Data Service -organisaatiosi **Palvelinosoite** ja valitse **Kirjaudu sisään**.

   > [!div class="mx-imgBorder"]
   > ![Valintaruutu Common Data Servicen palvelinosoitteen syöttämiselle](media/enter-CDS-org-details.png)

6. Valitse luettelosta käytettävä entiteetti.    

   > [!NOTE]
   > Jos joitakin entiteettejä on jo valittuna, muut Dynamics 365- sovellukset (kuten Dynamics 365 Sales Insights tai Customer Service Insights) saattavat käyttää niitä. Tätä valintaa ei voi muuttaa. Nämä kohteet ovat käytettävissä, kun tietolähde on luotu.

   > [!div class="mx-imgBorder"]
   > ![Valintaikkuna, jossa näkyy Common Data Service -organisaation entiteettiluettelo](media/select-analytical-entities.png)

7. Tallenna valintasi, jos haluat aloittaa valittujen entiteettien synkronoinnin Common Data Servicen hallittuun tallennustilaan. Löydät juuri lisätyn yhteyden **Tietolähteet**-sivulta. Se asetetaan päivitysjonoon, ja entiteettimääränä näkyy 0, kunnes kaikki entiteetit on synkronoitu.

Vain yksi ympäristön tietolähde voi käyttää samanaikaisesti samaa Common Data Servicen hallittua Data Lake -tallennustilaa.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Common Data Servicen hallitun tallennustilan tietolähteen muokkaaminen

Entiteetin valintaa voi muokata vasta tietolähteen luomisen jälkeen. Esimerkiksi silloin, jos lisäentiteettejä lisättiin Common Data Serviceen ja haluat tuoda myös ne.    
Jos haluat muodostaa yhteyden eri Common Data Serviceen, [luo uusi tietolähde](#connect-to-a-common-data-service-managed-lake).

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Tietolähteet**.

2. Valitse päivitettävän tietolähteen vieressä kolme pistettä.

3. Valitse luettelossa **Muokkaa**-vaihtoehto.

4. Valitse lisäentiteetit käytettävissä olevien entiteettien luettelosta ja valitse **Tallenna**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]