---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Uživatelem definovaný typ GeneratorSystem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 20092a8deca50c90f46f4d79c6b40b805f135754
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225223"
---
# <a name="generatorsystem-user-defined-type"></a>Uživatelem definovaný typ GeneratorSystem

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje kolekci `GeneratorIndex` ES.

Procházíme přes tuto kolekci s použitím jednoho indexu celé číslo a velikost kolekce se předpokládá jako známá.

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>Poznámky

Instance `GeneratorSystem` lze snadno definovat pomocí <xref:microsoft.quantum.arrays.lookupfunction> funkce.

## <a name="see-also"></a>Viz také

- [Microsoft. Forms. Arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)