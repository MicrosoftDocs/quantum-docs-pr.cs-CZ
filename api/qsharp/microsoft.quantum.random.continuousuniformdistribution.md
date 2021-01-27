---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842320"
---
# <a name="continuousuniformdistribution-function"></a>ContinuousUniformDistribution – funkce

Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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

## <a name="example"></a>Příklad

Následující fragment Q # náhodně vykreslí úhel mezi $0 $ a $2 \pi $:

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a>Poznámky

Dojde k chybě `max <= min` , pokud.

## <a name="see-also"></a>Viz také

- [Microsoft. DrawRandomDouble.](xref:Microsoft.Quantum.DrawRandomDouble)