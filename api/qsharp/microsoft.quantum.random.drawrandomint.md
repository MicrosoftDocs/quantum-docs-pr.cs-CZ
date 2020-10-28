---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operace DrawRandomInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708932"
---
# <a name="drawrandomint-operation"></a>Operace DrawRandomInt

Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)

Balíček [](https://nuget.org/packages/)


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