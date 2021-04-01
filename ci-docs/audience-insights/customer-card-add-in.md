---
title: Asiakaskortin apuohjelman asentaminen ja määrittäminen
description: Dynamics 365 Customer Insightsin asiakaskortin apuohjelman asentaminen ja määrittäminen.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597323"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="08453-103">Asiakaskortin apuohjelma (esiversio)</span><span class="sxs-lookup"><span data-stu-id="08453-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="08453-104">Saat kokonaisvaltainen näkymän asiakkaista suoraan Dynamics 365 -sovelluksissa.</span><span class="sxs-lookup"><span data-stu-id="08453-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="08453-105">Tarkastele demografiatietoja, näkemyksiä ja aktiviteettiaikajanoja asiakaskortin apuohjelman avulla.</span><span class="sxs-lookup"><span data-stu-id="08453-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="08453-106">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="08453-106">Prerequisites</span></span>

- <span data-ttu-id="08453-107">Dynamics 365 -sovellus (kuten myyntikeskus tai asiakaspalvelukeskus), versio 9.0 tai uudempi, jossa Unified Interface käytössä.</span><span class="sxs-lookup"><span data-stu-id="08453-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="08453-108">Asiakasprofiilit [käsitellään Dynamics 365 -sovelluksessa Common Data Servicen avulla](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="08453-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="08453-109">Asiakaskortin lisäosan käyttäjät on [lisättävä käyttäjinä](permissions.md) käyttäjäryhmän merkityksellisissä tiedoissa.</span><span class="sxs-lookup"><span data-stu-id="08453-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="08453-110">[Määritetyt haku- ja suodatusominaisuudet ](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="08453-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="08453-111">Demografiatietojen ohjausobjekti: demografiset kentät (kuten ikä tai sukupuoli), ovat käytettävissä yhdistetyssä asiakasprofiilissa.</span><span class="sxs-lookup"><span data-stu-id="08453-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="08453-112">Rikastus-ohjausobjekti: edellyttää aktiivisia [rikastuksia](enrichment-hub.md), joita käytetään asiakasprofiileihin.</span><span class="sxs-lookup"><span data-stu-id="08453-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="08453-113">Analytiikan ohjausobjekti: edellyttää tietoja, jotka on luotu käyttämällä Azuren automaattianalyysipalveluita ([ennusteet](predictions.md) tai [mukautetut mallit](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="08453-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="08453-114">Mittarin ohjausobjekti: edellyttää [määritettyjä mittareita](measures.md).</span><span class="sxs-lookup"><span data-stu-id="08453-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="08453-115">Aikajanan ohjausobjekti: edellyttää [määritettyjä aktiviteetteja](activities.md).</span><span class="sxs-lookup"><span data-stu-id="08453-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="08453-116">Asiakaskortin apuohjelman asentaminen</span><span class="sxs-lookup"><span data-stu-id="08453-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="08453-117">Asiakaskortin apuohjelma on Dynamics 365:n Customer Engagement -sovellusten ratkaisu.</span><span class="sxs-lookup"><span data-stu-id="08453-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="08453-118">Jos haluat asentaa ratkaisun, siirry AppSourceen ja hae sanalla **Dynamics Customer Card**.</span><span class="sxs-lookup"><span data-stu-id="08453-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="08453-119">Valitse [Customer Card Add-in AppSourcessa](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) ja sitten **Hanki nyt**.</span><span class="sxs-lookup"><span data-stu-id="08453-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="08453-120">Ratkaisun asentaminen voi edellyttää kirjautumista Dynamics 365 -sovelluksen järjestelmänvalvojan tunnistetiedoilla.</span><span class="sxs-lookup"><span data-stu-id="08453-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="08453-121">Ratkaisun asentaminen ympäristöön voi kestää jonkin aikaa.</span><span class="sxs-lookup"><span data-stu-id="08453-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="08453-122">Asiakaskortin apuohjelman määrittäminen</span><span class="sxs-lookup"><span data-stu-id="08453-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="08453-123">Siirry järjestelmänvalvojana Dynamics 365:n **Asetukset**-osaan ja valitse **Ratkaisut**.</span><span class="sxs-lookup"><span data-stu-id="08453-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="08453-124">Valitse **Näyttönimi**-linkki **Dynamics 365 Customer Insights – Asiakaskortti-apuohjelma (esiversio)** -ratkaisulle.</span><span class="sxs-lookup"><span data-stu-id="08453-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08453-125">![Näyttönimen valinta](media/select-display-name.png "Näyttönimen valinta")</span><span class="sxs-lookup"><span data-stu-id="08453-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="08453-126">Valitse **Kirjaudu sisään** ja anna sen järjestelmänvalvojatilin tunniste tiedot, jota käytät Customer Insightsin määrittämiseen.</span><span class="sxs-lookup"><span data-stu-id="08453-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="08453-127">Tarkista, että selaimen ponnahdusikkunoiden estotoiminto ei estä todennusikkunan avautumista, kun valitset **Kirjaudu sisään**-painikkeen.</span><span class="sxs-lookup"><span data-stu-id="08453-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="08453-128">Valitse ympäristö, josta tietoja noudetaan.</span><span class="sxs-lookup"><span data-stu-id="08453-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="08453-129">Määritä, mikä kenttä yhdistetään tietueisiin Dynamics 365 -sovelluksessa.</span><span class="sxs-lookup"><span data-stu-id="08453-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="08453-130">Yhteyshenkilö yhdistetään valitsemalla asiakasentiteetissä kenttä, joka vastaa yhteyshenkilöentiteetin tunnusta.</span><span class="sxs-lookup"><span data-stu-id="08453-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="08453-131">Tili yhdistetään valitsemalla asiakasentiteetissä kenttä, joka vastaa tilientiteetin tunnusta.</span><span class="sxs-lookup"><span data-stu-id="08453-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08453-132">![Yhteyshenkilön tunnus -kenttä](media/contact-id-field.png "Yhteyshenkilön tunnus -kenttä")</span><span class="sxs-lookup"><span data-stu-id="08453-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="08453-133">Tallenna asetukset valitsemalla **Tallenna määritys**.</span><span class="sxs-lookup"><span data-stu-id="08453-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="08453-134">Seuraavaksi sinun täytyy määrittää käyttöoikeusroolit Dynamics 365:ssä, jotta käyttäjät voivat mukauttaa ja nähdä asiakaskortin.</span><span class="sxs-lookup"><span data-stu-id="08453-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="08453-135">Valitse Dynamics 365:ssä **Asetukset** > **Suojaus** > **Käyttäjät**.</span><span class="sxs-lookup"><span data-stu-id="08453-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="08453-136">Valitse käyttäjät, joiden käyttäjärooleja haluat muokata, ja valitse **Roolien hallinta**.</span><span class="sxs-lookup"><span data-stu-id="08453-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="08453-137">Delegoi **Customer Insights -kortin mukauttaja** -rooli käyttäjille, jotka mukauttavat koko organisaation kortissa näkemää sisältöä.</span><span class="sxs-lookup"><span data-stu-id="08453-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="08453-138">Asiakaskortin ohjausobjektien lisääminen lomakkeisiin</span><span class="sxs-lookup"><span data-stu-id="08453-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="08453-139">Voit lisätä Asiakaskortti-ohjausobjekteja Yhteyshenkilö-lomakkeeseen siirtymällä Dynamics 365 -järjestelmässä kohtaan **Asetukset** > **Mukautukset**.</span><span class="sxs-lookup"><span data-stu-id="08453-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="08453-140">Valitse **Mukauta järjestelmää**.</span><span class="sxs-lookup"><span data-stu-id="08453-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="08453-141">Siirry **Yhteyshenkilö**-entiteettiin, laajenna se ja valitse sitten **Lomakkeet**.</span><span class="sxs-lookup"><span data-stu-id="08453-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="08453-142">Valitse yhteyshenkilölomake, jonka haluat lisätä asiakaskortin ohjausobjekteihin.</span><span class="sxs-lookup"><span data-stu-id="08453-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="08453-143">![Yhteyshenkilölomakkeen valitseminen](media/contact-active-forms.png "Yhteyshenkilölomakkeen valitseminen")</span><span class="sxs-lookup"><span data-stu-id="08453-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="08453-144">Voit lisätä ohjausobjektin vetämällä kentän lomake-editorissa **kenttien hallinnasta** kohtaan, johon haluat sijoittaa ohjausobjektin.</span><span class="sxs-lookup"><span data-stu-id="08453-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="08453-145">Valitse juuri lisätty lomakkeen kenttä ja valitse sitten **Muuta ominaisuuksia**.</span><span class="sxs-lookup"><span data-stu-id="08453-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="08453-146">Valitse **Ohjausobjektit**-välilehdessä **Lisää ohjausobjekti**.</span><span class="sxs-lookup"><span data-stu-id="08453-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="08453-147">Valitse jokin käytettävissä olevista mukautetuista ohjausobjekteistä ja valitse sitten **Lisää**.</span><span class="sxs-lookup"><span data-stu-id="08453-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="08453-148">Poista **Kentän ominaisuudet** -valintaikkunassa **Näytä otsikko lomakkeessa** -valintaruudun valinta.</span><span class="sxs-lookup"><span data-stu-id="08453-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="08453-149">Valitse ohjausobjektille asetus **WWW**.</span><span class="sxs-lookup"><span data-stu-id="08453-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="08453-150">Jos kyseessä on rikastusohjausobjekti, valitse näytettävä rikastustyyppi määrittämällä **enrichmentType**-kenttä.</span><span class="sxs-lookup"><span data-stu-id="08453-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="08453-151">Lisää jokaiselle rikastustyypille erillinen rikastusohjausobjekti.</span><span class="sxs-lookup"><span data-stu-id="08453-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="08453-152">Julkaise päivitetty yhteyshenkilölomake valitsemalla **Tallenna** ja **Julkaise**.</span><span class="sxs-lookup"><span data-stu-id="08453-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="08453-153">Siirry julkaistuun yhteyshenkilölomakkeeseen.</span><span class="sxs-lookup"><span data-stu-id="08453-153">Go to the published contact form.</span></span> <span data-ttu-id="08453-154">Näet juuri lisätyn ohjausobjektin.</span><span class="sxs-lookup"><span data-stu-id="08453-154">You'll see the newly added control.</span></span> <span data-ttu-id="08453-155">Kirjautuminen voi olla välttämätöntä, kun sitä käytetään ensimmäisen kerran.</span><span class="sxs-lookup"><span data-stu-id="08453-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="08453-156">Voit mukauttaa mukautetussa ohjausobjektissa näkyviä tietoja valitsemalla muokkauspainikkeen oikeassa yläkulmassa.</span><span class="sxs-lookup"><span data-stu-id="08453-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="08453-157">Asiakaskortin apuohjelman päivittäminen</span><span class="sxs-lookup"><span data-stu-id="08453-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="08453-158">Asiakaskortin apuohjelmaa ei päivitetä automaattisesti.</span><span class="sxs-lookup"><span data-stu-id="08453-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="08453-159">Voit päivittää uusimman version toimimalla seuraavasti Dynamics 365 -sovelluksessa, johon apuohjelma on asennettu.</span><span class="sxs-lookup"><span data-stu-id="08453-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="08453-160">Siirry Dynamics 365 -sovelluksissa kohtaan **Asetukset** > **Mukauttaminen** ja valitse **Ratkaisut**.</span><span class="sxs-lookup"><span data-stu-id="08453-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="08453-161">Etsi apuohjelmien taulukosta **CustomerInsightsCustomerCard** ja valitse rivi.</span><span class="sxs-lookup"><span data-stu-id="08453-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="08453-162">Valitse **Ota ratkaisun päivitys käyttöön** toimintorivillä.</span><span class="sxs-lookup"><span data-stu-id="08453-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Ratkaisun päivittäminen Dynamics 365 -sovellusten Mukauttaminen-alueella":::

1. <span data-ttu-id="08453-164">Kun olet käynnistänut päivityksen, latausilmaisin näkyy päivityksen valmistumiseen asti.</span><span class="sxs-lookup"><span data-stu-id="08453-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="08453-165">Jos uudempia versioja ei ole, päivitys näyttää virhesanoman.</span><span class="sxs-lookup"><span data-stu-id="08453-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]