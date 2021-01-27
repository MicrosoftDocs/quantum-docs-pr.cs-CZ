---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Uživatelem definovaný typ GeneratorSystem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 3748d3fb79597fb526c86a91bc28290155189014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858412"
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