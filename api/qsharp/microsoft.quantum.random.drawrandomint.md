---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operace DrawRandomInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851145"
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

## <a name="example"></a>Příklad

Následující fragment Q # náhodně zavede na šestou kostku:

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a>Poznámky

Dojde k chybě `max <= min` , pokud.

## <a name="see-also"></a>Viz také

- [Microsoft. DiscreteUniformDistribution.](xref:Microsoft.Quantum.DiscreteUniformDistribution)