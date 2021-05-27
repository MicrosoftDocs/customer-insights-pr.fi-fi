---
title: Asiakaskortti-apuohjelma Dynamics 365 -sovelluksiin
description: Näytä käyttäjäryhmän merkitykselliset tiedot Dynamics 365 -sovelluksissa tämän apuohjelman avulla.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059584"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="a21f5-103">Asiakaskortin apuohjelma (esiversio)</span><span class="sxs-lookup"><span data-stu-id="a21f5-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a21f5-104">Saat kokonaisvaltainen näkymän asiakkaista suoraan Dynamics 365 -sovelluksissa.</span><span class="sxs-lookup"><span data-stu-id="a21f5-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="a21f5-105">Kun Asiakaskortti-apuohjelma on asennettu tuettuun Dynamics 365 -sovellukseen, voit näyttää demografiset tiedot, kävijätiedot ja aktiivisuuden aikajanat.</span><span class="sxs-lookup"><span data-stu-id="a21f5-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="a21f5-106">Apuohjelma hakee tietoja Customer Insights -sovelluksesta vaikuttamatta yhdistetyn Dynamics 365 -sovelluksen tietoihin.</span><span class="sxs-lookup"><span data-stu-id="a21f5-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a21f5-107">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="a21f5-107">Prerequisites</span></span>

- <span data-ttu-id="a21f5-108">Apuohjelma toimii vain Dynamics 365 - mallipohjaisissa sovelluksissa, kuten Salesissa tai Customer Servicen versiossa 9.0 ja uudemmissa.</span><span class="sxs-lookup"><span data-stu-id="a21f5-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="a21f5-109">Jotta Dynamics 365 -tiedot voidaan yhdistää kohdeyleisön merkistyksellisten tietojen siakasprofiileihin, ne on [saatava Dynamics 365 -sovelluksesta Common Data Service -yhdistimen avulla](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a21f5-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="a21f5-110">Kaikki Asiakaskortti-apuohjelman Dynamics 365 -käyttäjät [on lisättävä käyttäjiksi](permissions.md) kohdeyleisön merkityksellisissä tiedoissa, jotta tiedot näkyvät heille.</span><span class="sxs-lookup"><span data-stu-id="a21f5-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="a21f5-111">[Haku- ja suodatustoiminnot](search-filter-index.md) kohdeyleisön merkityksellisissä tiedoissa vaaditaan, jotta tietojen haku toimii.</span><span class="sxs-lookup"><span data-stu-id="a21f5-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="a21f5-112">Kukin apuohjelman ohjausobjekti perustuu tiettyihin tietoihin kohdeyleisön merkityksellisissä tiedoissa:</span><span class="sxs-lookup"><span data-stu-id="a21f5-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="a21f5-113">Mittarin ohjausobjekti: edellyttää [määritettyjä mittareita](measures.md).</span><span class="sxs-lookup"><span data-stu-id="a21f5-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="a21f5-114">Älykkyyden hallinta: Edellyttää [ennusteiden](predictions.md) tai [mukautettujen mallien](custom-models.md) avulla luotuja tietoja.</span><span class="sxs-lookup"><span data-stu-id="a21f5-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="a21f5-115">Demografiatietojen ohjausobjekti: demografiset kentät (kuten ikä tai sukupuoli), ovat käytettävissä yhdistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="a21f5-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="a21f5-116">Rikastus-ohjausobjekti: edellyttää aktiivisia [rikastuksia](enrichment-hub.md), joita käytetään asiakasprofiileihin.</span><span class="sxs-lookup"><span data-stu-id="a21f5-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="a21f5-117">Aikajanan ohjausobjekti: edellyttää [määritettyjä aktiviteetteja](activities.md).</span><span class="sxs-lookup"><span data-stu-id="a21f5-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="a21f5-118">Asiakaskortin apuohjelman asentaminen</span><span class="sxs-lookup"><span data-stu-id="a21f5-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="a21f5-119">Asiakaskortin apuohjelma on Dynamics 365:n Customer Engagement -sovellusten ratkaisu.</span><span class="sxs-lookup"><span data-stu-id="a21f5-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="a21f5-120">Jos haluat asentaa ratkaisun, siirry AppSourceen ja hae sanalla **Dynamics Customer Card**.</span><span class="sxs-lookup"><span data-stu-id="a21f5-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="a21f5-121">Valitse [Customer Card Add-in AppSourcessa](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) ja sitten **Hanki nyt**.</span><span class="sxs-lookup"><span data-stu-id="a21f5-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="a21f5-122">Ratkaisun asentaminen voi edellyttää kirjautumista Dynamics 365 -sovelluksen järjestelmänvalvojan tunnistetiedoilla.</span><span class="sxs-lookup"><span data-stu-id="a21f5-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="a21f5-123">Ratkaisun asentaminen ympäristöön voi kestää jonkin aikaa.</span><span class="sxs-lookup"><span data-stu-id="a21f5-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="a21f5-124">Asiakaskortin apuohjelman määrittäminen</span><span class="sxs-lookup"><span data-stu-id="a21f5-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="a21f5-125">Siirry järjestelmänvalvojana Dynamics 365:n **Asetukset**-osaan ja valitse **Ratkaisut**.</span><span class="sxs-lookup"><span data-stu-id="a21f5-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="a21f5-126">Valitse **Näyttönimi**-linkki **Dynamics 365 Customer Insights – Asiakaskortti-apuohjelma (esiversio)** -ratkaisulle.</span><span class="sxs-lookup"><span data-stu-id="a21f5-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a21f5-127">![Näyttönimen valinta](media/select-display-name.png "Näyttönimen valinta")</span><span class="sxs-lookup"><span data-stu-id="a21f5-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="a21f5-128">Valitse **Kirjaudu sisään** ja anna sen järjestelmänvalvojatilin tunniste tiedot, jota käytät Customer Insightsin määrittämiseen.</span><span class="sxs-lookup"><span data-stu-id="a21f5-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a21f5-129">Tarkista, että selaimen ponnahdusikkunoiden estotoiminto ei estä todennusikkunan avautumista, kun valitset **Kirjaudu sisään**-painikkeen.</span><span class="sxs-lookup"><span data-stu-id="a21f5-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="a21f5-130">Valitse se Customer Insights -ympäristö, josta haluat noutaa tietoja.</span><span class="sxs-lookup"><span data-stu-id="a21f5-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="a21f5-131">Määritä Dynamics 365 -sovelluksen tietueiden kenttien yhdistämismääritys.</span><span class="sxs-lookup"><span data-stu-id="a21f5-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="a21f5-132">Customer Insights -tiedoistasi riippuen voit valita seuraavista yhdistämisvaihtoehdoista:</span><span class="sxs-lookup"><span data-stu-id="a21f5-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="a21f5-133">Yhteyshenkilö yhdistetään valitsemalla asiakasentiteetissä kenttä, joka vastaa yhteyshenkilöentiteetin tunnusta.</span><span class="sxs-lookup"><span data-stu-id="a21f5-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="a21f5-134">Tili yhdistetään valitsemalla asiakasentiteetissä kenttä, joka vastaa tilientiteetin tunnusta.</span><span class="sxs-lookup"><span data-stu-id="a21f5-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a21f5-135">![Yhteyshenkilön tunnus -kenttä](media/contact-id-field.png "Yhteyshenkilön tunnus -kenttä")</span><span class="sxs-lookup"><span data-stu-id="a21f5-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="a21f5-136">Tallenna asetukset valitsemalla **Tallenna määritys**.</span><span class="sxs-lookup"><span data-stu-id="a21f5-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="a21f5-137">Seuraavaksi sinun täytyy määrittää käyttöoikeusroolit Dynamics 365:ssä, jotta käyttäjät voivat mukauttaa ja nähdä asiakaskortin.</span><span class="sxs-lookup"><span data-stu-id="a21f5-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="a21f5-138">Valitse Dynamics 365:ssä **Asetukset** > **Suojaus** > **Käyttäjät**.</span><span class="sxs-lookup"><span data-stu-id="a21f5-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="a21f5-139">Valitse käyttäjät, joiden käyttäjärooleja haluat muokata, ja valitse **Roolien hallinta**.</span><span class="sxs-lookup"><span data-stu-id="a21f5-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="a21f5-140">Delegoi **Customer Insights -kortin mukauttaja** -rooli käyttäjille, jotka mukauttavat koko organisaation kortissa näkemää sisältöä.</span><span class="sxs-lookup"><span data-stu-id="a21f5-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="a21f5-141">Asiakaskortin ohjausobjektien lisääminen lomakkeisiin</span><span class="sxs-lookup"><span data-stu-id="a21f5-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="a21f5-142">Voit lisätä Asiakaskortti-ohjausobjekteja Yhteyshenkilö-lomakkeeseen siirtymällä Dynamics 365 -järjestelmässä kohtaan **Asetukset** > **Mukautukset**.</span><span class="sxs-lookup"><span data-stu-id="a21f5-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="a21f5-143">Valitse **Mukauta järjestelmää**.</span><span class="sxs-lookup"><span data-stu-id="a21f5-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="a21f5-144">Siirry **Yhteyshenkilö**-entiteettiin, laajenna se ja valitse sitten **Lomakkeet**.</span><span class="sxs-lookup"><span data-stu-id="a21f5-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="a21f5-145">Valitse yhteyshenkilölomake, jonka haluat lisätä asiakaskortin ohjausobjekteihin.</span><span class="sxs-lookup"><span data-stu-id="a21f5-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a21f5-146">![Yhteyshenkilölomakkeen valitseminen](media/contact-active-forms.png "Yhteyshenkilölomakkeen valitseminen")</span><span class="sxs-lookup"><span data-stu-id="a21f5-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="a21f5-147">Voit lisätä ohjausobjektin vetämällä kentän lomake-editorissa **kenttien hallinnasta** kohtaan, johon haluat sijoittaa ohjausobjektin.</span><span class="sxs-lookup"><span data-stu-id="a21f5-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="a21f5-148">Valitse juuri lisätty lomakkeen kenttä ja valitse sitten **Muuta ominaisuuksia**.</span><span class="sxs-lookup"><span data-stu-id="a21f5-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="a21f5-149">Valitse **Ohjausobjektit**-välilehdessä **Lisää ohjausobjekti**.</span><span class="sxs-lookup"><span data-stu-id="a21f5-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="a21f5-150">Valitse jokin käytettävissä olevista mukautetuista ohjausobjekteistä ja valitse sitten **Lisää**.</span><span class="sxs-lookup"><span data-stu-id="a21f5-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="a21f5-151">Poista **Kentän ominaisuudet** -valintaikkunassa **Näytä otsikko lomakkeessa** -valintaruudun valinta.</span><span class="sxs-lookup"><span data-stu-id="a21f5-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="a21f5-152">Valitse ohjausobjektille asetus **WWW**.</span><span class="sxs-lookup"><span data-stu-id="a21f5-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="a21f5-153">Jos kyseessä on rikastusohjausobjekti, valitse näytettävä rikastustyyppi määrittämällä **enrichmentType**-kenttä.</span><span class="sxs-lookup"><span data-stu-id="a21f5-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="a21f5-154">Lisää jokaiselle rikastustyypille erillinen rikastusohjausobjekti.</span><span class="sxs-lookup"><span data-stu-id="a21f5-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="a21f5-155">Julkaise päivitetty yhteyshenkilölomake valitsemalla **Tallenna** ja **Julkaise**.</span><span class="sxs-lookup"><span data-stu-id="a21f5-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="a21f5-156">Siirry julkaistuun yhteyshenkilölomakkeeseen.</span><span class="sxs-lookup"><span data-stu-id="a21f5-156">Go to the published contact form.</span></span> <span data-ttu-id="a21f5-157">Näet juuri lisätyn ohjausobjektin.</span><span class="sxs-lookup"><span data-stu-id="a21f5-157">You'll see the newly added control.</span></span> <span data-ttu-id="a21f5-158">Kirjautuminen voi olla välttämätöntä, kun sitä käytetään ensimmäisen kerran.</span><span class="sxs-lookup"><span data-stu-id="a21f5-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="a21f5-159">Voit mukauttaa mukautetussa ohjausobjektissa näkyviä tietoja valitsemalla muokkauspainikkeen oikeassa yläkulmassa.</span><span class="sxs-lookup"><span data-stu-id="a21f5-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="a21f5-160">Asiakaskortin apuohjelman päivittäminen</span><span class="sxs-lookup"><span data-stu-id="a21f5-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="a21f5-161">Asiakaskortin apuohjelmaa ei päivitetä automaattisesti.</span><span class="sxs-lookup"><span data-stu-id="a21f5-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="a21f5-162">Voit päivittää uusimman version toimimalla seuraavasti Dynamics 365 -sovelluksessa, johon apuohjelma on asennettu.</span><span class="sxs-lookup"><span data-stu-id="a21f5-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="a21f5-163">Siirry Dynamics 365 -sovelluksissa kohtaan **Asetukset** > **Mukauttaminen** ja valitse **Ratkaisut**.</span><span class="sxs-lookup"><span data-stu-id="a21f5-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="a21f5-164">Etsi apuohjelmien taulukosta **CustomerInsightsCustomerCard** ja valitse rivi.</span><span class="sxs-lookup"><span data-stu-id="a21f5-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="a21f5-165">Valitse **Ota ratkaisun päivitys käyttöön** toimintorivillä.</span><span class="sxs-lookup"><span data-stu-id="a21f5-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Ratkaisun päivittäminen Dynamics 365 -sovellusten Mukauttaminen-alueella":::

1. <span data-ttu-id="a21f5-167">Kun olet käynnistänut päivityksen, latausilmaisin näkyy päivityksen valmistumiseen asti.</span><span class="sxs-lookup"><span data-stu-id="a21f5-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="a21f5-168">Jos uudempia versioja ei ole, päivitys näyttää virhesanoman.</span><span class="sxs-lookup"><span data-stu-id="a21f5-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
