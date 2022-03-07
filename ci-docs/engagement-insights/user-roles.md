---
title: Roolit ja oikeudet
description: Yleiskatsaus työtilan jäsenten käytettävissä olevista rooleista ja oikeuksista.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036689"
---
# <a name="roles-and-permissions"></a>Roolit ja oikeudet

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Työtila on paikka tapahtumien ja raporttien tallentamista ja hallintaa varten. Jäsen on käyttäjä, joka voi käyttää työtilaa. Voit delegoida jäseniä työtilaasi ja määrittää heidän roolinsa ja oikeutensa. Järjestelmänvalvojaroolit hallitsevat työtiloja ja ympäristöjä ja määrittävät sitoutumistietoja muille käyttäjille. Nämä osallistujaroolit on suunnattu analyytikoille, joiden ei tarvitse määrittää sitoutumisen tietoja, vaan haluavat luoda omia raportteja, suppiloita tai segmenttejä.

## <a name="permissions"></a>Käyttöoikeudet
  
Seuraavassa kaaviossa esitetään kunkin roolin oikeudet. 

| Käyttöoikeus | Ympäristön järjestelmänvalvoja | Työtilan järjestelmänvalvoja | Ympäristön osallistuja | Työtilan osallistuja | 
|--|--|--|--|--|
| Ympäristön luominen (tekijästä tulee automaattisesti ympäristön järjestelmänvalvoja) | X* | X* | X* | X* |  
| Ympäristön määrittäminen (ympäristön jäsenet, ympäristön poistaminen) | X |  |  |  |  
| Työtilojen luominen | X |  |  |  |  
| Työtilojen määrittäminen (työtilan jäsenet, työtilan poistaminen) | X | X |  |  |  
| Tapahtumien ja tarkennettujen tapahtumien määrittäminen | X | X | |  |  
| Työtilatapahtumien ja tarkennettujen tapahtumien tarkasteleminen | X | X | |  |  
| Työtilaresurssien (raporttien, segmenttien ja mittausarvojen) tarkasteleminen| X | X | X | X |  
| Luo mukautettuja raportteja ja suppiloita | X | X | X | X |  
| Perusmittareiden ja dimensioiden luominen| X | X |  |  |  
| Segmenttien luominen| X | X | X | X |  

*Kokeiluympäristöjä voi luoda vain esiversiossa. 

## <a name="add-members"></a>Lisää jäseniä

Voit lisätä ja poistaa jäseniä työtiloista ja ympäristöistä. Lisätietoja: [Ympäristöt ja työtilat](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
