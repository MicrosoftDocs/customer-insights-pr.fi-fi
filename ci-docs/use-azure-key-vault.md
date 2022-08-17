---
title: Bring your own Azure key vault (esiversio)
description: Tietoja Customer Insightsin määrittämisestä siten, että salaisia koodeja voidaan hallita oman Azure Key Vaultin avulla.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246151"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Bring your own Azure key vault (esiversio)

Erillisen [Azure key vaultin](/azure/key-vault/general/basic-concepts) linkittäminen Customer Insights -ympäristöön auttaa organisaatioita täyttämään vaatimustenmukaisuuden.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Linkitä key vault Customer Insights -ympäristöön

Määritä erillinen key vault salaisten koodien valmisteluun ja käyttämiseen organisaation vaatimustenmukaisuusrajalla.

### <a name="prerequisites"></a>edellytykset

- Aktiivinen Azure-tilaus.

- [Järjestelmänvalvoja](permissions.md#admin)-rooli [määritetty](permissions.md#add-users) Customer Insightsissa.

- [Osallistuja](/azure/role-based-access-control/built-in-roles#contributor)- ja [Käyttäjän käyttöoikeuksien järjestelmänvalvoja](/azure/role-based-access-control/built-in-roles#user-access-administrator) -roolit key vaultissa tai resurssiryhmässä, jolle key vault kuuluu. Jos haluat lisätietoja, siirry kohtaan [Lisää tai poista Azure-roolimäärityksiä käyttäen Azure-portaalia](/azure/role-based-access-control/role-assignments-portal). Jos sinulla ei ole Käyttäjän käyttöoikeuksien järjestelmänvalvoja -roolia key vaultissa, määritä roolipohjaiset käyttöoikeuksien valvontaoikeudet Dynamics 365 Customer Insightsin Azure-palveluobjektille erikseen. Seuraa vaiheita [Azure-palveluobjektin käyttämiseksi](connect-service-principal.md) linkitettävää key vaultia varten.

- Key vaultissa on Key Vault -palomuurin oltava **poissa käytöstä**.

- Key vault on samassa [Azure-sijainnissa](https://azure.microsoft.com/global-infrastructure/geographies/#overview) kuin Customer Insights -ympäristö. Siirry Customer Insightsissa kohtaan **Järjestelmänhallinta** > **Järjestelmä** ja **Tietoja**-välilehti halutessasi tarkastella ympäristön aluetta.

### <a name="recommendations"></a>Suosituksia

- [Käytä erillistä key vaultia](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults), joka sisältää vain ne salaiset koodit, jotka tarvitaan Customer Insightsia varten.

- Seuraa [Key Vault -käytön parhaita käytäntöjä](/azure/key-vault/general/best-practices#turn-on-logging) liittyen käyttöoikeuksien hallintaan, varmuuskopiointiin ja seurantaan.

### <a name="link-a-key-vault-to-the-environment"></a>Linkitä key vault ympäristöön

1. Siirry kohtaan **Järjestelmänvalvoja** > **Tietoturva** ja valitse sitten **Key Vault** -välilehti.
1. Valitse **Key Vault** -ruudussa **Määritys**.
1. Valitse **Tilaus**.
1. Valitse key vault avattavasta **Key Vault** -luettelosta. Jos liian monta key vaultia on saatavilla, valitse resurssiryhmä hakutulosten rajoittamiseksi.
1. Tarkista tietojen [Tietosuoja ja vaatimustenmukaisuus](connections.md#data-privacy-and-compliance) ja valitse **Hyväksyn**.
1. Valitse **Tallenna**.

**Key Vault** -ruutu näyttää linkitetyn key vaultin nimen, tilauksen ja resurssiryhmän. Se on valmis käytettäväksi yhteysasetuksissa.
Jos haluat lisätietoja siitä, mitä oikeuksia Customer Insightsille annetaan key vaultissa, siirry kohtaan [annetut oikeudet key vaultissa](#permissions-granted-on-the-key-vault).

## <a name="use-the-key-vault-in-the-connection-setup"></a>Key vaultin käyttö yhteysasetuksissa

Kun [yhteyksiä määritetään](connections.md) [tuetun kolmannen osapuolen](#supported-connection-types) järjestelmiin, linkitetyn Key Vaultin salaisia koodeja käytetään yhteyksien määrittämiseen.

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.
1. Valitse **Lisää yhteys**.
1. Tuetuissa yhteystyypeissä **Käytä Key Vaultia** -käyttöpainike on käytettävissä, jos key vault on linkitetty.
1. Salaisen koodin manuaalisen syöttämisen sijaan valitse salaisen koodin nimi, joka osoittaa salaisen koodin arvoon key vaultissa.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Yhteysruutu ja SFTP-yhteys, joka käyttää Key Vaultin salaista koodia.":::

1. Valitse **Tallenna** luodaksesi yhteyden.

## <a name="supported-connection-types"></a>Tuetut yhteystyypit

Seuraavia [vientiyhteyksiä](export-destinations.md) tuetaan:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Key vaultiin myönnetyt oikeudet

Customer Insightsille annetaan seuraavat oikeudet key vaultissa, jos joko [Key Vault -käyttöoikeuskäytäntö](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) tai [Azuren roolipohjainen käyttöoikeuksien valvonta](/azure/key-vault/general/rbac-guide?tabs=azure-cli) on otettu käyttöön.

### <a name="key-vault-access-policy"></a>Key Vaultin käyttöoikeuskäytäntö

| Laji        | Käyttöoikeudet          |
| ----------- | -------------------- |
| Selite         | [Hanki avaimet](/rest/api/keyvault/keys/get-keys/get-keys), [Hanki avain](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Salainen koodi      | [Hanki salaiset koodit](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Hanki salainen koodi](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Varmenne | [Hanki varmenteet](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Hanki varmenne](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Edelliset arvot ovat luetteloinnin ja lukemisen vähimmäisarvot suorituksen aikana.

### <a name="azure-role-based-access-control"></a>Azuren roolipohjainen käyttöoikeuksien valvonta

[Key Vault -lukija- ja Key Vault -salaisten koodien käyttäjä -roolit](/azure/key-vault/general/rbac-guide?tabs=azure-cli) lisätään Customer Insightsia varten.

## <a name="frequently-asked-questions"></a>Usein kysyttyjä kysymyksiä

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Voiko Customer Insights kirjoittaa tai korvata salaisia koodeja key vaultiin?

Ei. Vain luku- ja luettelo-oikeudet, jotka kuvattiin [myönnetyt käyttöoikeudet](#permissions-granted-on-the-key-vault) -osassa, myönnetään Customer Insightsille. Järjestelmä ei voi lisätä, poistaa tai korvata salaisia koodeja key vaultissa. Siksi valtuustietoja ei voi syöttää, kun yhteys käyttää Key Vaultia.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Voinko vaihtaa yhteyden Key Vaultin salaisten koodien käyttämisestä oletustodentamiseen?

Ei. Et voi vaihtaa takaisin oletusyhteyteen sen jälkeen, kun olet määrittänyt sen käyttäen salaista koodia linkitetystä key vaultista. Luo erillinen yhteys ja poista vanha, jos et enää tarvitse sitä.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Miten voin kumota Customer Insightsin käyttöoikeudet key vaultiin?

Jos [Key Vault -käyttöoikeuskäytäntö](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) tai [Azuren roolipohjainen käyttöoikeuksien valvonta](/azure/key-vault/general/rbac-guide?tabs=azure-cli) on otettu käyttöön, sinun on poistettava oikeudet palveluobjektilta `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` nimeltä `Dynamics 365 AI for Customer Insights`. Kaikki key vaultia käyttävät yhteydet lakkaavat toimimasta.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Salainen koodi, jota käytetään yhteydessä, poistettiin key vaultista. Mitä voin tehdä?

Näkyviin tulee ilmoitus Customer Insightsissa, kun määritettyä salaista koodia key vaultista ei enää voi käyttää. Ota käyttöön [pehmeä poisto](/azure/key-vault/general/soft-delete-overview) key vaultissa, jotta voit palauttaa salaiset koodit, jos ne poistettiin vahingossa.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Yhteys ei toimi, mutta salainen koodini on key vaultissa. Mikä voi olla syy?

Näkyviin tulee ilmoitus Customer Insightsissa, kun se ei voi käyttää key vaultia. Syy voi olla:

- Customer Insightsin palveluobjektin oikeudet on poistettu. Ne on palautettava manuaalisesti.

- Key vaultin palomuuri on käytössä. Palomuurin on oltava poissa käytöstä, jotta Customer Insights voi taas käyttää key vaultia.
