---
title: Luo ja hallitse ympäristöjä
description: Tietoja palveluun rekisteröitymisestä ja ympäristöjen hallinnasta.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: fcdb7f073ff73322ff69d0a8684391819a809d00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646307"
---
# <a name="manage-environments"></a>Ympäristöjen hallinta

## <a name="switch-environments"></a>Ympäristöjen vaihtaminen

Voit vaihtaa ympäristöä valitsemalla sivun oikeassa yläkulmassa **Ympäristöt**.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Näyttökuva ohjausobjektista, jonka avulla voit vaihtaa ympäristöä.":::

Järjestelmänvalvojat voivat [Luoda](create-environment.md) ja hallita ympäristöjä.

## <a name="edit-an-existing-environment"></a>Aiemmin luodun ympäristön muokkaaminen

Voit muokata joitakin aiemmin luotujen ympäristöjen tietoja.

1.  Valitse sovelluksen otsikossa **Ympäristö**-valitsin.

2.  Valitse **Muokkaa**-kuvake.

3. Voit päivittää ympäristön asetuksia **Muokkaa ympäristöä** -ruudussa.

Lisätietoja ympäristön asetuksista on kohdassa [Uuden ympäristön luominen](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Yhdistä Microsoft Dataverseen
   
Tässä **Microsoft Dataverse** -vaiheessa voit yhdistää Customer Insightsin Dataverse-ympäristöösi. 

Tarjoa oma Microsoft Dataverse -ympäristösi tietojen (profiilien ja tietojen) jakamiseksi Dataverseen perustuviin liiketoimintasovelluksiin, kuten Dynamics 365 Marketingiin tai mallipohjaisiin sovelluksiin Power Appsissa.

Jos haluat käyttää [valmiita ennustemalleja](predictions-overview.md#out-of-box-models), määritä tietojen jakaminen Dataversen kanssa. Voit myös ottaa käyttöön tietojen käsittelyn paikallisista tietolähteistä antamalla organisaatiosi hallinnoiman Microsoft Dataverse -ympäristön URL-osoitteen.

Kun tietojen jakaminen otetaan käyttöön Microsoft Dataversen kanssa valitsemalla tietojen jakamisen valintaruutu, tietolähteiden ja muiden prosessien täydellinen päivitys käynnistyy kerran.

> [!IMPORTANT]
> 1. Customer Insightsin ja Dataversen on oltava samalla alueella, jotta tietojen jakaminen voidaan ottaa käyttöön.
> 1. Dataverse-ympäristössä on oltava yleisen järjestelmänvalvojan rooli. Tarkista, onko tämä [Dataverse-ympäristö liitetty](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) tiettyihin käyttöoikeusryhmiin, ja varmista, että sinut on lisätty näihin käyttöoikeusryhmiin.
> 1. Tähän Dataverse-ympäristöön ei ole jo aiemmin liitetty Customer Insights -ympäristöä. Opettele poistamaan [aiemmin luotu yhteys Dataverse-ympäristöön](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Määritysvalinnat tietojen jakamista varten Microsoft Dataversen kanssa.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Tietojen jakamisen ottaminen käyttöön Dataversen kanssa omasta Azure Data Lake Storagesta (esiversio)

Jos ympäristösi on määritetty käyttämään omaa Azure Data Lake Storagea Customer Insights -tietojen tallentamiseen, tietojen jakamisen ottaminen käyttöön Microsoft Dataversen kanssa edellyttää lisämäärityksiä.

1. Luo Azure-tilaukseen kaksi käyttöoikeusryhmää, yksi **Lukija**-käyttöoikeusryhmä ja yksi **Osallistuja**-käyttöoikeusryhmä ja määritä Microsoft Dataverse -palvelu kummankin käyttöoikeusryhmän omistajaksi.
2. Voit hallita tallennustilatilin CustomerInsights-säilön Access control list (ACL) -luetteloa näiden käyttöoikeusryhmien kautta. Lisää Microsoft Dataverse-palvelu ja muut Dataverse-pohjaiset liiketoimintasovellukset, kuten Dynamics 365 Marketing,**Lukija**-käyttöoikeusryhmään **vain luku** -oikeuksilla. Lisää *vain* Customers Insights -sovellus **Osallistuja**-käyttöoikeusryhmään, jotta voit myöntää sekä profiilien ja tietojen **luku- että kirjoitusoikeudet**.
   
#### <a name="prerequisites"></a>edellytykset

PowerShell-komentosarjojen suorittamiseen on tuotava seuraavat kolme moduulia. 

1. Asenna [Azure Active Directory PowerShell for Graphin ](/powershell/azure/active-directory/install-adv2)uusin versio.
   1. Valitse tietokoneessa näppäimistön Windows-avain, hae **Windows PowerShell** ja valitse **Suorita Järjestelmänvalvojana**.
   1. Anna avautuvassa PowerShell-ikkunassa `Install-Module AzureAD`.
2. Tuo kolme moduulia.
    1. Kirjoita PowerShell-ikkunaan `Install-Module -Name Az.Accounts` ja seuraa ohjeita. 
    1. Toista kohteiden `Install-Module -Name Az.Resources` ja `Install-Module -Name Az.Storage` kohdalla.

#### <a name="configuration-steps"></a>Määrityksen vaiheet

1. Lataa kaksi suoritettavaa PowerShell-komentosarjaa insinöörin [GitHub-säilöstä](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Tämän PowerShell-komentosarjan suorittamiseen tarvitaan *vuokraajan järjestelmänvalvojan* käyttöoikeudet. 
       - Tämä PowerShell-komentosarja luo kaksi käyttöoikeusryhmää Azure-tilaukseen. Yhden Lukija-ryhmälle ja yhden Osallistuja-ryhmälle ja tekee Microsoft Dataverse-palvelusta näiden käyttöoikeusryhmien omistajan.
       - Suorita tämä PowerShell-komentosarja Windows PowerShellissä antamalla Azure-tilauksen tunnus, joka sisältää Azure Data Lake Storagen. Avaamalla PowerShell-komentosarjan editorissa voit tarkastella lisätietoja ja käyttöön otettua logiikkaa.
       - Tallenna molemmat tämän komentosarjan luomat käyttöoikeusryhmän tunnusarvot, koska niitä käytetään `ByolSetup.ps1`-komentosarjassa.
       
        > [!NOTE]
        > Käyttöoikeusryhmän luonnin voi poistaa käytöstä vuokraajassa. Tällöin tarvitaan manuaalinen asennus, ja Azure AD-järjestelmänvalvojan on [otettava käyttöön käyttöoikeusryhmän luonti](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Tarvitset *Säilön BLOB-tietojen omistajan* oikeudet tallennustilatili-/säilötasolla komentosarjan suorittamiseen tai tämä komentosarja luo komentosarjan sinulle. Roolimääritys voidaan poistaa manuaalisesti, kun komentosarja on suoritettu.
        - Tämä PowerShell-komentosarja lisää Microsoft Dataverse-palveluun ja mihin tahansa Dataverse-pohjaisiin liiketoimintasovelluksiin tarvittavan roolipohjaisen käyttöoikeuksien hallinnan. Se päivittää myös CustomerInsights-säilön access control list (ACL) -luettelon `CreateSecurityGroups.ps1`-komentosarjalla luoduille käyttöoikeusryhmille. Osallistuja-ryhmällä on *rwx*-käyttöoikeudet ja Lukijat-ryhmällä on vain *r-x*-käyttöoikeudet.
        - Suorita tämä PowerShell-komentosarja Windows PowerShellissä antamalla Azure-tilaustunnus, joka sisältää Azure Data Lake Storagen, tallennustilin nimen, resurssiryhmän nimen sekä Lukija- ja Osallistuja-käyttöoikeusryhmän tunnusarvot. Avaamalla PowerShell-komentosarjan editorissa voit tarkastella lisätietoja ja käyttöön otettua logiikkaa.
        - Kopioi tulosmerkkijono, kun komentosarja on suoritettu. Tulosmerkkijono näyttää tältä: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Kirjoita edellä kopioitu tulosmerkkijono **Oikeuksien tunnus** -kenttään ympäristön määritysvaiheessa Microsoft Dataverselle.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Määritysvaihtoehdot, joilla voit ottaa käyttöön tietojen jakamisen omasta kohteesta Azure Data Lake Storage kohteella Microsoft Dataverse.":::

Customer Insights ei tue seuraavia tietojen jakamisen skenaarioita:
- Jos otat käyttöön tietojen jakamisen Dataversen kanssa, et voi [luoda ennustettuja tai puuttuvia arvoja entiteetissä](predictions.md).
- Jos otat tietojen jakamisen käyttöön Dataversella, et voi tarkastella valinnaisia PowerBI Embedded -raportteja Customer Insights -ympäristössä.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Poista aiemmin luotu yhteys Dataverse-ympäristöön

Kun muodostat yhteyden Dataverse-ympäristöön, virheilmoitus **Tämä CDS-organisaatio on jo liitetty toiseen Customer Insights -esiintymään** tarkoittaa, että Dataverse-ympäristöä käytetään jo Customer Insights -ympäristössä. Voit poistaa aiemmin luodun yhteyden yleisenä Järjestelmänvalvoja Dataverse-ympäristössä. Muutosten täyttäminen voi kestää muutaman tunnin.

1. Siirry [Power Appsiin](https://make.powerapps.com).
1. Valitse ympäristön valitsimesta ympäristö.
1. Valitse **Ratkaisut**
1. Poista **Dynamics 365 Customer Insights -asiakaskortin apuohjelma (esiversio)** -niminen ratkaisu tai sen asennus.

Tai 

1. Avaa Dataverse-ympäristösi.
1. Siirry kohtaan **Lisäasetukset** > **Ratkaisut**.
1. Poista **CustomerInsightsCustomerCard**-ratkaisun asennus.

## <a name="copy-the-environment-configuration"></a>Kopioi ympäristön määritys

Järjestelmänvalvojana voit kopioida määrityksen aiemmin luodusta ympäristöstä, kun luot uuden. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Näyttökuva ympäristöasetusten asetusvaihtoehdoista.":::

Näkyviin tulee luettelo kaikista organisaation käytettävissä olevista ympäristöistä, joista voit kopioida tietoja.

Seuraavat määritysasetukset kopioidaan:

- Käsitellyt/tuodut tietolähteet
- Tietojen yhtenäistämisen (yhdistäminen, vastaavuus) määritys
- Segmentit
- Mittarit
- Suhteet
- Aktiviteetit
- Haku- ja suodatusindeksi
- Vientikohteet
- Ajoitettu päivitys
- Rikastukset
- Mallien hallinta
- Roolimääritykset

## <a name="set-up-a-copied-environment"></a>Kopioidun ympäristön määrittäminen

Kun kopioit ympäristön määrityksen, seuraavat tiedot *eivät* kopioidu:

- Asiakasprofiilit.
- Tietolähteen tunnistetiedot. Sinun on annettava kunkin tietolähteen tunnistetiedot ja päivitettävä tietolähteet manuaalisesti.
- Tietolähteet Common Data Model -kansiosta ja Dataversen hallitusta Data Lake -tallennustilasta. Nämä tietolähteet on luotava manuaalisesti samalla nimellä kuin lähdeympäristössä.
- Yhteyksiin liittyvät salaisuudet, joita käytetään viennissä ja rikastamisissa. Yhteyksien todennus on suoritettava uudelleen ja sitten rikastamisen ja viennit on aktivoitava uudelleen. 

Kun kopioit ympäristön, näkyviin tulee vahvistussanoma siitä, että uusi ympäristö on luotu. Valitse **Siirry tietolähteisiin**, kun haluat nähdä tietolähteiden luettelon.

Kaikkien tietolähteiden tilana näkyy **Vaatii tunnistetietoja**. Muokkaa tietolähteitä ja päivitä ne syöttämällä tunnistetiedot.

:::image type="content" source="media/data-sources-copied.png" alt-text="Luettelo kopioiduista tietolähteistä, jotka vaativat todennusta.":::

Kun olet päivittänyt tietolähteet, siirry kohtaan **Tiedot** > **Yhtenäistäminen**. Siellä ovat lähdeympäristön asetukset. Voit muokata niitä tarpeen mukaan tai valita **Suorita**, jolloin tietojen yhtenäistämisprosessi alkaa ja yhtenäistetty asiakasentiteetti luodaan.

Kun tietojen yhtenäistäminen on valmis, päivitä myös kohdat **Mittarit** ja **Segmentit** siirtymällä niihin.

Ennen kuin aktivoit viennit ja rikastamisen uudelleen, siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet** ja aloita yhteyksien uudelleentodennus uudessa ympäristössä.

## <a name="change-the-owner-of-an-environment"></a>Ympäristön omistajan muuttaminen

Vaikka useilla käyttäjillä voi olla järjestelmänvalvojan oikeudet Customer Insightsissa, vain yksi käyttäjä on ympäristön omistaja. Oletusarvon mukaan järjestelmänvalvoja luo ympäristön. Ympäristön järjestelmänvalvojana voit delegoida omistuksen toiselle käyttäjälle, jolla on järjestelmänvalvojan oikeudet.

1. Valitse sovelluksen otsikossa **Ympäristö**-valitsin.

1. Valitse **Muokkaa**-kuvake.

1. Siirry **Muokkaa ympäristöä** -ruudussa **Perustiedot**-vaiheeseen.

1. Valitse **Muuta ympäristön omistajaa** -kentässä ympäristön uusi omistaja.  

1. Valitse **Tarkasta ja viimeistele** ja sitten **Päivitä** ottaaksesi muutokset käyttöön. 

## <a name="claim-ownership-of-an-environment"></a>Ympäristön omistajuuden vaatiminen

Jos ympäristön omistaja lähtee organisaatiosta tai hänen tilinsä poistetaan, ympäristöllä ei ole omistajaa. Käyttäjä, jolla on järjestelmänvalvojan oikeudet, voi vaatia omistajuuden ja hänestä voi tulla uusi omistaja. Hän voi jatkaa ympäristön omistajana tai [vaihtaa omistuksen toiselle järjestelmänvalvojalle](#change-the-owner-of-an-environment). 

Vaadi omistus valitsemalla **Ota omistus** -painike, joka näkyy jokaisen Customer Insights -sivun yläosassa, kun alkuperäinen omistaja on lähtenyt organisaatiosta.

## <a name="reset-an-existing-environment"></a>Aiemmin luodun ympäristön palauttaminen

Ympäristön omistajana voit nollata ympäristön tyhjään tilaan, jos haluat poistaa kaikki määritykset ja poistaa käytetyt tiedot.

1.  Valitse sovelluksen otsikossa **Ympäristö**-valitsin. 

2.  Valitse ympäristö, jonka haluat palauttaa, ja valitse sitten kolme pistettä (**...**). 

3. Valitse **Palauta**-vaihtoehto. 

4.  Vahvista poisto antamalla ympäristön nimi ja valitsemalla **Palauta**.

## <a name="delete-an-existing-environment"></a>Olemassa olevan ympäristön poistaminen

Ympäristön omistajana voit poistaa ympäristön, jonka järjestelmänvalvoja olet.

1.  Valitse sovelluksen otsikossa **Ympäristö**-valitsin.

2.  Valitse ympäristö, jonka haluat palauttaa, ja valitse sitten kolme pistettä (**...**). 

3. Valitse **Poista**-vaihtoehto. 

4.  Vahvista poisto antamalla ympäristön nimi ja valitsemalla **Poista**.

> [!NOTE]
> Ympäristön poistaminen ei poista yhteyttä Dataverse-ympäristöön. Opettele [poistamaan aiemmin luotu yhteys Dataverse-ympäristöön](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE [footer-include](includes/footer-banner.md)]
