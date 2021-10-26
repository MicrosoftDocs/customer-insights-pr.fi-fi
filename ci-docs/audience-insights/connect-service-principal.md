---
title: Yhteyden muodostaminen Azure Data Lake Storage -tiliin palvelun päätunnuksen avulla
description: Muodosta yhteys Data Lake -tallennustilaan Azure-palvelun päätoiminnon avulla.
ms.date: 09/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b901d799dbd73841a6ddbae754c4e4275f61146a
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645168"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Yhteyden muodostaminen Azure Data Lake Storage -tiliin Azure-palvelun päätunnuksen avulla

Azure-palveluja käyttävillä automaattisilla työkaluilla on oltava aina rajoitetut käyttöoikeudet. Sen sijaan että sovellukset kirjautusivat sisään käyttäjänä, jolla on kaikki oikeudet, Azure antaa mahdollisuuden käyttää palveluobjekteja. Lue lisää siitä, miten voit muodostaa yhteyden Dynamics 365 Customer Insights -tilin Azure Data Lake Storage -tiliin käyttämällä Azure-palvelun pääkäyttäjää tallennustilin avainten sijaan. 

Palvelun pääkansion avulla voit [lisätä tai muokata Common Data Model -kansiota tietolähteenä](connect-common-data-model.md) tai [luoda tai päivittää ympäristön](create-environment.md).

> [!IMPORTANT]
> - Palvelun päänimiä käyttävällä Data Lake Storage -tilillä on oltava [käytössä hierarkkinen nimitila](/azure/storage/blobs/data-lake-storage-namespace).
> - Palveluobjektin luontiin tarvitaan Azure-tilauksen järjestelmänvalvojan oikeudet.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Luo Azure-palvelun pääkäyttäjä Customer Insights -tietoja varten

Ennen kuin luot uuden palvelupääkäyttäjän kohdeyleisöä tai sitoutumistietoja varten, tarkista, onko se jo olemassa organisaatiossasi.

### <a name="look-for-an-existing-service-principal"></a>Aiemmin luodun palveluobjektin etsiminen

1. Siirry [Azure-hallintaportaaliin](https://portal.azure.com) ja kirjaudu organisaatioon.

2. Valitse **Azure-palvelut**-kohdassa **Azure Active Directory**.

3. Valitse **Hallinta**-kohdassa **Enterprise-sovellukset**.

4. Hae Microsoft-sovellustunnusta:
   - Käyttäjäryhmän merkitykselliset tiedot: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` nimellä `Dynamics 365 AI for Customer Insights`
   - Sitoutumistiedot: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` nimellä `Dynamics 365 AI for Customer Insights engagement insights`

5. Jos löydät vastaavan tietueen, palvelun pääkäyttäjä on jo olemassa. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Näyttökuva, jossa näkyy palvelun pääkäyttäjä.":::
   
6. Jos tuloksia ei ole, luo uusi palveluobjekti.

>[!NOTE]
>Jotta voit käyttää Dynamics 365 Customer Insightsia täydellä teholla, suosittelemme, että lisäät molemmat sovellukset palvelun pääkäyttäjään.

### <a name="create-a-new-service-principal"></a>Uuden palveluobjektin luominen

1. Asenna Azure Active Directory PowerShell for Graphin uusin versio. Lisätietoja on kohdassa [Asenna Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Valitse tietokoneessa näppäimistön Windows-avain, hae **Windows PowerShell** ja valitse **Suorita Järjestelmänvalvojana**.
   
   1. Anna avautuvassa PowerShell-ikkunassa `Install-Module AzureAD`.

2. Luo Customer Insights -palvelun pääkäyttäjä Azure AD PowerShell -moduulilla.

   1. Anna PowerShell-ikkunassa `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Vaihda *[vuokraajan tunnuksen]* paikkamerkin paikalle sen vuokraajan tunnus, jossa haluat luoda palveluobjektin. Ympäristön nimiparametri `AzureEnvironmentName` on valinnainen.
  
   1. Anna `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Tämä komento luo käyttäjäryhmän merkityksellisten tietojen palveluobjektin valitussa vuokraajassa. 

   1. Anna `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Tämä komento luo palvelun pääkäyttäjälle sitoutumistietoja varten valitulle vuokraajalle.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Tallennustilin käyttöön tarvittavien oikeuksien myöntäminen palveluobjektille

Siirry Azure-portaaliin myöntämään palveluobjektille sen tallennustilin oikeudet, jota haluat käyttää käyttäjäryhmän merkityksellisissä tiedoissa.

1. Siirry [Azure-hallintaportaaliin](https://portal.azure.com) ja kirjaudu organisaatioon.

1. Avaa se tallennustili, jota haluat käyttäjäryhmän merkityksellisten tietojen palveluobjektin voivan käyttää.

1. Valitse vasemmanpuoleisesta ruudusta **Käytönvalvonta (IAM)** ja valitse sitten **Lisää** > **Lisää roolimääritys**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Näyttökuva, jossa näkyy Azure-portaali, kun lisätään roolimääritystä.":::

1. Määritä **Lisää roolien määritys** -ruudussa seuraavat ominaisuudet:
   - Rooli: **Tallennustilan BLOB-tietojen osallistuja**
   - Käyttöoikeuden delegointi: **Käyttäjä, ryhmä tai palveluobjekti**
   - Valitse: **Dynamics 365 AI for Customer Insights** ja **Dynamics 365 AI for Customer Insights -sitoutumistiedot** (kaksi aiemmin tässä toimintosarjassa luomaa [palvelun pääkäyttäjää](#create-a-new-service-principal))

1.  Valitse **Tallenna**.

Muutosten päivittyminen voi kestää 15 minuuttia.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Anna Azure-resurssitunnus tai Azure-tilauksen tiedot käyttäjäryhmän merkityksellisten tietojen tallennustililiitteessä

Voit liittää Data Lake -tallennustilan kohdeyleisötietoihin, jotta voit [tallentaa tulostietoja](manage-environments.md) tai [käyttää niitä tietolähteenä](connect-common-data-service-lake.md). Tämän vaihtoehdon avulla voit valita resurssipohjaisen tai tilauspohjaisen vaihtoehdon. Noudata valitsemasi toimintatavan mukaisesti jossakin seuraavista osasta annettuja ohjeita.

### <a name="resource-based-storage-account-connection"></a>Resurssipohjainen tallennustiliyhteys

1. Siirry [Azure-hallintaportaaliin](https://portal.azure.com), kirjaudu tilaukseen ja avaa tallennustili.

1. Valitse vasemmanpuoleisessa ruudussa **Asetukset** > **Ominaisuudet**.

1. Kopioi tallennustilin resurssitunnuksen arvo.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Tallennustilin resurssitunnuksen arvon kopiointi":::

1. Lisää käyttäjäryhmän resurssitunnus tallennustilin yhteysnäytössä näkyvään resurssikenttään.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Tallennustilin resurssitunnuksen tietojen antaminen":::   

1. Liitä tallennustili suorittamalla jäljellä olevat vaiheet käyttäjäryhmän merkityksellisissä tiedoissa.

### <a name="subscription-based-storage-account-connection"></a>Tilauspohjainen tallennustiliyhteys

1. Siirry [Azure-hallintaportaaliin](https://portal.azure.com), kirjaudu tilaukseen ja avaa tallennustili.

1. Valitse vasemmanpuoleisessa ruudussa **Asetukset** > **Ominaisuudet**.

1. Varmista, että valitset oikeat tiedot käyttäjäryhmän merkityksellisissä tiedoissa tarkista tallennustilin **Tilaus**-, **Resurssiryhmä**- ja **Nimi**-kohtien tiedot.

1. Valitse käyttäjäryhmän tiedoissa vastaavien kenttien arvot, kun liität tallennustilin.

1. Liitä tallennustili suorittamalla jäljellä olevat vaiheet käyttäjäryhmän merkityksellisissä tiedoissa.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
