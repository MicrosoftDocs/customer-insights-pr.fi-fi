---
title: Käytä omaa Azure Data Lake Storage Gen2 -tiliäsi
author: mukeshpo
description: Tietoja vaatimuksista käyttää omaa Azure Data Lake Storage -tiliäsi Customer Insights -tietojen tallentamista varten.
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: d2ff49c324c5c5c28213f362ff330d441fcb6052
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246197"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Käytä omaa Azure Data Lake Storage Gen2 -tiliäsi

Dynamics 365 Customer Insightsissa voit tallentaa kaikki tiedot [Azure Data Lake Storage Gen 2 -ohjelmaan](/azure/storage/blobs/data-lake-storage-introduction).

Kun tiedot tallennetaan Data Lake Storageen, hyväksyt, että tiedot siirretään ja tiedot tallennetaan tämän Azure-tallennustilin maantieteellisen sijainnin mukaisesti. Lisätietoja: [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Customer Insights -järjestelmänvalvojat voivat [luoda ympäristöjä](create-environment.md) ja [määrittää tietojen tallennusvaihtoehdon](create-environment.md#step-2-configure-data-storage) prosessissa.

## <a name="prerequisites-to-use-your-storage-account"></a>Tallennustilatilin käytön edellytykset

- Azure Data Lake Storage -tilien tulee olla samalla Azure-alueella, jonka valitsit Customer Insights -ympäristöä luotaessa. Katso tietoja Customer Insights -ympäristön alueesta kohdassa **Järjestelmänvalvoja** > **Järjestelmä** > **Tietoja**.
- Data Lake Storagen on oltava Gen2 ja sillä on oltava [hierarkkisen nimitilan ominaisuus käytössä](/azure/storage/blobs/create-data-lake-storage-account). Gen1-tallennustilejä ei tueta.
- Säilöllä, jonka nimi on `customerinsights`, on oltava tallennustili. Se on luotava, ennen kuin voit käyttää omaa Data Lake Storagea Customer Insightsissa. Customer Insights-ympäristön määrittävä järjestelmänvalvoja tarvitsee Säilön BLOB-tietojen osallistuja- tai Säilön BLOB-tietojen omistaja -roolin tallennustilillä tai `customerinsights`-säilöön. Lisätietoja käyttöoikeuksien määrittämisestä tallennustilillä on ohjeaiheessa [Tallennustilin luominen](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Yhdistä Customer Insights tallennustilatiliisi

Kun luot uuden ympäristön, varmista, että Data Lake Storage -tili on olemassa ja että kaikki edellytykset täyttyvät.

1. Aseta **Tietosäilö**-vaiheessa ympäristön luomisen aikana kohdan **Tallenna lähtötiedot** arvoksi **Azure Data Lake Storage Gen2**.
1. Valitse **Tallennustilan yhdistäminen**. Voit valita resurssipohjaisen vaihtoehdon ja tilauspohjaisen vaihtoehdon todentamista varten. Lisätietoja on kohdassa [Yhteyden muodostaminen Azure Data Lake Storage -tiliin Azure-palvelun päänimen avulla](connect-service-principal.md).
   - Valitse **Azure-tilauksessa** `customerinsights`-säilön sisältävä **Tilaus**-, **Resurssiryhmä**- ja **Tallennustilatili** .
   - Anna **Tiliavaimelle** **Tilin nimi** ja **Tilin avain** Data Lake Storage -tilille. Kun käytät tätä todennusmenetelmää, sinulle ilmoitetaan, jos organisaatiosi käyttää avaimia. [Ympäristön määritykset on päivitettävä](manage-environments.md#edit-an-existing-environment) uudella avaimella, kun se vaihtuu.
1. Valitse, käytätkö Azuren yksityistä linkki muodostamaan yhteys tallennustiliin, ja [luo yhteys yksityiseen linkkiin](security-overview.md#set-up-an-azure-private-link) kaksivaiheisen prosessin avulla.

Kun järjestelmäprosessit, kuten tietojen käsittely, ovat valmiit, järjestelmä luo vastaavat kansiot tallennustilille. Datatiedostot ja *model.json*-tiedostot luodaan ja lisätään kansioihin prosessin nimen perusteella.

Jos luot useita Customer Insights -ympäristöjä ja päätät tallentaa näiden ympäristöjen tuloste-entiteetit tallennustilillesi, Customer Insights luo erilliset kansiot kullekin ympäristölle ja `ci_environmentID`-tunnuksen säilöön.
