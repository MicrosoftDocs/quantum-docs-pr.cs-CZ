---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operace DrawRandomInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192906"
---
# <a name="drawrandomint-operation"></a>Operace DrawRandomInt

Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vykreslí náhodné celé číslo v daném rozsahu.

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a>Vstup

### <a name="min--int"></a>minimum: [int](xref:microsoft.quantum.lang-ref.int)

Nejmenší celé číslo, které se má vykreslit.


### <a name="max--int"></a>maximum: [int](xref:microsoft.quantum.lang-ref.int)

Největší celé číslo, které se má vykreslit.



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Celé číslo v rozsahu v rozsahu od `min` do `max` s jednotnou pravděpodobností.

## <a name="remarks"></a>Poznámky

Dojde k chybě `max <= min` , pokud.

## <a name="see-also"></a>Viz také

- [Microsoft. DiscreteUniformDistribution.](xref:Microsoft.Quantum.DiscreteUniformDistribution)