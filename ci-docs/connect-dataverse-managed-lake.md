---
title: Yhdistä Microsoft Dataversen taulukoihin
description: Tietojen tuominen Microsoft Dataversen hallitusta Data Lake -tallennustilasta.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: c470956b0453ac2558ed85acdeebba120a0ca55d
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011699"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Yhteyden muodostaminen hallinnoidun Microsoft Dataverse Data Lake -tallennustilan tietoihin

Microsoft Dataverse -käyttäjät voivat muodostaa nopeasti yhteyden Microsoft Dataversen hallitun Data Lake -tallennustilan analyysientiteetteihin.

> [!NOTE]
> Sinun täytyy olla Dataverse-organisaation järjestelmänvalvoja, jotta voit jatkaa ja tarkastella hallitussa data lakessa käytettävissä olevien entiteettien luetteloa.

## <a name="important-considerations"></a>Tärkeitä huomioon otettavia seikkoja

1. Verkkopalveluihin, kuten Azure Data Lake Storageen, tallennetut tiedot voivat tallennettuina eri sijainnissa kuin missä tietoja käsitellään tai tallennetaan Dynamics 365 Customer Insightsissa. Tuomalla verkkopalveluun tallennetut tiedot tai muodostamalla niihin yhteyden hyväksyt, että tiedot voidaan siirtää ja tallentaa yhdessä Dynamics 365 Customer Insightsin kanssa.  [Lisätietoja on Microsoftin luottamuskeskuksessa](https://www.microsoft.com/trust-center).
2. Vain Dataverse-entiteetit, joissa [muutosten seuranta](/power-platform/admin/enable-change-tracking-control-data-synchronization) on otettu käyttöön, ovat näkyvissä. Nämä entiteetit voidaan viedä Dataverse-hallittuun Data Lake -tallennustilaan, ja niitä voidaan käyttää Customer Insightsissa. Käyttövalmiissa Dataverse-taulukoissa muutosten seuranta on oletusarvoisesti käytössä. Ota muutosten seuranta käyttöön mukautetuissa taulukoissa. Jos haluat tarkistaa, onko Dataverse-taulukossa otettu käyttöön muutosten seuranta, siirry kohtaan [Power Apps](https://make.powerapps.com) > **Tiedot** > **Taulukot**. Etsi kiinnostava taulukko ja valitse se. Valitse **Asetukset** > **Lisäasetukset** ja tarkista **Muutosten seuranta** asetus.

## <a name="connect-to-a-dataverse-managed-lake"></a>Yhteyden muodostaminen Dataversen hallittuun tallennustilaan

1. Valitse **Tiedot** > **Tietolähteet**.

1. Valitse **Lisää tietolähde**.

1. Valitse **Microsoft Dataverse**.

1. Anna tietolähteelle **nimi** ja valinnainen **kuvaus**

1. Anna Dataverse-organisaation **palvelinosoite** ja valitse **Kirjaudu sisään**.

1. Valitse käytettävissä olevasta luettelosta taulukot, joiden entiteettejä haluat käsitellä Customer Insightsiin.

   > [!NOTE]
   > Jos jotkin taulukot on jo valittu, muut Dynamics 365 -sovellukset (kuten Dynamics 365 Sales Insights tai Customer Service Insights) saattavat käyttää niitä. Tätä valintaa ei voi muuttaa. Nämä taulukot ovat käytettävissä entiteetteinä, kun tietolähde on luotu.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Valintaikkuna, jossa näkyy luettelo Dataverse-ympäristön entiteeteistä.":::

1. Tallenna valinta, jos haluat aloittaa valittujen taulukoiden synkronoinnin Dataversesta. Löydät juuri lisätyn yhteyden **Tietolähteet**-sivulta. Se laitetaan jonoon päivitystä varten ja se näyttää entiteetin määränä 0, kunnes kaikki valitut taulukot on synkronoitu.

Vain yksi ympäristön tietolähde voi käyttää samanaikaisesti samaa Dataversen hallittua Data Lake -tallennustilaa.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataversen hallitun tallennustilan tietolähteen muokkaaminen

Entiteetin valintaa voi muokata vasta tietolähteen luomisen jälkeen. Esimerkiksi silloin, jos lisäentiteettejä lisättiin Dataverseen ja haluat tuoda myös ne.
Jos haluat muodostaa yhteyden toiseen Dataverse-tietojärveen, [luo uusi tietolähde](#connect-to-a-dataverse-managed-lake).

1. Valitse **Tiedot** > **Tietolähteet**.

1. Valitse päivitettävän tietolähteen vieressä **Muokkaa**.

1. Valitse lisäentiteetit käytettävissä olevien entiteettien luettelosta ja valitse **Tallenna**.
