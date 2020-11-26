---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 08a62805f59df339ef6b91dff802c40c407808f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193008"
---
# <a name="discreteuniformdistribution-function"></a>DiscreteUniformDistribution – funkce

Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vrátí jednotnou distribuci v rámci daného celkového rozsahu.

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>Vstup

### <a name="min--int"></a>minimum: [int](xref:microsoft.quantum.lang-ref.int)

Nejmenší celé číslo, které se má vykreslit.


### <a name="max--int"></a>maximum: [int](xref:microsoft.quantum.lang-ref.int)

Největší celé číslo, které se má vykreslit.



## <a name="output--discretedistribution"></a>Výstup: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Distribuce, jejíž náhodná variates jsou celá čísla v rozsahu, od `min` do `max` s jednotnou pravděpodobností.

## <a name="remarks"></a>Poznámky

Dojde k chybě `max <= min` , pokud.

## <a name="see-also"></a>Viz také

- [Microsoft. DrawRandomDouble.](xref:Microsoft.Quantum.DrawRandomDouble)