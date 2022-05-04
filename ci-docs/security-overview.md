---
title: Käyttöoikeusasetukset Dynamics 365 Customer Insightsissa
description: Tietoja tietoturva-asetuksista Dynamics 365 Customer Insightsissa.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653712"
---
# <a name="security-overview-page"></a>Tietoturvan yleiskatsaussivu

**Tietoturva**-sivulla on vaihtoehtoja, joiden avulla voit määrittää käyttöoikeuksia ja ominaisuuksia, jotka auttavat tekemään Dynamics 365 Customer Insightsista entistä turvallisemman. Vain järjestelmänvalvojat voivat käyttää tätä sivua. 

Määritä asetukset kohdassa **Järjestelmänvalvoja** > **Tietoturva**.

**Tietoturva**-sivu sisältää seuraavat välilehdet:
- [Käyttäjät](#users-tab)
- [Ohjelmointirajapinnat](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Käyttäjät-välilehti

Customer Insights -tietojen käyttöoikeus rajoittuu organisaatiosi käyttäjiin, jotka järjestelmänvalvoja on lisännyt sovellukseen. **Käyttäjät**-välilehdessä voit hallita käyttäjien pääsy- ja käyttöoikeuksia. Lisätietoja on kohdassa [käyttäjän oikeudet](permissions.md).

## <a name="apis-tab"></a>Ohjelmointirajapinnat-välilehti

Tarkastele ja hallitse avaimia, joilla voit käyttää [Customer Insights -ohjelmointirajapintoja](apis.md) ympäristön tietojen kanssa.

Voit luoda uusia perus- ja toissijaisia avaimia valitsemalla **Luo uudelleen ensisijainen** tai **Luo uudelleen toissijainen**. 

Jos haluat estää ympäristön ohjelmointirajapinnan käytön, valitse **Poista käytöstä**. Jos ohjelmointirajapinnat on poistettu käytöstä, voit valita **Ota käyttöön**, jos haluat myöntää käyttöoikeudet uudelleen.

## <a name="key-vault-tab"></a>Key Vault -välilehti

**Key Vault** -välilehdessä voi linkittää oman [Azure Key Vaultin](/azure/key-vault/general/basic-concepts) ympäristöön ja hallita sitä.
Erillistä key vaultia voidaan käyttää salaisten koodien valmisteluun ja käyttämiseen organisaation vaatimustenmukaisuusrajalla. Customer Insights voi käyttää Azure Key Vaultin salaisia koodeja [yhteyksien määrittämiseen](connections.md) kolmannen osapuolen järjestelmiin.

Lisätietoja on kohdassa [Oman Azure Key Vaultin tuominen](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
