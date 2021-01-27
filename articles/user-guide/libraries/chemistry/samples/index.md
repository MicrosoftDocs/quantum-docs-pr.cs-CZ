---
title: Ukázkové aplikace pro kvantovou chemii
description: Projděte si ukázkové aplikace knihovny Microsoft Quantum pro chemii.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: conceptual
uid: microsoft.quantum.chemistry.examples
no-loc:
- Q#
- $$v
ms.openlocfilehash: b2a8740f9c94ca733e24012aaf5c80b15b731c2e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858924"
---
# <a name="quantum-chemistry-examples"></a>Příklady pro kvantovou chemii

Na konceptech kvantové chemie jsme ručně sestavili ukázkové fermionové hamiltoniány. Nyní kombinujeme algoritmy chemické simulace, které jsou uvedené v popisu [simulace hamiltoniánské dynamiky](xref:microsoft.quantum.libraries.standard.algorithms), s [odhadem kvantové fáze](xref:microsoft.quantum.libraries.characterization) v knihovně kánonu. Tato kombinace nám umožňuje získat odhady energetických úrovní v reprezentované molekule, což je jedna z klíčových aplikací kvantové chemie na kvantových počítačích. 

Namísto určování jednotlivých termínů hamiltoniánů také pracujeme s několika příklady, které nám umožňují provádět experimenty kvantové chemie ve velkém. Začneme s příklady, které načítají chemický hamiltonián kódovaný ve [schématu Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).

I pro molekuly, které jsou moc velké pro simulaci na [simulátoru celkového stavu](xref:microsoft.quantum.machines.full-state-simulator), se pořád dá dělat zajímavá věda. Například stále jde vyhodnotit náklady na prostředky k provádění velkých chemických simulací zaměřením na [simulátor trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro).

Podívejme se nyní na zajímavé aplikace chemické simulační knihovny prostřednictvím několika z poskytnutých ukázek.
