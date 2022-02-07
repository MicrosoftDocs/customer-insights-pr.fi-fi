---
title: Customer Insights -tietojen vienti Dynamics 365 Marketingiin
description: Tietoja yhteyden määrittämisestä ja viennistä Dynamics 365 Marketingiin.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
---

# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Käytä segmenttejä Dynamics 365 Marketingissa (esiversio)



Luo [segmenttien](segments.md) avulla kampanjoita ja ota yhteyttä tiettyihin asiakasryhmiin Dynamics 365 Marketingin avulla. Lisätietoja on kohdassa [Dynamics 365 Customer Insightsin segmenttien käyttäminen Dynamics 365 Marketingin kanssa](/dynamics365/marketing/customer-insights-segments).

Jos käytät Dynamics 365 Marketingin uusia ominaisuuksia reaaliaikaiseen asiakassiirtymään Dataverse-organisaatiossa, vakioviennin luominen Dynamics 365 Marketingiin ei ole tarpeen. Yhteyshenkilöt ja segmentit käyttäjäryhmän tiedoista ovat käytettävissä suoraan Dynamics 365 Marketingissa, kun olet yhdistänyt Marketingin ja Customer Insightsin. Ennen kuin poistat aiemmin luodut viennit, tutustu ohjeisiin [miten yhdistää kohdeyleisön tiedot ja Dynamics 365 Marketing -asiakassiirtymän orkestrointi](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Yhteyden edellytykset

- Yhteyshenkilötietueiden on oltava Dynamics 365 Marketingissa, ennen kuin segmentti voidaan viedä Customer Insightsista Marketingiin. Lisätietoja yhteyshenkilöiden käyttämisestä [Dynamics 365 Marketingissa Microsoft Dataversein avulla](connect-power-query.md).

  > [!NOTE]
  > Segmenttien vieminen käyttäjäryhmän tiedoista Marketingiin ei luo Marketing-esiintymiin uusia yhteyshenkilötietueita. Marketingin yhteyshenkilötietueet on käsiteltävä käyttäjäryhmän tiedoissa, ja niitä on käytettävä tietolähteenä. Ne on myös sisällytettävä yhdistettyyn asiakasentiteettiin, jotta asiakastunnukset voidaan yhdistää yhteyshenkilötunnuksiin ennen segmenttien viemistä.

## <a name="set-up-connection-to-marketing"></a>Määritä yhteys Marketingiin

1. Siirry kohtaan **Järjestelmänvalvoja** > **Yhteydet**.

1. Valitse **Lisää yhteys** ja määritä yhteys valitsemalla **Dynamics 365 Marketing**.

1. Anna yhteydelle tunnistettava nimi **Näyttönimi**-kentässä. Yhteyden nimi ja tyyppi kuvaavat yhteyttä. On suositeltavaa valita nimi, joka kertoo yhteyden tarkoituksen ja kohteen.

1. Valitse, kuka voi käyttää tätä yhteyttä. Jos et tee mitään, oletusarvo on Järjestelmänvalvojat. Lisätietoja on ohjeaiheessa [Salli osallistujien käyttää yhteyttä viennissä](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Syötä organisaatiosi Marketing-URL-osoite **Palvelinosoite**-kentässä.

1. Valitse **Palvelimen järjestelmänvalvojan tili** -osassa **Kirjaudu sisään** ja valitse sitten Dynamics 365 Marketing -tili.

1. Yhdistä asiakasentiteetin Yhteyshenkilön tunnus -kenttä Dynamics 365:n yhteyshenkilön tunnukseen.

1. Viimeistele yhteys valitsemalla **Tallenna**. 

## <a name="configure-an-export"></a>Viennin määrittäminen

Voit määrittää tämän viennin, jos sinulla on tämäntyyppisen yhteyden käyttöoikeus. Lisätietoja on ohjeaiheessa [Viennin määrittämiseen tarvittavat oikeudet](export-destinations.md#set-up-a-new-export).

1. Siirry kohtaan **Tiedot** > **Viennit**.

1. Luo uusi vienti valitsemalla **Lisää kohde**.

1. Valitse **Yhteys vientiä varten** -kentässä yhteys Dynamics 365 Marketing -osasta. Jos et näe tämän osan nimeä, tämäntyyppisiä yhteyksiä ei ole käytettävissäsi.

1. Valitse vähintään yksi segmentti.

1. Valitse **Tallenna**.

Viennin tallentaminen ei suorita vientiä heti.

Vienti suoritetaan jokaisen [ajoitetun päivityksen](system.md#schedule-tab) kanssa. Voit myös [viedä tietoja tarvittaessa](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
