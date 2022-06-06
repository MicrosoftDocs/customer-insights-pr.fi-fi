---
title: Yhdistä Microsoft Dataversen taulukoihin
description: Tietojen tuominen Microsoft Dataversen hallitusta Data Lake -tallennustilasta.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 7140e9254108bc6f0d518b3ccf4b10fc33cde115
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800166"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Yhteyden muodostaminen hallinnoidun Microsoft Dataverse Data Lake -tallennustilan tietoihin

Tässä artikkelissa on tietoja siitä, miten Dataverse-käyttäjät voivat muodostaa nopeasti yhteyden Microsoft Dataversen hallitun data laken analyysientiteetteihin. 

> [!NOTE]
> Sinun täytyy olla Dataverse-organisaation järjestelmänvalvoja, jotta voit jatkaa ja tarkastella hallitussa data lakessa käytettävissä olevien entiteettien luetteloa.

## <a name="important-considerations"></a>Tärkeitä huomioon otettavia seikkoja

1. Verkkopalveluihin, kuten Azure Data Lake Storageen, tallennetut tiedot voivat tallennettuina eri sijainnissa kuin missä tietoja käsitellään tai tallennetaan Dynamics 365 Customer Insightsissa. Tuomalla verkkopalveluun tallennetut tiedot tai muodostamalla niihin yhteyden hyväksyt, että tiedot voidaan siirtää ja tallentaa yhdessä Dynamics 365 Customer Insightsin kanssa.  [Lisätietoja on Microsoftin luottamuskeskuksessa](https://www.microsoft.com/trust-center).
2. Vain Dataverse-entiteetit, joissa [muutosten seuranta](/power-platform/admin/enable-change-tracking-control-data-synchronization) on otettu käyttöön, ovat näkyvissä. Nämä entiteetit voidaan viedä Dataverse-hallittuun Data Lake -tallennustilaan, ja niitä voidaan käyttää Customer Insightsissa. Käyttövalmiissa Dataverse-taulukoissa muutosten seuranta on oletusarvoisesti käytössä. Ota muutosten seuranta käyttöön mukautetuissa taulukoissa. Jos haluat tarkistaa, onko Dataverse-taulukossa otettu käyttöön muutosten seuranta, siirry kohtaan [Power Apps](https://make.powerapps.com) > **Tiedot** > **Taulukot**. Etsi kiinnostava taulukko ja valitse se. Valitse **Asetukset** > **Lisäasetukset** ja tarkista **Muutosten seuranta** asetus.

## <a name="connect-to-a-dataverse-managed-lake"></a>Yhteyden muodostaminen Dataversen hallittuun tallennustilaan

1. Valitse Customer Insightsissa **Tiedot** > **Tietolähteet**.

2. Valitse **Lisää tietolähde**.

3. Valitse **Microsoft Dataverse** ja valitse sitten **Seuraava**.

4. Anna tietolähteen **nimi** ja valitse **Seuraava**. 

5. Anna Dataverse-organisaation **palvelinosoite** ja valitse **Kirjaudu sisään**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Näyttö tietojenkäsittelyvaiheessa, jossa käyttäjä voi syöttää Dataverse-ympäristön URL-osoitteen.":::

6. Valitse käytettävissä olevasta luettelosta taulukot, joiden entiteettejä haluat käyttää Customer Insightsia varten.    

   > [!NOTE]
   > Jos jotkin taulukot on jo valittu, muut Dynamics 365 -sovellukset (kuten Dynamics 365 Sales Insights tai Customer Service Insights) saattavat käyttää niitä. Tätä valintaa ei voi muuttaa. Nämä taulukot ovat käytettävissä entiteetteinä, kun tietolähde on luotu.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Valintaikkuna, jossa näkyy luettelo Dataverse-ympäristön entiteeteistä.":::

7. Tallenna valinta, jos haluat aloittaa valittujen taulukoiden synkronoinnin Dataversesta. Löydät juuri lisätyn yhteyden **Tietolähteet**-sivulta. Se laitetaan jonoon päivitystä varten ja se näyttää entiteetin määränä 0, kunnes kaikki valitut taulukot on synkronoitu.

Vain yksi ympäristön tietolähde voi käyttää samanaikaisesti samaa Dataversen hallittua Data Lake -tallennustilaa.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataversen hallitun tallennustilan tietolähteen muokkaaminen

Entiteetin valintaa voi muokata vasta tietolähteen luomisen jälkeen. Esimerkiksi silloin, jos lisäentiteettejä lisättiin Dataverseen ja haluat tuoda myös ne.    
Jos haluat muodostaa yhteyden toiseen Dataverse-tietojärveen, [luo uusi tietolähde](#connect-to-a-dataverse-managed-lake).

1. Valitse **Tiedot** > **Tietolähteet**.

2. Valitse päivitettävän tietolähteen vieressä vertikaalinen kolme pistettä (&vellip;).

3. Valitse luettelossa **Muokkaa**-vaihtoehto.

4. Valitse lisäentiteetit käytettävissä olevien entiteettien luettelosta ja valitse **Tallenna**.

[!INCLUDE [footer-include](includes/footer-banner.md)]