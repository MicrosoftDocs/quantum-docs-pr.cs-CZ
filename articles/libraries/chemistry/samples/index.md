---
title: Příklady pro kvantovou chemii | Microsoft Docs
description: Příklady pro kvantovou chemii – dokumentace
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
ms.openlocfilehash: 586ea98321ff71947df8d81a2141a8b050dbd9ed
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2019
ms.locfileid: "72960407"
---
# <a name="quantum-chemistry-examples"></a>Příklady pro kvantovou chemii

Na konceptech kvantové chemie jsme ručně sestavili ukázkové fermionové hamiltoniány. Nyní kombinujeme algoritmy chemické simulace, které jsou uvedené v popisu [simulace hamiltoniánské dynamiky](xref:microsoft.quantum.libraries.standard.algorithms), s [odhadem kvantové fáze](xref:microsoft.quantum.libraries.characterization) v knihovně kánonu. Tato kombinace nám umožňuje získat odhady energetických úrovní v reprezentované molekule, což je jedna z klíčových aplikací kvantové chemie na kvantových počítačích. 

Namísto určování jednotlivých termínů hamiltoniánů také pracujeme s několika příklady, které nám umožňují provádět experimenty kvantové chemie ve velkém. Začneme s příklady, které načítají chemický hamiltonián kódovaný ve [schématu Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).

I pro molekuly, které jsou moc velké pro simulaci na [simulátoru celkového stavu](xref:microsoft.quantum.machines.full-state-simulator), se pořád dá dělat zajímavá věda. Například stále jde vyhodnotit náklady na prostředky k provádění velkých chemických simulací zaměřením na [simulátor trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro).

Podívejme se nyní na zajímavé aplikace chemické simulační knihovny prostřednictvím několika z poskytnutých ukázek.