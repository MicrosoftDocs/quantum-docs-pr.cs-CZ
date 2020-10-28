---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 5e93c66d891d9b6aec548c0cf266df35e6090c92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706728"
---
# <a name="discreteuniformdistribution-function"></a>DiscreteUniformDistribution – funkce

Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)

Balíček [](https://nuget.org/packages/)


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