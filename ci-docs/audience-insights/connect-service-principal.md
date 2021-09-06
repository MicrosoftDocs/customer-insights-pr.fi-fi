---
title: Yhteyden muodostaminen Azure Data Lake Storage -tiliin palvelun päätunnuksen avulla
description: Muodosta yhteys Data Lake -tallennustilaan Azure-palvelun päätoiminnon avulla.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461144"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Yhteyden muodostaminen Azure Data Lake Storage -tiliin Azure-palvelun päätunnuksen avulla
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Azure-palveluja käyttävillä automaattisilla työkaluilla on oltava aina rajoitetut käyttöoikeudet. Sen sijaan että sovellukset kirjautusivat sisään käyttäjänä, jolla on kaikki oikeudet, Azure antaa mahdollisuuden käyttää palveluobjekteja. Lue lisää siitä, miten voit muodostaa yhteyden Dynamics 365 Customer Insights -tilin Azure Data Lake Storage -tiliin käyttämällä Azure-palvelun pääkäyttäjää tallennustilin avainten sijaan. 

Palvelun pääkansion avulla voit [lisätä tai muokata Common Data Model -kansiota tietolähteenä](connect-common-data-model.md) tai [luoda tai päivittää ympäristön](get-started-paid.md).<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - Data Lake Storage -tallennustila, joka käyttää<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> palvelun pääkäyttäjää, on [oltava käytössä hierarkkinen nimitila](/azure/storage/blobs/data-lake-storage-namespace).
> - Palveluobjektin luontiin tarvitaan Azure-tilauksen järjestelmänvalvojan oikeudet.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Luo Azure-palvelun pääkäyttäjä Customer Insights -tietoja varten

Ennen kuin luot uuden palvelupääkäyttäjän kohdeyleisöä tai sitoutumistietoja varten, tarkista, onko se jo olemassa organisaatiossasi.

### <a name="look-for-an-existing-service-principal"></a>Aiemmin luodun palveluobjektin etsiminen

1. Siirry [Azure-hallintaportaaliin](https://portal.azure.com) ja kirjaudu organisaatioon.

2. Valitse **Azure-palvelut**-kohdassa **Azure Active Directory**.

3. Valitse **Hallinta**-kohdassa **Enterprise-sovellukset**.

4. Etsi Microsoft<!--note from editor: Via Microsoft Writing Style Guide.--> -sovellustunnus:
   - Käyttäjäryhmän merkitykselliset tiedot: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` nimellä `Dynamics 365 AI for Customer Insights`
   - Sitoutumistiedot: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` nimellä `Dynamics 365 AI for Customer Insights engagement insights`

5. Jos löydät vastaavan tietueen, palvelun pääkäyttäjä on jo olemassa. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Näyttökuva, jossa näkyy palvelun pääkäyttäjä.":::
   
6. Jos tuloksia ei ole, luo uusi palveluobjekti.

>[!NOTE]
>Jotta voit käyttää Dynamics 365 Customer Insightsia täydellä teholla, suosittelemme, että lisäät molemmat sovellukset palvelun pääkäyttäjään.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Uuden palveluobjektin luominen
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Asenna Azure Active Directory PowerShell for Graphin uusin versio. Lisätietoja on kohdassa [Asenna Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Valitse tietokoneessa näppäimistön Windows-avain, hae **Windows PowerShell** ja valitse **Suorita Järjestelmänvalvojana**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. Anna avautuvassa PowerShell-ikkunassa `Install-Module AzureAD`.

2. Luo Customer Insights -palvelun pääkäyttäjä Azure AD PowerShell -moduulilla.

   1. Anna PowerShell-ikkunassa `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Korvaa *"[vuokraajatunnuksesi]"*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> sen vuokraajan todellisella tunnuksella, johon haluat luoda palvelun päätunnuksen. Ympäristön nimiparametri `AzureEnvironmentName` on valinnainen.
  
   1. Anna `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Tämä komento luo käyttäjäryhmän merkityksellisten tietojen palveluobjektin valitussa vuokraajassa. 

   1. Anna `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Tämä komento luo palvelun pääkäyttäjälle sitoutumistietoja varten<!--note from editor: Edit okay?--> valittuun vuokraajaan.

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

Voit<!--note from editor: Edit suggested only if this section is optional.--> liittää Data Lake -tallennustilan kohdeyleisötietoihin, jotta voit [tallentaa tulostietoja](manage-environments.md) tai [käyttää niitä tietolähteenä](connect-common-data-service-lake.md). Tämän vaihtoehdon avulla voit valita resurssipohjaisen tai tilauspohjaisen vaihtoehdon. Noudata valitsemasi toimintatavan mukaisesti jossakin seuraavista osasta annettuja ohjeita.<!--note from editor: Suggested.-->

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