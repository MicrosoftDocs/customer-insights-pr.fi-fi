---
title: Yhteyden muodostaminen Azure Data Lake Storage Gen2 -tiliin palveluobjektia käyttämällä
description: Käyttäjäryhmän merkityksellisten tietojen Azure-palveluobjektin käyttäminen muodostamaan yhteys omaan Data Lake -tallennustilaan, kun se liitetään käyttäjäryhmän merkityksellisiin tietoihin.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644084"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Yhteyden muodostaminen Azure Data Lake Storage Gen2 -tiliin käyttäjäryhmän merkityksellisten tietojen Azure-palveluobjektilla

Azure-palveluja käyttävillä automaattisilla työkaluilla on oltava aina rajoitetut käyttöoikeudet. Sen sijaan että sovellukset kirjautusivat sisään käyttäjänä, jolla on kaikki oikeudet, Azure antaa mahdollisuuden käyttää palveluobjekteja. Aiheessa käsitellään käyttäjäryhmän merkityksellisten tietojen yhdistämisestä Azure Data Lake Storage Gen2 -tiliin käyttämällä Azure-palveluobjektia eikä tallennustilan tiliavaimia. 

Palveluobjektin avulla voi turvallisesti [lisätä Common Data Model -kansion tietolähteenä tai muokata sitä](connect-common-data-model.md) tai [luoda uuden ympäristön tai päivittää aiemmin luotua ympäristöä](manage-environments.md#create-an-environment-in-an-existing-organization).

Palveluobjektin luontiin tarvitaan Azure-tilauksen järjestelmänvalvojan oikeudet.

## <a name="create-azure-service-principal-for-audience-insights"></a>Käyttäjäryhmän merkityksellisten tietojen Azure-palveluobjektin luominen

Tarkista ennen uuden käyttäjäryhmän merkityksellisten tietojen palveluobjektin luontia, onko sellainen jo luotu organisaatioon.

### <a name="look-for-an-existing-service-principal"></a>Aiemmin luodun palveluobjektin etsiminen

1. Siirry [Azure-hallintaportaaliin](https://portal.azure.com) ja kirjaudu organisaatioon.

2. Valitse **Azure Active Directory** Azure-palveluissa.

3. Valitse **Hallinta**-kohdassa **Enterprise-sovellukset**.

4. Käytä hakusanana käyttäjäryhmän merkityksellisten tietojen ensimmäisen osapuolen sovellustunnusta `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` tai nimeä `Dynamics 365 AI for Customer Insights`.

5. Jos löydät vastaavan tietueen, käyttäjäryhmän merkityksellisillä tiedoilla on palveluobjekti. Sitä ei tarvitse luoda uudelleen.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Näyttökuva, jossa on aiemmin luotu palveluobjekti":::
   
6. Jos tuloksia ei ole, luo uusi palveluobjekti.

### <a name="create-a-new-service-principal"></a>Uuden palveluobjektin luominen

1. Asenna uusin **Azure Active Directory PowerShell for Graph** -versio. Lisätietoja on kohdassa [Azure Active Directory PowerShell for Graphin asentaminen](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).
   - Valitse tietokoneessa näppäimistön Windows-avain, tee haku hakusanalla **Windows PowerShell** ja **suorita järjestelmänvalvojana**.
   
   - Anna avautuvassa PowerShell-ikkunassa `Install-Module AzureAD`.

2. Luo käyttäjäryhmän merkityksellisten tietojen palveluobjekti Azure AD PowerShell -moduulissa.
   - Anna PowerShell-ikkunassa `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Vaihda vuokraajan tunnuksen paikkamerkin paikalle sen vuokraajan tunnus, jossa haluat luoda palveluobjektin. Ympäristön nimiparametri `AzureEnvironmentName` on valinnainen.
  
   - Anna `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Tämä komento luo käyttäjäryhmän merkityksellisten tietojen palveluobjektin valitussa vuokraajassa.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Tallennustilin käyttöön tarvittavien oikeuksien myöntäminen palveluobjektille

Siirry Azure-portaaliin myöntämään palveluobjektille sen tallennustilin oikeudet, jota haluat käyttää käyttäjäryhmän merkityksellisissä tiedoissa.

1. Siirry [Azure-hallintaportaaliin](https://portal.azure.com) ja kirjaudu organisaatioon.

1. Avaa se tallennustili, jota haluat käyttäjäryhmän merkityksellisten tietojen palveluobjektin voivan käyttää.

1. Valitse siirtymisruudussa **Käyttöoikeuksien hallinta (IAM)** ja valitse sitten **Lisää** > **Lisää roolimääritys**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Näyttökuvassa Azure-portaali roolimääritystä lisättäessä":::
   
1. Määritä seuraavat ominaisuudet **Lisää roolimääritys** -ruudussa:
   - Rooli: *Tallennustilan BLOB-tietojen osallistuja*
   - Käyttöoikeuden delegointi: *Käyttäjä, ryhmä tai palveluobjekti*
   - Valitse: *Dynamics 365 AI for Customer Insights* ([luotu palveluobjekti](#create-a-new-service-principal))

1.  Valitse **Tallenna**.

Muutosten päivittyminen voi kestää 15 minuuttia.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Anna Azure-resurssitunnus tai Azure-tilauksen tiedot käyttäjäryhmän merkityksellisten tietojen tallennustililiitteessä.

Liitä käyttäjäryhmän merkityksellisten tietojen Azure Data Lake -tallennustili [säilön tulostetietoihin](manage-environments.md) tai [käytä sitä tietolähteenä](connect-common-data-service-lake.md). Azure Data Lake -vaihtoehdon valinta antaa mahdollisuuden valita, käytetäänkö resurssi- tai tilauspohjaista menettelytapaa.

Anna valitussa menettelytavassa tarvittavat tiedot seuraavien ohjeiden mukaisesti.

### <a name="resounce-based-storage-account-connection"></a>Resurssipohjainen tallennustiliyhteys

1. Siirry [Azure-hallintaportaaliin](https://portal.azure.com), kirjaudu tilaukseen ja avaa tallennustili.

1. Valitse siirtymisruudussa **Asetukset** > **Ominaisuudet**.

1. Kopioi tallennustilin resurssitunnuksen arvo.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Tallennustilin resurssitunnuksen arvon kopiointi":::

1. Lisää käyttäjäryhmän merkityksellisissä tiedoissa resurssitunnus resurssikenttään, joka näkyy tallennustilin yhteysnäytössä.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Tallennustilin resurssitunnuksen tietojen antaminen":::   
   
1. Liitä tallennustili suorittamalla jäljellä olevat vaiheet käyttäjäryhmän merkityksellisissä tiedoissa.

### <a name="subscription-based-storage-account-connection"></a>Tilauspohjainen tallennustiliyhteys

1. Siirry [Azure-hallintaportaaliin](https://portal.azure.com), kirjaudu tilaukseen ja avaa tallennustili.

1. Valitse siirtymisruudussa **Asetukset** > **Ominaisuudet**.

1. Varmista, että valitset oikeat tiedot käyttäjäryhmän merkityksellisissä tiedoissa tarkista tallennustilin **Tilaus**-, **Resurssiryhmä**- ja **Nimi**-kohtien tiedot.

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa arvot tai vastaavat kentät tallennustiliä liitettäessä.

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Tallennustilin resurssitunnuksen tietojen antaminen":::
   
1. Liitä tallennustili suorittamalla jäljellä olevat vaiheet käyttäjäryhmän merkityksellisissä tiedoissa.
