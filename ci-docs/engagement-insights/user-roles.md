---
title: Roolit ja oikeudet
description: Yleiskatsaus työtilan jäsenten käytettävissä olevista rooleista ja oikeuksista.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ccc6a1b87b4cc28701e276b6e35432356e7647c4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227535"
---
# <a name="roles-and-permissions"></a>Roolit ja oikeudet

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Työtila on paikka tapahtumien ja raporttien tallentamista ja hallintaa varten. Lisätietoja löytyy kohdasta [Työtilan luominen ja jäsenten lisääminen](create-workspace.md). 

Työtilassa voi olla seuraavat roolit ja oikeudet:

- *Jäsen*-rooleilla voi käytää työtilaa. Voit delegoida jäseniä työtilaasi ja määrittää heidän roolinsa ja oikeutensa. 
- *Järjestelmänvalvoja*-roolit hallitsevat työtiloja ja ympäristöjä ja määrittävät sitoutumistietoja muille käyttäjille. 
- *Osallistuja*-roolit on suunnattu analyytikoille, joiden ei tarvitse määrittää sitoutumistietoja, mutta jotka haluavat luoda omia raporttejaan, suppiloitaan ja segmenttejään.

## <a name="permissions"></a>Käyttöoikeudet
  
Seuraavassa taulukossa on esitetty kunkin roolin käyttöoikeudet. 

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
