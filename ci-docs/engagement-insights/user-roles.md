---
title: Roolit ja oikeudet
description: Yleiskatsaus työtilan jäsenten käytettävissä olevista rooleista ja oikeuksista.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e28caf1c14c23acd506da5f7b441f1e3b72e8b
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645533"
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
