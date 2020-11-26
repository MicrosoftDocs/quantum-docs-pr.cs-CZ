---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Operace DrawRandomDouble
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192940"
---
# <a name="drawrandomdouble-operation"></a>Operace DrawRandomDouble

Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vykreslí náhodné reálné číslo v daném intervalu.

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a>Vstup

### <a name="min--double"></a>min: [Double](xref:microsoft.quantum.lang-ref.double)

Nejmenší reálné číslo, které se má vykreslit.


### <a name="max--double"></a>Max: [Double](xref:microsoft.quantum.lang-ref.double)

Největší reálné číslo, které se má vykreslit.



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)

Náhodné reálné číslo v intervalu zahrnujícím v rámci `min` `max` s jednotnou pravděpodobností.

## <a name="remarks"></a>Poznámky

Dojde k chybě `max <= min` , pokud.

## <a name="see-also"></a>Viz také

- [Microsoft. ContinuousUniformDistribution.](xref:Microsoft.Quantum.ContinuousUniformDistribution)