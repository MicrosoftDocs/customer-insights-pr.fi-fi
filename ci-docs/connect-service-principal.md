---
title: Yhteyden muodostaminen Azure Data Lake Storage -tiliin Azure-palvelun päätunnuksen avulla
description: Muodosta yhteys Data Lake -tallennustilaan Azure-palvelun päätoiminnon avulla.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304193"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Yhteyden muodostaminen Azure Data Lake Storage -tiliin Azure-palvelun päätunnuksen avulla

Dynamics 365 Customer Insights tarjoaa mahdollisuuden yhdistää Azure Data Lake Storage -tiliin käyttämällä Azure-palvelun pääkäyttäjää tallennustilin avainten sijaan.

Azure-palveluja käyttävillä automaattisilla työkaluilla on oltava rajoitetut käyttöoikeudet. Sen sijaan että sovellukset kirjautusivat sisään käyttäjänä, jolla on kaikki oikeudet, Azure antaa mahdollisuuden käyttää palveluobjekteja. Palvelun päänimen avulla voit [lisätä tai muokata Common Data Model -kansiota tietolähteenä](connect-common-data-model.md) tai [luoda tai päivittää ympäristön](create-environment.md).

## <a name="prerequisites"></a>edellytykset

- Palvelun päänimeä käyttävän Data Lake Storage -tilin on oltava Gen2-versio. Azure Data Lake Gen1 -tallennustilejä ei tueta.
- Data Lake Storage -tilillä on [hierarkkisen nimitilan ominaisuus käytössä](/azure/storage/blobs/data-lake-storage-namespace).
- Azure-vuokraajaan järjestelmänvalvojan oikeudet, jos uusi palvelun pääkäyttäjä on luotava.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Luo Azure-palvelun pääkäyttäjä Customer Insights -tietoja varten

Ennen kuin luot uuden palvelun päänimen Customer Insightsille, tarkista, onko se jo organisaatiossasi. Useimmissa tapauksissa se on jo olemassa.

### <a name="look-for-an-existing-service-principal"></a>Aiemmin luodun palveluobjektin etsiminen

1. Siirry [Azure-hallintaportaaliin](https://portal.azure.com) ja kirjaudu organisaatioon.

2. Valitse **Azure-palvelut**-kohdassa **Azure Active Directory**.

3. Valitse **Hallinta**-kohdasta **Microsoft-sovellus**.

4. Lisää suodatin kohteelle **Sovellustunnuksen alku** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` tai etsi nimeä `Dynamics 365 AI for Customer Insights`.

5. Jos löydät vastaavan tietueen, palvelun pääkäyttäjä on jo olemassa. Tallennustilin käyttöön tarvittavien [oikeuksien myöntäminen](#grant-permissions-to-the-service-principal-to-access-the-storage-account) palveluobjektille.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Näyttökuva, jossa näkyy palvelun pääkäyttäjä.":::

6. Jos tuloksia ei ole, [luo uusi palveluobjekti](#create-a-new-service-principal).

### <a name="create-a-new-service-principal"></a>Uuden palveluobjektin luominen

1. Asenna Azure Active Directory PowerShell for Graphin uusin versio. Lisätietoja on kohdassa [Asenna Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Paina tietokoneessa näppäimistön Windows-näppäintä, hae **Windows PowerShell** ja valitse **Suorita järjestelmänvalvojana**.

   1. Anna avautuvassa PowerShell-ikkunassa `Install-Module AzureAD`.

2. Luo Customer Insights -palvelun pääkäyttäjä Azure AD PowerShell -moduulilla.

   1. Anna PowerShell-ikkunassa `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Korvaa *[hakemistotunnus]* Azure-tilauksesi todellisella hakemistotunnuksella, johon haluat luoda palvelun päätunnuksen. Ympäristön nimiparametri `AzureEnvironmentName` on valinnainen.
  
   1. Anna `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Tämä komento luo Customer Insights -palvelun pääasiakkaan valitulle Azure-tilaukselle.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Tallennustilin käyttöön tarvittavien oikeuksien myöntäminen palveluobjektille

Jotta voit myöntää käyttöoikeudet Customer Insightsissa käytettävän tallennustilatilin pääobjektille, jokin seuraavista rooleista on delegoitava tallennustilille tai säilölle:

|Tunnistetiedot|Edellytykset|
|----------|------------|
|Kirjautuneena oleva käyttäjä|**Rooli**: tallennuksen blob-tietojen lukija, tallennuksen blob-objektin osallistuja tai tallennuksen blob-objektin omistaja.<br>**Taso**: oikeudet myönnetään tallennustilille tai säilölle.</br>|
|Customer Insightsin palvelun päänimi –<br>Azure Data Lake Storagen käyttäminen tietolähteenä</br>|Asetus 1<ul><li>**Rooli**: tallennuksen blob-tietojen lukija, tallennuksen blob-tietojen osallistuja tai tallennuksen blob-tietojen omistaja.</li><li>**Taso**: oikeudet myönnetään tallennustilille.</li></ul>Vaihtoehto 2 *(palvelun päänimen käyttöoikeutta ei jaeta tallennustilille)*<ul><li>**Rooli 1**: tallennuksen blob-tietojen lukija, tallennuksen blob-tietojen osallistuja tai tallennuksen blob-tietojen omistaja.</li><li>**Taso**: oikeudet myönnetään säilölle.</li><li>**Rooli 2**: tallennuksen blob-tietojen delegoija.</li><li>**Taso**: oikeudet myönnetään tallennustilille.</li></ul>|
|Customer Insightsin palvelun päänimi – <br>Azure Data Lake Storagen käyttäminen tuloksena tai kohteena</br>|Asetus 1<ul><li>**Rooli**: tallennuksen blob-objektin osallistuja tai tallennuksen blob-objektin omistaja.</li><li>**Taso**: oikeudet myönnetään tallennustilille.</li></ul>Vaihtoehto 2 *(palvelun päänimen käyttöoikeutta ei jaeta tallennustilille)*<ul><li>**Rooli**: tallennuksen blob-objektin osallistuja tai tallennuksen blob-objektin omistaja.</li><li>**Taso**: oikeudet myönnetään säilölle.</li><li>**Rooli 2**: tallennuksen blob-objektin delegoija.</li><li>**Taso**: oikeudet myönnetään tallennustilille.</li></ul>|

1. Siirry [Azure-hallintaportaaliin](https://portal.azure.com) ja kirjaudu organisaatioon.

1. Avaa tallennustilatili, jonka käyttöoikeudet haluat Customer Insights -palvelun pääasiakkaan käyttöön.

1. Valitse vasemmanpuoleisesta ruudusta **Käytönvalvonta (IAM)** ja valitse sitten **Lisää** > **Lisää roolimääritys**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Näyttökuva, jossa näkyy Azure-portaali, kun lisätään roolimääritystä.":::

1. Määritä **Lisää roolien määritys** -ruudussa seuraavat ominaisuudet:
   - **Rooli**: tallennuksen blob-tietojen lukija, tallennuksen blob-objektin osallistuja tai tallennuksen blob-objektin omistaja edellä mainittujen tunnistetietojen perusteella.
   - **Käyttöoikeuden delegointi**: **Käyttäjä, ryhmä tai palveluobjekti**
   - **Valitse** jäsenet: **Dynamics 365 AI for Customer Insights** (tässä ohjeessa aiemmin katsomasi [palvelun pääobjekti](#create-a-new-service-principal))

1. Valitse **Tarkista + määritä**.

Muutosten päivittyminen voi kestää 15 minuuttia.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Anna Azure-resurssitunnus tai Azure-tilauksen tiedot Customer Insightsin tallennustilatilin liitteeseen

Liitä Data Lake Storage -tallennustila Customer Insightsiin, jotta voit [tallentaa tulostietoja](manage-environments.md) tai [käyttää niitä tietolähteenä](connect-dataverse-managed-lake.md). Valitse [resurssipohjainen](#resource-based-storage-account-connection) tai [tilauspohjainen](#subscription-based-storage-account-connection) vaihtoehto ja seuraa sen ohjeita.

### <a name="resource-based-storage-account-connection"></a>Resurssipohjainen tallennustiliyhteys

1. Siirry [Azure-hallintaportaaliin](https://portal.azure.com), kirjaudu tilaukseen ja avaa tallennustili.

1. Siirry vasemmassa ruudussa kohtaan **Asetukset** > **Päätepisteet**.

1. Kopioi tallennustilin resurssitunnuksen arvo.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Tallennustilin resurssitunnuksen arvon kopiointi":::

1. Lisää Customer Insights -kentässä resurssitunnus tallennustilin yhteysnäytössä näkyvään resurssikenttään.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Tallennustilin resurssitunnuksen tietojen antaminen":::

1. Liitä tallennustilatili jatkamalla Customer Insightsin muita vaiheita.

### <a name="subscription-based-storage-account-connection"></a>Tilauspohjainen tallennustiliyhteys

1. Siirry [Azure-hallintaportaaliin](https://portal.azure.com), kirjaudu tilaukseen ja avaa tallennustili.

1. Valitse vasemmanpuoleisessa ruudussa **Asetukset** > **Ominaisuudet**.

1. Tarkista **tilaus**, **resurssiryhmä** ja tallennustilin **nimi** ja varmista, että Customer Insightsissa valitaan oikeat arvot.

1. Valitse Customer Insightsissa vastaavien kenttien arvot, kun liität tallennustilin.

1. Liitä tallennustilatili jatkamalla Customer Insightsin muita vaiheita.

[!INCLUDE [footer-include](includes/footer-banner.md)]
