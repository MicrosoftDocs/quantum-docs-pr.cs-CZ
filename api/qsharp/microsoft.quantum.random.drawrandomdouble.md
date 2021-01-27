---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Operace DrawRandomDouble
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847611"
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

## <a name="example"></a>Příklad

Následující fragment Q # náhodně vykreslí úhel mezi $0 $ a $2 \pi $:

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a>Poznámky

Dojde k chybě `max <= min` , pokud.

## <a name="see-also"></a>Viz také

- [Microsoft. ContinuousUniformDistribution.](xref:Microsoft.Quantum.ContinuousUniformDistribution)