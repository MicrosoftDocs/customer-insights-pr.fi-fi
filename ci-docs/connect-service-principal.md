---
title: Yhteyden muodostaminen Azure Data Lake Storage -tiliin palvelun päätunnuksen avulla
description: Muodosta yhteys Data Lake -tallennustilaan Azure-palvelun päätoiminnon avulla.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: b18d1f42b9510ebf23f0666322819865d132173b
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833381"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Yhteyden muodostaminen Azure Data Lake Storage -tiliin Azure-palvelun päätunnuksen avulla

Tässä artikkelissa kerrotaan, miten Azure Data Lake Storage -tiliin voi muodostaa yhteyden Dynamics 365 Customer Insightsista käyttämällä Azure-palvelun päänimeä tallennustilan tilin avainten sijaan.

Azure-palveluja käyttävillä automaattisilla työkaluilla on oltava aina rajoitetut käyttöoikeudet. Sen sijaan että sovellukset kirjautusivat sisään käyttäjänä, jolla on kaikki oikeudet, Azure antaa mahdollisuuden käyttää palveluobjekteja. Palvelun päänimen avulla voit [lisätä tai muokata Common Data Model -kansiota tietolähteenä](connect-common-data-model.md) tai [luoda tai päivittää ympäristön](create-environment.md).

> [!IMPORTANT]
>
> - Data Lake -tallennustilin, joka käyttää palvelun pääobjektia on oltava Gen2 ja sillä on oltava [käytössä hierarkinen nimiavaruus](/azure/storage/blobs/data-lake-storage-namespace). Azure Data Lake Gen1 -tallennustilejä ei tueta.
> - Tarvitset Azure-vuokraajaan järjestelmänvalvojan oikeudet palvelun pääkäyttäjän luomiseksi.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Luo Azure-palvelun pääkäyttäjä Customer Insights -tietoja varten

Ennen kuin luot uuden palvelun päänimen Customer Insightsille, tarkista, onko se jo organisaatiossasi.

### <a name="look-for-an-existing-service-principal"></a>Aiemmin luodun palveluobjektin etsiminen

1. Siirry [Azure-hallintaportaaliin](https://portal.azure.com) ja kirjaudu organisaatioon.

2. Valitse **Azure-palvelut**-kohdassa **Azure Active Directory**.

3. Valitse **Hallinta**-kohdasta **Microsoft-sovellus**.

4. Lisää suodatin kohteelle **Sovellustunnuksen alku** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` tai etsi nimeä `Dynamics 365 AI for Customer Insights`.

5. Jos löydät vastaavan tietueen, palvelun pääkäyttäjä on jo olemassa.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Näyttökuva, jossa näkyy palvelun pääkäyttäjä.":::

6. Jos tuloksia ei palauteta, voit luoda [uuden palveluobjektin](#create-a-new-service-principal). Useimmissa tapauksissa se on jo olemassa, ja sinun tarvitsee vain myöntää käyttöoikeudet palvelun päätuotteelle, jotta voit käyttää tallennustiliä.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Tallennustilin käyttöön tarvittavien oikeuksien myöntäminen palveluobjektille

Siirry Azure-portaaliin, jos haluat myöntää käyttöoikeudet palvelun pääasiakastilille, jota haluat käyttää Customer Insightsissa.

1. Siirry [Azure-hallintaportaaliin](https://portal.azure.com) ja kirjaudu organisaatioon.

1. Avaa tallennustilatili, jonka käyttöoikeudet haluat Customer Insights -palvelun pääasiakkaan käyttöön.

1. Valitse vasemmanpuoleisesta ruudusta **Käytönvalvonta (IAM)** ja valitse sitten **Lisää** > **Lisää roolimääritys**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Näyttökuva, jossa näkyy Azure-portaali, kun lisätään roolimääritystä.":::

1. Määritä **Lisää roolien määritys** -ruudussa seuraavat ominaisuudet:
   - Rooli: **Tallennustilan BLOB-tietojen osallistuja**
   - Käyttöoikeuden delegointi: **Käyttäjä, ryhmä tai palveluobjekti**
   - Valitse jäsenet: **Dynamics 365 AI for Customer Insights** (tässä ohjeessa aiemmin katsomasi [palvelun pääasiakas](#create-a-new-service-principal))

1. Valitse **Tarkista + määritä**.

Muutosten päivittyminen voi kestää 15 minuuttia.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Anna Azure-resurssitunnus tai Azure-tilauksen tiedot Customer Insightsin tallennustilatilin liitteeseen

Voit liittää Data Lake Storage -tilin Customer Insightsissa [tulostietojen tallentamiseksi](manage-environments.md) tai [käyttää sitä tietolähteenä](connect-dataverse-managed-lake.md). Tämän vaihtoehdon avulla voit valita resurssipohjaisen tai tilauspohjaisen vaihtoehdon. Noudata valitsemasi toimintatavan mukaisesti jossakin seuraavista osasta annettuja ohjeita.

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

### <a name="create-a-new-service-principal"></a>Uuden palveluobjektin luominen

1. Asenna Azure Active Directory PowerShell for Graphin uusin versio. Lisätietoja on kohdassa [Asenna Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Paina tietokoneessa näppäimistön Windows-näppäintä, hae **Windows PowerShell** ja valitse **Suorita järjestelmänvalvojana**.

   1. Anna avautuvassa PowerShell-ikkunassa `Install-Module AzureAD`.

2. Luo Customer Insights -palvelun pääkäyttäjä Azure AD PowerShell -moduulilla.

   1. Anna PowerShell-ikkunassa `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Korvaa *[hakemistotunnus]* Azure-tilauksesi todellisella hakemistotunnuksella, johon haluat luoda palvelun päätunnuksen. Ympäristön nimiparametri `AzureEnvironmentName` on valinnainen.
  
   1. Anna `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Tämä komento luo Customer Insights -palvelun pääasiakkaan valitulle Azure-tilaukselle.

[!INCLUDE [footer-include](includes/footer-banner.md)]