---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611099"
---
- **Koulutusmallin suorituskyky**: Luokka A, B tai C osoittaa ennusteen suorituskyvyn. Sen avulla voit päättää, käytetäänkö tulosentiteettiin tallennettuja tuloksia.

  Luokat määritetään seuraavien sääntöjen perusteella:
  - **A**, kun mallin tarkkuudeksi on ennustettu vähintään 50 % ennusteesta yhteensä ja kun vaihtuvuusasiakkaiden tarkka ennusteprosentti on ainakin 10 % suurempi kuin lähtöarvo.
  - **B**, kun mallin tarkkuudeksi on ennustettu vähintään 50 % ennusteesta yhteensä ja kun vaihtuvuusasiakkaiden tarkka ennusteprosentti on enintään 10 % suurempi kuin lähtöarvo.
  - **C**, kun mallin tarkkuudeksi on ennustettu alle 50 % ennusteista yhteensä tai kun vaihtuvuusasiakkaiden tarkka ennusteprosentti on pienempi kuin perustaso.
  - **Perustaso** käyttää mallin ennusteen aikaikkunan (kuten yhden vuoden) ja luo eri aikajakoja jakamalla sen kahdella, kunnes tuloksena on yksi kuukausi tai sitä lyhyempi jakso. Se luo liiketoimintasäännön näiden osien avulla asiakkaille, jotka eivät ole tehneet ostona kyseisellä aikavälillä. Näiden asiakkaiden katsotaan vaihtuneen. Perustasomalliksi valitaan aikaperusteinen liiketoimintasääntö, joka ennustaa parhaiten todennäköisen vaihtuvuuden.

- **Vaihtuvuuden todennäköisyys (asiakkaiden määrä)**: Asiakasryhmät ennustetun vaihtuvuusriskin perusteella. Valinnaisesti voidaan [luoda asiakassegmentti](../prediction-based-segment.md) asiakkaista, joilla on korkea vaihtuvuusriski. Tällaiset segmentit auttavat ymmärtämään, missä segmentin jäsenyyden rajan on oltava.

- **Tärkeimmät tekijät**: Ennusteen luomisessa otetaan huomioon useita tekijöitä. Kunkin tekijän tärkeys lasketaan mallin luomille kooste-ennusteille. Näiden tekijöiden avulla voidaan tarkistaa ennusteen tulokset. Näitä tietoja voi käyttää myös myöhemmin sellaisten [segmenttien luontiin](../prediction-based-segment.md), joilla voi vaikuttaa asiakkaiden vaihtuvuusriskiin.