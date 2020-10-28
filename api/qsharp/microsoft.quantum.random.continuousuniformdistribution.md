---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697140"
---
# <a name="continuousuniformdistribution-function"></a>ContinuousUniformDistribution – funkce

Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)

Balíček [](https://nuget.org/packages/)


Vrátí jednotnou distribuci v rámci daného intervalu zahrnujícího interval.

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Vstup

### <a name="min--double"></a>min: [Double](xref:microsoft.quantum.lang-ref.double)

Nejmenší reálné číslo, které se má vykreslit.


### <a name="max--double"></a>Max: [Double](xref:microsoft.quantum.lang-ref.double)

Největší reálné číslo, které se má vykreslit.



## <a name="output--continuousdistribution"></a>Výstup: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Distribuce, jejíž náhodná variates jsou skutečná čísla v intervalu zahrnujícím, od `min` do `max` s jednotnou pravděpodobností.

## <a name="remarks"></a>Poznámky

Dojde k chybě `max <= min` , pokud.

## <a name="see-also"></a>Viz také

- [Microsoft. DrawRandomDouble.](xref:Microsoft.Quantum.DrawRandomDouble)